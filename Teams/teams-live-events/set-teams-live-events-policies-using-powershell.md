---
title: Usar PowerShell para configurar directivas de eventos en directo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Ejemplos de uso de PowerShell para configurar directivas en Teams con el fin de controlar quién puede contener eventos en directo de su organización y las características disponibles en los eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d5f1cceb42afd2be92aedcd0a40af4e23650512
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140651"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="d890e-103">Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d890e-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="d890e-104">Puede usar los siguientes cmdlets de Windows PowerShell para establecer y asignar la configuración de directiva para eventos en directo de Teams:</span><span class="sxs-lookup"><span data-stu-id="d890e-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="d890e-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d890e-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="d890e-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d890e-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="d890e-107">Nuevo: CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d890e-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="d890e-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d890e-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="d890e-109">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d890e-109">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="d890e-110">Para poder ejecutar estos cmdlets, debe estar conectado a Skype empresarial online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d890e-110">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="d890e-111">Para obtener más información, vea [administrar Skype empresarial online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d890e-111">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="d890e-112">Permitir a los usuarios programar eventos en vivo</span><span class="sxs-lookup"><span data-stu-id="d890e-112">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="d890e-113">Estos ejemplos son para eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="d890e-113">These examples are for events produced in Teams.</span></span> <span data-ttu-id="d890e-114">Para los eventos generados con una aplicación externa o un dispositivo, hay pasos adicionales que debe realizar.</span><span class="sxs-lookup"><span data-stu-id="d890e-114">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="d890e-115">Para obtener más información, vea [permitir a los usuarios programar eventos generados con una aplicación o un dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="d890e-115">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="d890e-116">**Permitir que un usuario programe eventos en vivo**</span><span class="sxs-lookup"><span data-stu-id="d890e-116">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="d890e-117">Si se asigna al usuario la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* se establece en *true*:</span><span class="sxs-lookup"><span data-stu-id="d890e-117">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="d890e-118">A continuación, asigne el usuario a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-118">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="d890e-119">Escenarios de usuario</span><span class="sxs-lookup"><span data-stu-id="d890e-119">User scenarios</span></span>
<span data-ttu-id="d890e-120">**Desea que todos los usuarios de su organización puedan programar eventos en vivo**</span><span class="sxs-lookup"><span data-stu-id="d890e-120">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="d890e-121">Si los usuarios tienen asignada la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* \* se establece en *verdadero*:</span><span class="sxs-lookup"><span data-stu-id="d890e-121">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="d890e-122">Si a los usuarios se les asigna una directiva distinta de la directiva global, ejecute y compruebe que *-AllowBroadcastScheduling* esté establecido en *true*:</span><span class="sxs-lookup"><span data-stu-id="d890e-122">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="d890e-123">**Desea que la programación de eventos en directo se deshabilite en toda la organización**</span><span class="sxs-lookup"><span data-stu-id="d890e-123">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="d890e-124">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-124">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="d890e-125">Asignar todos los usuarios de la organización a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-125">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="d890e-126">**Desea que un gran número de usuarios pueda programar eventos en vivo e impedir que un grupo de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="d890e-126">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="d890e-127">Ejecute y compruebe que *AllowBroadcastScheduling* se establece en *true*:</span><span class="sxs-lookup"><span data-stu-id="d890e-127">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="d890e-128">A continuación, asigne un usuario o usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-128">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="d890e-129">Crear una nueva directiva que no permita programar eventos en vivo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d890e-129">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="d890e-130">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-130">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="d890e-131">A continuación, asigne usuarios a esta Directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-131">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="d890e-132">**Desea deshabilitar la programación de eventos en vivo para un gran número de usuarios y permitir que un conjunto de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="d890e-132">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="d890e-133">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-133">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="d890e-134">A continuación, asigne esos usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-134">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="d890e-135">Crear una directiva para permitir la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-135">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="d890e-136">Habilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-136">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="d890e-137">A continuación, asigne usuarios a esta Directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d890e-137">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="d890e-138">Establecer quién puede unirse a eventos en directo</span><span class="sxs-lookup"><span data-stu-id="d890e-138">Set who can join live events</span></span>
 
<span data-ttu-id="d890e-139">Establezca la directiva global para permitir a los usuarios crear eventos que todos los usuarios, incluidos los anónimos, pueden asistir, ejecutar:</span><span class="sxs-lookup"><span data-stu-id="d890e-139">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="d890e-140">Establecer la opción de grabación de eventos en directo</span><span class="sxs-lookup"><span data-stu-id="d890e-140">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="d890e-141">Esta configuración se aplica solo a los eventos generados en Teams.</span><span class="sxs-lookup"><span data-stu-id="d890e-141">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="d890e-142">Establezca la directiva global para deshabilitar la grabación de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="d890e-142">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="d890e-143">Establecer subtítulos en vivo y subtítulos en eventos en directo</span><span class="sxs-lookup"><span data-stu-id="d890e-143">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="d890e-144">Esta configuración se aplica solo a los eventos generados en Teams.</span><span class="sxs-lookup"><span data-stu-id="d890e-144">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="d890e-145">Establezca la directiva global para activar los subtítulos en vivo y los subtítulos (transcripción) para los asistentes del evento:</span><span class="sxs-lookup"><span data-stu-id="d890e-145">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="d890e-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d890e-146">Related topics</span></span>
- [<span data-ttu-id="d890e-147">Configuración de eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="d890e-147">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="d890e-148">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="d890e-148">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)


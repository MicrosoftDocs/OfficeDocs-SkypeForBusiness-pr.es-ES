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
ms.openlocfilehash: d83dd66914c835f62028fc4941da34646c75411d
ms.sourcegitcommit: c49698e03fa3bdd7c82496189b200ac6bb4e05a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48320805"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="52611-103">Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52611-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="52611-104">Puede usar los siguientes cmdlets de Windows PowerShell para establecer y asignar la configuración de directiva para eventos en directo de Teams:</span><span class="sxs-lookup"><span data-stu-id="52611-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="52611-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52611-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52611-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52611-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52611-107">Nuevo: CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52611-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52611-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52611-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52611-109">Nuevo: CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="52611-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="52611-110">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="52611-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="52611-111">Para poder ejecutar estos cmdlets, debe estar conectado a Skype empresarial online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52611-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="52611-112">Para obtener más información, vea [administrar Skype empresarial online con Microsoft 365 u Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="52611-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="52611-113">Permitir a los usuarios programar eventos en vivo</span><span class="sxs-lookup"><span data-stu-id="52611-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="52611-114">Estos ejemplos son para eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="52611-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="52611-115">Para los eventos generados con una aplicación externa o un dispositivo, hay pasos adicionales que debe realizar.</span><span class="sxs-lookup"><span data-stu-id="52611-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="52611-116">Para obtener más información, vea [permitir a los usuarios programar eventos generados con una aplicación o un dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="52611-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="52611-117">**Permitir que un usuario programe eventos en vivo**</span><span class="sxs-lookup"><span data-stu-id="52611-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="52611-118">Si se asigna al usuario la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* se establece en *true*:</span><span class="sxs-lookup"><span data-stu-id="52611-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="52611-119">A continuación, asigne el usuario a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="52611-120">Escenarios de usuario</span><span class="sxs-lookup"><span data-stu-id="52611-120">User scenarios</span></span>
<span data-ttu-id="52611-121">**Desea que todos los usuarios de su organización puedan programar eventos en vivo**</span><span class="sxs-lookup"><span data-stu-id="52611-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="52611-122">Si los usuarios tienen asignada la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* \* se establece en *verdadero*:</span><span class="sxs-lookup"><span data-stu-id="52611-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="52611-123">Si a los usuarios se les asigna una directiva distinta de la directiva global, ejecute y compruebe que *-AllowBroadcastScheduling* esté establecido en *true*:</span><span class="sxs-lookup"><span data-stu-id="52611-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="52611-124">**Desea que la programación de eventos en directo se deshabilite en toda la organización**</span><span class="sxs-lookup"><span data-stu-id="52611-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="52611-125">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="52611-126">Asignar todos los usuarios de la organización a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="52611-127">**Desea que un gran número de usuarios pueda programar eventos en vivo e impedir que un grupo de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="52611-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="52611-128">Ejecute y compruebe que *AllowBroadcastScheduling* se establece en *true*:</span><span class="sxs-lookup"><span data-stu-id="52611-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="52611-129">A continuación, asigne un usuario o usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="52611-130">Crear una nueva directiva que no permita programar eventos en vivo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52611-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="52611-131">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="52611-132">A continuación, asigne usuarios a esta Directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="52611-133">**Desea deshabilitar la programación de eventos en vivo para un gran número de usuarios y permitir que un conjunto de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="52611-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="52611-134">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="52611-135">A continuación, asigne esos usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="52611-136">Crear una directiva para permitir la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="52611-137">Habilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="52611-138">A continuación, asigne usuarios a esta Directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="52611-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="52611-139">Establecer quién puede unirse a eventos en directo</span><span class="sxs-lookup"><span data-stu-id="52611-139">Set who can join live events</span></span>
 
<span data-ttu-id="52611-140">Establezca la directiva global para permitir a los usuarios crear eventos que todos los usuarios, incluidos los anónimos, pueden asistir, ejecutar:</span><span class="sxs-lookup"><span data-stu-id="52611-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="52611-141">Establecer la opción de grabación de eventos en directo</span><span class="sxs-lookup"><span data-stu-id="52611-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="52611-142">Esta configuración se aplica solo a los eventos generados en Teams.</span><span class="sxs-lookup"><span data-stu-id="52611-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="52611-143">Establezca la directiva global para deshabilitar la grabación de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="52611-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="52611-144">Establecer subtítulos en vivo y subtítulos en eventos en directo</span><span class="sxs-lookup"><span data-stu-id="52611-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="52611-145">Esta configuración se aplica solo a los eventos generados en Teams.</span><span class="sxs-lookup"><span data-stu-id="52611-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="52611-146">Establezca la directiva global para activar los subtítulos en vivo y los subtítulos (transcripción) para los asistentes del evento:</span><span class="sxs-lookup"><span data-stu-id="52611-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="52611-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="52611-147">Related topics</span></span>
- [<span data-ttu-id="52611-148">Configuración de Eventos en Directo de Teams</span><span class="sxs-lookup"><span data-stu-id="52611-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="52611-149">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="52611-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)


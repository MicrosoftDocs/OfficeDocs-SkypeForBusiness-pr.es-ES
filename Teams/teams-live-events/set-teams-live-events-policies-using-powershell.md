---
title: Usar PowerShell para establecer directivas de eventos en directo
author: cichur
ms.author: v-cichur
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
description: Ejemplos de cómo usar PowerShell para establecer directivas en Teams para controlar quién puede tener eventos en directo en su organización y las características disponibles en los eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815630"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="3c1d6-103">Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c1d6-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="3c1d6-104">Puede usar los siguientes cmdlets Windows PowerShell para establecer y asignar configuraciones de directiva para eventos en directo en Teams:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="3c1d6-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3c1d6-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="3c1d6-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3c1d6-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="3c1d6-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3c1d6-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="3c1d6-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3c1d6-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="3c1d6-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="3c1d6-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="3c1d6-110">Estos son algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="3c1d6-111">Antes de ejecutar estos cmdlets, debe estar conectado a PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="3c1d6-112">Para obtener más información, [consulte Administrar Skype Empresarial Online con Microsoft 365 u Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="3c1d6-113">Permitir a los usuarios programar eventos en directo</span><span class="sxs-lookup"><span data-stu-id="3c1d6-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="3c1d6-114">Estos ejemplos son para eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="3c1d6-115">Para eventos producidos con una aplicación o dispositivo externo, hay pasos adicionales que debe realizar.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="3c1d6-116">Para obtener más información, vea [Permitir a los usuarios programar eventos producidos con una aplicación o dispositivo externos.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="3c1d6-117">**Permitir que un usuario programe eventos en directo**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="3c1d6-118">Si se asigna al usuario la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* está establecido en *True:*</span><span class="sxs-lookup"><span data-stu-id="3c1d6-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="3c1d6-119">Después, asigne al usuario a la directiva global y ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="3c1d6-120">Escenarios de usuario</span><span class="sxs-lookup"><span data-stu-id="3c1d6-120">User scenarios</span></span>
<span data-ttu-id="3c1d6-121">**Desea que todos los usuarios de su organización puedan programar eventos en directo**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="3c1d6-122">Si se asigna a los usuarios la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* \*está establecido en *True:*</span><span class="sxs-lookup"><span data-stu-id="3c1d6-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="3c1d6-123">Si a los usuarios se les asigna una directiva que no sea la directiva global, ejecute y compruebe que *-AllowBroadcastScheduling* está establecido en *True:*</span><span class="sxs-lookup"><span data-stu-id="3c1d6-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="3c1d6-124">**Quiere que la programación de eventos en directo se deshabilite en toda la organización**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="3c1d6-125">Para deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="3c1d6-126">Para asignar todos los usuarios de la organización a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="3c1d6-127">**Desea que un gran número de usuarios pueda programar eventos en directo e impedir que un conjunto de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="3c1d6-128">Ejecute y compruebe que *AllowBroadcastScheduling* está establecido en *True:*</span><span class="sxs-lookup"><span data-stu-id="3c1d6-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="3c1d6-129">Después, asigne un usuario o usuarios a la directiva global y ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="3c1d6-130">Para crear una nueva directiva que no permita la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="3c1d6-131">Para deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="3c1d6-132">Después, asigne usuarios a esta directiva y ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="3c1d6-133">**Desea deshabilitar la programación de eventos en directo para un gran número de usuarios y permitir que un conjunto de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="3c1d6-134">Para deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="3c1d6-135">Después, asigne esos usuarios a la directiva global y ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="3c1d6-136">Para crear una directiva para permitir la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="3c1d6-137">Para habilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="3c1d6-138">Después, asigne usuarios a esta directiva y ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="3c1d6-139">Establecer quién puede unirse a eventos en directo</span><span class="sxs-lookup"><span data-stu-id="3c1d6-139">Set who can join live events</span></span>
 
<span data-ttu-id="3c1d6-140">Establezca la directiva global para permitir a los usuarios crear eventos a los que todos los usuarios, incluidos los usuarios anónimos, puedan asistir, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="3c1d6-141">Establecer la opción de grabación para eventos en directo</span><span class="sxs-lookup"><span data-stu-id="3c1d6-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="3c1d6-142">Esta configuración se aplica solo a los eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="3c1d6-143">Establezca la directiva global para deshabilitar la grabación de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="3c1d6-144">Establecer subtítulos en directo y subtítulos en eventos en directo</span><span class="sxs-lookup"><span data-stu-id="3c1d6-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="3c1d6-145">Esta configuración se aplica solo a los eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="3c1d6-146">Establezca la directiva global para activar los subtítulos en directo y los subtítulos (transcripción) para los asistentes al evento:</span><span class="sxs-lookup"><span data-stu-id="3c1d6-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="3c1d6-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3c1d6-147">Related topics</span></span>
- [<span data-ttu-id="3c1d6-148">Configuración de Eventos en Directo de Teams</span><span class="sxs-lookup"><span data-stu-id="3c1d6-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="3c1d6-149">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="3c1d6-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)


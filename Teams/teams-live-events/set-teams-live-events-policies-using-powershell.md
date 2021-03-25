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
description: Ejemplos de cómo usar PowerShell para establecer directivas en Teams para controlar quién puede contener eventos en directo en su organización y las características disponibles en los eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119149"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="18db7-103">Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18db7-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="18db7-104">Puede usar los siguientes cmdlets Windows PowerShell para establecer y asignar la configuración de directiva para eventos en directo en Teams:</span><span class="sxs-lookup"><span data-stu-id="18db7-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="18db7-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="18db7-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="18db7-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="18db7-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="18db7-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="18db7-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="18db7-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="18db7-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="18db7-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="18db7-109">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="18db7-110">Estos son algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="18db7-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="18db7-111">Antes de poder ejecutar estos cmdlets, debe estar conectado a PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="18db7-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="18db7-112">Para obtener más información, vea [Administrar Skype Empresarial Online con Microsoft 365 u Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="18db7-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="18db7-113">Permitir a los usuarios programar eventos en directo</span><span class="sxs-lookup"><span data-stu-id="18db7-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="18db7-114">Estos ejemplos son para eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="18db7-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="18db7-115">Para los eventos producidos con una aplicación o dispositivo externos, hay pasos adicionales que debe realizar.</span><span class="sxs-lookup"><span data-stu-id="18db7-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="18db7-116">Para obtener más información, vea Habilitar a los usuarios para programar eventos que se [produjeron con una aplicación o dispositivo externos.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="18db7-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="18db7-117">**Permitir que un usuario programe eventos en directo**</span><span class="sxs-lookup"><span data-stu-id="18db7-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="18db7-118">Si al usuario se le asigna la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* está establecido en *True:*</span><span class="sxs-lookup"><span data-stu-id="18db7-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="18db7-119">A continuación, asigne al usuario a la directiva global y ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="18db7-120">Escenarios de usuario</span><span class="sxs-lookup"><span data-stu-id="18db7-120">User scenarios</span></span>
<span data-ttu-id="18db7-121">**Desea que todos los usuarios de su organización puedan programar eventos en directo**</span><span class="sxs-lookup"><span data-stu-id="18db7-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="18db7-122">Si a los usuarios se les asigna la directiva global, ejecute y compruebe *que AllowBroadcastScheduling* \*está establecido en *True:*</span><span class="sxs-lookup"><span data-stu-id="18db7-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="18db7-123">Si a los usuarios se les asigna una directiva que no sea la directiva global, ejecute y compruebe que *-AllowBroadcastScheduling* se establece en *True:*</span><span class="sxs-lookup"><span data-stu-id="18db7-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="18db7-124">**Desea que la programación de eventos en directo se deshabilite en toda la organización**</span><span class="sxs-lookup"><span data-stu-id="18db7-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="18db7-125">Deshabilite la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="18db7-126">Asignar todos los usuarios de su organización a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="18db7-127">**Desea que un gran número de usuarios puedan programar eventos en directo e impedir que un conjunto de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="18db7-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="18db7-128">Ejecute y compruebe que *AllowBroadcastScheduling* se establece en *True:*</span><span class="sxs-lookup"><span data-stu-id="18db7-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="18db7-129">A continuación, asigne un usuario o usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="18db7-130">Cree una nueva directiva que no permita programar eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="18db7-131">Deshabilite la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="18db7-132">A continuación, asigne usuarios a esta directiva y ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="18db7-133">**Desea deshabilitar la programación de eventos en directo para un gran número de usuarios y permitir que un conjunto de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="18db7-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="18db7-134">Deshabilite la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="18db7-135">Después, asigne esos usuarios a la directiva global y ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="18db7-136">Cree una directiva para permitir la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="18db7-137">Habilitar la programación de eventos en directo, ejecutar:</span><span class="sxs-lookup"><span data-stu-id="18db7-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="18db7-138">A continuación, asigne usuarios a esta directiva y ejecute:</span><span class="sxs-lookup"><span data-stu-id="18db7-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="18db7-139">Establecer quién puede unirse a eventos en directo</span><span class="sxs-lookup"><span data-stu-id="18db7-139">Set who can join live events</span></span>
 
<span data-ttu-id="18db7-140">Establezca la directiva global para permitir a los usuarios crear eventos a los que todos, incluidos los usuarios anónimos, puedan asistir y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="18db7-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="18db7-141">Establecer la opción de grabación para eventos en directo</span><span class="sxs-lookup"><span data-stu-id="18db7-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="18db7-142">Esta configuración solo se aplica a los eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="18db7-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="18db7-143">Establezca la directiva global para deshabilitar la grabación de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="18db7-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="18db7-144">Establecer subtítulos y subtítulos en directo en eventos en directo</span><span class="sxs-lookup"><span data-stu-id="18db7-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="18db7-145">Esta configuración solo se aplica a los eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="18db7-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="18db7-146">Establezca la directiva global para activar subtítulos y subtítulos en directo (transcripción) para los asistentes al evento:</span><span class="sxs-lookup"><span data-stu-id="18db7-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="18db7-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="18db7-147">Related topics</span></span>
- [<span data-ttu-id="18db7-148">Configuración de Eventos en Directo de Teams</span><span class="sxs-lookup"><span data-stu-id="18db7-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="18db7-149">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="18db7-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)
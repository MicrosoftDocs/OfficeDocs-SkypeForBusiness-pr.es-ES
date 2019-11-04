---
title: Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Ejemplos de uso de PowerShell para establecer directivas en Teams para controlar quién puede contener eventos en directo en la organización y características que están disponibles en los eventos que crean
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37570173"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="ee958-103">Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee958-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="ee958-104">Puede usar los siguientes cmdlets de Windows PowerShell para establecer y asignar la configuración de directiva para eventos en directo de Teams:</span><span class="sxs-lookup"><span data-stu-id="ee958-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="ee958-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="ee958-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="ee958-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="ee958-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="ee958-107">Nuevo: CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="ee958-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="ee958-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="ee958-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="ee958-109">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ee958-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="ee958-110">Permitir a los usuarios programar eventos en vivo</span><span class="sxs-lookup"><span data-stu-id="ee958-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="ee958-111">Estos ejemplos son para eventos producidos en Teams.</span><span class="sxs-lookup"><span data-stu-id="ee958-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="ee958-112">Para los eventos generados con una aplicación externa o un dispositivo, hay pasos adicionales que debe realizar.</span><span class="sxs-lookup"><span data-stu-id="ee958-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="ee958-113">Para obtener más información, vea [permitir a los usuarios programar eventos generados con una aplicación o un dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="ee958-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="ee958-114">**Permitir que un usuario programe eventos en vivo**</span><span class="sxs-lookup"><span data-stu-id="ee958-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="ee958-115">Si se asigna al usuario la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* se establece en *true*:</span><span class="sxs-lookup"><span data-stu-id="ee958-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="ee958-116">A continuación, asigne el usuario a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="ee958-117">Escenarios de usuario</span><span class="sxs-lookup"><span data-stu-id="ee958-117">User scenarios</span></span>
<span data-ttu-id="ee958-118">**Desea que todos los usuarios de su organización puedan programar eventos en vivo**</span><span class="sxs-lookup"><span data-stu-id="ee958-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="ee958-119">Si los usuarios tienen asignada la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* \* se establece en *verdadero*:</span><span class="sxs-lookup"><span data-stu-id="ee958-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="ee958-120">Si a los usuarios se les asigna una directiva distinta de la directiva global, ejecute y compruebe que *-AllowBroadcastScheduling* esté establecido en *true*:</span><span class="sxs-lookup"><span data-stu-id="ee958-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="ee958-121">**Desea que la programación de eventos en directo se deshabilite en toda la organización**</span><span class="sxs-lookup"><span data-stu-id="ee958-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="ee958-122">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="ee958-123">Asignar todos los usuarios de la organización a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="ee958-124">**Desea que un gran número de usuarios pueda programar eventos en vivo e impedir que un grupo de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="ee958-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="ee958-125">Ejecute y compruebe que *AllowBroadcastScheduling* se establece en *true*:</span><span class="sxs-lookup"><span data-stu-id="ee958-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="ee958-126">A continuación, asigne un usuario o usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="ee958-127">Crear una nueva directiva que no permita programar eventos en vivo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee958-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="ee958-128">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="ee958-129">A continuación, asigne usuarios a esta Directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="ee958-130">**Desea deshabilitar la programación de eventos en vivo para un gran número de usuarios y permitir que un conjunto de usuarios los programe**</span><span class="sxs-lookup"><span data-stu-id="ee958-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="ee958-131">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="ee958-132">A continuación, asigne esos usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="ee958-133">Crear una directiva para permitir la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="ee958-134">Habilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="ee958-135">A continuación, asigne usuarios a esta Directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ee958-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="ee958-136">Establecer quién puede unirse a eventos en directo</span><span class="sxs-lookup"><span data-stu-id="ee958-136">Set who can join live events</span></span>
 
<span data-ttu-id="ee958-137">Establezca la directiva global para permitir a los usuarios crear eventos que todos los usuarios, incluidos los anónimos, pueden asistir, ejecutar:</span><span class="sxs-lookup"><span data-stu-id="ee958-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="ee958-138">Establecer la opción de grabación de eventos en directo</span><span class="sxs-lookup"><span data-stu-id="ee958-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="ee958-139">Esta configuración se aplica solo a los eventos generados en Teams.</span><span class="sxs-lookup"><span data-stu-id="ee958-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="ee958-140">Establezca la directiva global para deshabilitar la grabación de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="ee958-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="ee958-141">Establecer subtítulos en vivo y subtítulos en eventos en directo</span><span class="sxs-lookup"><span data-stu-id="ee958-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="ee958-142">Esta configuración se aplica solo a los eventos generados en Teams.</span><span class="sxs-lookup"><span data-stu-id="ee958-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="ee958-143">Establezca la directiva global para activar los subtítulos en vivo y los subtítulos (transcripción) para los asistentes del evento:</span><span class="sxs-lookup"><span data-stu-id="ee958-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="ee958-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ee958-144">Related topics</span></span>
- [<span data-ttu-id="ee958-145">Configuración de eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="ee958-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)



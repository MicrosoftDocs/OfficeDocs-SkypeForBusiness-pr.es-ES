---
title: Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Ejemplos de cómo usar PowerShell para establecer directivas en los equipos para controlar quién puede contener eventos en directo en la organización y las características que están disponibles en los eventos que crean
appliesto:
- Microsoft Teams
ms.openlocfilehash: c198711d918914bbd6a1929514d7c2e9aa7dfe00
ms.sourcegitcommit: ff0c4bef4d4cbc71d51fce941aff63739a0016e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2018
ms.locfileid: "26626226"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="1ccf9-103">Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ccf9-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="1ccf9-104">Puede usar los siguientes cmdlets de Windows PowerShell para establecer y asignar a configuraciones de directiva para eventos en directo en los equipos:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="1ccf9-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1ccf9-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="1ccf9-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1ccf9-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="1ccf9-107">Nueva CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1ccf9-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="1ccf9-108">GRANT CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1ccf9-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="1ccf9-109">Aquí tiene algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1ccf9-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="1ccf9-110">Permitir a los usuarios programar eventos en directo</span><span class="sxs-lookup"><span data-stu-id="1ccf9-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="1ccf9-111">Estos ejemplos son para los eventos de inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="1ccf9-111">These examples are for quick start events.</span></span> <span data-ttu-id="1ccf9-112">Para los eventos de codificador externo, existen pasos adicionales que debe hacer.</span><span class="sxs-lookup"><span data-stu-id="1ccf9-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="1ccf9-113">Para obtener más información, vea [Permitir a los usuarios programar eventos codificador externo](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span><span class="sxs-lookup"><span data-stu-id="1ccf9-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="1ccf9-114">**Permitir que un usuario programar eventos en directo**</span><span class="sxs-lookup"><span data-stu-id="1ccf9-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="1ccf9-115">Si el usuario se le asigna la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* está establecido en *True*:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="1ccf9-116">A continuación, asigne al usuario a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="1ccf9-117">Escenarios de usuario</span><span class="sxs-lookup"><span data-stu-id="1ccf9-117">User scenarios</span></span>
<span data-ttu-id="1ccf9-118">**Desea que todos los usuarios de la organización para poder programar eventos en directo**</span><span class="sxs-lookup"><span data-stu-id="1ccf9-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="1ccf9-119">Si los usuarios tienen asignados la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* \* está establecida en *True*:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="1ccf9-120">Si los usuarios se asignan a una directiva que no sea la directiva global, ejecute y compruebe que *- AllowBroadcastScheduling* está establecido en *True*:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="1ccf9-121">**Desea que los eventos en directo deshabilitarse en toda la organización de la programación**</span><span class="sxs-lookup"><span data-stu-id="1ccf9-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="1ccf9-122">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="1ccf9-123">Asignar a todos los usuarios de la organización a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="1ccf9-124">**Desea que un gran número de usuarios puedan programar eventos en directo y evitar que un conjunto de usuarios de programación de las mismas**</span><span class="sxs-lookup"><span data-stu-id="1ccf9-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="1ccf9-125">Ejecute y compruebe que *AllowBroadcastScheduling* está establecido en *True*:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="1ccf9-126">A continuación, asignar un usuario o a los usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="1ccf9-127">Crear una nueva directiva que no permite la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="1ccf9-128">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="1ccf9-129">A continuación, asignar a usuarios a esta directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="1ccf9-130">**Desea deshabilitar el evento en directo de programación para un gran número de los usuarios y permitir que un conjunto de usuarios a programarlas**</span><span class="sxs-lookup"><span data-stu-id="1ccf9-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="1ccf9-131">Deshabilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="1ccf9-132">A continuación, asignar a los usuarios a la directiva global, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="1ccf9-133">Crear una directiva para permitir la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="1ccf9-134">Habilitar la programación de eventos en directo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="1ccf9-135">A continuación, asignar a usuarios a esta directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="1ccf9-136">Conjunto que se puede unir a eventos en directo</span><span class="sxs-lookup"><span data-stu-id="1ccf9-136">Set who can join live events</span></span>
 
<span data-ttu-id="1ccf9-137">Establecer la directiva global para permitir a los usuarios crear eventos de que todos los usuarios, incluidos los usuarios anónimos, puede asistir, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="1ccf9-138">Establecer la opción de grabación de eventos en directo</span><span class="sxs-lookup"><span data-stu-id="1ccf9-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="1ccf9-139">Esta configuración se aplica sólo a los eventos de inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="1ccf9-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="1ccf9-140">Establecer la directiva global para deshabilitar el registro de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="1ccf9-141">Establecer transcripción y traducción de eventos en directo (próximamente)</span><span class="sxs-lookup"><span data-stu-id="1ccf9-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="1ccf9-142">Esta configuración se aplica sólo a los eventos de inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="1ccf9-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="1ccf9-143">Establecer la directiva global para activar en transcripción y traducción para los asistentes de evento:</span><span class="sxs-lookup"><span data-stu-id="1ccf9-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="1ccf9-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1ccf9-144">Related topics</span></span>
- [<span data-ttu-id="1ccf9-145">Configurar para los equipos de eventos en directo</span><span class="sxs-lookup"><span data-stu-id="1ccf9-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)



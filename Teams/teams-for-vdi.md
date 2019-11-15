---
title: Teams para la infraestructura de escritorio virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: Aprenda a ejecutar Microsoft Teams en un entorno de infraestructura de escritorio virtual (VDI).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 450fd98d65d092f3cbc684e4efd90691b5e389a1
ms.sourcegitcommit: 69217fb6d6b71081386364db58083eb5d1932c07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38638810"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="af9ed-103">Teams para la infraestructura de escritorio virtualizada</span><span class="sxs-lookup"><span data-stu-id="af9ed-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="af9ed-104">En este artículo se describen los requisitos y las limitaciones para usar Microsoft Teams en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="af9ed-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="af9ed-105">¿Qué es VDI?</span><span class="sxs-lookup"><span data-stu-id="af9ed-105">What is VDI?</span></span>

<span data-ttu-id="af9ed-106">La infraestructura de escritorio virtual (VDI) es una tecnología de virtualización que hospeda un sistema operativo de escritorio y aplicaciones en un servidor centralizado en un centro de datos.</span><span class="sxs-lookup"><span data-stu-id="af9ed-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="af9ed-107">Esto permite una experiencia de escritorio totalmente personalizada para los usuarios con un origen centralizado totalmente seguro y compatible.</span><span class="sxs-lookup"><span data-stu-id="af9ed-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="af9ed-108">Actualmente, Teams en un entorno virtualizado está disponible con soporte técnico para la funcionalidad de colaboración y chats con una máquina virtualizada dedicada (VM).</span><span class="sxs-lookup"><span data-stu-id="af9ed-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="af9ed-109">Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="af9ed-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="af9ed-110">Requisitos de Teams</span><span class="sxs-lookup"><span data-stu-id="af9ed-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="af9ed-111">Establecer directivas para desactivar las funciones de llamada y de reunión en Teams</span><span class="sxs-lookup"><span data-stu-id="af9ed-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="af9ed-112">La experiencia de llamadas y reuniones de equipos no está optimizada para un entorno de VDI (próximamente).</span><span class="sxs-lookup"><span data-stu-id="af9ed-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="af9ed-113">Le recomendamos que establezca directivas de nivel de usuario para desactivar las funciones de llamada y de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="af9ed-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="af9ed-114">Aún puede elegir ejecutar Teams por completo en VDI con la aplicación de escritorio de Teams o la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="af9ed-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="af9ed-115">Sin embargo, le recomendamos que establezca las directivas para evitar poner en peligro la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="af9ed-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="af9ed-116">Los cambios de Directiva pueden tardar un poco (algunas horas) en propagarse.</span><span class="sxs-lookup"><span data-stu-id="af9ed-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="af9ed-117">Si no ve los cambios de una cuenta determinada inmediatamente, inténtelo de nuevo en unas pocas horas.</span><span class="sxs-lookup"><span data-stu-id="af9ed-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="af9ed-118">Cuando las llamadas y las reuniones de Teams están optimizadas para su uso en entornos de escritorio virtuales, puede revertir estas directivas y permitir que los usuarios usen Teams como lo harían normalmente.</span><span class="sxs-lookup"><span data-stu-id="af9ed-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="af9ed-119">Llamadas</span><span class="sxs-lookup"><span data-stu-id="af9ed-119">Calling</span></span>

<span data-ttu-id="af9ed-120">Use los cmdlets de **CSTeamsCallingPolicy** para controlar si los usuarios pueden usar las opciones de llamadas y llamadas en los chats privados y grupales.</span><span class="sxs-lookup"><span data-stu-id="af9ed-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="af9ed-121">A continuación se muestra la lista de opciones de directiva y los valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="af9ed-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="af9ed-122">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="af9ed-122">Policy name</span></span>  |<span data-ttu-id="af9ed-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9ed-123">Description</span></span> |<span data-ttu-id="af9ed-124">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="af9ed-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="af9ed-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="af9ed-125">AllowCalling</span></span>    |<span data-ttu-id="af9ed-126">Controla las capacidades de llamadas de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="af9ed-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="af9ed-127">Activar este servicio permite que los usuarios de Skype empresarial tengan llamadas individuales con usuarios de Teams y viceversa.</span><span class="sxs-lookup"><span data-stu-id="af9ed-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="af9ed-128">Se establece en false para evitar que las llamadas de los usuarios de Skype empresarial se desembarquen en Teams.</span><span class="sxs-lookup"><span data-stu-id="af9ed-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="af9ed-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="af9ed-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="af9ed-130">Controla si la aplicación de llamada está disponible en la barra de la aplicación en el lado izquierdo del cliente de equipos y si los usuarios ven las opciones de llamadas y videollamadas en una conversación privada</span><span class="sxs-lookup"><span data-stu-id="af9ed-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="af9ed-131">Se establece en false para quitar la aplicación que llama de la barra de aplicaciones situada en el lado izquierdo de Teams y quitar las opciones de llamadas y videollamadas en la conversación privada.</span><span class="sxs-lookup"><span data-stu-id="af9ed-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="af9ed-132">Crear y asignar una directiva de llamadas</span><span class="sxs-lookup"><span data-stu-id="af9ed-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="af9ed-133">Inicie una sesión de Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="af9ed-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="af9ed-134">Conéctate al conector de Skype online.</span><span class="sxs-lookup"><span data-stu-id="af9ed-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="af9ed-135">Ver una lista de las opciones de directiva de llamada.</span><span class="sxs-lookup"><span data-stu-id="af9ed-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="af9ed-136">Busque la opción de directiva integrada donde todas las directivas de llamadas están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="af9ed-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="af9ed-137">Tiene el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="af9ed-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="af9ed-138">Aplique la opción de directiva integrada DisallowCalling a todos los usuarios que vayan a usar Teams en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="af9ed-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="af9ed-139">Para obtener más información sobre las directivas de llamadas de Teams, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="af9ed-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="af9ed-140">Reuniones</span><span class="sxs-lookup"><span data-stu-id="af9ed-140">Meetings</span></span>

<span data-ttu-id="af9ed-141">Use los cmdlets de **CsTeamsMeetingPolicy** para controlar el tipo de reuniones que los usuarios pueden crear, las características a las que pueden acceder durante una reunión y las características de la reunión que están disponibles para los usuarios anónimos y anónimos.</span><span class="sxs-lookup"><span data-stu-id="af9ed-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="af9ed-142">A continuación se muestra la lista de opciones de directiva y los valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="af9ed-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="af9ed-143">Nombre de la Directiva</span><span class="sxs-lookup"><span data-stu-id="af9ed-143">Policy Name</span></span> |<span data-ttu-id="af9ed-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9ed-144">Description</span></span>|<span data-ttu-id="af9ed-145">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="af9ed-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="af9ed-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="af9ed-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="af9ed-147">Determina si un usuario puede programar reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="af9ed-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="af9ed-148">Se establece en false para impedir que el usuario pueda programar reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="af9ed-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="af9ed-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="af9ed-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="af9ed-150">Determina si un usuario puede programar reuniones de canal.</span><span class="sxs-lookup"><span data-stu-id="af9ed-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="af9ed-151">Se establece en false para impedir que el usuario pueda programar reuniones de canal.</span><span class="sxs-lookup"><span data-stu-id="af9ed-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="af9ed-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="af9ed-152">AllowMeetNow</span></span> |<span data-ttu-id="af9ed-153">Determina si un usuario puede crear o iniciar reuniones ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="af9ed-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="af9ed-154">Establezca este valor en false para impedir que el usuario pueda iniciar reuniones ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="af9ed-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="af9ed-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="af9ed-155">ScreenSharingMode</span></span> | <span data-ttu-id="af9ed-156">Determina el modo en el que un usuario puede compartir su pantalla en llamadas o reuniones.</span><span class="sxs-lookup"><span data-stu-id="af9ed-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="af9ed-157">Establecer en deshabilitado para impedir que el usuario comparta su pantalla</span><span class="sxs-lookup"><span data-stu-id="af9ed-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="af9ed-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="af9ed-158">AllowIPVideo</span></span> |<span data-ttu-id="af9ed-159">Determina si el vídeo está habilitado en las reuniones o las llamadas de un usuario.</span><span class="sxs-lookup"><span data-stu-id="af9ed-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="af9ed-160">Se establece en false para impedir que el usuario comparta el vídeo.</span><span class="sxs-lookup"><span data-stu-id="af9ed-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="af9ed-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="af9ed-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="af9ed-162">Determina si los usuarios anónimos pueden llamar a un número de RTC.</span><span class="sxs-lookup"><span data-stu-id="af9ed-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="af9ed-163">Se establece en false para impedir que los usuarios anónimos llamen</span><span class="sxs-lookup"><span data-stu-id="af9ed-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="af9ed-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="af9ed-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="af9ed-165">Determina si los usuarios anónimos pueden iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="af9ed-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="af9ed-166">Se establece en false para impedir que los usuarios inicien una reunión</span><span class="sxs-lookup"><span data-stu-id="af9ed-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="af9ed-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="af9ed-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="af9ed-168">Determina si un usuario puede programar reuniones de Teams en el cliente de escritorio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="af9ed-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="af9ed-169">Se establece en false para impedir que un usuario programe reuniones de Teams en el cliente de escritorio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="af9ed-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="af9ed-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="af9ed-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="af9ed-171">Determina si los participantes pueden solicitar o ceder el control de la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="af9ed-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="af9ed-172">Se establece en false para impedir que el usuario asigne y solicite el control en una reunión.</span><span class="sxs-lookup"><span data-stu-id="af9ed-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="af9ed-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="af9ed-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="af9ed-174">Determina si los participantes externos pueden solicitar o ceder el control de la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="af9ed-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="af9ed-175">Se establece en false para impedir que un usuario externo otorgue un control a una reunión</span><span class="sxs-lookup"><span data-stu-id="af9ed-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="af9ed-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="af9ed-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="af9ed-177">Determina si se permite el uso compartido de PowerPoint en las reuniones de un usuario.</span><span class="sxs-lookup"><span data-stu-id="af9ed-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="af9ed-178">Se establece en false para impedir que un usuario comparta archivos de PowerPoint en una reunión</span><span class="sxs-lookup"><span data-stu-id="af9ed-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="af9ed-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="af9ed-179">AllowWhiteboard</span></span> | <span data-ttu-id="af9ed-180">Determina si se permite la pizarra en las reuniones de un usuario.</span><span class="sxs-lookup"><span data-stu-id="af9ed-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="af9ed-181">Establecer en falso para prohibir la pizarra en una reunión</span><span class="sxs-lookup"><span data-stu-id="af9ed-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="af9ed-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="af9ed-182">AllowTranscription</span></span> |<span data-ttu-id="af9ed-183">Determina si se permiten las transcripciones y los títulos de tiempo real o posterior a la reunión en las reuniones de un usuario.</span><span class="sxs-lookup"><span data-stu-id="af9ed-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="af9ed-184">Se establece en false para prohibir transcripción y leyendas en una reunión</span><span class="sxs-lookup"><span data-stu-id="af9ed-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="af9ed-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="af9ed-185">AllowSharedNotes</span></span> | <span data-ttu-id="af9ed-186">Determina si los usuarios pueden tomar notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="af9ed-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="af9ed-187">Se establece en false para impedir que los usuarios tomen notas compartidas</span><span class="sxs-lookup"><span data-stu-id="af9ed-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="af9ed-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="af9ed-188">MediaBitRateKB</span></span> |<span data-ttu-id="af9ed-189">Determina la tasa de bits multimedia para transllamadas de uso compartido de audio, vídeo y aplicaciones en reuniones.</span><span class="sxs-lookup"><span data-stu-id="af9ed-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="af9ed-190">El valor sugerido es 5000 (5 MB).</span><span class="sxs-lookup"><span data-stu-id="af9ed-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="af9ed-191">Puede cambiarla en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="af9ed-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="af9ed-192">Crear y asignar una directiva de reunión</span><span class="sxs-lookup"><span data-stu-id="af9ed-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="af9ed-193">Inicie una sesión de Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="af9ed-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="af9ed-194">Conéctate al conector de Skype online.</span><span class="sxs-lookup"><span data-stu-id="af9ed-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="af9ed-195">Ver una lista de opciones de directiva de reunión.</span><span class="sxs-lookup"><span data-stu-id="af9ed-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="af9ed-196">Busque la opción de directiva integrada en la que se deshabilitaron todas las directivas de reunión.</span><span class="sxs-lookup"><span data-stu-id="af9ed-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="af9ed-197">Tiene el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="af9ed-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="af9ed-198">Aplique la opción de directiva integrada AllOff a todos los usuarios que vayan a usar Teams en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="af9ed-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="af9ed-199">Para obtener más información sobre las directivas de reunión de Teams, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="af9ed-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="af9ed-200">Requisitos del proveedor de virtualización</span><span class="sxs-lookup"><span data-stu-id="af9ed-200">Virtualization provider requirements</span></span>

<span data-ttu-id="af9ed-201">La aplicación de Teams se ha validado en los principales proveedores de soluciones de virtualización.</span><span class="sxs-lookup"><span data-stu-id="af9ed-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="af9ed-202">Con varios proveedores de mercado, consulte a su proveedor de soluciones de virtualización para asegurarse de que se cumplan los requisitos mínimos.</span><span class="sxs-lookup"><span data-stu-id="af9ed-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="af9ed-203">Requisitos de la máquina virtual</span><span class="sxs-lookup"><span data-stu-id="af9ed-203">Virtual Machine requirements</span></span>

> [!NOTE]
> <span data-ttu-id="af9ed-204">Los siguientes requisitos se aplican a la aplicación de escritorio de Teams y a teams Web App.</span><span class="sxs-lookup"><span data-stu-id="af9ed-204">The following requirements apply to both the Teams desktop app and the Teams Web app.</span></span>

<span data-ttu-id="af9ed-205">Con las diversas cargas de trabajo y necesidades de los usuarios en un entorno virtualizado, la configuración de VM mínima recomendada es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="af9ed-205">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="af9ed-206">Parámetro</span><span class="sxs-lookup"><span data-stu-id="af9ed-206">Parameter</span></span>  |<span data-ttu-id="af9ed-207">Cód</span><span class="sxs-lookup"><span data-stu-id="af9ed-207">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="af9ed-208">vCPU</span><span class="sxs-lookup"><span data-stu-id="af9ed-208">vCPU</span></span>    |  <span data-ttu-id="af9ed-209">2 núcleos</span><span class="sxs-lookup"><span data-stu-id="af9ed-209">2 cores</span></span>       |
|<span data-ttu-id="af9ed-210">MEMORIAS</span><span class="sxs-lookup"><span data-stu-id="af9ed-210">RAM</span></span>     |  <span data-ttu-id="af9ed-211">4 GB</span><span class="sxs-lookup"><span data-stu-id="af9ed-211">4 GB</span></span>      |
|<span data-ttu-id="af9ed-212">Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="af9ed-212">Storage</span></span>     | <span data-ttu-id="af9ed-213">8 GB</span><span class="sxs-lookup"><span data-stu-id="af9ed-213">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="af9ed-214">Requisitos del sistema operativo de la máquina virtual</span><span class="sxs-lookup"><span data-stu-id="af9ed-214">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="af9ed-215">Los sistemas operativos compatibles con la VM son:</span><span class="sxs-lookup"><span data-stu-id="af9ed-215">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="af9ed-216">Windows 10 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="af9ed-216">Windows 10 and later</span></span>
- <span data-ttu-id="af9ed-217">Windows Server 2012 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="af9ed-217">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="af9ed-218">Instalar Teams en VDI</span><span class="sxs-lookup"><span data-stu-id="af9ed-218">Install Teams on VDI</span></span>

<span data-ttu-id="af9ed-219">Este es el proceso y las herramientas para implementar la aplicación de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="af9ed-219">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="af9ed-220">Descargue el paquete de MSI de Teams con uno de los siguientes vínculos en función del entorno.</span><span class="sxs-lookup"><span data-stu-id="af9ed-220">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="af9ed-221">Recomendamos la versión de 64 bits para una VM VDI con un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="af9ed-221">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="af9ed-222">versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="af9ed-222">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="af9ed-223">versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="af9ed-223">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="af9ed-224">Ejecute el siguiente comando para instalar el MSI en la máquina virtual de VDI (o actualizarlo).</span><span class="sxs-lookup"><span data-stu-id="af9ed-224">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="af9ed-225">Instala Teams en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="af9ed-225">This installs Teams to Program Files.</span></span> <span data-ttu-id="af9ed-226">En este momento, la configuración de la imagen de oro está completa.</span><span class="sxs-lookup"><span data-stu-id="af9ed-226">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="af9ed-227">La siguiente sesión de inicio de sesión interactivo inicia Teams y solicita las credenciales.</span><span class="sxs-lookup"><span data-stu-id="af9ed-227">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="af9ed-228">Tenga en cuenta que no es posible deshabilitar el inicio automático de equipos al instalar Teams en VDI mediante la propiedad ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="af9ed-228">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="af9ed-229">Ejecute el siguiente comando para desinstalar el MSI de la máquina virtual de VDI (o prepararse para actualizarlo).</span><span class="sxs-lookup"><span data-stu-id="af9ed-229">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="af9ed-230">Esto desinstalará Teams de archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="af9ed-230">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="af9ed-231">Problemas conocidos y limitaciones</span><span class="sxs-lookup"><span data-stu-id="af9ed-231">Known issues and limitations</span></span>

<span data-ttu-id="af9ed-232">A continuación se indican los problemas conocidos y las limitaciones de Teams en VDI.</span><span class="sxs-lookup"><span data-stu-id="af9ed-232">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="af9ed-233">**Implementaciones de tipo de host de sesión compartida**: implementaciones de tipo de host de sesión compartida (por ejemplo, configuración de VM no persistente compartida) no están en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="af9ed-233">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="af9ed-234">**Llamadas y reuniones**:</span><span class="sxs-lookup"><span data-stu-id="af9ed-234">**Calling and meetings**:</span></span>

    - <span data-ttu-id="af9ed-235">Los escenarios de llamadas y reuniones no están optimizados para VDI.</span><span class="sxs-lookup"><span data-stu-id="af9ed-235">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="af9ed-236">Estos escenarios no se realizarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="af9ed-236">These scenarios will perform poorly.</span></span> <span data-ttu-id="af9ed-237">Le recomendamos que use directivas de nivel de usuario tal y como se describe en la sección [establecer directivas para desactivar la función de llamadas y reuniones de Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="af9ed-237">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="af9ed-238">La aplicación de las directivas descritas en este artículo afecta a la posibilidad de usar la funcionalidad de llamadas y reuniones, que depende de otras directivas, puede afectar a otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="af9ed-238">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="af9ed-239">Si los usuarios de su organización usan clientes que no son VDI, puede optar por no aplicar las directivas.</span><span class="sxs-lookup"><span data-stu-id="af9ed-239">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="af9ed-240">**Unirse a llamadas y reuniones creadas por otros usuarios**: aunque las directivas restringen la creación de reuniones, aún pueden unirse a ellas si otro usuario llama a ellas desde la reunión.</span><span class="sxs-lookup"><span data-stu-id="af9ed-240">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="af9ed-241">En estas reuniones, la capacidad del usuario de compartir vídeo, usar la pizarra y otras características depende de si ha deshabilitado esas características con TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="af9ed-241">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="af9ed-242">**Contenido almacenado en caché**: Si el entorno virtual en el que se ejecutan los equipos no es persistente (y los datos se limpian al final de cada sesión de usuario), es posible que los usuarios noten una degradación en el rendimiento debido a la actualización del contenido, independientemente de si el usuario tuvo acceso al mismo contenido de una sesión anterior.</span><span class="sxs-lookup"><span data-stu-id="af9ed-242">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="af9ed-243">**Actualizaciones de cliente**: Teams en VDI no se actualiza automáticamente con la instalación de MSI por máquina.</span><span class="sxs-lookup"><span data-stu-id="af9ed-243">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="af9ed-244">Tiene que actualizar la imagen de VM instalando un nuevo MSI, como se describe en la sección [instalar Teams en VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="af9ed-244">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="af9ed-245">Debe desinstalar la versión actual para actualizar a una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="af9ed-245">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="af9ed-246">**Experiencia de usuario**: la experiencia de usuario de los equipos en un entorno de VDI puede diferir de un entorno que no sea de VDI.</span><span class="sxs-lookup"><span data-stu-id="af9ed-246">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="af9ed-247">Las diferencias pueden deberse a la configuración de directivas o a la compatibilidad de características en el entorno.</span><span class="sxs-lookup"><span data-stu-id="af9ed-247">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="af9ed-248">Para los problemas conocidos de teams que no se relacionan con VDI, consulte [problemas conocidos de Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af9ed-248">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="af9ed-249">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="af9ed-249">Related topics</span></span>

- [<span data-ttu-id="af9ed-250">Instalar Microsoft Teams mediante MSI</span><span class="sxs-lookup"><span data-stu-id="af9ed-250">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)

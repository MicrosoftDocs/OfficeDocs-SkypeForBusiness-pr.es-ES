---
title: Teams para la infraestructura de escritorio virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Obtenga información sobre cómo ejecutar Microsoft Teams en un entorno virtualizado de Desktop Infrastructure (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223427"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="eb57b-103">Teams para la infraestructura de escritorio virtualizada</span><span class="sxs-lookup"><span data-stu-id="eb57b-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="eb57b-104">En este artículo se describen los requisitos y limitaciones para el uso de Microsoft Teams en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="eb57b-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="eb57b-105">¿Qué es VDI?</span><span class="sxs-lookup"><span data-stu-id="eb57b-105">What is VDI?</span></span>

<span data-ttu-id="eb57b-106">Infraestructura de escritorio virtual (VDI) es la tecnología de virtualización que hospeda un sistema operativo de escritorio y las aplicaciones en un servidor centralizado en un centro de datos.</span><span class="sxs-lookup"><span data-stu-id="eb57b-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="eb57b-107">Esto permite una experiencia de escritorio totalmente personalizada a los usuarios con un origen centralizado totalmente compatibles con y protegido.</span><span class="sxs-lookup"><span data-stu-id="eb57b-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="eb57b-108">Actualmente, los equipos en un entorno virtualizado está disponible con soporte para la funcionalidad de colaboración y chat con un equipo virtualizado persistente dedicado (VM).</span><span class="sxs-lookup"><span data-stu-id="eb57b-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="eb57b-109">Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="eb57b-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="eb57b-110">Requisitos de los equipos</span><span class="sxs-lookup"><span data-stu-id="eb57b-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="eb57b-111">Establecer directivas para desactivar la opción de llamada y funcionalidad en los equipos de la reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="eb57b-112">Los equipos de llamada y la experiencia de la reunión no está optimizado para un entorno VDI (próximamente).</span><span class="sxs-lookup"><span data-stu-id="eb57b-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="eb57b-113">Se recomienda que establecer directivas de nivel de usuario para desactivar la opción de llamada y funcionalidad en los equipos de la reunión.</span><span class="sxs-lookup"><span data-stu-id="eb57b-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="eb57b-114">Aún puede elegir ejecutar los equipos totalmente en VDI con la aplicación de escritorio de los equipos o la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="eb57b-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="eb57b-115">Sin embargo, le recomendamos que configure las directivas para evitar poner en peligro la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="eb57b-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="eb57b-116">Puede tardar cierto tiempo (unas cuantas horas) propagar los cambios de directiva.</span><span class="sxs-lookup"><span data-stu-id="eb57b-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="eb57b-117">Si no ve inmediatamente los cambios para una cuenta determinada, inténtelo de nuevo en unas cuantas horas.</span><span class="sxs-lookup"><span data-stu-id="eb57b-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="eb57b-118">Al llamar a los equipos y las reuniones están optimizadas para su uso en entornos de escritorio virtuales, puede revertir estas directivas y permitir a los usuarios utilizar los equipos como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="eb57b-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="eb57b-119">Llamar a</span><span class="sxs-lookup"><span data-stu-id="eb57b-119">Calling</span></span>

<span data-ttu-id="eb57b-120">Use los cmdlets **CSTeamsCallingPolicy** para controlar si los usuarios pueden usar al llamar a y las opciones de llamada en privado y grupo de chat.</span><span class="sxs-lookup"><span data-stu-id="eb57b-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="eb57b-121">Aquí es la lista de configuración de directiva y valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="eb57b-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="eb57b-122">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="eb57b-122">Policy name</span></span>  |<span data-ttu-id="eb57b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb57b-123">Description</span></span> |<span data-ttu-id="eb57b-124">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="eb57b-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="eb57b-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="eb57b-125">AllowCalling</span></span>    |<span data-ttu-id="eb57b-126">Interoperabilidad de controles al llamar a funciones.</span><span class="sxs-lookup"><span data-stu-id="eb57b-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="eb57b-127">Activar Esto permite Skype para los usuarios de negocios que las llamadas proporcionó con los usuarios de los equipos y viceversa.</span><span class="sxs-lookup"><span data-stu-id="eb57b-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="eb57b-128">Se establece en False para evitar que las llamadas de Skype para los usuarios de negocio en los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="eb57b-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="eb57b-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="eb57b-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="eb57b-130">Controla si la aplicación de llamada está disponible en la barra de la aplicación en el lado izquierdo del cliente para los equipos y si los usuarios ven llamadas y las opciones de llamadas de chat privado de vídeo</span><span class="sxs-lookup"><span data-stu-id="eb57b-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="eb57b-131">Se establece en False para quitar la aplicación de llamada de la barra de la aplicación en el lado izquierdo de los equipos y para quitar las opciones de llamada de llamadas y vídeo de chat privado.</span><span class="sxs-lookup"><span data-stu-id="eb57b-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="eb57b-132">Crear y asignar una directiva de llamada</span><span class="sxs-lookup"><span data-stu-id="eb57b-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="eb57b-133">Iniciar una sesión de Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="eb57b-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="eb57b-134">Conectar con el conector de Skype en línea.</span><span class="sxs-lookup"><span data-stu-id="eb57b-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="eb57b-135">Ver una lista de las opciones de directiva de llamada.</span><span class="sxs-lookup"><span data-stu-id="eb57b-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="eb57b-136">Busque la opción de directiva integrada donde se deshabilitan todas las directivas de llamada.</span><span class="sxs-lookup"><span data-stu-id="eb57b-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="eb57b-137">El siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="eb57b-137">It looks like this.</span></span>
   
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

5. <span data-ttu-id="eb57b-138">Aplicar la opción de directiva integrada DisallowCalling a todos los usuarios que van a usar los equipos en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="eb57b-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="eb57b-139">Para obtener más información acerca de los equipos al llamar a las directivas, vea [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="eb57b-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="eb57b-140">Reuniones</span><span class="sxs-lookup"><span data-stu-id="eb57b-140">Meetings</span></span>

<span data-ttu-id="eb57b-141">Use los cmdlets **CsTeamsMeetingPolicy** para controlar el tipo de las reuniones que los usuarios pueden crear, las características que puede tener acceso a mientras está en una reunión y las características de reunión que están disponibles para los usuarios anónimos y externos.</span><span class="sxs-lookup"><span data-stu-id="eb57b-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="eb57b-142">Aquí es la lista de configuración de directiva y valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="eb57b-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="eb57b-143">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="eb57b-143">Policy Name</span></span> |<span data-ttu-id="eb57b-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb57b-144">Description</span></span>|<span data-ttu-id="eb57b-145">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="eb57b-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="eb57b-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="eb57b-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="eb57b-147">Determina si se permite a un usuario para programar las conferencias privadas.</span><span class="sxs-lookup"><span data-stu-id="eb57b-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="eb57b-148">Se establece en False para prohibir al usuario la posibilidad de programar reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="eb57b-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="eb57b-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="eb57b-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="eb57b-150">Determina si se permite a un usuario para programar reuniones de canal.</span><span class="sxs-lookup"><span data-stu-id="eb57b-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="eb57b-151">Se establece en False para prohibir al usuario la posibilidad de programar reuniones de canal.</span><span class="sxs-lookup"><span data-stu-id="eb57b-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="eb57b-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="eb57b-152">AllowMeetNow</span></span> |<span data-ttu-id="eb57b-153">Determina si se permite a un usuario para crear o iniciar reuniones ad hoc.</span><span class="sxs-lookup"><span data-stu-id="eb57b-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="eb57b-154">Establézcalo en False para prohibir al usuario la posibilidad de iniciar reuniones ad hoc.</span><span class="sxs-lookup"><span data-stu-id="eb57b-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="eb57b-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="eb57b-155">ScreenSharingMode</span></span> | <span data-ttu-id="eb57b-156">Determina el modo en que un usuario se permite compartir su pantalla en las llamadas o reuniones.</span><span class="sxs-lookup"><span data-stu-id="eb57b-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="eb57b-157">Establecido en deshabilitado para prohibir el usuario de uso compartido de sus pantallas</span><span class="sxs-lookup"><span data-stu-id="eb57b-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="eb57b-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="eb57b-158">AllowIPVideo</span></span> |<span data-ttu-id="eb57b-159">Determina si el vídeo está habilitado en las reuniones o las llamadas de un usuario.</span><span class="sxs-lookup"><span data-stu-id="eb57b-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="eb57b-160">Se establece en False para prohibir al usuario de uso compartido de su vídeo</span><span class="sxs-lookup"><span data-stu-id="eb57b-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="eb57b-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="eb57b-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="eb57b-162">Determina si los usuarios anónimos pueden marcar un número RTC.</span><span class="sxs-lookup"><span data-stu-id="eb57b-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="eb57b-163">Se establece en False para prohibir a los usuarios anónimos llamadas de salida</span><span class="sxs-lookup"><span data-stu-id="eb57b-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="eb57b-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="eb57b-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="eb57b-165">Determina si los usuarios anónimos pueden iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="eb57b-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="eb57b-166">Se establece en False para prohibir a los usuarios iniciar una reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="eb57b-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="eb57b-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="eb57b-168">Determina si un usuario puede programar reuniones en los equipos en el cliente de escritorio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="eb57b-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="eb57b-169">Se establece en False para prohibir a un usuario de programación de reuniones de los equipos en el cliente de escritorio de Outlook</span><span class="sxs-lookup"><span data-stu-id="eb57b-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="eb57b-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="eb57b-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="eb57b-171">Determina si los participantes pueden solicitar o ceder el control de uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="eb57b-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="eb57b-172">Se establece en False para prohibir al usuario proporcionar y solicitar el control en una reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="eb57b-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="eb57b-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="eb57b-174">Determina si los participantes externos pueden solicitar o ceder el control de uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="eb57b-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="eb57b-175">Establece en False para prohibir a un usuario externo que proporciona, solicitar el control en una reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="eb57b-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="eb57b-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="eb57b-177">Determina si se permite el uso compartido de PowerPoint en las reuniones de un usuario.</span><span class="sxs-lookup"><span data-stu-id="eb57b-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="eb57b-178">Se establece en False para prohibir a un usuario de uso compartido de archivos de PowerPoint en una reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="eb57b-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="eb57b-179">AllowWhiteboard</span></span> | <span data-ttu-id="eb57b-180">Determina si se permite la Pizarra en las reuniones de un usuario.</span><span class="sxs-lookup"><span data-stu-id="eb57b-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="eb57b-181">Se establece en False para prohibir la Pizarra en una reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="eb57b-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="eb57b-182">AllowTranscription</span></span> |<span data-ttu-id="eb57b-183">Determina si se permiten los títulos en tiempo real o posteriores a la reunión y transcripciones en las reuniones de un usuario.</span><span class="sxs-lookup"><span data-stu-id="eb57b-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="eb57b-184">Se establece en False para prohibir la transcripción y títulos en una reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="eb57b-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="eb57b-185">AllowSharedNotes</span></span> | <span data-ttu-id="eb57b-186">Determina si los usuarios pueden tomar notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="eb57b-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="eb57b-187">Se establece en False para prohibir a los usuarios tomar notas compartidas</span><span class="sxs-lookup"><span data-stu-id="eb57b-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="eb57b-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="eb57b-188">MediaBitRateKB</span></span> |<span data-ttu-id="eb57b-189">Determina la velocidad de bits de medios de audio/vídeo/aplicación de uso compartido de las transmisiones de reuniones</span><span class="sxs-lookup"><span data-stu-id="eb57b-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="eb57b-190">Valor sugerido es 5000 (5 MB).</span><span class="sxs-lookup"><span data-stu-id="eb57b-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="eb57b-191">Se puede cambiar en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="eb57b-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="eb57b-192">Crear y asignar una directiva de reunión</span><span class="sxs-lookup"><span data-stu-id="eb57b-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="eb57b-193">Iniciar una sesión de Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="eb57b-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="eb57b-194">Conectar con el conector de Skype en línea.</span><span class="sxs-lookup"><span data-stu-id="eb57b-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="eb57b-195">Ver una lista de opciones de directiva de reunión.</span><span class="sxs-lookup"><span data-stu-id="eb57b-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="eb57b-196">Busque la opción de directiva integrada donde se deshabilitan todas las directivas de reunión.</span><span class="sxs-lookup"><span data-stu-id="eb57b-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="eb57b-197">El siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="eb57b-197">It looks like this.</span></span>
   
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

5. <span data-ttu-id="eb57b-198">Aplicar la opción de directiva integrada AllOff a todos los usuarios que van a usar los equipos en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="eb57b-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="eb57b-199">Para obtener más información acerca de las directivas de reunión de los equipos, vea [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="eb57b-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="eb57b-200">Requisitos de virtualización de proveedor</span><span class="sxs-lookup"><span data-stu-id="eb57b-200">Virtualization provider requirements</span></span>

<span data-ttu-id="eb57b-201">La aplicación de los equipos ha sido validada en proveedores de soluciones de virtualización a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="eb57b-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="eb57b-202">Con varios proveedores de mercado, consulte a su proveedor de soluciones de virtualización para asegurarse de que se cumplen los requisitos mínimos.</span><span class="sxs-lookup"><span data-stu-id="eb57b-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="eb57b-203">Requisitos de máquina virtual</span><span class="sxs-lookup"><span data-stu-id="eb57b-203">Virtual Machine requirements</span></span>

<span data-ttu-id="eb57b-204">Con las diversas cargas de trabajo y las necesidades del usuario en un entorno virtualizado, el siguiente es el mínimo recomendado de configuración de máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="eb57b-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="eb57b-205">Parámetro</span><span class="sxs-lookup"><span data-stu-id="eb57b-205">Parameter</span></span>  |<span data-ttu-id="eb57b-206">Medida</span><span class="sxs-lookup"><span data-stu-id="eb57b-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="eb57b-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="eb57b-207">vCPU</span></span>    |  <span data-ttu-id="eb57b-208">2 núcleos</span><span class="sxs-lookup"><span data-stu-id="eb57b-208">2 cores</span></span>       |
|<span data-ttu-id="eb57b-209">MEMORIA RAM</span><span class="sxs-lookup"><span data-stu-id="eb57b-209">RAM</span></span>     |  <span data-ttu-id="eb57b-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="eb57b-210">4 GB</span></span>      |
|<span data-ttu-id="eb57b-211">Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="eb57b-211">Storage</span></span>     | <span data-ttu-id="eb57b-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="eb57b-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="eb57b-213">Requisitos de sistema operativo de la máquina virtual</span><span class="sxs-lookup"><span data-stu-id="eb57b-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="eb57b-214">Los sistemas operativos admitidos para la máquina virtual son:</span><span class="sxs-lookup"><span data-stu-id="eb57b-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="eb57b-215">10 y versiones posteriores de Windows</span><span class="sxs-lookup"><span data-stu-id="eb57b-215">Windows 10 and later</span></span>
- <span data-ttu-id="eb57b-216">Windows Server 2012 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="eb57b-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="eb57b-217">Instalar los equipos de la VDI</span><span class="sxs-lookup"><span data-stu-id="eb57b-217">Install Teams on VDI</span></span>

<span data-ttu-id="eb57b-218">Este es el proceso y las herramientas necesarias para implementar la aplicación de escritorio de los equipos.</span><span class="sxs-lookup"><span data-stu-id="eb57b-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="eb57b-219">Descargar el paquete de MSI de los equipos mediante uno de los siguientes vínculos según el entorno.</span><span class="sxs-lookup"><span data-stu-id="eb57b-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="eb57b-220">Se recomienda la versión de 64 bits para una VM de VDI con un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="eb57b-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="eb57b-221">versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="eb57b-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="eb57b-222">versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="eb57b-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="eb57b-223">Ejecute el siguiente comando para instalar el archivo MSI en la VM VDI (o completar su actualización).</span><span class="sxs-lookup"><span data-stu-id="eb57b-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="eb57b-224">Este archivo instala los equipos a los archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="eb57b-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="eb57b-225">En este momento, la configuración de imagen oro está completa.</span><span class="sxs-lookup"><span data-stu-id="eb57b-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="eb57b-226">La sesión de inicio de sesión interactivo siguiente inicia los equipos y solicita credenciales.</span><span class="sxs-lookup"><span data-stu-id="eb57b-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="eb57b-227">Tenga en cuenta que no es posible deshabilitar el inicio automático de los equipos al instalar los equipos de la VDI mediante la propiedad correspondiente a.</span><span class="sxs-lookup"><span data-stu-id="eb57b-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="eb57b-228">Ejecute el siguiente comando para desinstalar el archivo MSI de la VM VDI (o preparar para su actualización).</span><span class="sxs-lookup"><span data-stu-id="eb57b-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="eb57b-229">Esto desinstala los equipos de los archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="eb57b-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="eb57b-230">Limitaciones y problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="eb57b-230">Known issues and limitations</span></span>

<span data-ttu-id="eb57b-231">Los siguientes son problemas conocidas y limitaciones para los equipos de la VDI.</span><span class="sxs-lookup"><span data-stu-id="eb57b-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="eb57b-232">**Implementaciones de tipo de host de sesión de compartidos**: implementaciones de tipo de host de sesión de compartidos (por ejemplo, que no son persistentes VM configuración compartida) no están en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="eb57b-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="eb57b-233">**Llamadas y reuniones**:</span><span class="sxs-lookup"><span data-stu-id="eb57b-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="eb57b-234">Llamada y escenarios de la reunión no están optimizados para VDI.</span><span class="sxs-lookup"><span data-stu-id="eb57b-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="eb57b-235">Estos escenarios realizará mal.</span><span class="sxs-lookup"><span data-stu-id="eb57b-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="eb57b-236">Se recomienda usar las directivas de nivel de usuario, tal como se describe en la sección [establecer directivas para desactivar la opción de llamada y funcionalidad en los equipos de la reunión](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="eb57b-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="eb57b-237">Aplicar las directivas que se describen en este artículo afecta a la capacidad de usar la funcionalidad de llamada y convocatorias de reunión que según otras directivas, puede afectar a otros usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="eb57b-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="eb57b-238">Si los usuarios de la organización utilizan a los clientes que no sean de VDI, puede elegir no aplicar las directivas.</span><span class="sxs-lookup"><span data-stu-id="eb57b-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="eb57b-239">**Unirse a las llamadas y las reuniones creadas por otros usuarios**: aunque las directivas de restringen a los usuarios de la creación de las reuniones, todavía pueden unirse a reuniones si otro usuario marca a ellos desde la reunión.</span><span class="sxs-lookup"><span data-stu-id="eb57b-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="eb57b-240">En estas reuniones, la capacidad del usuario para compartir vídeo, usar la Pizarra y otras características dependen de si deshabilita las características mediante TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="eb57b-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="eb57b-241">**Contenido en caché**: si es el entorno virtual en los equipos que se ejecuten no es persistente (y se limpian de datos al final de cada sesión de usuario), los usuarios pueden observar la degradación del rendimiento debido a la actualización de contenido, independientemente de si el usuario tiene acceso a la misma contenido en una sesión anterior.</span><span class="sxs-lookup"><span data-stu-id="eb57b-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="eb57b-242">**Actualizaciones de cliente**: no se actualizan automáticamente los equipos de la VDI similar al modo en que los clientes de equipos que no sean de VDI.</span><span class="sxs-lookup"><span data-stu-id="eb57b-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="eb57b-243">Se debe actualizar la imagen de la máquina virtual mediante la instalación de un nuevo MSI tal como se describe en la sección [Instalación de los equipos de la VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="eb57b-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="eb57b-244">Debe desinstalar la versión actual para actualizar a una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="eb57b-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="eb57b-245">**Experiencia del usuario**: los equipos de la experiencia del usuario en un entorno VDI puede ser distinta de un entorno que no sean VDI.</span><span class="sxs-lookup"><span data-stu-id="eb57b-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="eb57b-246">Las diferencias se pueden debido a la configuración de directiva o cuentan con soporte en el entorno.</span><span class="sxs-lookup"><span data-stu-id="eb57b-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="eb57b-247">Para los equipos de los problemas conocidos que no están relacionados con VDI, consulte [problemas para los equipos de Microsoft conocidos](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eb57b-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb57b-248">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="eb57b-248">Related topics</span></span>

- [<span data-ttu-id="eb57b-249">Instalar Teams Microsoft con MSI</span><span class="sxs-lookup"><span data-stu-id="eb57b-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
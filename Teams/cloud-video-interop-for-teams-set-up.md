---
title: Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: En este artículo se explica cómo planear y configurar la interoperabilidad de vídeo en la nube para los usuarios de su organización.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102606"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="0c919-103">Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c919-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="0c919-104">Una vez que haya elegido sus partners de interoperabilidad de vídeo en la [nube,](cloud-video-interop.md)tendrá que planear la implementación, configurarse con detalles de aprovisionamiento y clave de inquilino de partners, y dar su consentimiento a la aplicación de interoperabilidad de vídeo de su organización.</span><span class="sxs-lookup"><span data-stu-id="0c919-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="0c919-105">En el siguiente diagrama se describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="0c919-105">The following diagram outlines the process.</span></span> 

![Implementar CVI en su organización](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="0c919-107">Plan</span><span class="sxs-lookup"><span data-stu-id="0c919-107">Plan</span></span>

<span data-ttu-id="0c919-108">Vea [Interoperabilidad de](cloud-video-interop.md) vídeo en la nube para obtener Microsoft Teams información sobre cómo identificar un partner o partners para usarlo en su organización.</span><span class="sxs-lookup"><span data-stu-id="0c919-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="0c919-109">Para planear la habilitación de todo el sitio/ simultánea o basada en el usuario:</span><span class="sxs-lookup"><span data-stu-id="0c919-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="0c919-110">Elegir un modelo de implementación o modelo hospedado para su uso</span><span class="sxs-lookup"><span data-stu-id="0c919-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="0c919-111">Seleccione el plan de licencia ideal para su organización.</span><span class="sxs-lookup"><span data-stu-id="0c919-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="0c919-112">Planear la capacidad de las máquinas virtuales es hospedar su infraestructura de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0c919-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="0c919-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="0c919-113">Configure</span></span> 

<span data-ttu-id="0c919-114">Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0c919-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="0c919-115">Obtenga información de configuración de los partners que ha elegido (clave de inquilino, appIds...).</span><span class="sxs-lookup"><span data-stu-id="0c919-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="0c919-116">Puede usar uno o varios partners de interoperabilidad de vídeo en su organización</span><span class="sxs-lookup"><span data-stu-id="0c919-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="0c919-117">Asegúrese de que la red está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0c919-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="0c919-118">Configure el firewall de vídeo basado en estándares para que se admita el recorrido de red perimetral.</span><span class="sxs-lookup"><span data-stu-id="0c919-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="0c919-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c919-119">For example:</span></span> 
    - <span data-ttu-id="0c919-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="0c919-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="0c919-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="0c919-121">Polycom RPAD</span></span>

3. <span data-ttu-id="0c919-122">Configure salas integradas con exchange y OTD.</span><span class="sxs-lookup"><span data-stu-id="0c919-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="0c919-123">En la mayoría de los casos, es necesario configurar y configurar relés adicionales en su entorno.</span><span class="sxs-lookup"><span data-stu-id="0c919-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="0c919-124">Aprovisionar</span><span class="sxs-lookup"><span data-stu-id="0c919-124">Provision</span></span>
 
<span data-ttu-id="0c919-125">La clave de inquilino será la llamada al servicio de partners.</span><span class="sxs-lookup"><span data-stu-id="0c919-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="0c919-126">En el ejemplo siguiente, 813878896@t.plcm.vc es la clave de inquilino.</span><span class="sxs-lookup"><span data-stu-id="0c919-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Ejemplo de clave de inquilino](media/tenant-key-example.png) 

<span data-ttu-id="0c919-128">Tendrá que ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y también habilitar usuarios seleccionados o toda la organización para crear reuniones con coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0c919-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="0c919-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft proporciona directivas preconstrucciones para cada uno de nuestros partners compatibles que le permiten designar qué partners usar para la interoperabilidad de vídeo en la nube.</span><span class="sxs-lookup"><span data-stu-id="0c919-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="0c919-130">Este cmdlet le permite identificar las directivas preconstrucciones que puede usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="0c919-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="0c919-131">Puede asignar esta directiva a uno o varios de sus usuarios aprovechando el cmdlet Grant-CsTeamsVideoInteropServicePolicy usuario.</span><span class="sxs-lookup"><span data-stu-id="0c919-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="0c919-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** El cmdlet Grant-CsTeamsVideoInteropServicePolicy permite asignar una directiva preconstrucciones para su uso en su organización o asignar la directiva a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="0c919-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="0c919-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use la New-CsVideoInteropServiceProvider para especificar información sobre un partner CVI compatible que su organización desea usar.</span><span class="sxs-lookup"><span data-stu-id="0c919-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="0c919-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use la Set-CsVideoInteropServiceProvider para actualizar información sobre un partner CVI compatible que usa su organización.</span><span class="sxs-lookup"><span data-stu-id="0c919-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="0c919-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenga todos los proveedores que se han configurado para su uso dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="0c919-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="0c919-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para quitar toda la información del proveedor sobre un proveedor que su organización ya no usa.</span><span class="sxs-lookup"><span data-stu-id="0c919-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="0c919-137">Consentimiento</span><span class="sxs-lookup"><span data-stu-id="0c919-137">Consent</span></span>

<span data-ttu-id="0c919-138">Tendrá que proporcionar permiso para que los dispositivos de videoconferencia (VTC) se unan a las reuniones de su organización a través del servicio de partners.</span><span class="sxs-lookup"><span data-stu-id="0c919-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="0c919-139">Este vínculo de consentimiento también será proporcionado por tu partner.</span><span class="sxs-lookup"><span data-stu-id="0c919-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="0c919-140">Cuando se completen estos pasos, los usuarios que estén habilitados individualmente a través del cmdlet Grant anterior, o todos los usuarios de la organización si el espacio empresarial está habilitado, tendrán coordenadas VTC en todas las reuniones Teams que programe.</span><span class="sxs-lookup"><span data-stu-id="0c919-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="0c919-141">Cualquier VTC puede unirse a estas reuniones a través de esas coordenadas.</span><span class="sxs-lookup"><span data-stu-id="0c919-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="0c919-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="0c919-142">Name</span></span>|<span data-ttu-id="0c919-143">Descripción breve del permiso de aplicación</span><span class="sxs-lookup"><span data-stu-id="0c919-143">Application Permission Short Description</span></span>| <span data-ttu-id="0c919-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c919-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="0c919-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="0c919-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="0c919-146">Unirse a llamadas de grupo y reuniones como una aplicación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0c919-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="0c919-147">Permite a la aplicación unirse a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="0c919-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="0c919-148">La aplicación se unirá con los privilegios de un usuario de directorio a las reuniones de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="0c919-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="0c919-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="0c919-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="0c919-150">Unirse a llamadas de grupo y reuniones como usuario invitado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0c919-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="0c919-151">Permite que la aplicación se una de forma anónima a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="0c919-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="0c919-152">La aplicación se unirá como invitado a las reuniones de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="0c919-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="0c919-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="0c919-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="0c919-154">Acceder a transmisiones multimedia en una llamada como una aplicación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0c919-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="0c919-155">Permite que la aplicación obtenga acceso directo a las transmisiones multimedia en una llamada, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="0c919-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="0c919-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="0c919-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="0c919-157">Leer detalles de la reunión en línea (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0c919-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="0c919-158">Permite que la aplicación lea los detalles de la reunión en línea en su organización, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="0c919-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="0c919-159">Programar</span><span class="sxs-lookup"><span data-stu-id="0c919-159">Schedule</span></span>

<span data-ttu-id="0c919-160">A continuación, programe Teams reunión con coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0c919-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="0c919-161">El usuario habilitado puede programar reuniones de equipos a través de:</span><span class="sxs-lookup"><span data-stu-id="0c919-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="0c919-162">Teams Complemento de reunión para Outlook</span><span class="sxs-lookup"><span data-stu-id="0c919-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="0c919-163">Teams cliente de escritorio y móvil</span><span class="sxs-lookup"><span data-stu-id="0c919-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="0c919-164">Join</span><span class="sxs-lookup"><span data-stu-id="0c919-164">Join</span></span>

<span data-ttu-id="0c919-165">Puede unirse a Teams reuniones con sus dispositivos VTC de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="0c919-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="0c919-166">IVR (respuesta de voz interactiva)</span><span class="sxs-lookup"><span data-stu-id="0c919-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="0c919-167">Puede llamar al IVR del partner con el tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="0c919-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="0c919-168">Una vez que esté en el IVR asociado, se le pedirá que escriba el id. de conferencia de VTC, que le conectará a la reunión Teams asociado.</span><span class="sxs-lookup"><span data-stu-id="0c919-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="0c919-169">Marcado directo</span><span class="sxs-lookup"><span data-stu-id="0c919-169">Direct dial</span></span>
    - <span data-ttu-id="0c919-170">Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo con la cadena completa de tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="0c919-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="0c919-171">Marcado con un solo toque</span><span class="sxs-lookup"><span data-stu-id="0c919-171">One-touch dial</span></span>
    - <span data-ttu-id="0c919-172">Si tiene un salón de Teams integrado, puede usar las capacidades de marcado de un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).</span><span class="sxs-lookup"><span data-stu-id="0c919-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="0c919-173">Por último, interactúe con Teams usuarios en sus reuniones mediante el uso compartido de audio, vídeo y contenido.</span><span class="sxs-lookup"><span data-stu-id="0c919-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span>
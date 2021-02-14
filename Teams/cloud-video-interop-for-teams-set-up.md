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
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582637"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="6e441-103">Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e441-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="6e441-104">Después de haber elegido los partners de interoperabilidad de vídeo en la [nube,](cloud-video-interop.md)necesitará planear la implementación, configurar los detalles de aprovisionamiento y la clave del inquilino del partner, y dar su consentimiento para la aplicación de interoperabilidad de vídeo en su organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="6e441-105">En el siguiente diagrama se describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="6e441-105">The following diagram outlines the process.</span></span> 

![Implementar CVI en su organización](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="6e441-107">Plan</span><span class="sxs-lookup"><span data-stu-id="6e441-107">Plan</span></span>

<span data-ttu-id="6e441-108">Vea [Cloud Video Interoperabilidad para Microsoft Teams](cloud-video-interop.md) para obtener información sobre cómo identificar a un partner o partners para usarlos en su organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="6e441-109">Para planear la habilitación del ancho del sitio/basado en usuarios/simultáneos/sitio:</span><span class="sxs-lookup"><span data-stu-id="6e441-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="6e441-110">Elegir un modelo de implementación/modelo hospedado para su uso</span><span class="sxs-lookup"><span data-stu-id="6e441-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="6e441-111">Seleccione el plan de licencia ideal para su organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="6e441-112">La planificación de la capacidad de las máquinas virtuales es hospedar la infraestructura de vídeo.</span><span class="sxs-lookup"><span data-stu-id="6e441-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="6e441-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="6e441-113">Configure</span></span> 

<span data-ttu-id="6e441-114">Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e441-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="6e441-115">Obtenga información de configuración de los partners que haya elegido (clave de inquilino, appIds...).</span><span class="sxs-lookup"><span data-stu-id="6e441-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="6e441-116">Puede usar uno o varios partners de interoperabilidad de vídeo en su organización</span><span class="sxs-lookup"><span data-stu-id="6e441-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="6e441-117">Asegúrese de que la red está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6e441-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="6e441-118">Configure su firewall de vídeo basado en estándares para recorrer la red perimetral como soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="6e441-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="6e441-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6e441-119">For example:</span></span> 
    - <span data-ttu-id="6e441-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="6e441-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="6e441-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="6e441-121">Polycom RPAD</span></span>

3. <span data-ttu-id="6e441-122">Configure salas integradas con exchange y OTD.</span><span class="sxs-lookup"><span data-stu-id="6e441-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="6e441-123">En la mayoría de los casos, tendría que configurar retransmisión adicional en su entorno.</span><span class="sxs-lookup"><span data-stu-id="6e441-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="6e441-124">Aprovisionar</span><span class="sxs-lookup"><span data-stu-id="6e441-124">Provision</span></span>
 
<span data-ttu-id="6e441-125">La clave del inquilino será la llamada al servicio del asociado.</span><span class="sxs-lookup"><span data-stu-id="6e441-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="6e441-126">En el ejemplo siguiente, 813878896@t.plcm.vc clave de inquilino.</span><span class="sxs-lookup"><span data-stu-id="6e441-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Ejemplo de clave de espacio empresarial](media/tenant-key-example.png) 

<span data-ttu-id="6e441-128">Tendrá que ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y, además, habilitar a los usuarios seleccionados o a toda la organización para crear reuniones con coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="6e441-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="6e441-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft proporciona directivas de construcción previa para cada uno de nuestros socios compatibles que le permiten designar qué socios usar para la interoperabilidad de vídeo en la nube.</span><span class="sxs-lookup"><span data-stu-id="6e441-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="6e441-130">Este cmdlet le permite identificar las directivas pre-construir que puede usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="6e441-131">Puede asignar esta directiva a uno o varios de los usuarios aprovechando el cmdlet Grant-CsTeamsVideoInteropServicePolicy web.</span><span class="sxs-lookup"><span data-stu-id="6e441-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="6e441-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** El Grant-CsTeamsVideoInteropServicePolicy cmdlet le permite asignar una directiva predefinida para su uso en su organización o asignar la directiva a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="6e441-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="6e441-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use la New-CsVideoInteropServiceProvider para especificar información sobre un partner de CVI compatible que le gustaría usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="6e441-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use la aplicación Set-CsVideoInteropServiceProvider para actualizar la información sobre un partner de CVI compatible que usa su organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="6e441-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenga todos los proveedores que se han configurado para su uso dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="6e441-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para quitar toda la información del proveedor sobre un proveedor que ya no usa su organización.</span><span class="sxs-lookup"><span data-stu-id="6e441-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="6e441-137">Consentimiento</span><span class="sxs-lookup"><span data-stu-id="6e441-137">Consent</span></span>

<span data-ttu-id="6e441-138">Deberá proporcionar el consentimiento de permisos para los dispositivos de teleconferencia (VTC) para unirse a las reuniones de su organización a través del servicio de asociados.</span><span class="sxs-lookup"><span data-stu-id="6e441-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="6e441-139">Este vínculo de consentimiento también será proporcionado por tu partner.</span><span class="sxs-lookup"><span data-stu-id="6e441-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="6e441-140">Cuando se completen estos pasos, los usuarios habilitados individualmente a través del cmdlet Grant anterior, o todos los usuarios de la organización si el espacio empresarial está habilitado, tendrán coordenadas de VTC en todas las reuniones de Teams que programe.</span><span class="sxs-lookup"><span data-stu-id="6e441-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="6e441-141">Cualquier VTC puede unirse a estas reuniones a través de esas coordenadas.</span><span class="sxs-lookup"><span data-stu-id="6e441-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="6e441-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="6e441-142">Name</span></span>|<span data-ttu-id="6e441-143">Descripción breve de permiso de aplicación</span><span class="sxs-lookup"><span data-stu-id="6e441-143">Application Permission Short Description</span></span>| <span data-ttu-id="6e441-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e441-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="6e441-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="6e441-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="6e441-146">Unirse a llamadas y reuniones grupales como aplicación (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6e441-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="6e441-147">Permite que la aplicación se una a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="6e441-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="6e441-148">La aplicación se unirá con los privilegios de un usuario de directorio para las reuniones de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="6e441-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="6e441-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="6e441-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="6e441-150">Unirse a llamadas y reuniones grupales como usuario invitado (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6e441-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="6e441-151">Permite que la aplicación se una anónimamente a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="6e441-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="6e441-152">La aplicación se unirá como invitado a las reuniones de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="6e441-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="6e441-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="6e441-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="6e441-154">Acceder a las transmisiones multimedia en una llamada como una aplicación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="6e441-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="6e441-155">Permite a la aplicación obtener acceso directo a las transmisiones multimedia en una llamada, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="6e441-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="6e441-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="6e441-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="6e441-157">Leer detalles de la reunión en línea (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6e441-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="6e441-158">Permite que la aplicación lea los detalles de la reunión en línea de su organización, sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="6e441-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="6e441-159">Programación</span><span class="sxs-lookup"><span data-stu-id="6e441-159">Schedule</span></span>

<span data-ttu-id="6e441-160">Después, programe la reunión de Teams con las coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="6e441-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="6e441-161">El usuario habilitado puede programar reuniones de equipos a través de:</span><span class="sxs-lookup"><span data-stu-id="6e441-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="6e441-162">Complemento para reunión de Teams para Outlook</span><span class="sxs-lookup"><span data-stu-id="6e441-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="6e441-163">Equipos de escritorio y dispositivos móviles del cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="6e441-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="6e441-164">Join</span><span class="sxs-lookup"><span data-stu-id="6e441-164">Join</span></span>

<span data-ttu-id="6e441-165">Puede unirse a las reuniones de Teams con sus dispositivos VTC de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="6e441-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="6e441-166">IVR (respuesta interactiva de voz)</span><span class="sxs-lookup"><span data-stu-id="6e441-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="6e441-167">Puedes llamar al IVR del partner mediante el tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="6e441-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="6e441-168">Una vez que se encuentra en el IVR asociado, se le pedirá que introduzca el id. de conferencia de VTC, que le conectará a la reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="6e441-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="6e441-169">Marcado directo</span><span class="sxs-lookup"><span data-stu-id="6e441-169">Direct dial</span></span>
    - <span data-ttu-id="6e441-170">Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo con la cadena completa de clave de inquilino. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="6e441-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="6e441-171">Marcado con un solo toque</span><span class="sxs-lookup"><span data-stu-id="6e441-171">One-touch dial</span></span>
    - <span data-ttu-id="6e441-172">Si tiene una sala de Teams integrada, puede usar las capacidades de marcado con un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).</span><span class="sxs-lookup"><span data-stu-id="6e441-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="6e441-173">Por último, interactúe con los usuarios de Teams en sus reuniones mediante el uso compartido de audio, vídeo y contenido.</span><span class="sxs-lookup"><span data-stu-id="6e441-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 

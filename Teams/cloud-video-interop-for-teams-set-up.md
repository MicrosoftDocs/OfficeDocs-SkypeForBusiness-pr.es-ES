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
description: En este artículo se explica cómo se puede planear y configurar la interoperabilidad de vídeo en la nube para los usuarios de su organización.
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
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="63671-103">Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63671-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="63671-104">Una vez que haya [elegido sus socios de interoperabilidad de video en la nube](cloud-video-interop.md), tendrá que planear su implementación, configurar los detalles de aprovisionamiento y la clave de inquilino del Partner, y el consentimiento de la aplicación de interoperabilidad de vídeo de su organización.</span><span class="sxs-lookup"><span data-stu-id="63671-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="63671-105">En el siguiente diagrama se describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="63671-105">The following diagram outlines the process.</span></span> 

![Implementar CVI en su organización](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="63671-107">Plan</span><span class="sxs-lookup"><span data-stu-id="63671-107">Plan</span></span>

<span data-ttu-id="63671-108">Consulte [interoperabilidad de vídeo en la nube para Microsoft Teams](cloud-video-interop.md) para obtener información sobre cómo identificar un partner o socios para usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="63671-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="63671-109">Para planificar la habilitación de los sitios de forma simultánea o concurrente:</span><span class="sxs-lookup"><span data-stu-id="63671-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="63671-110">Elegir un modelo de implementación o un modelo hospedado para su uso</span><span class="sxs-lookup"><span data-stu-id="63671-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="63671-111">Seleccione el plan de licencia ideal para su organización.</span><span class="sxs-lookup"><span data-stu-id="63671-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="63671-112">Planee la capacidad de las VMs para hospedar su infraestructura de video.</span><span class="sxs-lookup"><span data-stu-id="63671-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="63671-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="63671-113">Configure</span></span> 

<span data-ttu-id="63671-114">Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="63671-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="63671-115">Obtener información de configuración de los socios o socios que ha elegido (clave de inquilino, appIds...).</span><span class="sxs-lookup"><span data-stu-id="63671-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="63671-116">Puede usar uno o varios socios de interoperabilidad de vídeo de su organización</span><span class="sxs-lookup"><span data-stu-id="63671-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="63671-117">Asegúrese de que la red está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="63671-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="63671-118">Configure su firewall de vídeo basado en estándares para que sea compatible con la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="63671-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="63671-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="63671-119">For example:</span></span> 
    - <span data-ttu-id="63671-120">VCS-e de Cisco</span><span class="sxs-lookup"><span data-stu-id="63671-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="63671-121">RPAD Polycom</span><span class="sxs-lookup"><span data-stu-id="63671-121">Polycom RPAD</span></span>

3. <span data-ttu-id="63671-122">Configurar salas integradas con Exchange y OTD.</span><span class="sxs-lookup"><span data-stu-id="63671-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="63671-123">En la mayoría de los casos, será necesario configurar y configurar la retransmisión adicional en su entorno.</span><span class="sxs-lookup"><span data-stu-id="63671-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="63671-124">Aprovisionar</span><span class="sxs-lookup"><span data-stu-id="63671-124">Provision</span></span>
 
<span data-ttu-id="63671-125">La clave de inquilino se enviará a través del servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="63671-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="63671-126">En el ejemplo siguiente, 813878896@t.plcm.vc es la clave de inquilino.</span><span class="sxs-lookup"><span data-stu-id="63671-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Ejemplo de clave de inquilino](media/tenant-key-example.png) 

<span data-ttu-id="63671-128">Tendrá que ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y también habilitar a usuarios seleccionados o a toda la organización para crear reuniones con coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="63671-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="63671-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft proporciona directivas preconstruidas para cada uno de nuestros socios compatibles, que le permiten designar qué asociados usar para la interoperabilidad de vídeo en la nube.</span><span class="sxs-lookup"><span data-stu-id="63671-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="63671-130">Este cmdlet le permite identificar las directivas preconstruidas que puede usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="63671-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="63671-131">Puede asignar esta directiva a uno o más de los usuarios que aprovechan el cmdlet Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="63671-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="63671-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* El cmdlet Grant-CsTeamsVideoInteropServicePolicy le permite asignar una directiva preconstruida para su uso en su organización o asignar la Directiva a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="63671-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="63671-133">\*\* [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Use el nuevo-CsVideoInteropServiceProvider para especificar información sobre un socio de CVI admitido que su organización desea usar.</span><span class="sxs-lookup"><span data-stu-id="63671-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="63671-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Use set-CsVideoInteropServiceProvider para actualizar la información sobre un socio de CVI compatible que usa su organización.</span><span class="sxs-lookup"><span data-stu-id="63671-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="63671-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Obtener todos los proveedores que se han configurado para su uso dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="63671-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="63671-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Use Remove-CsVideoInteropServiceProvider para quitar toda la información de proveedores de un proveedor que ya no use su organización.</span><span class="sxs-lookup"><span data-stu-id="63671-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="63671-137">Concede</span><span class="sxs-lookup"><span data-stu-id="63671-137">Consent</span></span>

<span data-ttu-id="63671-138">Necesitará proporcionar autorización de permiso para que los dispositivos de teleconferencia de vídeo (VTCs) se unan a las reuniones de su organización a través del servicio de asociación.</span><span class="sxs-lookup"><span data-stu-id="63671-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="63671-139">El socio también proporcionará este vínculo de consentimiento.</span><span class="sxs-lookup"><span data-stu-id="63671-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="63671-140">Una vez completados estos pasos, los usuarios que se habilitan individualmente mediante el cmdlet Grant anterior o todos los usuarios de la organización si el inquilino está habilitado, tendrán coordenadas de VTC en todas las reuniones de teams que programen.</span><span class="sxs-lookup"><span data-stu-id="63671-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="63671-141">Cualquier VTC puede unirse a estas reuniones a través de esas coordinadas.</span><span class="sxs-lookup"><span data-stu-id="63671-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="63671-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="63671-142">Name</span></span>|<span data-ttu-id="63671-143">Descripción breve de permisos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="63671-143">Application Permission Short Description</span></span>| <span data-ttu-id="63671-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="63671-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="63671-145">Calls. JoinGroupCall. All</span><span class="sxs-lookup"><span data-stu-id="63671-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="63671-146">Unirse a reuniones grupales y reuniones como una aplicación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="63671-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="63671-147">Permite a la aplicación unirse a llamadas grupales y a las reuniones programadas de su organización, sin necesidad de que un usuario haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="63671-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="63671-148">La aplicación se unirá con los privilegios de un usuario del directorio a las reuniones de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="63671-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="63671-149">Calls. JoinGroupCallasGuest. All</span><span class="sxs-lookup"><span data-stu-id="63671-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="63671-150">Unirse a reuniones de grupo y reuniones como un usuario invitado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="63671-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="63671-151">Permite a la aplicación unirse anónimamente a llamadas grupales y a reuniones programadas de su organización, sin necesidad de que un usuario haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="63671-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="63671-152">La aplicación se unirá como invitado a las reuniones de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="63671-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="63671-153">Calls. AccessMedia. All</span><span class="sxs-lookup"><span data-stu-id="63671-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="63671-154">Acceder a las transmisiones multimedia en una llamada como una aplicación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="63671-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="63671-155">Permite que la aplicación obtenga acceso directo a las transmisiones multimedia en una llamada, sin necesidad de que un usuario haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="63671-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="63671-156">OnlineMeetings. Read. All</span><span class="sxs-lookup"><span data-stu-id="63671-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="63671-157">Leer detalles de la reunión en línea (vista previa)</span><span class="sxs-lookup"><span data-stu-id="63671-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="63671-158">Permite que la aplicación Lea los detalles de la reunión en línea en su organización, sin necesidad de que un usuario haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="63671-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="63671-159">Programa</span><span class="sxs-lookup"><span data-stu-id="63671-159">Schedule</span></span>

<span data-ttu-id="63671-160">A continuación, programe Teams reunión con coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="63671-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="63671-161">El usuario habilitado puede programar reuniones de Teams a través de:</span><span class="sxs-lookup"><span data-stu-id="63671-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="63671-162">Complemento de reunión de Teams para Outlook</span><span class="sxs-lookup"><span data-stu-id="63671-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="63671-163">Equipo cliente de escritorio y móvil</span><span class="sxs-lookup"><span data-stu-id="63671-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="63671-164">Join</span><span class="sxs-lookup"><span data-stu-id="63671-164">Join</span></span>

<span data-ttu-id="63671-165">Puede unirse a las reuniones de Teams con sus dispositivos de VTC de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="63671-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="63671-166">IVR (respuesta interactiva de voz)</span><span class="sxs-lookup"><span data-stu-id="63671-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="63671-167">Puedes llamar al IVR del socio con el tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="63671-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="63671-168">Una vez que se encuentre en el IVR de socio, se le pedirá que introduzca el VTC conferenceId, que le conectará a la reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="63671-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="63671-169">Marcado directo</span><span class="sxs-lookup"><span data-stu-id="63671-169">Direct dial</span></span>
    - <span data-ttu-id="63671-170">Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del socio mediante la característica de marcado directo con la cadena completa de tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="63671-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="63671-171">Marcación sencilla</span><span class="sxs-lookup"><span data-stu-id="63671-171">One-touch dial</span></span>
    - <span data-ttu-id="63671-172">Si tiene una sala de equipos integrada, puede usar las funciones de marcado con un solo toque que le ofrece su partner (sin necesidad de escribir ninguna cadena de marcado).</span><span class="sxs-lookup"><span data-stu-id="63671-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="63671-173">Por último, comuníquese con los usuarios de Teams en sus reuniones con audio, vídeo y uso compartido de contenido.</span><span class="sxs-lookup"><span data-stu-id="63671-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 

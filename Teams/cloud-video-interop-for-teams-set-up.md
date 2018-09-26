---
title: Configurar la interoperabilidad de vídeo en la nube de Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: En este artículo se explica cómo puede planear y configurar interoperabilidad de vídeo en la nube para los usuarios de la organización.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2090036aa5e1a05e46581d365d9b6b4aeb94b32
ms.sourcegitcommit: fbef2bfa4e5eb27799aa25f0e890cfb18013cf72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25040783"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="d35ce-103">Configurar la interoperabilidad de vídeo en la nube de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d35ce-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="d35ce-104">Cuando haya [elegido en sus socios de interoperabilidad de vídeo en la nube](cloud-video-interop.md), debe planear la implementación, configurar get con detalles de aprovisionamiento y clave de inquilino de socio y consentimiento a la aplicación de interoperabilidad de vídeo en su organización.</span><span class="sxs-lookup"><span data-stu-id="d35ce-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="d35ce-105">En el siguiente diagrama describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="d35ce-105">The following diagram outlines the process.</span></span> 

![Implementación de CVI en la organización](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="d35ce-107">Planificar</span><span class="sxs-lookup"><span data-stu-id="d35ce-107">Plan</span></span>

<span data-ttu-id="d35ce-108">Vea [Interoperabilidad de vídeo en la nube para los equipos de Microsoft](cloud-video-interop.md) para obtener información acerca de cómo identificar un socio o socios para usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="d35ce-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="d35ce-109">Para planear la habilitación todo el usuario en función o simultánea/sitio:</span><span class="sxs-lookup"><span data-stu-id="d35ce-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="d35ce-110">Elegir un modelo de implementación hospedada por el modelo o para su uso</span><span class="sxs-lookup"><span data-stu-id="d35ce-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="d35ce-111">Seleccione el plan de licencia ideal para su organización.</span><span class="sxs-lookup"><span data-stu-id="d35ce-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="d35ce-112">Planeación de capacidad de las máquinas virtuales es que va a hospedar la infraestructura de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d35ce-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="d35ce-113">Configurar</span><span class="sxs-lookup"><span data-stu-id="d35ce-113">Configure</span></span> 

<span data-ttu-id="d35ce-114">Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d35ce-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="d35ce-115">Para obtener información de configuración de los socios y socios que tiene elegido (clave de inquilino, AppID...).</span><span class="sxs-lookup"><span data-stu-id="d35ce-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="d35ce-116">Puede usar a uno o más asociados de interoperabilidad vídeo en su organización</span><span class="sxs-lookup"><span data-stu-id="d35ce-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="d35ce-117">Asegúrese de que su red está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d35ce-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="d35ce-118">Configure el firewall de vídeo basada en estándares para recorrido por la red perimetral admitir.</span><span class="sxs-lookup"><span data-stu-id="d35ce-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="d35ce-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d35ce-119">For example:</span></span> 
    - <span data-ttu-id="d35ce-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="d35ce-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="d35ce-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="d35ce-121">Polycom RPAD</span></span>

3. <span data-ttu-id="d35ce-122">Configurar salones integrados con exchange y OTD.</span><span class="sxs-lookup"><span data-stu-id="d35ce-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="d35ce-123">En la mayoría de los casos, retransmisión adicional tendría que configurarse y configurado en el entorno.</span><span class="sxs-lookup"><span data-stu-id="d35ce-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="d35ce-124">Aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="d35ce-124">Provision</span></span>
 
<span data-ttu-id="d35ce-125">La clave de inquilino será la llamada de salida para el servicio de socio.</span><span class="sxs-lookup"><span data-stu-id="d35ce-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="d35ce-126">En el ejemplo siguiente, 813878896@t.plcm.vc es la clave de inquilino.</span><span class="sxs-lookup"><span data-stu-id="d35ce-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Ejemplo de clave de inquilino](media/tenant-key-example.png) 

<span data-ttu-id="d35ce-128">Debe ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y también permiten seleccionar usuarios o toda la organización crear reuniones con coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d35ce-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="d35ce-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft proporciona directivas construidas previamente para cada uno de nuestros socios compatibles que le permiten designar que socios a usar para la interoperabilidad de vídeo en la nube.</span><span class="sxs-lookup"><span data-stu-id="d35ce-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="d35ce-130">Este cmdlet permite identificar las directivas construidas previa a la que pueden usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="d35ce-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="d35ce-131">Puede asignar esta directiva a uno o varios de los usuarios aprovecha el cmdlet Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="d35ce-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="d35ce-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* El cmdlet Grant-CsTeamsVideoInteropServicePolicy permite asignar una directiva previamente construida para su uso en la organización o asignar la directiva a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="d35ce-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="d35ce-133">\*\* [Nuevo CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Use el nuevo-CsVideoInteropServiceProvider para especificar la información acerca de un socio CVI compatible la organización le gustaría usar.</span><span class="sxs-lookup"><span data-stu-id="d35ce-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="d35ce-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Utilice el Set-CsVideoInteropServiceProvider para actualizar la información sobre un socio CVI compatible que usa la organización.</span><span class="sxs-lookup"><span data-stu-id="d35ce-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="d35ce-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Obtener todos los proveedores que se han configurado para su uso dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="d35ce-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="d35ce-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Use Remove-CsVideoInteropServiceProvider para quitar toda la información de proveedor de un proveedor que ya no se usa la organización.</span><span class="sxs-lookup"><span data-stu-id="d35ce-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="d35ce-137">Consentimiento</span><span class="sxs-lookup"><span data-stu-id="d35ce-137">Consent</span></span>

<span data-ttu-id="d35ce-138">Debe proporcionar el consentimiento de permiso para los dispositivos de videoconferencias (VTCs) para participar en las reuniones de las organizaciones a través del servicio de socio.</span><span class="sxs-lookup"><span data-stu-id="d35ce-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="d35ce-139">También se proporcionará este vínculo de consentimiento por su socio.</span><span class="sxs-lookup"><span data-stu-id="d35ce-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="d35ce-140">Una vez completados estos pasos, los usuarios que están habilitados de forma individual mediante el cmdlet Grant por encima o todos los usuarios de la organización si está habilitado el inquilino, tendrán coordenadas VTC en todas las reuniones de los equipos programan.</span><span class="sxs-lookup"><span data-stu-id="d35ce-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="d35ce-141">Cualquier VTC puede unirse a estas reuniones a través de esas coordenadas.</span><span class="sxs-lookup"><span data-stu-id="d35ce-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="d35ce-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="d35ce-142">Name</span></span>|<span data-ttu-id="d35ce-143">Breve descripción de permisos de aplicación</span><span class="sxs-lookup"><span data-stu-id="d35ce-143">Application Permission Short Description</span></span>| <span data-ttu-id="d35ce-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="d35ce-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="d35ce-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="d35ce-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="d35ce-146">Unirse a reuniones y llamadas de grupo como una aplicación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="d35ce-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="d35ce-147">Permite que la aplicación para unirse a llamadas de grupo y las reuniones programadas en la organización, sin que el usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="d35ce-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="d35ce-148">La aplicación se van a unir con los privilegios de un usuario de Active directory a las reuniones en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="d35ce-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="d35ce-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="d35ce-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="d35ce-150">Unirse a reuniones y llamadas de grupo como un usuario invitado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="d35ce-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="d35ce-151">Permite que la aplicación de forma anónima unirse a llamadas de grupo y las reuniones programadas en la organización, sin que el usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="d35ce-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="d35ce-152">La aplicación se unirá como invitado a las reuniones en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="d35ce-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="d35ce-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="d35ce-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="d35ce-154">Secuencias de medios de acceso en una llamada como una aplicación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="d35ce-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="d35ce-155">Permite que la aplicación obtener acceso directo a secuencias de medios en una llamada, sin que el usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="d35ce-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="d35ce-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="d35ce-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="d35ce-157">Detalles de la reunión en línea de lectura (vista previa)</span><span class="sxs-lookup"><span data-stu-id="d35ce-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="d35ce-158">Permite que la aplicación leer los detalles de la reunión en línea en la organización, sin que el usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="d35ce-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="d35ce-159">Programación</span><span class="sxs-lookup"><span data-stu-id="d35ce-159">Schedule</span></span>

<span data-ttu-id="d35ce-160">A continuación, programar reuniones de los equipos con las coordenadas de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d35ce-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="d35ce-161">El usuario habilitado puede programar reuniones de los equipos a través de:</span><span class="sxs-lookup"><span data-stu-id="d35ce-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="d35ce-162">Equipos de la reunión complemento para Outlook</span><span class="sxs-lookup"><span data-stu-id="d35ce-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="d35ce-163">Cliente de los equipos móvil y de escritorio</span><span class="sxs-lookup"><span data-stu-id="d35ce-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="d35ce-164">Join</span><span class="sxs-lookup"><span data-stu-id="d35ce-164">Join</span></span>

<span data-ttu-id="d35ce-165">Puede unirse a reuniones de los equipos con los dispositivos VTC de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="d35ce-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="d35ce-166">IVR (respuesta interactiva de voz)</span><span class="sxs-lookup"><span data-stu-id="d35ce-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="d35ce-167">Puede marcar a IVR del socio con la tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="d35ce-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="d35ce-168">Una vez que se encuentra en el socio IVR, se le pedirá que lo especifique el conferenceId VTC, que, a continuación, se conectará a la reunión de los equipos.</span><span class="sxs-lookup"><span data-stu-id="d35ce-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="d35ce-169">Marcado directo</span><span class="sxs-lookup"><span data-stu-id="d35ce-169">Direct dial</span></span>
    - <span data-ttu-id="d35ce-170">Puede marcar directamente a la reunión de los equipos sin necesidad de interacción con IVR del socio mediante la característica de marcado directo con la cadena completa de tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="d35ce-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="d35ce-171">Marcado con un solo toque</span><span class="sxs-lookup"><span data-stu-id="d35ce-171">One-touch dial</span></span>
    - <span data-ttu-id="d35ce-172">Si tiene un salón de equipos integrado, puede usar las capacidades de acceso telefónico con un solo toque ofrecidas por su socio (sin necesidad de escribir cualquier cadena de marcado).</span><span class="sxs-lookup"><span data-stu-id="d35ce-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="d35ce-173">Por último, integrarse con los usuarios de los equipos en las reuniones de uso compartido de audio, vídeo y contenido.</span><span class="sxs-lookup"><span data-stu-id="d35ce-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 
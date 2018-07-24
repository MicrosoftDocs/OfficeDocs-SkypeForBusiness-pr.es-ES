---
title: Configurar un VTC para la interoperación con Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumen: Configure los dispositivos VTC para que funcione con Skype para Business Server.'
ms.openlocfilehash: cc6b8d4fb48a0f43d646d204d399c575af503390
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21017910"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="aa4f9-103">Configurar un VTC para la interoperación con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="aa4f9-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="aa4f9-104">**Resumen:** Configurar los dispositivos VTC para que funcione con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="aa4f9-105">Deberá realizar los procedimientos de personalización de configuración siguientes para cada VTC que se conectará a la Skype para servidor empresarial respecto a través de un tronco SIP y Cisco Unified Communications Manager (CallManager o CUCM) puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="aa4f9-106">La configuración que se describen aquí está diseñada sólo como ejemplos de cómo se puede configurar CUCM para funcionar con un VIS</span><span class="sxs-lookup"><span data-stu-id="aa4f9-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="aa4f9-107">Se puede recurrir a otras configuraciones o a otros usos de funciones de CUCM distintas para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="aa4f9-108">Este documento no tiene que tomarse como una recomendación de configuración óptima para un escenario en particular.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="aa4f9-109">Configurar un VTC registrado con CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="aa4f9-110">Inicie sesión el dispositivo Cisco VTC y vaya a configuración -\>configuración del sistema -\>Provisioning.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="aa4f9-111">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="aa4f9-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="aa4f9-112">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-112">**Parameter**</span></span>|<span data-ttu-id="aa4f9-113">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="aa4f9-114">Modo de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="aa4f9-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="aa4f9-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="aa4f9-116">Dirección del administrador externo</span><span class="sxs-lookup"><span data-stu-id="aa4f9-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="aa4f9-117">FQDN de CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="aa4f9-118">Dominio ExternalManager</span><span class="sxs-lookup"><span data-stu-id="aa4f9-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="aa4f9-119">Dominio del CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="aa4f9-120">Vaya a configuración -\>configuración del sistema -\>red.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="aa4f9-121">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="aa4f9-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="aa4f9-122">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-122">**Parameter**</span></span>|<span data-ttu-id="aa4f9-123">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="aa4f9-124">Nombre de dominio DNS</span><span class="sxs-lookup"><span data-stu-id="aa4f9-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="aa4f9-125">Nombre de dominio de CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="aa4f9-126">Dirección 1 del servidor DNS</span><span class="sxs-lookup"><span data-stu-id="aa4f9-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="aa4f9-127">Su dirección del servidor DNS</span><span class="sxs-lookup"><span data-stu-id="aa4f9-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="aa4f9-128">Vaya a configuración -\>configuración del sistema -\>servicios de red.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="aa4f9-129">Asegúrese de que el modo H.323 está desactivado y de que el modo SIP está activado.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="aa4f9-p103">Estas opciones se establecen automáticamente cuando el extremo se registra con CUCM. Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="aa4f9-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="aa4f9-132">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-132">**Parameter**</span></span>|<span data-ttu-id="aa4f9-133">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="aa4f9-134">Modo H.323</span><span class="sxs-lookup"><span data-stu-id="aa4f9-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="aa4f9-135">Desactivado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-135">Off</span></span> <br/> |
   |<span data-ttu-id="aa4f9-136">Modo HTTP</span><span class="sxs-lookup"><span data-stu-id="aa4f9-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="aa4f9-137">Activado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-137">On</span></span> <br/> |
   | <span data-ttu-id="aa4f9-138">Modo SIP</span><span class="sxs-lookup"><span data-stu-id="aa4f9-138">SIP Mode</span></span> <br/> | <span data-ttu-id="aa4f9-139">Activado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-139">On</span></span> <br/> |
   |<span data-ttu-id="aa4f9-140">Modo Telnet</span><span class="sxs-lookup"><span data-stu-id="aa4f9-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="aa4f9-141">Activado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-141">On</span></span> <br/> |
   |<span data-ttu-id="aa4f9-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="aa4f9-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="aa4f9-143">Activado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-143">On</span></span> <br/> |
   |<span data-ttu-id="aa4f9-144">Modo XMLAPI</span><span class="sxs-lookup"><span data-stu-id="aa4f9-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="aa4f9-145">Activado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-145">On</span></span> <br/> |
   
7. <span data-ttu-id="aa4f9-146">Vaya a configuración -\>configuración del sistema -\>SIP.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="aa4f9-147">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="aa4f9-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="aa4f9-148">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-148">**Parameter**</span></span>|<span data-ttu-id="aa4f9-149">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="aa4f9-150">Perfil 1: DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="aa4f9-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="aa4f9-151">TCP</span><span class="sxs-lookup"><span data-stu-id="aa4f9-151">TCP</span></span> <br/> |
   |<span data-ttu-id="aa4f9-152">Perfil 1: Outbound</span><span class="sxs-lookup"><span data-stu-id="aa4f9-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="aa4f9-153">Desactivado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-153">Off</span></span> <br/> |
   |<span data-ttu-id="aa4f9-154">Perfil 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="aa4f9-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="aa4f9-155">Activado</span><span class="sxs-lookup"><span data-stu-id="aa4f9-155">On</span></span> <br/> |
   |<span data-ttu-id="aa4f9-156">Perfil 1: Type</span><span class="sxs-lookup"><span data-stu-id="aa4f9-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="aa4f9-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="aa4f9-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="aa4f9-158">Perfil 1: URI</span><span class="sxs-lookup"><span data-stu-id="aa4f9-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="aa4f9-159">Asignado automáticamente al registrar CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="aa4f9-160">Proxy 1: Address</span><span class="sxs-lookup"><span data-stu-id="aa4f9-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="aa4f9-161">Nombre de host de CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="aa4f9-p104">El VTC ya está registrado para interoperar. Para iniciar el servicio, necesitará realizar algunos pasos finales en CUCM.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="aa4f9-164">Configurar dispositivos VTC en CUCM</span><span class="sxs-lookup"><span data-stu-id="aa4f9-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="aa4f9-165">Inicie sesión CUCM y vaya a Cisco Unified CM administración -\>dispositivo -\>teléfono -\>buscar.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="aa4f9-p105">Seleccione el dispositivo VTC que quiera configurar. Compruebe las siguientes configuraciones en la pantalla Configuración del teléfono (corrigiendo las que considere necesarias). Tras cambiar o confirmar las configuraciones, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="aa4f9-169">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-169">**Parameter**</span></span>|<span data-ttu-id="aa4f9-170">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="aa4f9-171">Información del dispositivo: plantilla de botón de teléfono</span><span class="sxs-lookup"><span data-stu-id="aa4f9-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="aa4f9-172">Cisco estándar telepresencia códec C40</span><span class="sxs-lookup"><span data-stu-id="aa4f9-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="aa4f9-173">Información del dispositivo: perfil de teléfono común</span><span class="sxs-lookup"><span data-stu-id="aa4f9-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="aa4f9-174">Perfil de teléfono común estándar</span><span class="sxs-lookup"><span data-stu-id="aa4f9-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="aa4f9-175">Información del dispositivo: espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="aa4f9-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="aa4f9-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="aa4f9-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="aa4f9-177">Información del dispositivo: espacio de búsqueda de llamadas AAR</span><span class="sxs-lookup"><span data-stu-id="aa4f9-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="aa4f9-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="aa4f9-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="aa4f9-179">Información del dispositivo: lista del grupo de los recursos del medio</span><span class="sxs-lookup"><span data-stu-id="aa4f9-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="aa4f9-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="aa4f9-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="aa4f9-181">Información específica del protocolo: perfil de seguridad del dispositivo</span><span class="sxs-lookup"><span data-stu-id="aa4f9-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="aa4f9-182">Cisco telepresencia códec C40</span><span class="sxs-lookup"><span data-stu-id="aa4f9-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="aa4f9-183">Información específica del protocolo: espacio de búsqueda de llamadas de reenrutamiento</span><span class="sxs-lookup"><span data-stu-id="aa4f9-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="aa4f9-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="aa4f9-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="aa4f9-185">Información específica de protocolo - SUSCRIBIRSE al llamar a espacio de búsqueda</span><span class="sxs-lookup"><span data-stu-id="aa4f9-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="aa4f9-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="aa4f9-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="aa4f9-187">Información específica del protocolo: perfil SIP</span><span class="sxs-lookup"><span data-stu-id="aa4f9-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="aa4f9-188">Perfil SIP estándar para el extremo de telepresencia</span><span class="sxs-lookup"><span data-stu-id="aa4f9-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="aa4f9-189">Una vez que haya guardado la configuración de VTC, vaya de nuevo a la pantalla de configuración del teléfono para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="aa4f9-190">En la parte superior de la pantalla, en el grupo Asociación, haga clic en la asociación para la interoperabilidad del vídeo.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="aa4f9-191">De este modo se abrirá la pantalla Configuración de número de directorio.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="aa4f9-192">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="aa4f9-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="aa4f9-193">Realice los cambios pertinentes en Información de números de directorio y Configuración de números de directorio como se indica.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="aa4f9-194">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-194">**Parameter**</span></span>|<span data-ttu-id="aa4f9-195">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="aa4f9-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="aa4f9-196">Información de números de directorio: partición de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="aa4f9-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="aa4f9-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="aa4f9-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="aa4f9-198">Configuración de números de directorio: espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="aa4f9-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="aa4f9-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="aa4f9-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="aa4f9-200">Configuración de nivel de acceso confidencial y de parte alternativa de MLPP: espacio de búsqueda de llamadas de MLPP</span><span class="sxs-lookup"><span data-stu-id="aa4f9-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="aa4f9-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="aa4f9-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="aa4f9-202">Línea 1 en dispositivo - para mostrar (identificador de autor de la llamada)</span><span class="sxs-lookup"><span data-stu-id="aa4f9-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="aa4f9-203">Según prefiera</span><span class="sxs-lookup"><span data-stu-id="aa4f9-203">As desired</span></span> <br/> |
   |<span data-ttu-id="aa4f9-204">Línea 1 en dispositivo - ASCII para mostrar (identificador de autor de la llamada)</span><span class="sxs-lookup"><span data-stu-id="aa4f9-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="aa4f9-205">Según prefiera</span><span class="sxs-lookup"><span data-stu-id="aa4f9-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="aa4f9-206">Cuando termine, vaya a la parte superior de la pantalla y presione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="aa4f9-p107">De este modo, habrá completado la configuración de este dispositivo VTC. Este proceso tendrá que repetirse con cada dispositivo VTC de la compañía.</span><span class="sxs-lookup"><span data-stu-id="aa4f9-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>


---
title: Configurar un VTC para la interoperabilidad con Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumen: Configure los dispositivos de VTC para que funcionen con Skype empresarial Server.'
ms.openlocfilehash: 460ac0a301ee9c9b2cb5bb1b4ca4c1aaf6ee4825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302799"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="3619c-103">Configurar un VTC para la interoperabilidad con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3619c-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="3619c-104">**Resumen:** Configure los dispositivos de VTC para que funcionen con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3619c-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="3619c-105">Tendrá que realizar los siguientes procedimientos de personalización de la configuración para cada VTC que se conecte al servidor de Skype empresarial VIS a través de un tronco de SIP y una puerta de enlace de vídeo Cisco Unified Communications Manager (CallManager o CUCM).</span><span class="sxs-lookup"><span data-stu-id="3619c-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="3619c-106">La configuración aquí descrita solo se refería como ejemplos de cómo se puede configurar CUCM para trabajar con VIS.</span><span class="sxs-lookup"><span data-stu-id="3619c-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="3619c-107">Se puede recurrir a otras configuraciones o a otros usos de funciones de CUCM distintas para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="3619c-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="3619c-108">Este documento no tiene que tomarse como una recomendación de configuración óptima para un escenario en particular.</span><span class="sxs-lookup"><span data-stu-id="3619c-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="3619c-109">Configurar un VTC registrado con CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="3619c-110">Inicie sesión en el dispositivo Cisco VTC y vaya a configuración-\>sistema de configuración\>-aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="3619c-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="3619c-111">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="3619c-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="3619c-112">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="3619c-112">**Parameter**</span></span>|<span data-ttu-id="3619c-113">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="3619c-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3619c-114">Modo de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="3619c-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="3619c-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="3619c-116">Dirección del administrador externo</span><span class="sxs-lookup"><span data-stu-id="3619c-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="3619c-117">FQDN de CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="3619c-118">Dominio de ExternalManager</span><span class="sxs-lookup"><span data-stu-id="3619c-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="3619c-119">Dominio de CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="3619c-120">Vaya a configuración:\>configuración del sistema\>-red.</span><span class="sxs-lookup"><span data-stu-id="3619c-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="3619c-121">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="3619c-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="3619c-122">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="3619c-122">**Parameter**</span></span>|<span data-ttu-id="3619c-123">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="3619c-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3619c-124">Nombre de dominio DNS</span><span class="sxs-lookup"><span data-stu-id="3619c-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="3619c-125">Nombre de dominio de CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="3619c-126">Dirección 1 del servidor DNS</span><span class="sxs-lookup"><span data-stu-id="3619c-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="3619c-127">Su dirección del servidor DNS</span><span class="sxs-lookup"><span data-stu-id="3619c-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="3619c-128">Vaya a configuración:\>configuración del sistema\>-servicios de red.</span><span class="sxs-lookup"><span data-stu-id="3619c-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="3619c-129">Asegúrese de que el modo H.323 está desactivado y de que el modo SIP está activado.</span><span class="sxs-lookup"><span data-stu-id="3619c-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="3619c-p103">Estas opciones se establecen automáticamente cuando el extremo se registra con CUCM. Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="3619c-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="3619c-132">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="3619c-132">**Parameter**</span></span>|<span data-ttu-id="3619c-133">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="3619c-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3619c-134">Modo H.323</span><span class="sxs-lookup"><span data-stu-id="3619c-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="3619c-135">Desactivado</span><span class="sxs-lookup"><span data-stu-id="3619c-135">Off</span></span> <br/> |
   |<span data-ttu-id="3619c-136">Modo HTTP</span><span class="sxs-lookup"><span data-stu-id="3619c-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="3619c-137">Activado</span><span class="sxs-lookup"><span data-stu-id="3619c-137">On</span></span> <br/> |
   | <span data-ttu-id="3619c-138">Modo SIP</span><span class="sxs-lookup"><span data-stu-id="3619c-138">SIP Mode</span></span> <br/> | <span data-ttu-id="3619c-139">Activado</span><span class="sxs-lookup"><span data-stu-id="3619c-139">On</span></span> <br/> |
   |<span data-ttu-id="3619c-140">Modo Telnet</span><span class="sxs-lookup"><span data-stu-id="3619c-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="3619c-141">Activado</span><span class="sxs-lookup"><span data-stu-id="3619c-141">On</span></span> <br/> |
   |<span data-ttu-id="3619c-142">Texto de bienvenida</span><span class="sxs-lookup"><span data-stu-id="3619c-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="3619c-143">Activado</span><span class="sxs-lookup"><span data-stu-id="3619c-143">On</span></span> <br/> |
   |<span data-ttu-id="3619c-144">Modo XMLAPI</span><span class="sxs-lookup"><span data-stu-id="3619c-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="3619c-145">Activado</span><span class="sxs-lookup"><span data-stu-id="3619c-145">On</span></span> <br/> |
   
7. <span data-ttu-id="3619c-146">Vaya a configuración:\>configuración del sistema\>-SIP.</span><span class="sxs-lookup"><span data-stu-id="3619c-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="3619c-147">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="3619c-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="3619c-148">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="3619c-148">**Parameter**</span></span>|<span data-ttu-id="3619c-149">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="3619c-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3619c-150">Perfil 1: DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="3619c-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="3619c-151">TCP</span><span class="sxs-lookup"><span data-stu-id="3619c-151">TCP</span></span> <br/> |
   |<span data-ttu-id="3619c-152">Perfil 1: Outbound</span><span class="sxs-lookup"><span data-stu-id="3619c-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="3619c-153">Desactivado</span><span class="sxs-lookup"><span data-stu-id="3619c-153">Off</span></span> <br/> |
   |<span data-ttu-id="3619c-154">Perfil 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="3619c-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="3619c-155">Activado</span><span class="sxs-lookup"><span data-stu-id="3619c-155">On</span></span> <br/> |
   |<span data-ttu-id="3619c-156">Perfil 1: Type</span><span class="sxs-lookup"><span data-stu-id="3619c-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="3619c-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="3619c-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="3619c-158">Perfil 1: URI</span><span class="sxs-lookup"><span data-stu-id="3619c-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="3619c-159">Asignado automáticamente al registrar CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="3619c-160">Proxy 1: Address</span><span class="sxs-lookup"><span data-stu-id="3619c-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="3619c-161">Nombre de host de CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="3619c-p104">El VTC ya está registrado para interoperar. Para iniciar el servicio, necesitará realizar algunos pasos finales en CUCM.</span><span class="sxs-lookup"><span data-stu-id="3619c-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="3619c-164">Configurar dispositivos VTC en CUCM</span><span class="sxs-lookup"><span data-stu-id="3619c-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="3619c-165">Inicie sesión en CUCM y vaya a administración de CM unificada\>de Cisco\>-dispositivo\>-teléfono-buscar.</span><span class="sxs-lookup"><span data-stu-id="3619c-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="3619c-p105">Seleccione el dispositivo VTC que quiera configurar. Compruebe las siguientes configuraciones en la pantalla Configuración del teléfono (corrigiendo las que considere necesarias). Tras cambiar o confirmar las configuraciones, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3619c-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="3619c-169">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="3619c-169">**Parameter**</span></span>|<span data-ttu-id="3619c-170">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="3619c-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3619c-171">Información del dispositivo: plantilla de botón de teléfono</span><span class="sxs-lookup"><span data-stu-id="3619c-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="3619c-172">Códec de telepresencia estándar de C40</span><span class="sxs-lookup"><span data-stu-id="3619c-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="3619c-173">Información del dispositivo: perfil de teléfono común</span><span class="sxs-lookup"><span data-stu-id="3619c-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="3619c-174">Perfil de teléfono común estándar</span><span class="sxs-lookup"><span data-stu-id="3619c-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="3619c-175">Información del dispositivo: espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="3619c-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="3619c-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3619c-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="3619c-177">Información del dispositivo: espacio de búsqueda de llamadas AAR</span><span class="sxs-lookup"><span data-stu-id="3619c-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="3619c-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3619c-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="3619c-179">Información del dispositivo: lista del grupo de los recursos del medio</span><span class="sxs-lookup"><span data-stu-id="3619c-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="3619c-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3619c-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="3619c-181">Información específica del protocolo: perfil de seguridad del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3619c-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="3619c-182">Códec de Telepresencia de Cisco C40</span><span class="sxs-lookup"><span data-stu-id="3619c-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="3619c-183">Información específica del protocolo: espacio de búsqueda de llamadas de reenrutamiento</span><span class="sxs-lookup"><span data-stu-id="3619c-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="3619c-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3619c-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="3619c-185">Información específica de protocolo: SUSCRIBIrse a espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="3619c-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="3619c-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3619c-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="3619c-187">Información específica del protocolo: perfil SIP</span><span class="sxs-lookup"><span data-stu-id="3619c-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="3619c-188">Perfil SIP estándar para el extremo de telepresencia</span><span class="sxs-lookup"><span data-stu-id="3619c-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="3619c-189">Una vez que haya guardado la configuración de VTC, vaya de nuevo a la pantalla de configuración del teléfono para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3619c-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="3619c-190">En la parte superior de la pantalla, en el grupo Asociación, haga clic en la asociación para la interoperabilidad del vídeo.</span><span class="sxs-lookup"><span data-stu-id="3619c-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="3619c-191">De este modo se abrirá la pantalla Configuración de número de directorio.</span><span class="sxs-lookup"><span data-stu-id="3619c-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="3619c-192">Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias):</span><span class="sxs-lookup"><span data-stu-id="3619c-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="3619c-193">Realice los cambios pertinentes en Información de números de directorio y Configuración de números de directorio como se indica.</span><span class="sxs-lookup"><span data-stu-id="3619c-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="3619c-194">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="3619c-194">**Parameter**</span></span>|<span data-ttu-id="3619c-195">**Configuración recomendada**</span><span class="sxs-lookup"><span data-stu-id="3619c-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="3619c-196">Información de números de directorio: partición de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="3619c-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="3619c-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="3619c-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="3619c-198">Configuración de números de directorio: espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="3619c-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="3619c-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3619c-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="3619c-200">Configuración de nivel de acceso confidencial y de parte alternativa de MLPP: espacio de búsqueda de llamadas de MLPP</span><span class="sxs-lookup"><span data-stu-id="3619c-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="3619c-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3619c-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="3619c-202">Línea 1 en el dispositivo: Mostrar (identificación de llamadas)</span><span class="sxs-lookup"><span data-stu-id="3619c-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="3619c-203">Según prefiera</span><span class="sxs-lookup"><span data-stu-id="3619c-203">As desired</span></span> <br/> |
   |<span data-ttu-id="3619c-204">Línea 1 en el dispositivo: pantalla en ASCII (identificación de llamadas)</span><span class="sxs-lookup"><span data-stu-id="3619c-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="3619c-205">Según prefiera</span><span class="sxs-lookup"><span data-stu-id="3619c-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="3619c-206">Cuando termine, vaya a la parte superior de la pantalla y presione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3619c-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="3619c-p107">De este modo, habrá completado la configuración de este dispositivo VTC. Este proceso tendrá que repetirse con cada dispositivo VTC de la compañía.</span><span class="sxs-lookup"><span data-stu-id="3619c-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>


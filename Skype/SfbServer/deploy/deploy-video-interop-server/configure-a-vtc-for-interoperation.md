---
title: Configurar una VTC para interoperación con Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumen: configure los dispositivos VTC para que funcionen con Skype Empresarial Server.'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802080"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="42163-103">Configurar una VTC para interoperación con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="42163-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="42163-104">**Resumen:** Configure los dispositivos VTC para que funcionen con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="42163-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="42163-105">Deberá realizar los siguientes procedimientos de personalización de configuración para cada VTC que se conectará al servidor VIS de Skype Empresarial a través de un tronco SIP y una puerta de enlace de vídeo de Cisco Unified Communications Manager (CallManager o CUCM).</span><span class="sxs-lookup"><span data-stu-id="42163-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="42163-106">Las opciones que se describen aquí están pensadas solo como ejemplos de cómo CUCM se puede configurar para trabajar con un VIS.</span><span class="sxs-lookup"><span data-stu-id="42163-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="42163-107">También se podrían usar otras opciones de configuración o usos de funcionalidades alternativas de CUCM para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="42163-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="42163-108">No se recomienda la configuración óptima para un escenario determinado.</span><span class="sxs-lookup"><span data-stu-id="42163-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="42163-109">Configurar un VTC registrado con CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="42163-110">Inicie sesión en el dispositivo Cisco VTC y vaya a Configuración- \> Configuración del sistema- \> Aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="42163-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="42163-111">Compruebe la siguiente configuración, corrificándose según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="42163-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="42163-112">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="42163-112">**Parameter**</span></span>|<span data-ttu-id="42163-113">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="42163-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="42163-114">Modo de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="42163-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="42163-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="42163-116">ExternalManager Address</span><span class="sxs-lookup"><span data-stu-id="42163-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="42163-117">FQDN de CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="42163-118">Dominio ExternalManager</span><span class="sxs-lookup"><span data-stu-id="42163-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="42163-119">Dominio de CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="42163-120">Vaya a Configuración- \> Configuración del sistema- \> Red.</span><span class="sxs-lookup"><span data-stu-id="42163-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="42163-121">Compruebe la siguiente configuración, corrificándose según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="42163-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="42163-122">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="42163-122">**Parameter**</span></span>|<span data-ttu-id="42163-123">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="42163-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="42163-124">Nombre de dominio DNS</span><span class="sxs-lookup"><span data-stu-id="42163-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="42163-125">Nombre de dominio de CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="42163-126">Dirección del servidor DNS 1</span><span class="sxs-lookup"><span data-stu-id="42163-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="42163-127">la dirección del servidor DNS que desee</span><span class="sxs-lookup"><span data-stu-id="42163-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="42163-128">Vaya a Configuración- \> Configuración del sistema: \> Servicios de red.</span><span class="sxs-lookup"><span data-stu-id="42163-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="42163-129">Asegúrese de que el modo H.323 está desactivado y que el modo SIP está activado.</span><span class="sxs-lookup"><span data-stu-id="42163-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="42163-130">Estas opciones se establecen automáticamente cuando el extremo se registra con CUCM.</span><span class="sxs-lookup"><span data-stu-id="42163-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="42163-131">Compruebe la siguiente configuración, corrificándose según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="42163-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="42163-132">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="42163-132">**Parameter**</span></span>|<span data-ttu-id="42163-133">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="42163-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="42163-134">Modo H.323</span><span class="sxs-lookup"><span data-stu-id="42163-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="42163-135">Desactivado</span><span class="sxs-lookup"><span data-stu-id="42163-135">Off</span></span> <br/> |
   |<span data-ttu-id="42163-136">Modo HTTP</span><span class="sxs-lookup"><span data-stu-id="42163-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="42163-137">Activado</span><span class="sxs-lookup"><span data-stu-id="42163-137">On</span></span> <br/> |
   | <span data-ttu-id="42163-138">Modo SIP</span><span class="sxs-lookup"><span data-stu-id="42163-138">SIP Mode</span></span> <br/> | <span data-ttu-id="42163-139">Activado</span><span class="sxs-lookup"><span data-stu-id="42163-139">On</span></span> <br/> |
   |<span data-ttu-id="42163-140">Modo Telnet</span><span class="sxs-lookup"><span data-stu-id="42163-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="42163-141">Activado</span><span class="sxs-lookup"><span data-stu-id="42163-141">On</span></span> <br/> |
   |<span data-ttu-id="42163-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="42163-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="42163-143">Activado</span><span class="sxs-lookup"><span data-stu-id="42163-143">On</span></span> <br/> |
   |<span data-ttu-id="42163-144">Modo XMLAPI</span><span class="sxs-lookup"><span data-stu-id="42163-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="42163-145">Activado</span><span class="sxs-lookup"><span data-stu-id="42163-145">On</span></span> <br/> |
   
7. <span data-ttu-id="42163-146">Vaya a Configuración- \> Configuración del sistema- \> SIP.</span><span class="sxs-lookup"><span data-stu-id="42163-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="42163-147">Compruebe la siguiente configuración, corrificándose según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="42163-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="42163-148">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="42163-148">**Parameter**</span></span>|<span data-ttu-id="42163-149">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="42163-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="42163-150">Perfil 1: DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="42163-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="42163-151">TCP</span><span class="sxs-lookup"><span data-stu-id="42163-151">TCP</span></span> <br/> |
   |<span data-ttu-id="42163-152">Perfil 1: saliente</span><span class="sxs-lookup"><span data-stu-id="42163-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="42163-153">Desactivado</span><span class="sxs-lookup"><span data-stu-id="42163-153">Off</span></span> <br/> |
   |<span data-ttu-id="42163-154">Perfil 1: TlsVerify</span><span class="sxs-lookup"><span data-stu-id="42163-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="42163-155">Activado</span><span class="sxs-lookup"><span data-stu-id="42163-155">On</span></span> <br/> |
   |<span data-ttu-id="42163-156">Perfil 1: tipo</span><span class="sxs-lookup"><span data-stu-id="42163-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="42163-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="42163-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="42163-158">Perfil 1: URI</span><span class="sxs-lookup"><span data-stu-id="42163-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="42163-159">Asignado automáticamente en el registro de CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="42163-160">Proxy 1: dirección</span><span class="sxs-lookup"><span data-stu-id="42163-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="42163-161">El nombre de host de CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="42163-162">Los VTC ya están configurados para interoperación.</span><span class="sxs-lookup"><span data-stu-id="42163-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="42163-163">Antes de que el servicio pueda comenzar, hay pasos finales para realizar en CUCM.</span><span class="sxs-lookup"><span data-stu-id="42163-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="42163-164">Configurar dispositivos VTC en CUCM</span><span class="sxs-lookup"><span data-stu-id="42163-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="42163-165">Inicie sesión en CUCM y vaya a Administración de Cisco Unified CM- \> \> Dispositivo- Teléfono- \> Buscar.</span><span class="sxs-lookup"><span data-stu-id="42163-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="42163-166">Selecciona el dispositivo VTC que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="42163-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="42163-167">Compruebe la siguiente configuración en la pantalla Configuración del teléfono, corrificándose según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="42163-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="42163-168">Una vez que se hayan cambiado o comprobado estas opciones de configuración, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="42163-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="42163-169">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="42163-169">**Parameter**</span></span>|<span data-ttu-id="42163-170">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="42163-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="42163-171">Información del dispositivo: plantilla de botón Teléfono</span><span class="sxs-lookup"><span data-stu-id="42163-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="42163-172">Standard Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="42163-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="42163-173">Información del dispositivo: perfil de teléfono común</span><span class="sxs-lookup"><span data-stu-id="42163-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="42163-174">Perfil de teléfono común estándar</span><span class="sxs-lookup"><span data-stu-id="42163-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="42163-175">Información del dispositivo: espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="42163-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="42163-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="42163-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="42163-177">Información del dispositivo: espacio de búsqueda de llamadas de AAR</span><span class="sxs-lookup"><span data-stu-id="42163-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="42163-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="42163-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="42163-179">Información del dispositivo: lista de grupos de recursos multimedia</span><span class="sxs-lookup"><span data-stu-id="42163-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="42163-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="42163-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="42163-181">Información específica del protocolo: perfil de seguridad del dispositivo</span><span class="sxs-lookup"><span data-stu-id="42163-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="42163-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="42163-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="42163-183">Información específica del protocolo: volver a enrear el espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="42163-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="42163-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="42163-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="42163-185">Información específica del protocolo: espacio de búsqueda de llamadas SUBSCRIBE</span><span class="sxs-lookup"><span data-stu-id="42163-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="42163-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="42163-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="42163-187">Información específica del protocolo -Perfil SIP</span><span class="sxs-lookup"><span data-stu-id="42163-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="42163-188">Perfil SIP estándar para el extremo de telepresencia</span><span class="sxs-lookup"><span data-stu-id="42163-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="42163-189">Una vez guardada la configuración de VTC, vuelve a navegar a la pantalla Configuración del teléfono del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42163-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="42163-190">En la parte superior de la pantalla del grupo Asociación, haga clic en la asociación para la interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="42163-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="42163-191">Se abre la pantalla Configuración de números de directorio.</span><span class="sxs-lookup"><span data-stu-id="42163-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="42163-192">Compruebe la siguiente configuración, corrificándose según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="42163-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="42163-193">Realice los cambios adecuados como se muestra en la información de número de directorio y la configuración de número de directorio.</span><span class="sxs-lookup"><span data-stu-id="42163-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="42163-194">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="42163-194">**Parameter**</span></span>|<span data-ttu-id="42163-195">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="42163-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="42163-196">Información del número de directorio: partición de ruta</span><span class="sxs-lookup"><span data-stu-id="42163-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="42163-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="42163-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="42163-198">Configuración del número de directorio: espacio de búsqueda de llamadas</span><span class="sxs-lookup"><span data-stu-id="42163-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="42163-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="42163-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="42163-200">Configuración de nivel de acceso confidencial y de parte alternativa de MLPP: espacio de búsqueda de llamadas de MLPP</span><span class="sxs-lookup"><span data-stu-id="42163-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="42163-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="42163-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="42163-202">Línea 1 en el dispositivo: pantalla (identificador de llamada)</span><span class="sxs-lookup"><span data-stu-id="42163-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="42163-203">Según lo desee</span><span class="sxs-lookup"><span data-stu-id="42163-203">As desired</span></span> <br/> |
   |<span data-ttu-id="42163-204">Línea 1 en el dispositivo - Pantalla ASCII (identificador de llamada)</span><span class="sxs-lookup"><span data-stu-id="42163-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="42163-205">Según lo desee</span><span class="sxs-lookup"><span data-stu-id="42163-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="42163-206">Cuando haya terminado, desplácese hasta la parte superior de la pantalla y presione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="42163-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="42163-207">La configuración ya está completa para este dispositivo VTC.</span><span class="sxs-lookup"><span data-stu-id="42163-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="42163-208">Tendrá que repetir este proceso para otros dispositivos VTC de su empresa.</span><span class="sxs-lookup"><span data-stu-id="42163-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>


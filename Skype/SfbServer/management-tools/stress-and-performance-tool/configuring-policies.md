---
title: Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815040"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="3ba40-103">Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ba40-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="3ba40-104">Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3ba40-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="3ba40-105">Hay varias directivas y otras áreas que puede configurar en Skype Empresarial Server 2015, antes de ejecutar la Herramienta de esfuerzo y rendimiento:</span><span class="sxs-lookup"><span data-stu-id="3ba40-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="3ba40-106">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="3ba40-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="3ba40-107">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="3ba40-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="3ba40-108">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="3ba40-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="3ba40-109">Directiva de federación</span><span class="sxs-lookup"><span data-stu-id="3ba40-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="3ba40-110">Directiva de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="3ba40-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="3ba40-111">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="3ba40-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="3ba40-112">Aplicación Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="3ba40-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="3ba40-113">Servicio de estacionamiento de llamadas de servidor</span><span class="sxs-lookup"><span data-stu-id="3ba40-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="3ba40-114">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="3ba40-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="3ba40-115">Configuración de la aplicación grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="3ba40-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="3ba40-116">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="3ba40-116">Archiving policy</span></span>
<span data-ttu-id="3ba40-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="3ba40-118">Si tiene un servidor de archivado implementado en la topología de Skype Empresarial Server, puede ver el script ArchivingPolicy.ps1 cliente.</span><span class="sxs-lookup"><span data-stu-id="3ba40-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="3ba40-119">Si necesita más ayuda, consulte los cmdlets de archivado y conferencia web.</span><span class="sxs-lookup"><span data-stu-id="3ba40-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="3ba40-120">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="3ba40-120">Conferencing policy</span></span>
<span data-ttu-id="3ba40-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="3ba40-122">Para las conferencias, tenemos el script MeetingPolicy.ps1 conferencia.</span><span class="sxs-lookup"><span data-stu-id="3ba40-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="3ba40-123">Si necesita más ayuda, consulte los cmdlets de conferencia web.</span><span class="sxs-lookup"><span data-stu-id="3ba40-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="3ba40-124">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="3ba40-124">Contacts policy</span></span>
<span data-ttu-id="3ba40-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="3ba40-126">ContactsPolicy.ps1 script será el ejemplo que tendrás que revisar.</span><span class="sxs-lookup"><span data-stu-id="3ba40-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="3ba40-127">Los cmdlets de mensajería instantánea y presencia le ayudarán si necesita más referencias.</span><span class="sxs-lookup"><span data-stu-id="3ba40-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="3ba40-128">Directiva de federación</span><span class="sxs-lookup"><span data-stu-id="3ba40-128">Federation policy</span></span>
<span data-ttu-id="3ba40-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="3ba40-130">El script de ejemplo para federación es FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="3ba40-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="3ba40-131">Los cmdlets que se revisarán, si necesita más información, serán el servidor perimetral, la federación y el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="3ba40-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="3ba40-132">Directiva de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="3ba40-132">Call Admission Control policy</span></span>
<span data-ttu-id="3ba40-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="3ba40-134">Puede hacer referencia a BandwidthPolicy.ps1 para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3ba40-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="3ba40-135">Los cmdlets de control de admisión de llamadas también tendrán más información.</span><span class="sxs-lookup"><span data-stu-id="3ba40-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="3ba40-136">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="3ba40-136">Voice Routing rules</span></span>
<span data-ttu-id="3ba40-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="3ba40-138">Necesitará el script de ejemplo RoutingRules.ps1 para el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="3ba40-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="3ba40-139">Al configurar estas reglas, tome nota del contexto del teléfono (es decir, /Perfil de ubicación o /SimpleName) y códigos de área interno/externo, para que pueda especificarlas al crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="3ba40-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="3ba40-140">También los necesitará durante la configuración de LyncPerfTool (específicamente para RTC-UC y UC-RTC).</span><span class="sxs-lookup"><span data-stu-id="3ba40-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="3ba40-141">Por ejemplo, el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo RoutingRules.ps1 debe usarse para el valor LocationProfile en la siguiente figura de UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="3ba40-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Herramienta de configuración de carga de Skype Empresarial, pestaña Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="3ba40-143">Para obtener más información, puede revisar los Telefonía IP empresarial cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3ba40-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="3ba40-144">Aplicación Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="3ba40-144">Conference Attendant application</span></span>
<span data-ttu-id="3ba40-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="3ba40-146">En primer lugar, revise ConferenceAutoAttendantConfiguration.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="3ba40-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="3ba40-147">Necesitará tener en cuenta el número de teléfono ConferencingAutoAttendant (11211111111111 de forma predeterminada), de modo que pueda escribirlo en la herramienta de configuración LyncPerfTool para la generación de configuración, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3ba40-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![La pestaña Escenarios de voz que muestra el nivel de carga de conferencia y el número de teléfono.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="3ba40-149">Encontrará más detalles en los cmdlets de conferencia y conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="3ba40-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="3ba40-150">Servicio de estacionamiento de llamadas de servidor</span><span class="sxs-lookup"><span data-stu-id="3ba40-150">Server Call Park service</span></span>
<span data-ttu-id="3ba40-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="3ba40-152">En realidad, está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3ba40-152">This is actually disabled by default.</span></span> <span data-ttu-id="3ba40-153">Puede revisar el script CallParkConfiguration.ps1 ejemplo si necesita probarlo.</span><span class="sxs-lookup"><span data-stu-id="3ba40-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="3ba40-154">Además, consulte los cmdlets de aplicación de estacionamiento de llamadas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3ba40-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="3ba40-155">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="3ba40-155">Emergency calls</span></span>
<span data-ttu-id="3ba40-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="3ba40-157">Deberá realizar los siguientes pasos para configurar las pruebas de esfuerzo y rendimiento para llamadas de emergencia:</span><span class="sxs-lookup"><span data-stu-id="3ba40-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="3ba40-158">Configurar una ruta de voz para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="3ba40-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="3ba40-159">Puede usar el script RoutingRules.ps1 y consultar el comentario **"Ruta E911** a RTC" para ver un ejemplo de cómo configurar esta ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="3ba40-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3ba40-160">El comando de ejemplo RoutingRules.ps1 tiene un patrón de número que incluye el número 119 en lugar del 911.</span><span class="sxs-lookup"><span data-stu-id="3ba40-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="3ba40-161">Debe evitar el uso del 911 (o su número de emergencia local real) para evitar llamadas accidentales a los operadores de emergencia locales durante las pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="3ba40-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="3ba40-162">Recuerde que esta configuración es solo para fines de simulación.</span><span class="sxs-lookup"><span data-stu-id="3ba40-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="3ba40-163">Configure las direcciones rellenando  los valores de la pestaña Configuración del servicio de información de ubicación en UserProvisioningTool, como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ba40-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Herramienta de aprovisionamiento de usuarios que muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="3ba40-165">Cuando haya escrito todo en UserProvisioningTool, haga clic en el botón Generar archivos **de configuración LIS.**</span><span class="sxs-lookup"><span data-stu-id="3ba40-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="3ba40-166">Ahora se generarán archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="3ba40-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="3ba40-167">Puede usar los archivos CSV para las entradas al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration.ps1 ubicación.</span><span class="sxs-lookup"><span data-stu-id="3ba40-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="3ba40-168">Para ello, tendrás que mover el archivo Locations0.xml a la misma carpeta que el ejecutable de la Herramienta de esfuerzo y rendimiento (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="3ba40-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="3ba40-169">Esto le permitirá ejecutar escenarios de perfil de ubicación (plan de marcado).</span><span class="sxs-lookup"><span data-stu-id="3ba40-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="3ba40-170">Configuración de la aplicación grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="3ba40-170">Configuring Response Group application</span></span>
<span data-ttu-id="3ba40-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="3ba40-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="3ba40-172">El script de ejemplo es ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="3ba40-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="3ba40-173">También hay cmdlets de aplicación de Grupo de respuesta para consultar más detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="3ba40-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="3ba40-174">En el siguiente diagrama se mostrarán algunos de los detalles de configuración:</span><span class="sxs-lookup"><span data-stu-id="3ba40-174">The following diagram will show some of the configuration details:</span></span>
  
![La herramienta de configuración de grupo de respuesta que muestra los flujos de trabajo existentes para realizar pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  


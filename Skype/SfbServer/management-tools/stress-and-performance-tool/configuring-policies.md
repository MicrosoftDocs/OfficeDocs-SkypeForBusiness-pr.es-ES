---
title: Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015.
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816199"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="0af1c-103">Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0af1c-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="0af1c-104">Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0af1c-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="0af1c-105">Hay varias directivas y otras áreas que puede configurar en Skype empresarial Server 2015, antes de ejecutar la herramienta estrés and Performance:</span><span class="sxs-lookup"><span data-stu-id="0af1c-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="0af1c-106">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="0af1c-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="0af1c-107">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="0af1c-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="0af1c-108">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="0af1c-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="0af1c-109">Directiva de Federación</span><span class="sxs-lookup"><span data-stu-id="0af1c-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="0af1c-110">Directiva de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="0af1c-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="0af1c-111">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="0af1c-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="0af1c-112">Aplicación de operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="0af1c-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="0af1c-113">Servicio de estacionamiento de llamadas de servidor</span><span class="sxs-lookup"><span data-stu-id="0af1c-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="0af1c-114">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="0af1c-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="0af1c-115">Configuración de la aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="0af1c-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="0af1c-116">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="0af1c-116">Archiving policy</span></span>
<span data-ttu-id="0af1c-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="0af1c-118">Si tiene un servidor de archivado implementado en su topología de servidor de Skype empresarial, puede consultar el script ArchivingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="0af1c-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="0af1c-119">Si necesita más ayuda, consulte los cmdlets de archivado y conferencias web.</span><span class="sxs-lookup"><span data-stu-id="0af1c-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="0af1c-120">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="0af1c-120">Conferencing policy</span></span>
<span data-ttu-id="0af1c-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="0af1c-122">Para las conferencias, tenemos el script MeetingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="0af1c-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="0af1c-123">Si necesita más ayuda, consulte los cmdlets de conferencias web.</span><span class="sxs-lookup"><span data-stu-id="0af1c-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="0af1c-124">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="0af1c-124">Contacts policy</span></span>
<span data-ttu-id="0af1c-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="0af1c-126">El script ContactsPolicy. PS1 será el ejemplo que necesitarás revisar.</span><span class="sxs-lookup"><span data-stu-id="0af1c-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="0af1c-127">Los cmdlets de presencia y mensajería instantánea le ayudarán si necesita más referencias.</span><span class="sxs-lookup"><span data-stu-id="0af1c-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="0af1c-128">Directiva de Federación</span><span class="sxs-lookup"><span data-stu-id="0af1c-128">Federation policy</span></span>
<span data-ttu-id="0af1c-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="0af1c-130">El script de ejemplo para la Federación es FederationPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="0af1c-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="0af1c-131">Los cmdlets para revisar, si necesita más información, serán servidor perimetral, Federación y acceso externo.</span><span class="sxs-lookup"><span data-stu-id="0af1c-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="0af1c-132">Directiva de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="0af1c-132">Call Admission Control policy</span></span>
<span data-ttu-id="0af1c-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="0af1c-134">Puede hacer referencia a BandwidthPolicy. PS1 para esta Directiva.</span><span class="sxs-lookup"><span data-stu-id="0af1c-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="0af1c-135">Los cmdlets de control de admisión de llamadas también tendrán más información.</span><span class="sxs-lookup"><span data-stu-id="0af1c-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="0af1c-136">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="0af1c-136">Voice Routing rules</span></span>
<span data-ttu-id="0af1c-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="0af1c-138">Necesitarás el script de ejemplo RoutingRules. PS1 para el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="0af1c-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="0af1c-139">Cuando configure estas reglas, tome nota del contexto de teléfono (es decir, perfil de/Location o/SimpleName) y códigos de área interna y externa para poder especificarlos al crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="0af1c-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="0af1c-140">También los necesitará durante la configuración de LyncPerfTool (específicamente para PSTN-UC y UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="0af1c-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="0af1c-141">Por ejemplo, el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo de RoutingRules. PS1 debe usarse para el valor LocationProfile de la siguiente ilustración de UserProfileGenerator. exe:</span><span class="sxs-lookup"><span data-stu-id="0af1c-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Herramienta de configuración de carga de Skype Empresarial, ficha Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="0af1c-143">Para obtener información detallada, puede revisar los cmdlets de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="0af1c-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="0af1c-144">Aplicación de operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="0af1c-144">Conference Attendant application</span></span>
<span data-ttu-id="0af1c-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="0af1c-146">Primero revise el script ConferenceAutoAttendantConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="0af1c-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="0af1c-147">Querrá tomar nota del número de teléfono ConferencingAutoAttendant (1121111111 de forma predeterminada), de modo que pueda introducirlo en la herramienta de configuración de LyncPerfTool para la generación de configuración, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0af1c-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Pestaña Escenarios de voz donde se muestra el número de teléfono y el nivel de Carga de conferencia.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="0af1c-149">Encontrará más información en los cmdlets conferencias y conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="0af1c-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="0af1c-150">Servicio de estacionamiento de llamadas de servidor</span><span class="sxs-lookup"><span data-stu-id="0af1c-150">Server Call Park service</span></span>
<span data-ttu-id="0af1c-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="0af1c-152">En realidad, esto está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0af1c-152">This is actually disabled by default.</span></span> <span data-ttu-id="0af1c-153">Puede revisar el script de ejemplo CallParkConfiguration. PS1 si necesita probarlo.</span><span class="sxs-lookup"><span data-stu-id="0af1c-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="0af1c-154">Además, consulte los cmdlets de la aplicación Parque de llamadas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0af1c-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="0af1c-155">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="0af1c-155">Emergency calls</span></span>
<span data-ttu-id="0af1c-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="0af1c-157">Para configurar las pruebas de estrés y rendimiento para llamadas de emergencia, tendrá que realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0af1c-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="0af1c-158">Configura una ruta de voz para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="0af1c-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="0af1c-159">Puede usar el script RoutingRules. PS1 y comprobar en el comentario " **Route E911 to RTC** " para obtener un ejemplo de cómo configurar esta ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="0af1c-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0af1c-160">El comando de ejemplo en RoutingRules. PS1 tiene un patrón de números que incluye el número 119 en lugar de 911.</span><span class="sxs-lookup"><span data-stu-id="0af1c-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="0af1c-161">Debes evitar usar 911 (o tu número de emergencia local) para evitar llamadas accidentales a tus operadores de emergencia locales durante las pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="0af1c-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="0af1c-162">Recuerde que esta configuración solo es para fines de simulación.</span><span class="sxs-lookup"><span data-stu-id="0af1c-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="0af1c-163">Configure las direcciones rellenando los valores de la pestaña **Ubicación información de configuración del servicio** en la UserProvisioningTool, como se muestra en la siguiente ilustración:</span><span class="sxs-lookup"><span data-stu-id="0af1c-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Herramienta Aprovisionamiento de usuarios donde se muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="0af1c-165">Cuando haya escrito todo en la UserProvisioningTool, haga clic en el botón **generar archivos de configuración Lis** .</span><span class="sxs-lookup"><span data-stu-id="0af1c-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="0af1c-166">Ahora se generarán los archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta de carga y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0af1c-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="0af1c-167">Puede usar los archivos CSV para entradas al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="0af1c-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="0af1c-168">Para ello, tendrá que mover el archivo Locations0. XML a la misma carpeta que el ejecutable de la herramienta de carga y rendimiento (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="0af1c-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="0af1c-169">Esto le permitirá ejecutar escenarios de Perfil de ubicación (plan de marcado).</span><span class="sxs-lookup"><span data-stu-id="0af1c-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="0af1c-170">Configuración de la aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="0af1c-170">Configuring Response Group application</span></span>
<span data-ttu-id="0af1c-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="0af1c-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="0af1c-172">El script de ejemplo es ResponseGroupConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="0af1c-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="0af1c-173">También hay cmdlets de aplicación de grupo de respuesta para revisar para obtener más información sobre la configuración.</span><span class="sxs-lookup"><span data-stu-id="0af1c-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="0af1c-174">En el diagrama siguiente se mostrarán algunos de los detalles de configuración:</span><span class="sxs-lookup"><span data-stu-id="0af1c-174">The following diagram will show some of the configuration details:</span></span>
  
![Herramienta de configuración de grupo de respuesta donde se muestran los flujos de trabajo existentes para pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  


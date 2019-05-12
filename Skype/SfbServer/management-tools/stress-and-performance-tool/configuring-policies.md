---
title: Configuración de directivas para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuración de directiva de Skype para Business Server 2015 herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: 330be860d4d18eb06c4c64ac225ed621ea712767
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906602"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ad443-103">Configuración de directivas para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="ad443-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ad443-104">Configuración de directiva de Skype para Business Server 2015 herramienta de esfuerzo y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad443-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ad443-105">Existen varias directivas y otras áreas que puede configurar en Skype para Business Server 2015, antes de ejecutar la herramienta de rendimiento y esfuerzo:</span><span class="sxs-lookup"><span data-stu-id="ad443-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="ad443-106">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="ad443-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="ad443-107">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="ad443-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="ad443-108">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="ad443-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="ad443-109">Directiva de federación</span><span class="sxs-lookup"><span data-stu-id="ad443-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="ad443-110">Directiva de Control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="ad443-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="ad443-111">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="ad443-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="ad443-112">Aplicación de operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="ad443-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="ad443-113">Servicio de estacionamiento de llamadas de servidor</span><span class="sxs-lookup"><span data-stu-id="ad443-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="ad443-114">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="ad443-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="ad443-115">Aplicación de configuración de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="ad443-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="ad443-116">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="ad443-116">Archiving policy</span></span>
<span data-ttu-id="ad443-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-117"></span></span>

<span data-ttu-id="ad443-118">Si tiene un servidor de archivado implementado en su Skype para la topología de servidor empresarial, puede buscar en la secuencia de comandos ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad443-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="ad443-119">Si necesita más ayuda, desproteger los cmdlets de archivado y conferencias Web.</span><span class="sxs-lookup"><span data-stu-id="ad443-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="ad443-120">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="ad443-120">Conferencing policy</span></span>
<span data-ttu-id="ad443-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-121"></span></span>

<span data-ttu-id="ad443-122">Para las conferencias, tenemos el script MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad443-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="ad443-123">Si necesita más ayuda, desproteger los cmdlets de conferencias Web.</span><span class="sxs-lookup"><span data-stu-id="ad443-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="ad443-124">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="ad443-124">Contacts policy</span></span>
<span data-ttu-id="ad443-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-125"></span></span>

<span data-ttu-id="ad443-126">Secuencia de comandos de ContactsPolicy.ps1 será el ejemplo que necesitará para revisar.</span><span class="sxs-lookup"><span data-stu-id="ad443-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="ad443-127">Los cmdlets de mensajería instantánea y presencia le ayudará a si necesita más referencias.</span><span class="sxs-lookup"><span data-stu-id="ad443-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="ad443-128">Directiva de federación</span><span class="sxs-lookup"><span data-stu-id="ad443-128">Federation policy</span></span>
<span data-ttu-id="ad443-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-129"></span></span>

<span data-ttu-id="ad443-130">El script de ejemplo para la federación es FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad443-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="ad443-131">Los cmdlets para revisar, si necesita más insight, será el servidor perimetral, la federación y el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="ad443-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="ad443-132">Directiva de Control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="ad443-132">Call Admission Control policy</span></span>
<span data-ttu-id="ad443-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-133"></span></span>

<span data-ttu-id="ad443-134">Puede hacer referencia a BandwidthPolicy.ps1 para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="ad443-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="ad443-135">Los cmdlets de Control de admisión de llamadas tendrá más información así como.</span><span class="sxs-lookup"><span data-stu-id="ad443-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="ad443-136">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="ad443-136">Voice Routing rules</span></span>
<span data-ttu-id="ad443-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-137"></span></span>

<span data-ttu-id="ad443-138">Necesitará el script de ejemplo RoutingRules.ps1 para el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="ad443-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="ad443-139">Cuando está configurando estas reglas, tome nota del contexto de teléfono (es decir, /Location perfil o /SimpleName) y códigos de área internas y externas, por lo que puede especificar al crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="ad443-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="ad443-140">También necesitará ellos durante la configuración de LyncPerfTool (específicamente para UC de RTC y UC-RTC).</span><span class="sxs-lookup"><span data-stu-id="ad443-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="ad443-141">Por ejemplo, se debe usar el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo de RoutingRules.ps1 para el valor de LocationProfile en la siguiente ilustración de UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="ad443-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Herramienta de configuración de carga de Skype Empresarial, ficha Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="ad443-143">Para obtener información detallada, puede revisar los cmdlets de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ad443-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="ad443-144">Aplicación de operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="ad443-144">Conference Attendant application</span></span>
<span data-ttu-id="ad443-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-145"></span></span>

<span data-ttu-id="ad443-146">En primer lugar, revise la secuencia de comandos ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad443-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="ad443-147">Desea tome nota del número de teléfono de ConferencingAutoAttendant (1121111111 de forma predeterminada), para que pueda escribir en la herramienta de configuración de LyncPerfTool para la generación de la configuración, como sigue:</span><span class="sxs-lookup"><span data-stu-id="ad443-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Pestaña Escenarios de voz donde se muestra el número de teléfono y el nivel de Carga de conferencia.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="ad443-149">Encontrará más detalles en la conferencia y conferencia de acceso telefónico cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ad443-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="ad443-150">Servicio de estacionamiento de llamadas de servidor</span><span class="sxs-lookup"><span data-stu-id="ad443-150">Server Call Park service</span></span>
<span data-ttu-id="ad443-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-151"></span></span>

<span data-ttu-id="ad443-152">Esto realmente está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad443-152">This is actually disabled by default.</span></span> <span data-ttu-id="ad443-153">Puede revisar el script de ejemplo CallParkConfiguration.ps1 si necesita probar esto.</span><span class="sxs-lookup"><span data-stu-id="ad443-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="ad443-154">Además, desproteger los cmdlets de aplicación de estacionamiento de llamadas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ad443-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="ad443-155">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="ad443-155">Emergency calls</span></span>
<span data-ttu-id="ad443-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-156"></span></span>

<span data-ttu-id="ad443-157">Debe realizar los siguientes pasos para configurar de esfuerzo y pruebas de rendimiento para las llamadas de emergencia:</span><span class="sxs-lookup"><span data-stu-id="ad443-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="ad443-158">Configurar una ruta de voz para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ad443-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="ad443-159">Puede utilizar la secuencia de comandos RoutingRules.ps1 y comprobar bajo el comentario " **Ruta E911 a RTC** " para obtener un ejemplo de cómo configurar la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="ad443-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ad443-160">El comando de ejemplo en RoutingRules.ps1 tiene un patrón de número que incluye la cantidad 119 en lugar de 911.</span><span class="sxs-lookup"><span data-stu-id="ad443-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="ad443-161">Se debe evitar usar 911 (o su número de emergencia local real) para evitar que las llamadas accidentales a los operadores de emergencias locales durante las pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="ad443-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="ad443-162">Recuerde, esta configuración es únicamente con fines de simulación!</span><span class="sxs-lookup"><span data-stu-id="ad443-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="ad443-163">Configure las direcciones rellenar los valores en la ficha **Configuración del servicio de información de ubicación** en la UserProvisioningTool, tal como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad443-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Herramienta Aprovisionamiento de usuarios donde se muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="ad443-165">Cuando todo lo que ha especificado en el UserProvisioningTool, haga clic en el botón **Generar archivos de configuración de LIS** .</span><span class="sxs-lookup"><span data-stu-id="ad443-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="ad443-166">Ahora se generará archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta de esfuerzo y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad443-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="ad443-167">Puede usar los archivos CSV para entradas al configurar el servicio de información de ubicación (LIS) con la secuencia de comandos LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad443-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="ad443-168">Para ello, debe mover el archivo Locations0.xml a la misma carpeta que la herramienta Stress and Performance ejecutable (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="ad443-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="ad443-169">Esto le permitirá ejecutar escenarios (plan de marcado) de perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="ad443-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="ad443-170">Aplicación de configuración de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="ad443-170">Configuring Response Group application</span></span>
<span data-ttu-id="ad443-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="ad443-171"></span></span>

<span data-ttu-id="ad443-172">El script de ejemplo es ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad443-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="ad443-173">También hay cmdlets de aplicación de grupo de respuesta para revisar para obtener más información de configuración.</span><span class="sxs-lookup"><span data-stu-id="ad443-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="ad443-174">En el siguiente diagrama se muestra algunos de los detalles de configuración:</span><span class="sxs-lookup"><span data-stu-id="ad443-174">The following diagram will show some of the configuration details:</span></span>
  
![Herramienta de configuración de grupo de respuesta donde se muestran los flujos de trabajo existentes para pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  


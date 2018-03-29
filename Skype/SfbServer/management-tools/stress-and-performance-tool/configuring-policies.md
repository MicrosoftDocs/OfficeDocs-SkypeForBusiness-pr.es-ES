---
title: Configuración de directivas para el Skype para Business Server 2015 Stress y la herramienta de rendimiento
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuración de directiva de Skype para Business Server 2015 Stress y la herramienta de rendimiento.
ms.openlocfilehash: 5bdeb4c65b3649e7d417550578e277e01e55fcc3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="64d89-103">Configuración de directivas para el Skype para Business Server 2015 Stress y la herramienta de rendimiento</span><span class="sxs-lookup"><span data-stu-id="64d89-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="64d89-104">Configuración de directiva de Skype para Business Server 2015 Stress y la herramienta de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="64d89-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="64d89-105">Existen varias directivas y otras áreas que se pueden configurar en Skype Business Server 2015, antes de ejecutar la herramienta de rendimiento y esfuerzo:</span><span class="sxs-lookup"><span data-stu-id="64d89-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="64d89-106">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="64d89-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="64d89-107">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="64d89-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="64d89-108">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="64d89-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="64d89-109">Directiva de federación</span><span class="sxs-lookup"><span data-stu-id="64d89-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="64d89-110">Llamar a la directiva de Control de admisión</span><span class="sxs-lookup"><span data-stu-id="64d89-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="64d89-111">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="64d89-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="64d89-112">Solicitud de operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="64d89-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="64d89-113">Servicio de servidor llamada Park</span><span class="sxs-lookup"><span data-stu-id="64d89-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="64d89-114">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="64d89-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="64d89-115">Aplicación de configuración de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="64d89-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="64d89-116">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="64d89-116">Archiving policy</span></span>
<span data-ttu-id="64d89-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-117"></span></span>

<span data-ttu-id="64d89-118">Si tiene un servidor de archivado implementado en su Skype para la topología de servidores de negocios, puede mirar la secuencia de comandos ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d89-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="64d89-119">Si necesita asistencia adicional, consulte los cmdlets archivado y conferencias Web.</span><span class="sxs-lookup"><span data-stu-id="64d89-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="64d89-120">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="64d89-120">Conferencing policy</span></span>
<span data-ttu-id="64d89-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-121"></span></span>

<span data-ttu-id="64d89-122">Para conferencias, tenemos la secuencia de comandos MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d89-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="64d89-123">Si necesita asistencia adicional, consulte los cmdlets de conferencias Web.</span><span class="sxs-lookup"><span data-stu-id="64d89-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="64d89-124">Directiva de contactos</span><span class="sxs-lookup"><span data-stu-id="64d89-124">Contacts policy</span></span>
<span data-ttu-id="64d89-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-125"></span></span>

<span data-ttu-id="64d89-126">ContactsPolicy.ps1 secuencia de comandos será la muestra que debe revisar.</span><span class="sxs-lookup"><span data-stu-id="64d89-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="64d89-127">Los cmdlets de mensajería instantánea y presencia ayudará si necesita más referencias.</span><span class="sxs-lookup"><span data-stu-id="64d89-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="64d89-128">Directiva de federación</span><span class="sxs-lookup"><span data-stu-id="64d89-128">Federation policy</span></span>
<span data-ttu-id="64d89-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-129"></span></span>

<span data-ttu-id="64d89-130">La secuencia de comandos de ejemplo para la federación es FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d89-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="64d89-131">Los cmdlets para revisar, si necesita más información, será el servidor perimetral, la federación y el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="64d89-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="64d89-132">Llamar a la directiva de Control de admisión</span><span class="sxs-lookup"><span data-stu-id="64d89-132">Call Admission Control policy</span></span>
<span data-ttu-id="64d89-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-133"></span></span>

<span data-ttu-id="64d89-134">Puede hacer referencia a BandwidthPolicy.ps1 para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="64d89-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="64d89-135">Los cmdlets de Control de admisión de llamadas tendrá más información así.</span><span class="sxs-lookup"><span data-stu-id="64d89-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="64d89-136">Reglas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="64d89-136">Voice Routing rules</span></span>
<span data-ttu-id="64d89-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-137"></span></span>

<span data-ttu-id="64d89-138">Tendrá la secuencia de comandos de ejemplo RoutingRules.ps1 para el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="64d89-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="64d89-139">Para configurar estas reglas, tome nota del contexto de teléfono (es decir, sobre el perfil o /SimpleName) y los códigos de área internas y externas, para que pueda especificar al crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="64d89-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="64d89-140">Les necesitará también durante la configuración de LyncPerfTool (específicamente para PSTN-UC y UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="64d89-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="64d89-141">Por ejemplo, el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo RoutingRules.ps1 debe utilizarse para el valor de LocationProfile en la siguiente figura de UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="64d89-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Herramienta de configuración de carga de Skype Empresarial, ficha Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="64d89-143">Para obtener más información, puede revisar los cmdlets de Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="64d89-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="64d89-144">Solicitud de operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="64d89-144">Conference Attendant application</span></span>
<span data-ttu-id="64d89-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-145"></span></span>

<span data-ttu-id="64d89-146">Revisar la secuencia de comandos ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d89-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="64d89-147">Desea tomar nota del número de teléfono de ConferencingAutoAttendant (1121111111 de forma predeterminada), para que puedan introducir en la herramienta de configuración de LyncPerfTool para la generación de la configuración, como sigue:</span><span class="sxs-lookup"><span data-stu-id="64d89-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Pestaña Escenarios de voz donde se muestra el número de teléfono y el nivel de Carga de conferencia.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="64d89-149">Encontrará más detalles en la conferencia y conferencia telefónica de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="64d89-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="64d89-150">Servicio de servidor llamada Park</span><span class="sxs-lookup"><span data-stu-id="64d89-150">Server Call Park service</span></span>
<span data-ttu-id="64d89-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-151"></span></span>

<span data-ttu-id="64d89-152">En realidad no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="64d89-152">This is actually disabled by default.</span></span> <span data-ttu-id="64d89-153">Si necesita probar esto puede revisar la secuencia de comandos de ejemplo CallParkConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d89-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="64d89-154">Además, consulte los cmdlets llame al parque aplicación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="64d89-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="64d89-155">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="64d89-155">Emergency calls</span></span>
<span data-ttu-id="64d89-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-156"></span></span>

<span data-ttu-id="64d89-157">Debe realizar los pasos siguientes para configurar el estrés y pruebas de rendimiento para las llamadas de emergencia:</span><span class="sxs-lookup"><span data-stu-id="64d89-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="64d89-158">Establecer una ruta de voz para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="64d89-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="64d89-159">Puede utilizar la secuencia de comandos RoutingRules.ps1 y comprobar bajo el comentario " **E911 ruta a RTC** " para obtener un ejemplo de cómo establecer esta ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="64d89-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="64d89-160">El comando de ejemplo en RoutingRules.ps1 tiene un patrón de número que incluye el número 119 en lugar de 911.</span><span class="sxs-lookup"><span data-stu-id="64d89-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="64d89-161">Debe evitar el uso de 911 (o su número de emergencia local real) para evitar llamadas accidentales a los operadores de emergencia locales durante las pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="64d89-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="64d89-162">Recuerde que esta configuración es sólo con fines de simulación!</span><span class="sxs-lookup"><span data-stu-id="64d89-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="64d89-163">Configurar direcciones rellenando los valores en la ficha **Configuración del servicio de información de ubicación** en la UserProvisioningTool, como se muestra en la figura siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d89-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Herramienta Aprovisionamiento de usuarios donde se muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="64d89-165">Cuando haya insertado todos los elementos en el UserProvisioningTool, haga clic en el botón **Generar archivos de configuración de LIS** .</span><span class="sxs-lookup"><span data-stu-id="64d89-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="64d89-166">Ahora se generarán archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta de carga y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="64d89-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="64d89-167">Puede utilizar los archivos CSV para entradas al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d89-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="64d89-168">Para ello, debe mover el archivo Locations0.xml en la misma carpeta que la herramienta Stress and Performance ejecutable (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="64d89-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="64d89-169">Esto le permitirá ejecutar escenarios (dial plan) de perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="64d89-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="64d89-170">Aplicación de configuración de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="64d89-170">Configuring Response Group application</span></span>
<span data-ttu-id="64d89-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="64d89-171"></span></span>

<span data-ttu-id="64d89-172">La secuencia de comandos de ejemplo es ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d89-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="64d89-173">También hay cmdlets de aplicación de grupo de respuesta a revisar para obtener más información de configuración.</span><span class="sxs-lookup"><span data-stu-id="64d89-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="64d89-174">El diagrama siguiente muestra algunos de los detalles de configuración:</span><span class="sxs-lookup"><span data-stu-id="64d89-174">The following diagram will show some of the configuration details:</span></span>
  
![Herramienta de configuración de grupo de respuesta donde se muestran los flujos de trabajo existentes para pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  


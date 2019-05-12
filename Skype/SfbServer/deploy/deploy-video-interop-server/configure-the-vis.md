---
title: Configurar el servidor de interoperabilidad vídeo en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumen: Configure el rol de servidor de interoperabilidad de vídeo (VISIBLES) de Skype para Business Server.'
ms.openlocfilehash: 64a3baa9374b819fc16a77a12a18a906c8e09225
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894531"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="727a6-103">Configurar el servidor de interoperabilidad vídeo en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="727a6-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="727a6-104">**Resumen:** Configuración de la función de servidor de interoperabilidad de vídeo (VISIBLES) en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="727a6-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="727a6-105">Configure las opciones que se asociará el frente con vídeo troncos con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="727a6-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="727a6-106">Una configuración de tronco de vídeo de ámbito global se crea una vez que se instala el servicio de VIS.</span><span class="sxs-lookup"><span data-stu-id="727a6-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="727a6-107">Esta configuración de tronco de vídeo se aplica a todos los troncos que no cuentan con una configuración de tronco de vídeo con un ámbito más específico.</span><span class="sxs-lookup"><span data-stu-id="727a6-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="727a6-108">Tenga en cuenta que la configuración de tronco de vídeo es una colección de configuraciones que se aplica a los troncos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="727a6-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="727a6-109">Configurar el tronco de vídeo y el plan de marcado</span><span class="sxs-lookup"><span data-stu-id="727a6-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="727a6-110">Uso de planeación de los siguientes comandos de Windows PowerShell para especificar la configuración del tronco de vídeo y el marcado que se asociará con el recién definido trunk(s) definido en el documento de topología entre el frente y todas las puertas de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="727a6-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="727a6-111">Toda esta configuración se puede definir de forma global, en el sitio o en el servicio (puerta de enlace de vídeo).</span><span class="sxs-lookup"><span data-stu-id="727a6-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="727a6-112">Se crea un plan de marcado con ámbito global por Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="727a6-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="727a6-113">Este plan de marcado se aplica de forma con respecto a todos los troncos que no tienen ningún marcado planeación con ámbito más específica.</span><span class="sxs-lookup"><span data-stu-id="727a6-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="727a6-114">Configurar el respecto al uso de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="727a6-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="727a6-115">Crear una nueva configuración de tronco vídeo (una colección de opciones) para usar en el tronco entre el frente y Cisco Unified Communications Manager (CallManager o CUCM), mediante el siguiente cmdlet de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="727a6-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="727a6-116">Si no hay un tronco de vídeo existente que debe modificarse, use el siguiente cmdlet de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="727a6-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="727a6-117">Para ver la configuración asociada con una configuración de tronco de vídeo determinado, use el siguiente cmdlet de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="727a6-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="727a6-118">Para quitar una configuración de tronco de vídeo determinado, use el siguiente cmdlet de Windows PowerShell (tenga en cuenta que la configuración del tronco de vídeo con ámbito global se aplicará si no hay una configuración de ámbito más concretamente tronco de vídeo para un tronco determinado):</span><span class="sxs-lookup"><span data-stu-id="727a6-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="727a6-119">Establecer un plan de marcado para asociar con el tronco, con los siguientes cmdlets de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="727a6-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="727a6-120">El comando **Remove-CsVoiceNormalizationRule** es necesario para reemplazar una regla predeterminada que interferirá con la interacción de VIS y CUCM esperada.</span><span class="sxs-lookup"><span data-stu-id="727a6-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="727a6-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) puede utilizarse para quitar un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="727a6-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="727a6-122">Para una llamada de vídeo de tronco SIP desde una puerta de enlace vídeo cuyo identificador URI de solicitud contiene un número que no sean E.164, leerá el nombre del plan de marcado asociado con el tronco asociado respecto e incluirá el nombre del plan de marcado en el elemento de contexto de teléfono de la dirección URI de solicitud en la invitación a ese VI S envía a Front-End.</span><span class="sxs-lookup"><span data-stu-id="727a6-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="727a6-123">La aplicación de conversión en el front-end extrae las reglas de normalización asociadas con el plan de marcado y las aplica al URI de solicitud.</span><span class="sxs-lookup"><span data-stu-id="727a6-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="727a6-124">Opciones de configuración del tronco</span><span class="sxs-lookup"><span data-stu-id="727a6-124">Trunk configuration options</span></span>

<span data-ttu-id="727a6-125">Los cmdlets de Windows PowerShell para la configuración del tronco de vídeo que se ha mencionado anteriormente eran nuevos en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="727a6-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="727a6-126">La configuración asociada a la configuración del tronco vídeo requiere una explicación breve.</span><span class="sxs-lookup"><span data-stu-id="727a6-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="727a6-127">**GatewaySendsRtcpForActiveCalls** Este parámetro determina si RTCP se envían los paquetes desde el VTC a la luz visible para las llamadas activas.</span><span class="sxs-lookup"><span data-stu-id="727a6-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="727a6-128">En este contexto, una llamada activa es una llamada en la que se permite el flujo de medios como mínimo en una dirección.</span><span class="sxs-lookup"><span data-stu-id="727a6-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="727a6-129">Si GatewaySendsRtcpForActiveCalls se establece en True, VIS puede finalizar una llamada si no recibe paquetes RTCP durante un período superior a los 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="727a6-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="727a6-130">La opción predeterminada es **True**.</span><span class="sxs-lookup"><span data-stu-id="727a6-130">The default is **True**.</span></span>
  
 <span data-ttu-id="727a6-131">**GatewaySendsRtcpForCallsOnHold** Este parámetro determina si sigue paquetes RTCP enviarse a través del tronco para las llamadas que se han colocado en espera y no se esperaban que los paquetes multimedia en cualquier dirección de flujo.</span><span class="sxs-lookup"><span data-stu-id="727a6-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="727a6-132">VIS puede finalizar la llamada, si no hay paquetes RTCP que fluyan desde el dispositivo VTC a VIS mientras la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="727a6-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="727a6-133">El valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="727a6-133">The default is **True**.</span></span> <span data-ttu-id="727a6-134">Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.</span><span class="sxs-lookup"><span data-stu-id="727a6-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="727a6-135">**EnableMediaEncryptionForSipOverTls** Este parámetro habilita o deshabilita SRTP para los medios cuando se establece el protocolo SIPTransport en TLS.</span><span class="sxs-lookup"><span data-stu-id="727a6-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="727a6-136">La opción predeterminada es **True**.</span><span class="sxs-lookup"><span data-stu-id="727a6-136">The default is **True**.</span></span> <span data-ttu-id="727a6-137">Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.</span><span class="sxs-lookup"><span data-stu-id="727a6-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="727a6-138">**EnableSessionTimer** Este parámetro habilita o deshabilita a temporizadores de sesión en el lado respecto de cada cuadro de diálogo SIP asociada con el tronco SIP vídeo.</span><span class="sxs-lookup"><span data-stu-id="727a6-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="727a6-139">La opción predeterminada es **False**.</span><span class="sxs-lookup"><span data-stu-id="727a6-139">The default is **False**.</span></span>
  
 <span data-ttu-id="727a6-140">**ForwardErrorCorrectionType** Este parámetro se usa para determinar si está desviar Error corrección (FEC) para las secuencias de vídeo que se aplique en la bifurcación entre el servidor de interoperabilidad de vídeo y una puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="727a6-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="727a6-141">Opción de configuración ForwardErrorCorrectionType en "None" desactiva FEC entre respecto y puerta de enlace de vídeo/VTC.</span><span class="sxs-lookup"><span data-stu-id="727a6-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="727a6-142">Establecer ForwardErrorCorrectionType a "Cisco" permite FEC compatible con puertas de enlace de vídeo por Cisco, como Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="727a6-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="727a6-143">La opción predeterminada es **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="727a6-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="727a6-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="727a6-144">See also</span></span>

[<span data-ttu-id="727a6-145">Configurar CUCM para la interoperación con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="727a6-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)

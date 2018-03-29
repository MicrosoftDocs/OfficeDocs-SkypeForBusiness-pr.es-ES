---
title: Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumen: Configurar la función de servidor de interoperabilidad de vídeo (VIS) en Skype para Business Server 2015.'
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ae668-103">Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ae668-103">Configure the Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ae668-104">**Resumen:** Configurar la función de servidor de interoperabilidad de vídeo (VIS) en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ae668-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="ae668-105">Configure las opciones que se asociará el VIS con vídeo troncos mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae668-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="ae668-106">Una configuración de tronco de vídeo de ámbito global se crea una vez que se instala el servicio de VIS.</span><span class="sxs-lookup"><span data-stu-id="ae668-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="ae668-107">Esta configuración de tronco de vídeo se aplica a todos los troncos que no cuentan con una configuración de tronco de vídeo con un ámbito más específico.</span><span class="sxs-lookup"><span data-stu-id="ae668-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="ae668-108">Tenga en cuenta que la configuración de tronco de vídeo es una colección de configuraciones que se aplica a los troncos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="ae668-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="ae668-109">Configurar el tronco de vídeo y el plan de marcado</span><span class="sxs-lookup"><span data-stu-id="ae668-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="ae668-110">Utilice los siguientes comandos de Windows PowerShell para especificar la configuración de vídeo tronco y el marcado que se va a asociarse con el recién definido trunk(s) definido en el documento de la topología entre el VIS y todas las puertas de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="ae668-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="ae668-111">Toda esta configuración se puede definir de forma global, en el sitio o en el servicio (puerta de enlace de vídeo).</span><span class="sxs-lookup"><span data-stu-id="ae668-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="ae668-112">Un plan de marcado con ámbito global se crea por Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae668-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="ae668-113">Este plan de marcado se aplica con respecto a todos los troncos que no tienen marcado a cualquier plan de ámbito más específico.</span><span class="sxs-lookup"><span data-stu-id="ae668-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="ae668-114">Configurar el VIS mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae668-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="ae668-115">Crear una nueva configuración de vídeo tronco (una colección de valores) para utilizar en el maletero entre el VIS y CUCM, mediante el siguiente cmdlet de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae668-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and CUCM, using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="ae668-116">Si hay un tronco de vídeo existente que se debe modificar, utilice el siguiente cmdlet de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae668-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="ae668-117">Para ver la configuración asociada con una configuración de tronco de vídeo determinado, use el siguiente cmdlet de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae668-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="ae668-118">Para eliminar una configuración de troncales de vídeo determinado, use el siguiente cmdlet de Windows PowerShell (tenga en cuenta que la configuración de ámbito global tronco de vídeo se aplicará si no hay una configuración más específicamente con ámbito tronco de vídeo para un tronco particular):</span><span class="sxs-lookup"><span data-stu-id="ae668-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="ae668-119">Establecer un plan de marcado para asociar con el tronco, mediante los siguientes cmdlets de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae668-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="ae668-120">El comando **Remove-CsVoiceNormalizationRule** es necesario para reemplazar una regla predeterminada que interferirá con la interacción de VIS y CUCM esperada.</span><span class="sxs-lookup"><span data-stu-id="ae668-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="ae668-121">[Quitar CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) puede utilizarse para eliminar un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="ae668-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="ae668-122">Una llamada de troncal SIP vídeo desde una puerta de enlace de vídeo cuyo URI de solicitud contiene un número no E.164, leerá el nombre del plan de marcado asociado del tronco asociado VIS e incluirá el nombre del plan de marcado en el elemento de contexto de teléfono del identificador URI de solicitud en la invitación que VI S se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="ae668-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="ae668-123">La aplicación de conversión en el front-end extrae las reglas de normalización asociadas con el plan de marcado y las aplica al URI de solicitud.</span><span class="sxs-lookup"><span data-stu-id="ae668-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="ae668-124">Opciones de configuración del tronco</span><span class="sxs-lookup"><span data-stu-id="ae668-124">Trunk configuration options</span></span>

<span data-ttu-id="ae668-125">Los cmdlets de Windows PowerShell para la configuración de vídeo tronco mencionados anteriormente son nuevos en el Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ae668-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously are new to the Skype for Business Server 2015.</span></span> <span data-ttu-id="ae668-126">La configuración asociada a la configuración de troncales de vídeo requiere una breve explicación.</span><span class="sxs-lookup"><span data-stu-id="ae668-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="ae668-127">**GatewaySendsRtcpForActiveCalls** Este parámetro determina si los paquetes RTCP se envían desde el VTC a la VIS de llamadas activas.</span><span class="sxs-lookup"><span data-stu-id="ae668-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="ae668-128">En este contexto, una llamada activa es una llamada en la que se permite el flujo de medios como mínimo en una dirección.</span><span class="sxs-lookup"><span data-stu-id="ae668-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="ae668-129">Si GatewaySendsRtcpForActiveCalls se establece en True, VIS puede finalizar una llamada si no recibe paquetes RTCP durante un período superior a los 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="ae668-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="ae668-130">El valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="ae668-130">The default is **True**.</span></span>
  
 <span data-ttu-id="ae668-131">**GatewaySendsRtcpForCallsOnHold** Este parámetro determina si los paquetes RTCP siguen enviándose a través del tronco para las llamadas que se han colocado en suspensión y no hay paquetes de media deben fluir en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="ae668-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="ae668-132">VIS puede finalizar la llamada, si no hay paquetes RTCP que fluyan desde el dispositivo VTC a VIS mientras la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="ae668-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="ae668-133">El valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="ae668-133">The default is **True**.</span></span> <span data-ttu-id="ae668-134">Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.</span><span class="sxs-lookup"><span data-stu-id="ae668-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="ae668-135">**EnableMediaEncryptionForSipOverTls** Este parámetro habilita o deshabilita SRTP para medios cuando el protocolo SIPTransport se establece en TLS.</span><span class="sxs-lookup"><span data-stu-id="ae668-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="ae668-136">La opción predeterminada es **True**.</span><span class="sxs-lookup"><span data-stu-id="ae668-136">The default is **True**.</span></span> <span data-ttu-id="ae668-137">Cuando se establece el protocolo de transporte SIP en TCP, se ignora esta configuración.</span><span class="sxs-lookup"><span data-stu-id="ae668-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="ae668-138">**EnableSessionTimer** Este parámetro habilita o deshabilita los temporizadores de sesión en el lado de VIS para cada cuadro de diálogo SIP asociados a la troncal SIP vídeo.</span><span class="sxs-lookup"><span data-stu-id="ae668-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="ae668-139">La opción predeterminada es **False**.</span><span class="sxs-lookup"><span data-stu-id="ae668-139">The default is **False**.</span></span>
  
 <span data-ttu-id="ae668-140">**ForwardErrorCorrectionType** Este parámetro se utiliza para determinar si se aplica en la pierna entre el servidor de interoperabilidad de vídeo y una puerta de enlace de vídeo hacia delante Error corrección (FEC) para las secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="ae668-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="ae668-141">Configuración ForwardErrorCorrectionType como "None" desactiva FEC entre VIS y puerta de enlace de vídeo/VTC.</span><span class="sxs-lookup"><span data-stu-id="ae668-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="ae668-142">Establecer ForwardErrorCorrectionType a "Cisco" permite FEC compatible con puertas de enlace de vídeo por Cisco, como Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="ae668-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="ae668-143">La opción predeterminada es **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="ae668-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ae668-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae668-144">See also</span></span>

#### 

[<span data-ttu-id="ae668-145">Configurar CUCM para la interoperación con Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ae668-145">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)


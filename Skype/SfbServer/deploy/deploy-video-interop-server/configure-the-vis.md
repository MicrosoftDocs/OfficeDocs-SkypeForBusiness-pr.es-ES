---
title: Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server
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
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumen: configure el rol servidor de interoperabilidad de vídeo (VIS) en Skype Empresarial Server.'
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120309"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="c45c3-103">Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c45c3-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="c45c3-104">**Resumen:** Configure el rol Servidor de interoperabilidad de vídeo (VIS) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c45c3-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="c45c3-105">Configure las opciones que el VIS asociará a los troncos de vídeo mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c45c3-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="c45c3-106">Una configuración de tronco de vídeo con ámbito global se crea una vez instalado el servicio VIS.</span><span class="sxs-lookup"><span data-stu-id="c45c3-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="c45c3-107">El VIS aplica esta configuración de tronco de vídeo a todos los troncos que no tienen una configuración de tronco de vídeo con un ámbito más específico.</span><span class="sxs-lookup"><span data-stu-id="c45c3-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="c45c3-108">Tenga en cuenta que la configuración del tronco de vídeo es una colección de opciones que se aplican a los troncos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c45c3-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="c45c3-109">Configurar el tronco de vídeo y el plan de marcado</span><span class="sxs-lookup"><span data-stu-id="c45c3-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="c45c3-110">Use los siguientes comandos Windows PowerShell para especificar la configuración del tronco de vídeo y el plan de marcado que se asociarán con los troncos recién definidos definidos en el documento de topología entre el VIS y todas las puertas de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c45c3-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="c45c3-111">Todas estas opciones de configuración se pueden establecer en los niveles Global, Site o Service (Video Gateway).</span><span class="sxs-lookup"><span data-stu-id="c45c3-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="c45c3-112">Se crea un plan de marcado con ámbito global por implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c45c3-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="c45c3-113">Vis aplica este plan de marcado a todos los troncos que no tienen ningún plan de marcado con un ámbito más específico.</span><span class="sxs-lookup"><span data-stu-id="c45c3-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="c45c3-114">Configurar el VIS mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c45c3-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="c45c3-115">Cree una nueva configuración de tronco de vídeo (una colección de configuraciones) para usarla en el tronco entre el VIS y el Administrador de comunicaciones unificadas de Cisco (CallManager o CUCM), mediante el siguiente cmdlet Windows PowerShell web:</span><span class="sxs-lookup"><span data-stu-id="c45c3-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="c45c3-116">Si hay un tronco de vídeo existente que debe modificarse, use el siguiente cmdlet Windows PowerShell vídeo:</span><span class="sxs-lookup"><span data-stu-id="c45c3-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="c45c3-117">Para ver la configuración asociada a una configuración de tronco de vídeo determinada, use el siguiente cmdlet Windows PowerShell vídeo:</span><span class="sxs-lookup"><span data-stu-id="c45c3-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="c45c3-118">Para quitar una configuración de tronco de vídeo determinada, use el siguiente cmdlet Windows PowerShell (tenga en cuenta que la configuración del tronco de vídeo de ámbito global se aplicará si no hay una configuración de tronco de vídeo con ámbito más específico para un tronco concreto):</span><span class="sxs-lookup"><span data-stu-id="c45c3-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="c45c3-119">Establezca un plan de marcado para asociarlo con el tronco, mediante los siguientes cmdlets Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c45c3-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="c45c3-120">El **comando Remove-CsVoiceNormalizationRule** es necesario para invalidar una regla predeterminada que interfiera con la interacción vis y CUCM esperada.</span><span class="sxs-lookup"><span data-stu-id="c45c3-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="c45c3-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) se puede usar para quitar un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="c45c3-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="c45c3-122">Para una llamada troncal SIP de vídeo desde una puerta de enlace de vídeo cuyo URI de solicitud contiene un número que no es E.164, VIS leerá el nombre del plan de marcado asociado al tronco asociado e incluirá el nombre del plan de marcado en la parte de contexto del teléfono del URI de solicitud en la invitación que vis envía al front-end.</span><span class="sxs-lookup"><span data-stu-id="c45c3-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="c45c3-123">A continuación, la aplicación de traducción del front-end extrae y aplica las reglas de normalización asociadas con el plan de marcado al URI de solicitud.</span><span class="sxs-lookup"><span data-stu-id="c45c3-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="c45c3-124">Opciones de configuración de tronco</span><span class="sxs-lookup"><span data-stu-id="c45c3-124">Trunk configuration options</span></span>

<span data-ttu-id="c45c3-125">Los cmdlets Windows PowerShell para la configuración del tronco de vídeo mencionados anteriormente eran nuevos en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c45c3-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="c45c3-126">La configuración asociada a la configuración del tronco de vídeo requiere una breve explicación.</span><span class="sxs-lookup"><span data-stu-id="c45c3-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="c45c3-127">**GatewaySendsRtcpForActiveCalls** Este parámetro determina si los paquetes RTCP se envían desde VTC al VIS para llamadas activas.</span><span class="sxs-lookup"><span data-stu-id="c45c3-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="c45c3-128">En este contexto, una llamada activa es una llamada en la que se permite el flujo de medios como mínimo en una dirección.</span><span class="sxs-lookup"><span data-stu-id="c45c3-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="c45c3-129">Si GatewaySendsRtcpForActiveCalls se establece en True, VIS puede finalizar una llamada si no recibe paquetes RTCP durante un período superior a 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="c45c3-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="c45c3-130">El valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="c45c3-130">The default is **True**.</span></span>
  
 <span data-ttu-id="c45c3-131">**GatewaySendsRtcpForCallsOnHold** Este parámetro determina si los paquetes RTCP siguen en envío a través del tronco para las llamadas que se han colocado en espera y no se espera que los paquetes multimedia fluyan en ninguna dirección.</span><span class="sxs-lookup"><span data-stu-id="c45c3-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="c45c3-132">VIS puede finalizar la llamada, si no hay paquetes RTCP que fluyan desde VTC a VIS mientras la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="c45c3-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="c45c3-133">El valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="c45c3-133">The default is **True**.</span></span> <span data-ttu-id="c45c3-134">Cuando el protocolo SIPTransport se establece en TCP, esta configuración se omite.</span><span class="sxs-lookup"><span data-stu-id="c45c3-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="c45c3-135">**EnableMediaEncryptionForSipOverTls** Este parámetro habilita o deshabilita SRTP para medios cuando el protocolo SIPTransport está establecido en TLS.</span><span class="sxs-lookup"><span data-stu-id="c45c3-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="c45c3-136">El valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="c45c3-136">The default is **True**.</span></span> <span data-ttu-id="c45c3-137">Cuando el protocolo SIPTransport se establece en TCP, esta configuración se omite.</span><span class="sxs-lookup"><span data-stu-id="c45c3-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="c45c3-138">**EnableSessionTimer** Este parámetro habilita o deshabilita los temporizadores de sesión en el lado VIS para cada cuadro de diálogo SIP asociado al tronco SIP de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c45c3-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="c45c3-139">El valor predeterminado es **False**.</span><span class="sxs-lookup"><span data-stu-id="c45c3-139">The default is **False**.</span></span>
  
 <span data-ttu-id="c45c3-140">**ForwardErrorCorrectionType** Este parámetro se usa para determinar si la corrección de errores de reenvío (FEC) para secuencias de vídeo se va a aplicar en el tramo entre el servidor de interoperabilidad de vídeo y una puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c45c3-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="c45c3-141">Al establecer ForwardErrorCorrectionType en "None" se desactiva FEC entre VIS y Video Gateway/VTC.</span><span class="sxs-lookup"><span data-stu-id="c45c3-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="c45c3-142">Al establecer ForwardErrorCorrectionType en "Cisco" se habilita FEC compatible con las puertas de enlace de vídeo de Cisco, como Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="c45c3-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="c45c3-143">El valor predeterminado es **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="c45c3-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c45c3-144">Ver también</span><span class="sxs-lookup"><span data-stu-id="c45c3-144">See also</span></span>

[<span data-ttu-id="c45c3-145">Configurar CUCM para interoperación con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c45c3-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
---
title: Componentes de conectividad de RTC en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Obtenga información sobre el enlace troncal SIP y puertas de enlace RTC para Enterprise Voice en Skype para Business Server.
ms.openlocfilehash: 1e0e27f496512343f26f0d3d005221ecd8264723
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913588"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="87bd5-103">Componentes de conectividad de RTC en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="87bd5-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="87bd5-104">Obtenga información sobre el enlace troncal SIP y puertas de enlace RTC para Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="87bd5-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="87bd5-105">Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="87bd5-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="87bd5-106">Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas.</span><span class="sxs-lookup"><span data-stu-id="87bd5-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="87bd5-107">Desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra sesión SIP.</span><span class="sxs-lookup"><span data-stu-id="87bd5-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="87bd5-108">En las conexiones de RTC, puedes implementar un tronco SIP o una puerta de enlace RTC (también denominada vínculo SIP directo, con una PBX o sin ella).</span><span class="sxs-lookup"><span data-stu-id="87bd5-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="87bd5-109">Enlace troncal SIP</span><span class="sxs-lookup"><span data-stu-id="87bd5-109">SIP Trunking</span></span>

<span data-ttu-id="87bd5-110">Como alternativa al uso de puertas de enlace RTC, puede conectar la solución de Enterprise Voice a la RTC mediante el enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="87bd5-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="87bd5-111">El enlace troncal SIP habilita los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="87bd5-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="87bd5-112">Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.</span><span class="sxs-lookup"><span data-stu-id="87bd5-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="87bd5-113">Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.</span><span class="sxs-lookup"><span data-stu-id="87bd5-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="87bd5-114">El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="87bd5-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="87bd5-115">Puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="87bd5-115">PSTN gateways</span></span>

<span data-ttu-id="87bd5-116">Puertas de enlace RTC son dispositivos de otro fabricante que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y una RTC o un PBX.</span><span class="sxs-lookup"><span data-stu-id="87bd5-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="87bd5-117">Puertas de enlace RTC trabajen con el servidor de mediación para presentar una llamada de RTC o PBX a un cliente de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="87bd5-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="87bd5-118">El servidor de mediación también presenta llamadas desde clientes de Enterprise Voice a la puerta de enlace de RTC para el enrutamiento a la RTC o PBX.</span><span class="sxs-lookup"><span data-stu-id="87bd5-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="87bd5-119">Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionan con Skype para Business Server, vea [el sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="87bd5-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="87bd5-120">Centrales de conmutación</span><span class="sxs-lookup"><span data-stu-id="87bd5-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="87bd5-121">Si tiene una infraestructura de voz existente que usa una central de conmutación (PBX), puede usar su PBX con Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="87bd5-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="87bd5-122">Escenarios de integración de Enterprise Voice y PBX admitidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="87bd5-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="87bd5-123">IP-PBX que admite el desvío de medios, con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="87bd5-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="87bd5-124">IP-PBX que requiere una puerta de enlace RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="87bd5-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="87bd5-125">PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="87bd5-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="87bd5-126">La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC.</span><span class="sxs-lookup"><span data-stu-id="87bd5-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="87bd5-127">Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="87bd5-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="87bd5-128">Desvío de medios es compatible solo con productos y versiones que aparece al [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="87bd5-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="87bd5-129">Para obtener información detallada acerca de los socios que ofrecen soluciones de Enterprise Voice, consulte el [sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="87bd5-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="87bd5-130">Para obtener información detallada acerca de los socios que ofrecen soluciones de hardware de Enterprise Voice, incluidas las puertas de enlace RTC, consulte el [sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="87bd5-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  


---
title: Componentes de conectividad RTC en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Obtenga más información sobre la Troncalización SIP y las puertas de enlace RTC para telefonía IP empresarial en Skype empresarial Server.
ms.openlocfilehash: 443f5425beeed5b032968837ac56ce3a26468cdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802540"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="7a730-103">Componentes de conectividad RTC en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="7a730-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="7a730-104">Obtenga más información sobre la Troncalización SIP y las puertas de enlace RTC para telefonía IP empresarial en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7a730-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="7a730-105">Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="7a730-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="7a730-106">Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas.</span><span class="sxs-lookup"><span data-stu-id="7a730-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="7a730-107">Desde el punto de vista del usuario, una llamada entre la infraestructura de telefonía IP empresarial y la RTC debe parecer simplemente otra sesión de SIP.</span><span class="sxs-lookup"><span data-stu-id="7a730-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="7a730-108">En las conexiones de RTC, puedes implementar un tronco SIP o una puerta de enlace RTC (también denominada vínculo SIP directo, con una PBX o sin ella).</span><span class="sxs-lookup"><span data-stu-id="7a730-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="7a730-109">Enlace troncal SIP</span><span class="sxs-lookup"><span data-stu-id="7a730-109">SIP Trunking</span></span>

<span data-ttu-id="7a730-110">Como alternativa al uso de puertas de enlace RTC, puede conectar su solución de telefonía empresarial a la RTC mediante el uso de troncales SIP.</span><span class="sxs-lookup"><span data-stu-id="7a730-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="7a730-111">El enlace troncal SIP habilita los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="7a730-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="7a730-112">Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7a730-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="7a730-113">Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.</span><span class="sxs-lookup"><span data-stu-id="7a730-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="7a730-114">El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="7a730-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="7a730-115">Puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="7a730-115">PSTN gateways</span></span>

<span data-ttu-id="7a730-116">Las puertas de enlace RTC son dispositivos de terceros que traducen la señalización y los medios entre la infraestructura de voz empresarial y una RTC o un sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="7a730-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="7a730-117">Las puertas de enlace RTC funcionan con el servidor de mediación para presentar una llamada RTC o PBX a un cliente de telefonía empresarial.</span><span class="sxs-lookup"><span data-stu-id="7a730-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="7a730-118">El servidor de mediación también presenta llamadas de clientes de telefonía de empresa a la puerta de enlace RTC para el enrutamiento a la RTC o a la PBX.</span><span class="sxs-lookup"><span data-stu-id="7a730-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="7a730-119">Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionen con Skype empresarial Server, consulte [el sitio web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="7a730-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="7a730-120">Centrales de conmutación</span><span class="sxs-lookup"><span data-stu-id="7a730-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="7a730-121">Si ya tiene una infraestructura de voz que usa una central de conmutación (PBX), puede usar su PBX con telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="7a730-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="7a730-122">Los escenarios de integración de la telefonía IP empresarial compatibles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a730-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="7a730-123">IP-PBX que admite omisión de medios, con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7a730-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="7a730-124">IP-PBX que requiere una puerta de enlace RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="7a730-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="7a730-125">PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="7a730-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7a730-126">La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC.</span><span class="sxs-lookup"><span data-stu-id="7a730-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="7a730-127">Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="7a730-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="7a730-128">La omisión de contenido multimedia solo se admite con productos y versiones que se muestran en [el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="7a730-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="7a730-129">Para obtener más información sobre los partners que ofrecen soluciones de telefonía IP empresarial, consulte el [sitio web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="7a730-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="7a730-130">Para obtener más información sobre los partners que ofrecen soluciones de hardware de voz empresarial, incluidas las puertas de enlace RTC, consulte el [sitio web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="7a730-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  


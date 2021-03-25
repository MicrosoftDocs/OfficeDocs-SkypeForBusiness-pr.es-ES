---
title: Componentes de conectividad RTC en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Obtenga información sobre el enlace troncal SIP y las puertas de enlace RTC Telefonía IP empresarial en Skype Empresarial Server.
ms.openlocfilehash: 402aa365556ef52d135c3ee6c0a2e36e9bd2e780
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114626"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="d6703-103">Componentes de conectividad RTC en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d6703-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="d6703-104">Obtenga información sobre el enlace troncal SIP y las puertas de enlace RTC Telefonía IP empresarial en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d6703-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="d6703-p101">Una solución de telefonía VoIP profesional debe proporcionar llamadas entrantes y realizadas a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra sesión de SIP.</span><span class="sxs-lookup"><span data-stu-id="d6703-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="d6703-108">Para las conexiones RTC, puede implementar un tronco SIP o una puerta de enlace RTC (con una PBX, también conocida como vínculo SIP directo o sin PBX).</span><span class="sxs-lookup"><span data-stu-id="d6703-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="d6703-109">Enlace troncal SIP</span><span class="sxs-lookup"><span data-stu-id="d6703-109">SIP Trunking</span></span>

<span data-ttu-id="d6703-p102">Como alternativa al uso de puertas de enlace RTC, puede conectar la solución de Enterprise Voice a la RTC usando el enlace troncal SIP. El enlace troncal SIP habilita los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="d6703-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="d6703-112">Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d6703-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="d6703-113">Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d6703-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="d6703-114">El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="d6703-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="d6703-115">Puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="d6703-115">PSTN gateways</span></span>

<span data-ttu-id="d6703-116">Las puertas de enlace RTC son dispositivos de otro fabricante que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y una red telefónica conmutada (RTC) o una central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="d6703-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="d6703-117">Las puertas de enlace RTC trabajan con el servidor de mediación para presentar una llamada de RTC o de PBX a un cliente de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d6703-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="d6703-118">El servidor de mediación también presenta llamadas de los clientes de Enterprise Voice a la puerta de enlace RTC para redirigir las llamadas a la RTC o a la PBX.</span><span class="sxs-lookup"><span data-stu-id="d6703-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="d6703-119">Para obtener una lista de socios que trabajan con Microsoft para proporcionar dispositivos que funcionan con Skype Empresarial Server, vea el sitio web de  [Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d6703-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="d6703-120">Centrales de conmutación</span><span class="sxs-lookup"><span data-stu-id="d6703-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="d6703-121">Si tiene una infraestructura de voz existente que usa una central de conmutación (PBX), puede usar la PBX con Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6703-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="d6703-122">Los escenarios de integración de Enterprise Voice y PBX admitidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6703-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="d6703-123">IP-PBX que admite desvío de medios, con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d6703-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="d6703-124">IP-PBX que requiere una puerta de enlace de RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="d6703-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="d6703-125">PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace de RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="d6703-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d6703-126">El desvío de medios no interactuará con todas las puertas de RTC, los sistemas IP-PBX y las SBC.</span><span class="sxs-lookup"><span data-stu-id="d6703-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="d6703-127">Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="d6703-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d6703-128">La omisión de medios solo se admite con productos y versiones enumerados en el Programa de interoperabilidad abierta de comunicaciones unificadas [- Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="d6703-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).</span></span> 
  
<span data-ttu-id="d6703-129">Para obtener más información acerca de los partners que ofrecen Telefonía IP empresarial soluciones, consulte el sitio web de [Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d6703-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="d6703-130">Para obtener más información acerca de los partners que ofrecen Telefonía IP empresarial de hardware, incluidas las puertas de enlace RTC, consulte el sitio web de [Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d6703-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>

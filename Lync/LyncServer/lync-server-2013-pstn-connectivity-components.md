---
title: 'Lync Server 2013: componentes de conectividad con RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa82336ed96c61315da4c25a0152ba75d15d7b6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531747"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="0c969-102">Componentes de conectividad con RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c969-102">PSTN connectivity components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c969-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="0c969-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="0c969-p101">Una solución de telefonía VoIP profesional debe proporcionar llamadas entrantes y realizadas a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra sesión de SIP.</span><span class="sxs-lookup"><span data-stu-id="0c969-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="0c969-107">Para las conexiones RTC, puede implementar un tronco SIP o una puerta de enlace RTC (con una PBX, también conocida como vínculo SIP directo o sin PBX).</span><span class="sxs-lookup"><span data-stu-id="0c969-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="0c969-108">Enlace troncal SIP</span><span class="sxs-lookup"><span data-stu-id="0c969-108">SIP Trunking</span></span>

<span data-ttu-id="0c969-p102">Como alternativa al uso de puertas de enlace RTC, puede conectar la solución de Enterprise Voice a la RTC usando el enlace troncal SIP. El enlace troncal SIP habilita los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="0c969-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="0c969-111">Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0c969-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="0c969-112">Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.</span><span class="sxs-lookup"><span data-stu-id="0c969-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="0c969-113">El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="0c969-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="0c969-114">Puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="0c969-114">PSTN gateways</span></span>

<span data-ttu-id="0c969-115">Las puertas de enlace RTC son dispositivos de otro fabricante que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y una red telefónica conmutada (RTC) o una central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="0c969-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="0c969-116">Las puertas de enlace RTC trabajan con el servidor de mediación para presentar una llamada de RTC o de PBX a un cliente de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0c969-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="0c969-117">El servidor de mediación también presenta llamadas de los clientes de Enterprise Voice a la puerta de enlace RTC para redirigir las llamadas a la RTC o a la PBX.</span><span class="sxs-lookup"><span data-stu-id="0c969-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="0c969-118">Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionan con Lync Server, vea el sitio web de asociados de comunicaciones unificadas de Microsoft en [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="0c969-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="0c969-119">Centrales de conmutación</span><span class="sxs-lookup"><span data-stu-id="0c969-119">Private Branch Exchanges</span></span>

<span data-ttu-id="0c969-120">Si tiene una infraestructura de voz existente que usa una central de conmutación (PBX), puede usar la PBX con Lync Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0c969-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="0c969-121">Los escenarios de integración de Enterprise Voice y PBX admitidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c969-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="0c969-122">IP-PBX que admite desvío de medios, con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0c969-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="0c969-123">IP-PBX que requiere una puerta de enlace de RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="0c969-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="0c969-124">PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace de RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="0c969-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c969-125">El desvío de medios no interactuará con todas las puertas de RTC, los sistemas IP-PBX y las SBC.</span><span class="sxs-lookup"><span data-stu-id="0c969-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="0c969-126">Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="0c969-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="0c969-127">La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="0c969-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="0c969-128">Para obtener más información sobre los socios que ofrecen soluciones de telefonía IP empresarial, consulte el sitio web de asociados de comunicaciones unificadas de Microsoft en [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="0c969-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="0c969-129">Para obtener más información sobre los socios que ofrecen soluciones de hardware de telefonía IP empresarial, incluidas las puertas de enlace RTC, consulte el sitio web de asociados de comunicaciones unificadas de Microsoft [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="0c969-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


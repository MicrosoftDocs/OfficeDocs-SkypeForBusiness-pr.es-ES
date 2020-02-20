---
title: Lync Server 2013 admite el enlace troncal SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b370242bab888047b6f234f0b574311fe626773
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="a8ed4-102">Compatibilidad con enlaces troncales SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ed4-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8ed4-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a8ed4-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a8ed4-104">Si planea usar la telefonía IP empresarial con enlace troncal SIP, debe implementar un servidor de mediación y asegurarse de que otros componentes y la infraestructura cumplan los requisitos de soporte técnico apropiados para el modelo de implementación.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="a8ed4-105">Para obtener más información sobre cómo determinar si implementar el enlace troncal SIP, consulte [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="a8ed4-106">Puede usar el programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft para la infraestructura de telefonía empresarial para buscar puertas de enlace de red telefónica conmutada (RTC), PBX IP y servicios de enlace troncal SIP cualificados, incluida la telefonía IP completa. proveedores de servicios.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="a8ed4-107">Para obtener más información, consulte el sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft en [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span><span class="sxs-lookup"><span data-stu-id="a8ed4-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="a8ed4-108">Compatibilidad del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a8ed4-108">Mediation Server Support</span></span>

<span data-ttu-id="a8ed4-109">Para implementar el enlace troncal SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como un proxy para las sesiones de comunicaciones entre los clientes de Lync Server 2013 y el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="a8ed4-110">El servidor de mediación descodifica el tráfico de medios de los clientes y servidores y lo vuelve a codificar antes de enviarlo al proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="a8ed4-111">La recodificación es necesaria porque los troncos SIP no admiten algunos códecs usados, como la negociación de protocolo de audio en tiempo real (RTA) o la negociación del Protocolo de establecimiento interactivo de conectividad (ICE) para un ataque transversal de Firewall.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="a8ed4-112">Cada servidor de mediación puede tener dos adaptadores de red, para ofrecer una interfaz de red interna y otra externa.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="a8ed4-113">La interfaz externa suele denominarse interfaz de puerta de enlace porque, tradicionalmente, se ha usado para conectarse a una puerta de enlace RTC o a una IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="a8ed4-114">Para implementar un enlace troncal SIP, debe conectar la interfaz externa a un controlador de límite de sesión (SBC) de un proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="a8ed4-115">Enlace troncal SIP centralizado y distribuido</span><span class="sxs-lookup"><span data-stu-id="a8ed4-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="a8ed4-116">*Centralizado* El enlace troncal SIP enruta todo el tráfico del Protocolo de voz sobre IP (VoIP), incluido el tráfico del sitio de sucursal, a través de su centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="a8ed4-117">El modelo de implementación centralizada es sencillo, rentable y suele ser el método preferido para implementar troncos SIP con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="a8ed4-p106">Según los patrones de uso de su empresa, es posible que no desee enrutar a todos los usuarios a través del enlace troncal SIP centralizado. Para analizar sus necesidades, responda a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="a8ed4-p106">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk. To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="a8ed4-p107">¿Qué tamaño tiene cada sitio? ¿Cuántos usuarios tiene?</span><span class="sxs-lookup"><span data-stu-id="a8ed4-p107">How big is each site? How many users?</span></span>

  - <span data-ttu-id="a8ed4-122">¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?</span><span class="sxs-lookup"><span data-stu-id="a8ed4-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="a8ed4-p108">El enlace troncal SIP *distribuido* es un modelo de implementación con el que se implementa un enlace troncal SIP local en una o más sucursales. A partir de entonces, el tráfico de VoIP se enruta desde la sucursal directamente al proveedor de servicios que le corresponda, sin pasar por su centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-p108">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites. VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="a8ed4-125">El enlace troncal SIP distribuido solo se necesita en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="a8ed4-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="a8ed4-126">Si la sucursal necesita una conectividad telefónica con funciones de supervivencia (por ejemplo, si se cae la red WAN).</span><span class="sxs-lookup"><span data-stu-id="a8ed4-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="a8ed4-127">Si la sucursal necesita redundancia y conmutación por error, el proveedor de servicios cobrará más por ello y la configuración llevará más tiempo.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="a8ed4-128">Se deben analizar estas características en cada sucursal.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="a8ed4-129">Es posible que algunas de las ramas requieran redundancia y conmutación por error, mientras que otras no.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="a8ed4-p110">Si la sucursal y el centro de datos se encuentran en países o regiones diferentes. Por motivos legales y de compatibilidad, necesita al menos un enlace troncal SIP por cada país o región.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-p110">The branch site and data center are in different countries/regions. For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="a8ed4-132">La decisión de implementar un enlace troncal SIP centralizado o distribuido requiere un análisis de costos y beneficios.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="a8ed4-133">En algunos casos, puede ser ventajoso optar por el modo de implementación distribuida, incluso si no es necesario.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="a8ed4-134">En las implementaciones totalmente centralizadas, todo el tráfico de las sucursales se enruta a través de vínculos WAN.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="a8ed4-135">En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefiera usar el enlace troncal SIP distribuido.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8ed4-136">Para obtener más información sobre por qué y cómo podría usar el enlace troncal SIP distribuido, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="a8ed4-137">Tipos de conexión de enlace troncal SIP compatibles</span><span class="sxs-lookup"><span data-stu-id="a8ed4-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="a8ed4-138">Lync Server 2013 admite los siguientes tipos de conexión para el enlace troncal SIP:</span><span class="sxs-lookup"><span data-stu-id="a8ed4-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="a8ed4-p112">La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no necesita VPN. Un posible inconveniente es que el exceso de tráfico de IP puede interferir con el funcionamiento de VoIP, salvo que se le dé prioridad al tráfico de VoIP.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-p112">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require VPN. A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="a8ed4-p113">En general, las conexiones privadas sin otro tipo de tráfico son el tipo de conexión más seguro y fiable (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada). Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tengan un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-p113">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line). This connection type provides the highest call-carrying capacity, but is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="a8ed4-147">La Internet pública es el tipo de conexión menos costoso, pero también el menos fiable y el que tiene la menor capacidad de transferencia de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="a8ed4-148">El proveedor de servicios de telefonía por Internet (ITSP) puede ayudar a proteger este tipo de conexión de tronco de SIP si admite la seguridad de la capa de transporte (TLS) y el protocolo de transporte seguro en tiempo real (SRTP) para cifrar el tráfico multimedia y de señalización.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="a8ed4-149">Si no puede configurar una conexión de tronco SIP a través de Internet para que use TLS y SRTP, se recomienda encarecidamente que utilice un túnel de VPN para ofrecer una conexión más segura.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="a8ed4-150">Póngase en contacto con su ITSP para averiguar si admite TLS con SRTP.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="a8ed4-151">Selección de un tipo de conexión</span><span class="sxs-lookup"><span data-stu-id="a8ed4-151">Selecting a Connection Type</span></span>

<span data-ttu-id="a8ed4-152">El tipo de conexión de enlace troncal SIP más adecuado para su empresa depende de las necesidades y el presupuesto del que disponga.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="a8ed4-153">Para una empresa de tamaño mediano o grande, una red MPLS suele proporcionar el máximo valor.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="a8ed4-154">Es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="a8ed4-155">Las empresas grandes pueden necesitar una conexión de T1 o fibra óptica privada.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="a8ed4-156">Para una empresa pequeña o un sitio de sucursal con un volumen de llamadas bajo, el enlace troncal SIP a través de Internet puede ser la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="a8ed4-157">Sin embargo, este tipo de conexión no se recomienda para sitios de tamaño mediano o grandes.</span><span class="sxs-lookup"><span data-stu-id="a8ed4-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="a8ed4-158">Compatibilidad de códecs</span><span class="sxs-lookup"><span data-stu-id="a8ed4-158">Codec Support</span></span>

<span data-ttu-id="a8ed4-159">El proxy del proveedor de servicios debe admitir los siguientes códecs:</span><span class="sxs-lookup"><span data-stu-id="a8ed4-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="a8ed4-160">G.711 Ley A (que se usa principalmente fuera de Norteamérica)</span><span class="sxs-lookup"><span data-stu-id="a8ed4-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="a8ed4-161">G.711 Ley µ (que se usa en Norteamérica)</span><span class="sxs-lookup"><span data-stu-id="a8ed4-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


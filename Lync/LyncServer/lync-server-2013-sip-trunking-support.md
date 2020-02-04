---
title: 'Lync Server 2013: Compatibilidad con conexiones de enlace troncal SIP'
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
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="fc418-102">Compatibilidad con conexiones de enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc418-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc418-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fc418-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fc418-104">Si planea usar telefonía IP empresarial con Troncalización SIP, debe implementar un servidor de mediación y asegurarse de que otros componentes y la infraestructura cumplan con los requisitos de soporte técnico adecuados para su modelo de implementación.</span><span class="sxs-lookup"><span data-stu-id="fc418-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="fc418-105">Para obtener más información sobre cómo determinar si implementar la Troncalización SIP, consulte [información general sobre el enlace troncal de SIP en Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="fc418-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="fc418-106">Puede usar el programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft para la infraestructura de telefonía empresarial para encontrarse con puertas de enlace de red telefónica conmutada (RTC) públicas, PBX IP y servicios de Troncalización SIP, incluida la telefonía IP calificada. proveedores de servicios.</span><span class="sxs-lookup"><span data-stu-id="fc418-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="fc418-107">Para obtener más información, consulte el sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft en [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span><span class="sxs-lookup"><span data-stu-id="fc418-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="fc418-108">Compatibilidad con el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="fc418-108">Mediation Server Support</span></span>

<span data-ttu-id="fc418-109">Para implementar la Troncalización SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como un proxy para las sesiones de comunicaciones entre los clientes de Lync Server 2013 y el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="fc418-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="fc418-110">El servidor de mediación descodifica el tráfico multimedia de los clientes y los servidores y lo vuelve a codificar antes de enviarlo al proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="fc418-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="fc418-111">La recodificación es necesaria porque los troncos SIP no admiten algunos códecs usados, como la entrada de audio en tiempo real (RTA) o la negociación de protocolo ICE (establecimiento de conectividad interactiva) para el recorrido de Firewall.</span><span class="sxs-lookup"><span data-stu-id="fc418-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="fc418-112">Cada servidor de mediación puede tener dos adaptadores de red, que proporcionan una interfaz de red interna y externa.</span><span class="sxs-lookup"><span data-stu-id="fc418-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="fc418-113">La interfaz externa suele denominarse puerta de enlace porque, tradicionalmente, se ha usado para conectarse a una puerta de enlace PSTN o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="fc418-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="fc418-114">Para implementar un tronco de SIP, debe conectar la interfaz externa a un controlador de borde de sesión (SBC) en un proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="fc418-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="fc418-115">Enlace troncal SIP centralizado en comparación con uno distribuido</span><span class="sxs-lookup"><span data-stu-id="fc418-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="fc418-116">*Centralizado* El Troncalización SIP dirige todo el tráfico de voz sobre el protocolo de Internet (VoIP), incluido el tráfico de sitios de sucursales, a través de su centro de datos.</span><span class="sxs-lookup"><span data-stu-id="fc418-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="fc418-117">El modelo de implementación centralizada es simple, rentable y, por lo general, es el método preferido para implementar los troncos SIP con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc418-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="fc418-118">Según los patrones de uso dentro de su empresa, es posible que no desee enrutar a todos los usuarios a través del tronco SIP centralizado.</span><span class="sxs-lookup"><span data-stu-id="fc418-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="fc418-119">Para analizar tus necesidades, responde a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="fc418-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="fc418-120">¿Qué tamaño tiene cada sitio?</span><span class="sxs-lookup"><span data-stu-id="fc418-120">How big is each site?</span></span> <span data-ttu-id="fc418-121">¿Cuántos usuarios?</span><span class="sxs-lookup"><span data-stu-id="fc418-121">How many users?</span></span>

  - <span data-ttu-id="fc418-122">¿Cuáles son los números de marcación directa directos de cada sitio que reciben las llamadas más telefónicas?</span><span class="sxs-lookup"><span data-stu-id="fc418-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="fc418-123">*Distribuido* El Troncalización SIP es un modelo de implementación en el que se implementa un enlace SIP local en uno o más sitios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="fc418-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="fc418-124">El tráfico de VoIP se enruta directamente desde el sitio de la sucursal a su proveedor de servicios, sin necesidad de pasar por su centro de datos.</span><span class="sxs-lookup"><span data-stu-id="fc418-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="fc418-125">El enlace troncal SIP distribuido solo es necesario en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="fc418-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="fc418-126">El sitio de la sucursal requiere conectividad telefónica reactivable (por ejemplo, si la WAN deja de funcionar).</span><span class="sxs-lookup"><span data-stu-id="fc418-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="fc418-127">Si la sucursal necesita redundancia y conmutación por error, el proveedor de servicios cobrará más y la configuración tardará más tiempo.</span><span class="sxs-lookup"><span data-stu-id="fc418-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="fc418-128">Debe analizarse para cada sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="fc418-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="fc418-129">Es posible que algunas de las sucursales requieran redundancia y conmutación por error, mientras que otras no.</span><span class="sxs-lookup"><span data-stu-id="fc418-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="fc418-130">El sitio de la sucursal y el centro de datos se encuentran en diferentes países o regiones.</span><span class="sxs-lookup"><span data-stu-id="fc418-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="fc418-131">Por motivos legales y de compatibilidad, necesitas al menos un tronco SIP por cada país o región.</span><span class="sxs-lookup"><span data-stu-id="fc418-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="fc418-132">La decisión de implementar Troncalización SIP centralizada o distribuida requiere un análisis de costo-beneficio.</span><span class="sxs-lookup"><span data-stu-id="fc418-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="fc418-133">En algunos casos, puede resultar ventajoso optar por el modo de implementación distribuida, incluso si no es necesario.</span><span class="sxs-lookup"><span data-stu-id="fc418-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="fc418-134">En una implementación completamente centralizada, todo el tráfico de los sitios de las sucursales se enruta a través de vínculos de WAN.</span><span class="sxs-lookup"><span data-stu-id="fc418-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="fc418-135">En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefieras usar el enlace troncal SIP distribuido.</span><span class="sxs-lookup"><span data-stu-id="fc418-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc418-136">Para obtener más información sobre por qué y cómo puede usar la Troncalización de SIP distribuido, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Troncalización SIP de sitio de sucursal en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="fc418-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="fc418-137">Tipos de conexión de enlace troncal SIP compatibles</span><span class="sxs-lookup"><span data-stu-id="fc418-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="fc418-138">Lync Server 2013 admite los siguientes tipos de conexión para Troncalización SIP:</span><span class="sxs-lookup"><span data-stu-id="fc418-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="fc418-139">La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente.</span><span class="sxs-lookup"><span data-stu-id="fc418-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="fc418-140">El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor.</span><span class="sxs-lookup"><span data-stu-id="fc418-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="fc418-141">Este tipo de conexión no requiere VPN.</span><span class="sxs-lookup"><span data-stu-id="fc418-141">This connection type does not require VPN.</span></span> <span data-ttu-id="fc418-142">Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.</span><span class="sxs-lookup"><span data-stu-id="fc418-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="fc418-143">Normalmente, una conexión privada sin otro tráfico es el tipo de conexión más confiable y confiable (por ejemplo, una conexión de fibra óptica con leasing o una línea T1).</span><span class="sxs-lookup"><span data-stu-id="fc418-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="fc418-144">Este tipo de conexión proporciona la mayor capacidad de carga de llamadas, pero generalmente es la más costosa.</span><span class="sxs-lookup"><span data-stu-id="fc418-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="fc418-145">No se necesita VPN.</span><span class="sxs-lookup"><span data-stu-id="fc418-145">VPN is not required.</span></span> <span data-ttu-id="fc418-146">Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.</span><span class="sxs-lookup"><span data-stu-id="fc418-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="fc418-147">La Internet pública es el tipo de conexión menos costosa, pero también el menos confiable y el que tiene la capacidad de hacer llamadas más económicas.</span><span class="sxs-lookup"><span data-stu-id="fc418-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="fc418-148">El proveedor de servicios de telefonía por Internet (ITSP) puede ayudar a proteger este tipo de conexión de troncal de SIP, si es compatible con la seguridad de la capa de transporte (TLS) y el protocolo de transporte seguro en tiempo real (SRTP) para cifrar el tráfico de señales y multimedia.</span><span class="sxs-lookup"><span data-stu-id="fc418-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="fc418-149">Si no puede configurar una conexión de troncal de SIP a través de Internet para usar TLS y SRTP, le recomendamos encarecidamente que use un túnel VPN para proporcionar una conexión más segura.</span><span class="sxs-lookup"><span data-stu-id="fc418-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="fc418-150">Póngase en contacto con su ITSP para determinar si proporciona compatibilidad con TLS con SRTP.</span><span class="sxs-lookup"><span data-stu-id="fc418-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="fc418-151">Seleccionar un tipo de conexión</span><span class="sxs-lookup"><span data-stu-id="fc418-151">Selecting a Connection Type</span></span>

<span data-ttu-id="fc418-152">El tipo de conexión de enlace troncal SIP más adecuado para tu empresa depende de las necesidades y el presupuesto del que dispongas.</span><span class="sxs-lookup"><span data-stu-id="fc418-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="fc418-153">En el caso de una empresa de tamaño mediano o grande, una red MPLS generalmente proporciona el máximo valor.</span><span class="sxs-lookup"><span data-stu-id="fc418-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="fc418-154">Puede proporcionar el ancho de banda necesario a una tarifa económica que una red privada especializada.</span><span class="sxs-lookup"><span data-stu-id="fc418-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="fc418-155">Las grandes empresas pueden requerir una conexión privada de fibra óptica o T1.</span><span class="sxs-lookup"><span data-stu-id="fc418-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="fc418-156">En el caso de una pequeña empresa o sitio de sucursales con un volumen de llamada bajo, el Troncalización SIP a través de Internet puede ser la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="fc418-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="fc418-157">Sin embargo, no se recomienda este tipo de conexión para los sitios de tamaño mediano o más grande.</span><span class="sxs-lookup"><span data-stu-id="fc418-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="fc418-158">Compatibilidad de códecs</span><span class="sxs-lookup"><span data-stu-id="fc418-158">Codec Support</span></span>

<span data-ttu-id="fc418-159">El proxy del proveedor de servicios debe admitir los siguientes códecs:</span><span class="sxs-lookup"><span data-stu-id="fc418-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="fc418-160">G.711 Ley A (que se usa principalmente fuera de Norteamérica)</span><span class="sxs-lookup"><span data-stu-id="fc418-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="fc418-161">G.711 Ley µ (que se usa en Norteamérica)</span><span class="sxs-lookup"><span data-stu-id="fc418-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


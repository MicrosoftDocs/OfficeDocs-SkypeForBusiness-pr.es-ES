---
title: 'Lync Server 2013: ¿Cómo puedo implementar el enlace troncal SIP?'
description: 'Lync Server 2013: ¿Cómo puedo implementar el enlace troncal SIP?.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10882adc0bff573868dcd07268ed0446385d895c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553156"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="e15db-103">¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="e15db-103">How do I implement SIP trunking in Lync Server 2013?</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e15db-104">_**Última modificación del tema:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="e15db-104">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="e15db-105">Para implementar el enlace troncal SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como un proxy para las sesiones de comunicaciones entre los clientes de Lync Server 2013 y el proveedor de servicios, y transcodifica los medios, cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e15db-105">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="e15db-106">Cada servidor de mediación tiene una interfaz de red interna y una interfaz de red externa.</span><span class="sxs-lookup"><span data-stu-id="e15db-106">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="e15db-107">La interfaz interna se conecta a los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e15db-107">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="e15db-108">La interfaz externa suele denominarse interfaz de puerta de enlace porque se ha usado tradicionalmente para conectar el servidor de mediación a una puerta de enlace de red telefónica conmutada (RTC) o a una IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e15db-108">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="e15db-109">Para implementar un tronco SIP, debe conectar la interfaz externa del servidor de mediación con el componente perimetral externo de la ITSP.</span><span class="sxs-lookup"><span data-stu-id="e15db-109">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e15db-110">El componente perimetral externo del ITSP puede ser un controlador SBC (controlador de borde de sesión), un enrutador o una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="e15db-110">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="e15db-111">Para obtener más información sobre los servidores de mediación, vea [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="e15db-111">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="e15db-112">Enlace troncal SIP centralizado y distribuido</span><span class="sxs-lookup"><span data-stu-id="e15db-112">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="e15db-113">*Centralizado* El enlace troncal SIP enruta todo el tráfico del Protocolo de voz sobre IP (VoIP), incluido el tráfico del sitio de sucursal, a través del sitio central.</span><span class="sxs-lookup"><span data-stu-id="e15db-113">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="e15db-114">El modelo de implementación centralizada es sencillo, rentable y suele ser el enfoque recomendado para implementar troncos SIP con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e15db-114">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="e15db-115">*Distribución* El enlace troncal SIP es un modelo de implementación en el que se implementa un tronco SIP local en uno o más sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="e15db-115">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="e15db-116">A continuación, el tráfico de VoIP se redirige directamente desde el sitio de sucursal a un proveedor de servicios sin pasar por el sitio central.</span><span class="sxs-lookup"><span data-stu-id="e15db-116">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="e15db-117">El enlace troncal SIP distribuido solo es necesario en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="e15db-117">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="e15db-118">Si la sucursal necesita una conectividad telefónica con funciones de supervivencia (por ejemplo, si se cae la red WAN).</span><span class="sxs-lookup"><span data-stu-id="e15db-118">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="e15db-119">Este requisito debe analizarse para cada sitio de sucursal; es posible que algunas de las sucursales requieran redundancia y conmutación por error, mientras que otras no.</span><span class="sxs-lookup"><span data-stu-id="e15db-119">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="e15db-120">Se requiere resistencia entre dos sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="e15db-120">Resiliency is required between two central sites.</span></span> <span data-ttu-id="e15db-121">Debe asegurarse de que un tronco SIP finalice en cada sitio central.</span><span class="sxs-lookup"><span data-stu-id="e15db-121">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="e15db-122">Por ejemplo, si tiene los sitios centrales de Dublín y Tukwila y ambos usan solo el tronco SIP de un sitio, si el tronco deja de funcionar, los usuarios del otro sitio no pueden realizar llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="e15db-122">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="e15db-123">El sitio de sucursal y el sitio central se encuentran en diferentes países o regiones.</span><span class="sxs-lookup"><span data-stu-id="e15db-123">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="e15db-124">Por motivos legales y de compatibilidad, necesita al menos un tronco SIP por cada país o región.</span><span class="sxs-lookup"><span data-stu-id="e15db-124">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="e15db-125">Así, por ejemplo, en la Unión Europea las comunicaciones no pueden dejar un país/región sin que termine localmente en un punto centralizado.</span><span class="sxs-lookup"><span data-stu-id="e15db-125">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="e15db-126">En función de la ubicación geográfica de los sitios y de la cantidad de tráfico que se prevé dentro de la empresa, es posible que no desee enrutar a todos los usuarios a través del tronco SIP central, o puede optar por enrutar a algunos usuarios a través de un tronco SIP en su sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="e15db-126">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="e15db-127">Para analizar sus necesidades, responda a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="e15db-127">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="e15db-128">¿Cuál es el tamaño de cada sitio (es decir, cuántos usuarios están habilitados para Enterprise Voice)?</span><span class="sxs-lookup"><span data-stu-id="e15db-128">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="e15db-129">¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?</span><span class="sxs-lookup"><span data-stu-id="e15db-129">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="e15db-130">Para saber si compensa implementar un enlace troncal SIP centralizado o distribuido, se necesita un análisis de costo-beneficio.</span><span class="sxs-lookup"><span data-stu-id="e15db-130">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="e15db-131">En algunos casos, puede ser mejor decantarse por el modelo de implementación distribuido aunque no sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e15db-131">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="e15db-132">En las implementaciones totalmente centralizadas, todo el tráfico de las sucursales se enruta a través de vínculos WAN.</span><span class="sxs-lookup"><span data-stu-id="e15db-132">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="e15db-133">En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefiera usar el enlace troncal SIP distribuido.</span><span class="sxs-lookup"><span data-stu-id="e15db-133">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="e15db-134">Por ejemplo, puede que desee implementar un servidor Standard Edition en un sitio de sucursal con Federación al sitio central, o puede que desee implementar una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña.</span><span class="sxs-lookup"><span data-stu-id="e15db-134">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e15db-135">Para obtener más información sobre el enlace troncal SIP distribuido, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e15db-135">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="e15db-136">Tipos de conexión de enlace troncal SIP compatibles</span><span class="sxs-lookup"><span data-stu-id="e15db-136">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="e15db-137">Lync Server admite los siguientes tipos de conexión para el enlace troncal SIP:</span><span class="sxs-lookup"><span data-stu-id="e15db-137">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="e15db-p109">La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no necesita red privada virtual (VPN). Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.</span><span class="sxs-lookup"><span data-stu-id="e15db-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="e15db-p110">En general, las conexiones privadas sin otro tipo de tráfico (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada) son el tipo de conexión más seguro y fiable. Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.</span><span class="sxs-lookup"><span data-stu-id="e15db-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="e15db-146">Internet es el tipo de conexión menos costoso, pero también el menos fiable.</span><span class="sxs-lookup"><span data-stu-id="e15db-146">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="e15db-147">La conexión a Internet es el único tipo de conexión de enlace troncal SIP de Lync Server que requiere VPN.</span><span class="sxs-lookup"><span data-stu-id="e15db-147">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="e15db-148">Selección de un tipo de conexión</span><span class="sxs-lookup"><span data-stu-id="e15db-148">Selecting a Connection Type</span></span>

<span data-ttu-id="e15db-149">El tipo de conexión de enlace troncal SIP más adecuado para su empresa depende de las necesidades y el presupuesto del que disponga.</span><span class="sxs-lookup"><span data-stu-id="e15db-149">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="e15db-p112">En las empresas medianas o grandes, la red MPLS ofrece el mejor servicio en general, ya que es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.</span><span class="sxs-lookup"><span data-stu-id="e15db-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="e15db-152">Las grandes empresas pueden necesitar una conexión privada de fibra óptica, T1, T3 o superior (E1, E3 o superior en la Unión Europea).</span><span class="sxs-lookup"><span data-stu-id="e15db-152">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="e15db-153">Para una empresa pequeña o un sitio de sucursal con un volumen de llamadas bajo, el enlace troncal SIP a través de Internet puede ser la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="e15db-153">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="e15db-154">Este tipo de conexión no es recomendable en sitios de tamaño medio o mayor.</span><span class="sxs-lookup"><span data-stu-id="e15db-154">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="e15db-155">Requisitos de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="e15db-155">Bandwidth Requirements</span></span>

<span data-ttu-id="e15db-p114">La cantidad de ancho de banda necesaria en la implementación dependerá de la capacidad de llamada (esto es, del número de llamadas simultáneas que se admite). Debe tener en cuenta la disponibilidad de ancho de banda para poder sacar el máximo partido a la capacidad contratada. Use la siguiente fórmula para calcular el requisito de ancho de banda máximo del tronco SIP:</span><span class="sxs-lookup"><span data-stu-id="e15db-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="e15db-159">Ancho de banda máximo del tronco SIP = Nº máx. de llamadas simultáneas x (64 kbps + tamaño de encabezado)</span><span class="sxs-lookup"><span data-stu-id="e15db-159">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e15db-160">El tamaño de encabezado es de 20 bytes como máximo.</span><span class="sxs-lookup"><span data-stu-id="e15db-160">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="e15db-161">Compatibilidad de códecs</span><span class="sxs-lookup"><span data-stu-id="e15db-161">Codec Support</span></span>

<span data-ttu-id="e15db-162">Lync Server 2013 solo admite los siguientes códecs:</span><span class="sxs-lookup"><span data-stu-id="e15db-162">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="e15db-163">G.711 Ley A (que se usa principalmente fuera de Norteamérica)</span><span class="sxs-lookup"><span data-stu-id="e15db-163">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="e15db-164">G.711 Ley µ (que se usa en Norteamérica)</span><span class="sxs-lookup"><span data-stu-id="e15db-164">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="e15db-165">Proveedor de servicios de telefonía de Internet</span><span class="sxs-lookup"><span data-stu-id="e15db-165">Internet Telephony Service Provider</span></span>

<span data-ttu-id="e15db-166">El modo en el que se implementa el lado del proveedor de servicios de una conexión basada en troncos SIP varía de un ITSP a otro.</span><span class="sxs-lookup"><span data-stu-id="e15db-166">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="e15db-167">Para obtener información acerca de la implementación, póngase en contacto con su proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="e15db-167">For deployment information, contact your service provider.</span></span> <span data-ttu-id="e15db-168">Para obtener una lista de los proveedores de servicios de troncales SIP certificados, consulte el [sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="e15db-168">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="e15db-169">Para obtener más información acerca de los proveedores de enlaces troncales SIP certificados por Microsoft, póngase en contacto con su representante de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e15db-169">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e15db-p116">Debe usar un proveedor de servicios certificado por Microsoft para asegurarse de que su ITSP admite todas las funcionalidades que pasan por el tronco SIP (por ejemplo, la configuración y administración de sesiones y la compatibilidad con todos los servicios de VoIP ampliados). El Soporte técnico de Microsoft no se amplía para configuraciones que usan proveedores no certificados. Si está usando actualmente un proveedor de servicios de Internet que no está certificado para enlaces troncales SIP, puede seguir usando dicho proveedor como ISP y usar un proveedor certificado por Microsoft para enlaces troncales SIP.</span><span class="sxs-lookup"><span data-stu-id="e15db-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


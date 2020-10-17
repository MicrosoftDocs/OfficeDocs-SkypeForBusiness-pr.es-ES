---
title: 'Lync Server 2013: opciones de implementación de la puerta de enlace RTC'
description: 'Lync Server 2013: opciones de implementación de la puerta de enlace RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565596"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="f63d3-103">Opciones de implementación de la puerta de enlace RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f63d3-103">PSTN gateway deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f63d3-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f63d3-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="f63d3-105">Puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="f63d3-105">PSTN Gateways</span></span>

<span data-ttu-id="f63d3-106">Las puertas de enlace de red telefónica conmutada (RTC) son componentes de hardware de terceros que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y la RTC ya sea de forma directa o mediante una conexión a troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="f63d3-106">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="f63d3-107">En cualquier topología, la puerta de enlace finaliza la RTC.</span><span class="sxs-lookup"><span data-stu-id="f63d3-107">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="f63d3-108">La puerta de enlace se aísla en su propia subred y está conectada a la red de la empresa a través del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f63d3-108">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="f63d3-109">Una empresa con varios sitios, normalmente deberá implementar una o más puertas de enlace en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="f63d3-109">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="f63d3-110">Los sitios de sucursal pueden conectarse a la RTC a través de una puerta de enlace o a través de una aplicación de sucursal con funciones de supervivencia, que combina la puerta de enlace y los servidores en un único cuadro.</span><span class="sxs-lookup"><span data-stu-id="f63d3-110">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="f63d3-111">Si los sitios de sucursal usan una puerta de enlace, es necesario un registrador y un servidor de mediación en el sitio, a menos que el vínculo WAN sea resistente.</span><span class="sxs-lookup"><span data-stu-id="f63d3-111">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="f63d3-112">Uno o varios servidores de mediación, que se colocan en servidores front-end, pueden enrutar las llamadas de una o más puertas de enlace en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="f63d3-112">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="f63d3-113">Se recomienda que el registrador, el servidor de mediación y la puerta de enlace necesarios en el sitio se implementen como una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="f63d3-113">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="f63d3-114">La determinación del número, el tamaño y la ubicación de las puertas de enlace RTC es quizá la decisión más importante y costosa que debe tomarse al planear la infraestructura de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f63d3-114">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="f63d3-p103">A continuación presentamos las principales preguntas que hay que plantearse. Recuerde que las respuestas a estas preguntas están todas interrelacionadas</span><span class="sxs-lookup"><span data-stu-id="f63d3-p103">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="f63d3-p104">¿Cuántas puertas de enlace RTC se necesitan? La respuesta depende del número de usuarios, el número previsto de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita una).</span><span class="sxs-lookup"><span data-stu-id="f63d3-p104">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="f63d3-p105">¿Qué tamaño deben tener las puertas de enlace? La respuesta depende del número de usuarios en el sitio y en la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p105">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="f63d3-p106">¿Dónde deben colocarse las puertas de enlace? La respuesta depende en parte de la topología y en parte de la distribución geográfica de la organización.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p106">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="f63d3-123">Tenga en cuenta también las opciones de topología de la puerta de enlace (para más información, vea Topologías de puerta de enlace más adelante, en este tema).</span><span class="sxs-lookup"><span data-stu-id="f63d3-123">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="f63d3-124">Compatibilidad con troncos M:N</span><span class="sxs-lookup"><span data-stu-id="f63d3-124">M:N Trunk Support</span></span>

<span data-ttu-id="f63d3-125">Los servidores de mediación pueden enrutar las llamadas a través de varias puertas de enlace, controladores de borde de sesión (SBCs) proporcionados por proveedores de servicios de telefonía por Internet o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="f63d3-125">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="f63d3-126">Además, varios servidores de mediación del grupo pueden interactuar con varias puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="f63d3-126">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="f63d3-127">La ruta lógica definida entre un servidor de mediación y la puerta de enlace se denomina *tronco*.</span><span class="sxs-lookup"><span data-stu-id="f63d3-127">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="f63d3-128">Cuando un usuario interno realiza una llamada RTC, la lógica de enrutamiento de salida en el grupo de servidores front-end elige el tronco que se va a redirigir en todas las combinaciones posibles que pueden estar disponibles para enrutar esa llamada en particular.</span><span class="sxs-lookup"><span data-stu-id="f63d3-128">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="f63d3-129">Con el equilibrio de carga de DNS, si una llamada no consigue alcanzar una puerta de enlace debido a un problema con un servidor de mediación en particular en el grupo, la llamada se reintentará en un servidor de mediación alternativo del grupo.</span><span class="sxs-lookup"><span data-stu-id="f63d3-129">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="f63d3-130">Para obtener más información sobre cómo planear varias puertas de enlace, consulte [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="f63d3-130">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="f63d3-131">Para obtener más información sobre otras mejoras de enrutamiento saliente, consulte [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="f63d3-131">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="f63d3-132">Topologías de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="f63d3-132">Gateway Topologies</span></span>

<span data-ttu-id="f63d3-133">Cuando vaya a responder las preguntas fundamentales de la implementación de puertas de enlace, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f63d3-133">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="f63d3-134">Cuente los sitios en los que desea proporcionar conectividad con RTC mediante la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f63d3-134">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="f63d3-135">Calcule el tráfico en cada sitio (número de usuarios y promedio de llamadas por hora y por usuario).</span><span class="sxs-lookup"><span data-stu-id="f63d3-135">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="f63d3-136">Implemente una o varias puertas de enlace en cada sitio para administrar el tráfico previsto.</span><span class="sxs-lookup"><span data-stu-id="f63d3-136">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="f63d3-137">La topología de puertas de enlace distribuidas resultante se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="f63d3-137">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="f63d3-138">**Topología de puertas de enlace distribuida**</span><span class="sxs-lookup"><span data-stu-id="f63d3-138">**Distributed gateway topology**</span></span>

<span data-ttu-id="f63d3-139">![Diagrama de topología de puerta de enlace distribuida](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagrama de topología de puerta de enlace distribuida")</span><span class="sxs-lookup"><span data-stu-id="f63d3-139">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="f63d3-p108">Con esta topología, las llamadas entre los empleados de cada sitio y entre los sitios se redirigen a través de la intranet de la compañía. Las llamadas a la RTC se redirigen a través de la red IP de la empresa a las puertas de enlace que se encuentran más cerca de la ubicación de los números de destino. No obstante, ¿qué sucede si la organización admite docenas, cientos o incluso miles de sitios distribuidos por uno o varios continentes, como es el caso de muchas entidades financieras y otras empresas de gran tamaño? En esos casos, no es práctico implementar una puerta de enlace independiente en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p108">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="f63d3-143">Para solucionar este problema, muchas compañías grandes prefieren implementar uno o varios sitios centrales de telefonía grandes, tal como se muestra en la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="f63d3-143">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="f63d3-144">**Topología de sitio central de telefonía**</span><span class="sxs-lookup"><span data-stu-id="f63d3-144">**Telephony central site topology**</span></span>

<span data-ttu-id="f63d3-145">![Topología de puerta de enlace de centro de datos](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topología de puerta de enlace de centro de datos")</span><span class="sxs-lookup"><span data-stu-id="f63d3-145">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="f63d3-146">En esta topología, se implementan varias puertas de enlace grandes suficientes para dar cabida a la carga de usuarios anticipada en cada sitio central.</span><span class="sxs-lookup"><span data-stu-id="f63d3-146">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="f63d3-147">El proveedor de servicios de telefonía de la compañía transfiere a un sitio central todas las llamadas para los usuarios de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f63d3-147">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="f63d3-148">La lógica de enrutamiento en el sitio central determina si la llamada se debe enrutar a través de la intranet o de la RTC.</span><span class="sxs-lookup"><span data-stu-id="f63d3-148">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="f63d3-149">Ubicación de las puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="f63d3-149">Gateway Location</span></span>

<span data-ttu-id="f63d3-p110">La ubicación de las puertas de enlace también puede determinar los tipos de puertas de enlace elegidos y su configuración. Hay docenas de protocolos RTC, pero ninguno es un estándar mundial. Si todas las puertas de enlace se encuentran en un solo país o región, esto no supone un problema. Ahora bien, si se colocan puertas de enlace en varios países o regiones, cada una de ellas debe configurarse según las normas RTC de cada país o región. Es más, las puertas de enlace certificadas para, por ejemplo, Canadá pueden no estar certificadas en la India, Brasil o la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p110">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="f63d3-154">Tamaño y número de las puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="f63d3-154">Gateway Size and Number</span></span>

<span data-ttu-id="f63d3-p111">Las puertas de enlace RTC que la mayoría de las organizaciones considerarán implementar varía entre 2 y 960 puertos. (Hay puertas de enlace incluso más grandes, pero las usan principalmente los proveedores de servicios de telefonía.) A la hora de valorar el número de puertos que la organización necesita, siga estas directrices:</span><span class="sxs-lookup"><span data-stu-id="f63d3-p111">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="f63d3-p112">Las organizaciones con necesidades de telefonía reducidas (una llamada de RTC por usuario y por hora) deben asignar un puerto por cada quince usuarios. Por ejemplo, si hay veinte usuarios, se necesitará una puerta de enlace con dos puertos.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p112">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="f63d3-p113">Las organizaciones con necesidades de telefonía moderadas (dos llamadas de RTC por usuario y por hora) deben asignar un puerto por cada diez usuarios. Por ejemplo, si hay cien usuarios, se necesitará un total de diez puertos asignados a una o varias puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p113">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="f63d3-p114">Las organizaciones con grandes necesidades de telefonía (tres o más llamadas de RTC por usuario y por hora) deben asignar un puerto por cada cinco usuarios. Por ejemplo, si hay 47 000 usuarios, se necesitarán 9400 puertos repartidos entre al menos diez puertas de enlace grandes.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p114">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="f63d3-163">Se pueden adquirir puertos adicionales a medida que aumenta el número de usuarios o el tráfico de la organización.</span><span class="sxs-lookup"><span data-stu-id="f63d3-163">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="f63d3-p115">Sea cual sea el número de usuarios, existe la opción de implementar menos puertas de enlace grandes o más puertas de enlace pequeñas. Como regla general, se recomienda un mínimo de dos puertas de enlace para mantener la disponibilidad si una de ellas deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="f63d3-p115">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="f63d3-166">Cada puerta de enlace RTC que implemente debe tener al menos un servidor de mediación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f63d3-166">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


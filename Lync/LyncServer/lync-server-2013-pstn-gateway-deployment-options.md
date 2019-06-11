---
title: 'Lync Server 2013: Opciones de implementación de la puerta de enlace RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="84843-102">Opciones de implementación de la puerta de enlace RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84843-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84843-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="84843-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="84843-104">Puertas de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="84843-104">PSTN Gateways</span></span>

<span data-ttu-id="84843-105">Las puertas de enlace de red de telefonía pública conmutada (RTC) son componentes de hardware de terceros que traducen las señales y los medios entre la infraestructura de telefonía IP empresarial y la RTC, ya sea directamente o a través de una conexión a los troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="84843-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="84843-106">En cualquiera de las dos topologías, la puerta de enlace finaliza la RTC.</span><span class="sxs-lookup"><span data-stu-id="84843-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="84843-107">La puerta de enlace está aislada en su propia subred y está conectada a la red de la empresa a través del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="84843-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="84843-108">Una empresa con varios sitios normalmente implementaría una o más puertas de enlace en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="84843-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="84843-109">Los sitios de sucursales se pueden conectar a la RTC a través de una puerta de enlace o a través de un equipo de sucursales con la supervivencia, que combina puerta de enlace y servidores en un único cuadro.</span><span class="sxs-lookup"><span data-stu-id="84843-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="84843-110">Si los sitios de sucursal usan una puerta de enlace, se necesita un registrador y un servidor de mediación en el sitio, a menos que el vínculo WAN sea resistente.</span><span class="sxs-lookup"><span data-stu-id="84843-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="84843-111">Uno o varios servidores de mediación, que se colocan en servidores front-end, pueden enrutar las llamadas de una o más puertas de enlace en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="84843-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="84843-112">Recomendamos que el registrador, el servidor de mediación y la puerta de enlace necesaria en el sitio se implementen como un equipo de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="84843-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="84843-113">Determinar el número, el tamaño y la ubicación de las puertas de enlace RTC es quizás la decisión más importante y costosa que debe tomarse al planear la infraestructura de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="84843-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="84843-114">Estas son las principales preguntas que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="84843-114">Here are the main questions to consider.</span></span> <span data-ttu-id="84843-115">Tenga en cuenta que las respuestas a estas preguntas son totalmente interdependientes</span><span class="sxs-lookup"><span data-stu-id="84843-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="84843-116">¿Cuántas puertas de enlace RTC se necesitan?</span><span class="sxs-lookup"><span data-stu-id="84843-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="84843-117">La respuesta depende del número de usuarios, el número anticipado de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita uno).</span><span class="sxs-lookup"><span data-stu-id="84843-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="84843-118">¿Qué tamaño deberían tener las puertas de enlace?</span><span class="sxs-lookup"><span data-stu-id="84843-118">What size should the gateways be?</span></span> <span data-ttu-id="84843-119">La respuesta depende del número de usuarios del sitio y de la carga de tráfico.</span><span class="sxs-lookup"><span data-stu-id="84843-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="84843-120">¿Dónde se deben ubicar los gateways?</span><span class="sxs-lookup"><span data-stu-id="84843-120">Where should the gateways be located?</span></span> <span data-ttu-id="84843-121">La respuesta depende en parte de la topología y en parte de la distribución geográfica de su organización.</span><span class="sxs-lookup"><span data-stu-id="84843-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="84843-122">También debe tener en cuenta las opciones de topología de la puerta de enlace (para obtener información detallada, vea topologías de puertas de enlace más adelante en este tema).</span><span class="sxs-lookup"><span data-stu-id="84843-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="84843-123">Compatibilidad con troncos M:N</span><span class="sxs-lookup"><span data-stu-id="84843-123">M:N Trunk Support</span></span>

<span data-ttu-id="84843-124">Los servidores de mediación pueden enrutar las llamadas a través de varias puertas de enlace, controladores de borde de sesión (SBCs) proporcionados por proveedores de servicios de telefonía por Internet o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="84843-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="84843-125">Además, varios servidores de mediación en el grupo pueden interactuar con varias puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="84843-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="84843-126">La ruta lógica definida entre un servidor de mediación y la puerta de enlace se denomina *troncal*.</span><span class="sxs-lookup"><span data-stu-id="84843-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="84843-127">Cuando un usuario interno realiza una llamada RTC, la lógica de enrutamiento de salida en el grupo de servidores front-end elige el tronco que se va a enrutar sobre todas las combinaciones posibles que pueden estar disponibles para enrutar esa llamada en particular.</span><span class="sxs-lookup"><span data-stu-id="84843-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="84843-128">Con el equilibrio de carga de DNS, si una llamada no logra alcanzar una puerta de enlace debido a un problema con un servidor de mediación en particular en el grupo, la llamada se volverá a intentar con un servidor de mediación alternativo en el grupo.</span><span class="sxs-lookup"><span data-stu-id="84843-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="84843-129">Para obtener más información sobre la planeación de varias puertas de enlace, consulte [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="84843-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="84843-130">Para obtener más información sobre otras mejoras de enrutamiento saliente, vea [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="84843-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="84843-131">Topologías de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="84843-131">Gateway Topologies</span></span>

<span data-ttu-id="84843-132">Cuando considere las preguntas fundamentales de la implementación de puertas de enlace, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="84843-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="84843-133">Contar los sitios en los que desea proporcionar conectividad RTC mediante telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="84843-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="84843-134">Estimar el tráfico de cada sitio (número de usuarios y número promedio de llamadas por hora por usuario).</span><span class="sxs-lookup"><span data-stu-id="84843-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="84843-135">Implemente una o más puertas de enlace en cada sitio para controlar el tráfico anticipado.</span><span class="sxs-lookup"><span data-stu-id="84843-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="84843-136">La topología de la puerta de enlace distribuida resultante se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="84843-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="84843-137">**Topología de puerta de enlace distribuida**</span><span class="sxs-lookup"><span data-stu-id="84843-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="84843-138">![Diagrama de topología de puerta de enlace distribuida] (images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagrama de topología de puerta de enlace distribuida")</span><span class="sxs-lookup"><span data-stu-id="84843-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="84843-139">Con esta topología, las llamadas entre los trabajadores de cada sitio y entre sitios se enrutan a través de la intranet.</span><span class="sxs-lookup"><span data-stu-id="84843-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="84843-140">Las llamadas a la RTC se enrutan a través de la red IP de la empresa a las puertas de enlace que están más cerca de la ubicación de los números de destino. Pero, ¿qué sucede si su organización admite decenas, cientos o incluso miles de sitios distribuidos en uno o más continentes, ya que muchas instituciones financieras y otras grandes empresas sí lo hacen?</span><span class="sxs-lookup"><span data-stu-id="84843-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="84843-141">En estos casos, no es práctico implementar una puerta de enlace independiente en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="84843-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="84843-142">Para solucionar este problema, muchas de las grandes empresas prefieren implementar uno o varios sitios centrales de telefonía grandes, tal y como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="84843-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="84843-143">**Topología de sitio central de telefonía**</span><span class="sxs-lookup"><span data-stu-id="84843-143">**Telephony central site topology**</span></span>

<span data-ttu-id="84843-144">![Topología de puerta de enlace de centro de datos] (images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topología de puerta de enlace de centro de datos")</span><span class="sxs-lookup"><span data-stu-id="84843-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="84843-145">En esta topología, se implementan varias puertas de enlace grandes suficientes para dar cabida a la carga de usuarios prevista en cada sitio central.</span><span class="sxs-lookup"><span data-stu-id="84843-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="84843-146">El proveedor de servicios telefónicos de la empresa reenvía todas las llamadas a los usuarios de la empresa a un sitio central.</span><span class="sxs-lookup"><span data-stu-id="84843-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="84843-147">La lógica de enrutamiento en el sitio central determina si la llamada se debe enrutar a través de la intranet o de la RTC.</span><span class="sxs-lookup"><span data-stu-id="84843-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="84843-148">Ubicación de la puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="84843-148">Gateway Location</span></span>

<span data-ttu-id="84843-149">La ubicación de la puerta de enlace también puede determinar los tipos de puertas de enlace que elija y cómo se configuran.</span><span class="sxs-lookup"><span data-stu-id="84843-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="84843-150">Hay docenas de protocolos de RTC, ninguno de los cuales es un estándar de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="84843-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="84843-151">Si todas las puertas de enlace están ubicadas en un solo país o región, esto no es un problema, pero si encuentra puertas de enlace en varios países o regiones, cada una de ellas debe estar configurada de acuerdo con los estándares de la RTC de ese país o región.</span><span class="sxs-lookup"><span data-stu-id="84843-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="84843-152">Además, las puertas de enlace que están certificadas para funcionar, por ejemplo, Canadá, pueden no estar certificadas en India, Brasil ni la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="84843-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="84843-153">Número y tamaño de la puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="84843-153">Gateway Size and Number</span></span>

<span data-ttu-id="84843-154">Las puertas de enlace RTC que la mayoría de las organizaciones considerará para implementar intervalos de 2 a tan sólo puertos de 960.</span><span class="sxs-lookup"><span data-stu-id="84843-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="84843-155">(Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía). Al estimar el número de puertos que necesita su organización, siga estas pautas:</span><span class="sxs-lookup"><span data-stu-id="84843-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="84843-156">Las organizaciones con uso de telefonía leve (una llamada de RTC por usuario por hora) deben asignar un puerto por cada 15 usuarios.</span><span class="sxs-lookup"><span data-stu-id="84843-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="84843-157">Por ejemplo, si tiene 20 usuarios, necesitará una puerta de enlace con dos puertos.</span><span class="sxs-lookup"><span data-stu-id="84843-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="84843-158">Las organizaciones con uso moderado de telefonía (dos llamadas RTC por usuario por hora) deben asignar un puerto por cada 10 usuarios.</span><span class="sxs-lookup"><span data-stu-id="84843-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="84843-159">Por ejemplo, si tiene 100 usuarios, necesitará un total de 10 puertos asignados entre una o más puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="84843-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="84843-160">Las organizaciones con uso intensivo de telefonía (tres o más llamadas RTC por usuario por hora) deben asignar un puerto por cada cinco usuarios.</span><span class="sxs-lookup"><span data-stu-id="84843-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="84843-161">Por ejemplo, si tiene 47.000 usuarios, necesitará un total de 9.400 puertos asignados entre al menos 10 puertas de enlace grandes.</span><span class="sxs-lookup"><span data-stu-id="84843-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="84843-162">Se pueden adquirir puertos adicionales a medida que aumenta el número de usuarios o la cantidad de tráfico de la organización.</span><span class="sxs-lookup"><span data-stu-id="84843-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="84843-163">Para cualquier número de usuarios que deba admitir, tiene la opción de implementar menos puertas de enlace, más grandes o más pequeñas.</span><span class="sxs-lookup"><span data-stu-id="84843-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="84843-164">Como regla, se recomienda usar un mínimo de dos puertas de enlace para una organización para mantener la disponibilidad si una de ellas falla.</span><span class="sxs-lookup"><span data-stu-id="84843-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="84843-165">Cada puerta de enlace RTC que implemente debe tener al menos un servidor de mediación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="84843-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


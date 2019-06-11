---
title: 'Lync Server 2013: Componentes y topologías para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="ccce9-102">Componentes y topologías para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccce9-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccce9-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ccce9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ccce9-104">En este tema se describen los componentes de los que depende el servidor de mediación y las topologías en las que se puede implementar el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ccce9-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="ccce9-105">Dependencias</span><span class="sxs-lookup"><span data-stu-id="ccce9-105">Dependencies</span></span>

<span data-ttu-id="ccce9-106">El servidor de mediación tiene las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="ccce9-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="ccce9-107">**Registro.**</span><span class="sxs-lookup"><span data-stu-id="ccce9-107">**Registrar.**</span></span> <span data-ttu-id="ccce9-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ccce9-108">Required.</span></span> <span data-ttu-id="ccce9-109">El registrador es el próximo salto para la señalización en las interacciones del servidor de mediación con la red de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ccce9-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="ccce9-110">Tenga en cuenta que el servidor de mediación se puede poner en un servidor front-end junto con el registrador, además de instalarse en un grupo independiente que solo contiene servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="ccce9-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="ccce9-111">El registrador se colocará con un servidor de mediación y una puerta de enlace RTC en una aplicación de rama superviviente.</span><span class="sxs-lookup"><span data-stu-id="ccce9-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="ccce9-112">**Servidor de supervisión.**</span><span class="sxs-lookup"><span data-stu-id="ccce9-112">**Monitoring Server.**</span></span> <span data-ttu-id="ccce9-113">Opcional, pero muy recomendable.</span><span class="sxs-lookup"><span data-stu-id="ccce9-113">Optional but highly recommended.</span></span> <span data-ttu-id="ccce9-114">El servidor de supervisión permite que el servidor de mediación grabe métricas de calidad asociadas a sus sesiones de medios.</span><span class="sxs-lookup"><span data-stu-id="ccce9-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="ccce9-115">**Servidor perimetral.**</span><span class="sxs-lookup"><span data-stu-id="ccce9-115">**Edge Server.**</span></span> <span data-ttu-id="ccce9-116">Necesario para la compatibilidad con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ccce9-116">Required for external user support.</span></span> <span data-ttu-id="ccce9-117">El servidor perimetral permite que el servidor de mediación interactúe con los usuarios que se encuentran detrás de un NAT o firewall.</span><span class="sxs-lookup"><span data-stu-id="ccce9-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="ccce9-118">Topologías</span><span class="sxs-lookup"><span data-stu-id="ccce9-118">Topologies</span></span>

<span data-ttu-id="ccce9-119">Lync Server 2013, el servidor de mediación se encuentra de forma predeterminada con una instancia del registrador en un servidor Standard Edition, un grupo front-end o una aplicación de rama Reactivable.</span><span class="sxs-lookup"><span data-stu-id="ccce9-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="ccce9-120">Todos los servidores de mediación de un grupo de servidores front-end se deben configurar de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="ccce9-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="ccce9-121">Cuando el rendimiento es un problema, puede ser preferible implementar uno o varios servidores de mediación en un grupo independiente dedicado.</span><span class="sxs-lookup"><span data-stu-id="ccce9-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="ccce9-122">O bien, si va a implementar una Troncalización SIP, le recomendamos que implemente un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="ccce9-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="ccce9-123">Si implementa conexiones SIP directas en una puerta de enlace PSTN calificada que admite la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="ccce9-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="ccce9-124">No es necesario un grupo de servidores de mediación independiente porque las puertas de enlace válidas son capaces de equilibrar la carga de DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.</span><span class="sxs-lookup"><span data-stu-id="ccce9-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="ccce9-125">También le recomendamos que Collocate el servidor de mediación en un grupo de servidores front-end cuando haya implementado PBX IP o conecte con un controlador de borde de sesión (SBC) de un proveedor de servicios de telefonía por Internet, siempre que se cumpla cualquiera de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="ccce9-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="ccce9-126">El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.</span><span class="sxs-lookup"><span data-stu-id="ccce9-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="ccce9-127">El IP-PBX no admite la omisión de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas a las que no se aplica la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="ccce9-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="ccce9-128">Puede usar la herramienta de planeación de Microsoft Lync Server 2013 para evaluar si el grupo de servidores front-end en el que desea Collocate el servidor de mediación puede controlar la carga.</span><span class="sxs-lookup"><span data-stu-id="ccce9-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="ccce9-129">Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="ccce9-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="ccce9-130">Para más información sobre qué topología implementar, vea [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="ccce9-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="ccce9-131">En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados a través de un vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="ccce9-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="ccce9-132">El servidor de mediación se encuentra en el registrador de un grupo de servidores front-end en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="ccce9-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="ccce9-133">Los servidores de mediación del sitio 1 controlan la puerta de enlace PSTN en el sitio 1 y la puerta de enlace en el sitio 2.</span><span class="sxs-lookup"><span data-stu-id="ccce9-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="ccce9-134">En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen la omisión habilitada.</span><span class="sxs-lookup"><span data-stu-id="ccce9-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="ccce9-135">**Ejemplo de sitios conectados por medio de un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**</span><span class="sxs-lookup"><span data-stu-id="ccce9-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="ccce9-136">![Topología de voz con puerta de enlace WAN del servidor de mediación] (images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topología de voz con puerta de enlace WAN del servidor de mediación")</span><span class="sxs-lookup"><span data-stu-id="ccce9-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="ccce9-137">La siguiente figura muestra una topología simple en la que el servidor de mediación se encuentra con el registrador en el grupo front-end en el sitio 1 y tiene una conexión SIP directa con IP-PBX en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="ccce9-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="ccce9-138">En esta ilustración, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2.</span><span class="sxs-lookup"><span data-stu-id="ccce9-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="ccce9-139">Supongamos que los usuarios de Lync existen en los dos sitios 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="ccce9-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="ccce9-140">También se supone que el IP-PBX tiene un procesador de medios asociado al que deben atravesarse todos los medios originarios de los puntos de conexión de Lync antes de enviarlos a los puntos de conexión multimedia controlados por el IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ccce9-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="ccce9-141">En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a la puerta de enlace RTC y la PBX tienen la omisión de medios habilitada.</span><span class="sxs-lookup"><span data-stu-id="ccce9-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="ccce9-142">**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**</span><span class="sxs-lookup"><span data-stu-id="ccce9-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="ccce9-143">![Servidor de mediación de voz PBX PBX] (images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Servidor de mediación de voz PBX PBX")</span><span class="sxs-lookup"><span data-stu-id="ccce9-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="ccce9-144">Para más información sobre la planeación de topologías PBX, vea [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) y [Opciones de implementación de SIP directo en Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="ccce9-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="ccce9-145">En la última ilustración de este tema se muestra una topología en la que el servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="ccce9-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="ccce9-146">Para obtener más información sobre las topologías de tronco de SIP, consulte [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="ccce9-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


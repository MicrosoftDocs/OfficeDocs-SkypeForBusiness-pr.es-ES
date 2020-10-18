---
title: 'Lync Server 2013: componentes y topologías para el servidor de mediación'
description: 'Lync Server 2013: componentes y topologías para el servidor de mediación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: befd244508db9c98d565a76301e150da98708522
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576856"
---
# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="a669b-103">Componentes y topologías para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a669b-103">Components and topologies for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a669b-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a669b-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a669b-105">En este tema se describen los componentes de los que depende el servidor de mediación y las topologías en las que se puede implementar el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a669b-105">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="a669b-106">Dependencias</span><span class="sxs-lookup"><span data-stu-id="a669b-106">Dependencies</span></span>

<span data-ttu-id="a669b-107">El servidor de mediación tiene las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="a669b-107">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="a669b-108">**Dominios.**</span><span class="sxs-lookup"><span data-stu-id="a669b-108">**Registrar.**</span></span> <span data-ttu-id="a669b-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a669b-109">Required.</span></span> <span data-ttu-id="a669b-110">El registrador es el próximo salto para la señalización en las interacciones del servidor de mediación con la red Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a669b-110">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="a669b-111">Tenga en cuenta que el servidor de mediación se puede combinar en un servidor front-end junto con el registrador, además de estar instalado en un grupo independiente que solo consista en servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="a669b-111">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="a669b-112">El registrador se combina con un servidor de mediación y una puerta de enlace RTC en una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a669b-112">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="a669b-113">**Servidor de supervisión.**</span><span class="sxs-lookup"><span data-stu-id="a669b-113">**Monitoring Server.**</span></span> <span data-ttu-id="a669b-114">Opcional pero muy recomendable.</span><span class="sxs-lookup"><span data-stu-id="a669b-114">Optional but highly recommended.</span></span> <span data-ttu-id="a669b-115">El servidor de supervisión permite que el servidor de mediación registre las métricas de calidad asociadas con sus sesiones de medios.</span><span class="sxs-lookup"><span data-stu-id="a669b-115">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="a669b-116">**Servidor perimetral.**</span><span class="sxs-lookup"><span data-stu-id="a669b-116">**Edge Server.**</span></span> <span data-ttu-id="a669b-117">Obligatorio para la compatibilidad con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="a669b-117">Required for external user support.</span></span> <span data-ttu-id="a669b-118">El servidor perimetral permite que el servidor de mediación interactúe con los usuarios que se encuentren detrás de un firewall o NAT.</span><span class="sxs-lookup"><span data-stu-id="a669b-118">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="a669b-119">Topologías</span><span class="sxs-lookup"><span data-stu-id="a669b-119">Topologies</span></span>

<span data-ttu-id="a669b-120">El servidor de mediación de Lync Server 2013, que se combina de forma predeterminada con una instancia del registrador en un servidor Standard Edition, un grupo de servidores front-end o una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a669b-120">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="a669b-121">Todos los servidores de mediación de un grupo de servidores front-end deben estar configurados de forma idéntica.</span><span class="sxs-lookup"><span data-stu-id="a669b-121">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="a669b-122">Cuando el rendimiento es un problema, es preferible implementar uno o varios servidores de mediación en un grupo independiente dedicado.</span><span class="sxs-lookup"><span data-stu-id="a669b-122">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="a669b-123">O bien, si va a implementar un enlace troncal SIP, le recomendamos que implemente un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="a669b-123">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a669b-124">Si implementa conexiones SIP directas a una puerta de enlace RTC calificada que admita la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="a669b-124">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="a669b-125">No se necesita un servidor de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.</span><span class="sxs-lookup"><span data-stu-id="a669b-125">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="a669b-126">También recomendamos que instale el servidor de mediación en un grupo de servidores front-end cuando haya implementado sistemas PBX IP o que se conecte a un Controlador de borde de sesión (SBC) de servidor de telefonía por Internet, siempre y cuando se cumplan algunas de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="a669b-126">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="a669b-127">El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.</span><span class="sxs-lookup"><span data-stu-id="a669b-127">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="a669b-128">La IP-PBX no admite el desvío de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas en las que no se aplique el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="a669b-128">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="a669b-129">Puede usar la herramienta de planeación 2013 de Microsoft Lync Server para evaluar si el grupo de servidores front-end en el que desea combinar el servidor de mediación puede controlar la carga.</span><span class="sxs-lookup"><span data-stu-id="a669b-129">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="a669b-130">Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="a669b-130">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a669b-131">Para obtener información detallada sobre la topología que se va a implementar, consulte [directrices de implementación para servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="a669b-131">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="a669b-132">En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados mediante un vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="a669b-132">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="a669b-133">El servidor de mediación se combina con el registrador en un grupo de servidores front-end en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="a669b-133">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="a669b-134">Los servidores de mediación en el sitio 1 controlan tanto la puerta de enlace RTC en el sitio 1 como la puerta de enlace en el sitio 2.</span><span class="sxs-lookup"><span data-stu-id="a669b-134">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="a669b-135">En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen el desvío habilitado.</span><span class="sxs-lookup"><span data-stu-id="a669b-135">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="a669b-136">**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**</span><span class="sxs-lookup"><span data-stu-id="a669b-136">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="a669b-137">![Topología de voz con puerta de enlace WAN del servidor de mediación](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topología de voz con puerta de enlace WAN del servidor de mediación")</span><span class="sxs-lookup"><span data-stu-id="a669b-137">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="a669b-138">En la siguiente figura se muestra una topología sencilla en la que el servidor de mediación se combina con el registrador del grupo de servidores front-end en el sitio 1 y tiene una conexión SIP directa con el IP-PBX en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="a669b-138">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="a669b-139">En esta figura, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2.</span><span class="sxs-lookup"><span data-stu-id="a669b-139">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="a669b-140">Supongamos que los usuarios de Lync existen en los sitios 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="a669b-140">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="a669b-141">Supongamos también que la IP-PBX tiene un procesador de medios asociado que debe atravesar todos los medios que provienen de los puntos de conexión de Lync antes de enviarlos a los extremos de medios controlados por la IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a669b-141">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="a669b-142">En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a la puerta de enlace RTC y al PBX tienen el desvío de medios habilitado.</span><span class="sxs-lookup"><span data-stu-id="a669b-142">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="a669b-143">**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**</span><span class="sxs-lookup"><span data-stu-id="a669b-143">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="a669b-144">![Topología de voz servidor de mediación PBX para WAN](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Topología de voz servidor de mediación PBX para WAN")</span><span class="sxs-lookup"><span data-stu-id="a669b-144">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="a669b-145">Para obtener información detallada sobre la planeación de topologías PBX, consulte [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) y [Opciones de implementación SIP directa en Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="a669b-145">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="a669b-146">La última figura de este tema muestra una topología en la que el servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="a669b-146">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="a669b-147">Para obtener más información sobre las topologías de tronco SIP, consulte [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="a669b-147">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


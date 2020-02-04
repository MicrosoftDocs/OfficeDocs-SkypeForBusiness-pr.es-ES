---
title: 'Lync Server 2013: componente de servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363b277003d7ca1581475ec7c1197bb0f60ccfaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="f4466-102">Componente de servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4466-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4466-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f4466-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f4466-104">Debe implementar Lync Server 2013, servidor de mediación si implementa la carga de trabajo de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f4466-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="f4466-105">En esta sección se describen la funcionalidad básica, las dependencias, las topologías básicas y las directrices de planificación.</span><span class="sxs-lookup"><span data-stu-id="f4466-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="f4466-106">El servidor de mediación traduce la señalización y, en algunas configuraciones, multimedia entre su Lync Server 2013 interno, la infraestructura de telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="f4466-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="f4466-107">En el lado de Lync Server 2013, el servidor de mediación escucha en una única dirección de transporte TLS Mutual (MTLS).</span><span class="sxs-lookup"><span data-stu-id="f4466-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="f4466-108">En la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados a los troncos definidos en el documento de topología.</span><span class="sxs-lookup"><span data-stu-id="f4466-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="f4466-109">Todas las puertas de enlace calificadas necesitan compatibilidad con TLS, pero también pueden habilitar TCP.</span><span class="sxs-lookup"><span data-stu-id="f4466-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="f4466-110">TCP es compatible con las puertas de enlace que no son compatibles con TLS.</span><span class="sxs-lookup"><span data-stu-id="f4466-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="f4466-111">Si también tiene una central de conmutación (PBX) existente en su entorno, el servidor de mediación controla las llamadas entre los usuarios de voz de empresa y la PBX.</span><span class="sxs-lookup"><span data-stu-id="f4466-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="f4466-112">Si su PBX es IP-PBX, puede crear una conexión SIP directa entre la PBX y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f4466-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="f4466-113">Si su PBX es un PBX de división de tiempo (TDM), también debe implementar una puerta de enlace RTC entre el servidor de mediación y la PBX.</span><span class="sxs-lookup"><span data-stu-id="f4466-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="f4466-114">El servidor de mediación se encuentra en el servidor front-end de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f4466-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="f4466-115">El servidor de mediación también se puede implementar en un grupo independiente por razones de rendimiento o si implementa la Troncalización SIP, en cuyo caso se recomienda encarecidamente el grupo independiente.</span><span class="sxs-lookup"><span data-stu-id="f4466-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="f4466-116">Si implementa conexiones SIP directas en una puerta de enlace PSTN calificada que admite la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="f4466-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="f4466-117">No es necesario un grupo de servidores de mediación independiente porque las puertas de enlace válidas son capaces de equilibrar la carga de DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.</span><span class="sxs-lookup"><span data-stu-id="f4466-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="f4466-118">También le recomendamos que Collocate el servidor de mediación en un grupo de servidores front-end cuando haya implementado PBX IP o conecte con un controlador de borde de sesión (SBC) de un proveedor de servicios de telefonía por Internet, siempre que se cumpla cualquiera de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="f4466-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="f4466-119">El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.</span><span class="sxs-lookup"><span data-stu-id="f4466-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="f4466-120">El IP-PBX no admite la omisión de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas a las que no se aplica la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="f4466-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="f4466-121">Puede usar la herramienta de planeación de Microsoft Lync Server 2013 para evaluar si el grupo de servidores front-end en el que desea Collocate el servidor de mediación puede controlar la carga.</span><span class="sxs-lookup"><span data-stu-id="f4466-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="f4466-122">Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="f4466-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="f4466-123">Las funciones principales del servidor de mediación son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4466-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="f4466-124">Cifrar y descifrar SRTP en el servidor de Lync</span><span class="sxs-lookup"><span data-stu-id="f4466-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="f4466-125">Conversión de SIP a través de TCP (para puertas de enlace que no admiten TLS) a SIP a través de TLS Mutual</span><span class="sxs-lookup"><span data-stu-id="f4466-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="f4466-126">Traducción de transmisiones de medios entre Lync Server y Gateway peer of the Media Server</span><span class="sxs-lookup"><span data-stu-id="f4466-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="f4466-127">Conectar clientes que están fuera de la red a componentes de ICE internos, que permiten un recorrido multimedia de NAT y firewalls</span><span class="sxs-lookup"><span data-stu-id="f4466-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="f4466-128">Actuar como intermediario de los flujos de llamadas que no admite una puerta de enlace, como las llamadas de trabajadores remotos en un cliente de telefonía empresarial</span><span class="sxs-lookup"><span data-stu-id="f4466-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="f4466-129">En las implementaciones que incluyen el Troncalización SIP, al trabajar con el proveedor de servicios de Troncalización SIP para proporcionar compatibilidad con RTC, que elimina la necesidad de una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="f4466-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="f4466-130">La siguiente ilustración muestra los protocolos de señalización y multimedia que usa el servidor de mediación al comunicarse con una puerta de enlace PSTN básica y la infraestructura de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f4466-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="f4466-131">**Señalización y protocolos multimedia que usa el servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="f4466-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="f4466-132">![Diagrama de protocolos de servidor de mediación](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagrama de protocolos de servidor de mediación")</span><span class="sxs-lookup"><span data-stu-id="f4466-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4466-133">Si está usando TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace PSTN y el servidor de mediación, le recomendamos que tome medidas para garantizar la seguridad y la privacidad de la red.</span><span class="sxs-lookup"><span data-stu-id="f4466-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f4466-134">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f4466-134">In This Section</span></span>

  - [<span data-ttu-id="f4466-135">M:N troncal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4466-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="f4466-136">Control de admisión de llamadas y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4466-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="f4466-137">9-1-1 mejorado (E9-1-1) y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4466-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="f4466-138">Omisión de medios y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4466-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="f4466-139">Componentes y topologías para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4466-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="f4466-140">Instrucciones de implementación para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4466-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


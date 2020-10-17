---
title: 'Lync Server 2013: componentes y topologías para el enlace troncal SIP'
description: 'Lync Server 2013: componentes y topologías para el enlace troncal SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d9c826539084a539d3efe7f143c335ec6d8f62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549526"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="b2d37-103">Componentes y topologías para el enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2d37-103">Components and topologies for SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2d37-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b2d37-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b2d37-105">En la siguiente figura se muestra la topología de enlace troncal SIP en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2d37-105">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="b2d37-106">**Topología del enlace troncal SIP**</span><span class="sxs-lookup"><span data-stu-id="b2d37-106">**SIP trunking topology**</span></span>

<span data-ttu-id="b2d37-107">![Topología de enlace troncal SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topología de enlace troncal SIP")</span><span class="sxs-lookup"><span data-stu-id="b2d37-107">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="b2d37-p101">Como se muestra en el diagrama, se usa una red privada virtual (VPN) de IP para la conectividad entre la red empresarial y el proveedor de servicios de la red telefónica conmutada (RTC). El objetivo de esta red privada es proporcionar conectividad IP, mejorar la seguridad y obtener garantías (opcionales) de Calidad de servicio (QoS). Dada la naturaleza de una VPN, no necesita usar Seguridad de la capa de transporte (TLS) para el tráfico de señalización SIP ni el Protocolo de transporte en tiempo real seguro (SRTP) para el tráfico de medios. Las conexiones entre la empresa y el proveedor de servicios constan, por lo tanto, de conexiones TCP simples para SIP y el Protocolo de transporte en tiempo real (RTP) simple (sobre UDP) para los medios de túnel a través de una VPN de IP. Asegúrese de que todos los firewalls que hay entre los enrutadores de VPN tienen los puertos abiertos para permitir la comunicación de dichos enrutadores, y que las direcciones IP de los bordes externos de los enrutadores de VPN se pueden redirigir públicamente.</span><span class="sxs-lookup"><span data-stu-id="b2d37-p101">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b2d37-113">Consulte a su proveedor de servicios para saber si admite alta disponibilidad, incluida la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b2d37-113">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="b2d37-114">Si es así, tendrá que averiguar los procedimientos para instalarla.</span><span class="sxs-lookup"><span data-stu-id="b2d37-114">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="b2d37-115">Por ejemplo, ¿necesita configurar solo una dirección IP y un tronco SIP en cada servidor de mediación, o debe configurar varios troncos SIP en cada servidor de mediación?</span><span class="sxs-lookup"><span data-stu-id="b2d37-115">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="b2d37-116">Si tiene varios sitios centrales, pregunte también si el proveedor de servicios tiene la capacidad de habilitar conexiones hacia y desde otro sitio central.</span><span class="sxs-lookup"><span data-stu-id="b2d37-116">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b2d37-117">Para el enlace troncal SIP, se recomienda implementar servidores de mediación independientes.</span><span class="sxs-lookup"><span data-stu-id="b2d37-117">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="b2d37-118">Para obtener más información, consulte <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Defining Peers in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="b2d37-118">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="b2d37-119">Protección del servidor de mediación para el enlace troncal SIP</span><span class="sxs-lookup"><span data-stu-id="b2d37-119">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="b2d37-p104">Por motivos de seguridad, debe instalar una LAN virtual (VLAN) por cada conexión que haya entre ambos enrutadores de VPN. El proceso concreto para instalar una VLAN varía según el fabricante del enrutador. Para obtener información detallada, contacte con el proveedor de su enrutador.</span><span class="sxs-lookup"><span data-stu-id="b2d37-p104">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="b2d37-123">Se recomienda seguir estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="b2d37-123">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="b2d37-124">Configure una LAN virtual (VLAN) entre el servidor de mediación y el enrutador de VPN en la red perimetral (también denominada DMZ, zona desmilitarizada y subred filtrada).</span><span class="sxs-lookup"><span data-stu-id="b2d37-124">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="b2d37-125">No permita la difusión ni la transferencia de paquetes multidifusión desde el enrutador a la VLAN.</span><span class="sxs-lookup"><span data-stu-id="b2d37-125">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="b2d37-126">Bloquear todas las reglas de enrutamiento que enruten el tráfico del enrutador a cualquier lugar pero el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="b2d37-126">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="b2d37-127">Si usa un servidor de VPN, se recomienda seguir estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="b2d37-127">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="b2d37-128">Configure una VLAN entre el servidor VPN y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="b2d37-128">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="b2d37-129">No permita la difusión ni la transmisión de paquetes multidifusión desde el servidor de VPN a la VLAN.</span><span class="sxs-lookup"><span data-stu-id="b2d37-129">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="b2d37-130">Bloquee todas las reglas de enrutamiento que enruten el tráfico del servidor VPN hacia cualquier lugar y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="b2d37-130">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="b2d37-131">Cifre los datos de la VPN mediante encapsulación de enrutamiento genérico (GRE).</span><span class="sxs-lookup"><span data-stu-id="b2d37-131">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Troncalización SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="29ad2-102">Troncalización SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29ad2-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29ad2-103">_**Última modificación del tema:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="29ad2-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="29ad2-p101">El Protocolo de inicio de sesión (SIP) se usa para iniciar y administrar sesiones de comunicaciones de voz sobre IP (VoIP) del servicio telefónico básico y para otros servicios de comunicación en tiempo real, como la mensajería instantánea, las conferencias, la detección de presencia y los elementos multimedia. Esta sección ofrece información sobre la planificación para implementar *troncos SIP*, un tipo de conexión SIP que se extiende más allá del límite de la red local.</span><span class="sxs-lookup"><span data-stu-id="29ad2-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="29ad2-106">¿Qué es el enlace troncal SIP?</span><span class="sxs-lookup"><span data-stu-id="29ad2-106">What is SIP Trunking?</span></span>

<span data-ttu-id="29ad2-p102">Un tronco SIP es una conexión IP que establece un vínculo de comunicaciones SIP entre la organización y un proveedor de servicios de telefonía por Internet (ITSP) más allá del firewall. En general, los troncos SIP se usan para conectar el sitio central de la organización a un ITSP. En ciertos casos, se puede usar también el enlace troncal SIP para conectar un sitio de sucursal a un ITSP.</span><span class="sxs-lookup"><span data-stu-id="29ad2-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="29ad2-110">Troncos SIP en comparación con conexiones SIP directas</span><span class="sxs-lookup"><span data-stu-id="29ad2-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="29ad2-111">El término *tronco* deriva de la tecnología de circuitos conmutados.</span><span class="sxs-lookup"><span data-stu-id="29ad2-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="29ad2-112">Se refiere a una línea física dedicada que conecta el equipo de conmutación telefónica.</span><span class="sxs-lookup"><span data-stu-id="29ad2-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="29ad2-113">Como sus troncos predecesores, de multiplexación de la división horario (TDM), los troncos SIP son conexiones entre dos redes SIP independientes: Lync Server 2013 Enterprise y el ITSP.</span><span class="sxs-lookup"><span data-stu-id="29ad2-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="29ad2-114">A diferencia de los troncos de circuitos conmutados, los troncos SIP son conexiones virtuales que se pueden establecer sobre cualquiera de los tipos de conexión de enlaces troncales SIP compatibles.</span><span class="sxs-lookup"><span data-stu-id="29ad2-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="29ad2-115">Para obtener más información sobre los tipos de conexión compatibles, consulte [¿Cómo puedo implementar la Troncalización SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="29ad2-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="29ad2-116">Por otra parte, las conexiones SIP directas son conexiones SIP que no cruzan los límites de la red local (es decir, que se conectan a una puerta de enlace de la red telefónica conmutada [RTC] o a una central de conmutación [PBX] dentro de la red local).</span><span class="sxs-lookup"><span data-stu-id="29ad2-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="29ad2-117">Para obtener más información sobre cómo puede usar las conexiones SIP directas con Lync Server 2013, consulte [conexiones SIP directas en Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="29ad2-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="29ad2-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="29ad2-118">In This Section</span></span>

  - [<span data-ttu-id="29ad2-119">Información general sobre los enlaces troncales SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29ad2-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="29ad2-120">¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="29ad2-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="29ad2-121">Componentes y topologías para el enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29ad2-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="29ad2-122">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29ad2-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="29ad2-123">Lista de comprobaciones para la implementación del enlace troncal SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29ad2-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


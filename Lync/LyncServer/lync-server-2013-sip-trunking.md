---
title: 'Lync Server 2013: enlace troncal SIP'
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
ms.openlocfilehash: 4adf8dcee7ccd7adb393c8d13f7e9a8b186d2bb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519667"
---
# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="7b7d1-102">Enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b7d1-102">SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b7d1-103">_**Última modificación del tema:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="7b7d1-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="7b7d1-p101">El Protocolo de inicio de sesión (SIP) se usa para iniciar y administrar sesiones de comunicaciones de voz sobre IP (VoIP) del servicio telefónico básico y para otros servicios de comunicación en tiempo real, como la mensajería instantánea, las conferencias, la detección de presencia y los elementos multimedia. Esta sección ofrece información sobre la planeación para implementar *troncos SIP*, un tipo de conexión SIP que se extiende más allá del límite de su red local.</span><span class="sxs-lookup"><span data-stu-id="7b7d1-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="7b7d1-106">¿Qué es el enlace troncal SIP?</span><span class="sxs-lookup"><span data-stu-id="7b7d1-106">What is SIP Trunking?</span></span>

<span data-ttu-id="7b7d1-p102">Un tronco SIP es una conexión IP que establece un vínculo de comunicaciones SIP entre su organización y un proveedor de servicios de telefonía de Internet (ITSP) más allá de su firewall. En general, los troncos SIP se usan para conectar el sitio central de una organización a un ITSP. En ciertos casos, se puede usar también el enlace troncal SIP para conectar una sucursal a un ITSP.</span><span class="sxs-lookup"><span data-stu-id="7b7d1-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="7b7d1-110">Troncos SIP y conexiones SIP directas</span><span class="sxs-lookup"><span data-stu-id="7b7d1-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="7b7d1-111">El término *tronco* deriva de la tecnología de circuitos conmutados.</span><span class="sxs-lookup"><span data-stu-id="7b7d1-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="7b7d1-112">Se refiere a una línea física dedicada que conecta el equipo de conmutación telefónica.</span><span class="sxs-lookup"><span data-stu-id="7b7d1-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="7b7d1-113">Como sus antecesores, los troncos de multiplexación por división de tiempo (TDM), los troncos SIP son conexiones entre dos redes SIP independientes: la empresa Lync Server 2013 y la ITSP.</span><span class="sxs-lookup"><span data-stu-id="7b7d1-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="7b7d1-114">A diferencia de los troncos de circuitos conmutados, los enlaces troncales SIP son conexiones virtuales que se pueden establecer sobre cualquiera de los tipos de conexión de enlaces troncales SIP compatibles.</span><span class="sxs-lookup"><span data-stu-id="7b7d1-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="7b7d1-115">Para obtener más información sobre los tipos de conexión compatibles, vea [¿cómo se implementa el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="7b7d1-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="7b7d1-116">Por otra parte, las conexiones SIP directas son conexiones SIP que no cruzan los límites de la red local (es decir, que se conectan a central de conmutación (PBX) o a una red telefónica conmutada (RTC) dentro de su red local).</span><span class="sxs-lookup"><span data-stu-id="7b7d1-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="7b7d1-117">Para obtener información detallada sobre cómo usar las conexiones SIP directas con Lync Server 2013, consulte [Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="7b7d1-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b7d1-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7b7d1-118">In This Section</span></span>

  - [<span data-ttu-id="7b7d1-119">Información general sobre el enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b7d1-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="7b7d1-120">¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="7b7d1-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="7b7d1-121">Componentes y topologías para el enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b7d1-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="7b7d1-122">Enlace troncal SIP de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b7d1-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="7b7d1-123">Lista de comprobación para la implementación del tronco SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b7d1-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


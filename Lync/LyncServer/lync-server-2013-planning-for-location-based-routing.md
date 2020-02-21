---
title: 'Lync Server 2013: Planeación del enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef077c82a273a480977a21ca1e2e8b14043cae46
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="daa77-102">Planeación del enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daa77-103">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="daa77-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="daa77-104">La información de este tema se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="daa77-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="daa77-105">El enrutamiento basado en ubicación permite restringir el enrutamiento de las llamadas entre los extremos de VoIP y los extremos de RTC en función de la ubicación de las partes en la llamada.</span><span class="sxs-lookup"><span data-stu-id="daa77-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="daa77-106">El enrutamiento basado en ubicación forma parte de la infraestructura de Lync Server 2013 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="daa77-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="daa77-107">El enrutamiento basado en ubicación es una característica de administración de llamadas que controla cómo se enrutan las llamadas por parte de Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="daa77-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="daa77-108">Aplica las reglas de autorización de llamadas en cuanto a si las llamadas se pueden enrutar a puntos de conexión de PBX o RTC en función de la ubicación geográfica del autor de la llamada de Lync.</span><span class="sxs-lookup"><span data-stu-id="daa77-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="daa77-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="daa77-109">In This Section</span></span>

  - [<span data-ttu-id="daa77-110">Información general sobre el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="daa77-111">Guía para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="daa77-112">Escenarios para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="daa77-113">Consideraciones técnicas sobre el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="daa77-114">Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="daa77-115">Capacidades no compatibles con el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="daa77-116">Proceso de implementación para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="daa77-117">Enrutamiento basado en ubicación para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="daa77-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="daa77-118">See Also</span></span>


[<span data-ttu-id="daa77-119">Planear la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa77-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


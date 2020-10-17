---
title: 'Lync Server 2013: Planeación de enrutamiento de Location-Based'
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
ms.openlocfilehash: 114f92d0963e8d61c4b0854862ff7ebd59a12b64
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522047"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="97972-102">Planeación del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97972-103">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="97972-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="97972-104">La información de este tema se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="97972-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="97972-105">Location-Based enrutamiento permite restringir el enrutamiento de las llamadas entre los extremos de VoIP y los extremos de RTC en función de la ubicación de las partes en la llamada.</span><span class="sxs-lookup"><span data-stu-id="97972-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="97972-106">El enrutamiento Location-Based forma parte de la infraestructura de Lync Server 2013 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="97972-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="97972-107">El enrutamiento Location-Based es una característica de administración de llamadas que controla cómo se enrutan las llamadas por parte de Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="97972-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="97972-108">Aplica las reglas de autorización de llamadas en cuanto a si las llamadas se pueden enrutar a puntos de conexión de PBX o RTC en función de la ubicación geográfica del autor de la llamada de Lync.</span><span class="sxs-lookup"><span data-stu-id="97972-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97972-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="97972-109">In This Section</span></span>

  - [<span data-ttu-id="97972-110">Información general sobre el enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="97972-111">Guía para el enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="97972-112">Escenarios para Location-Based el enrutamiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="97972-113">Consideraciones técnicas sobre el enrutamiento Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="97972-114">Compatibilidad de cliente y servidor para el enrutamiento Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="97972-115">Capacidades no compatibles con el enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="97972-116">Proceso de implementación para el enrutamiento Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="97972-117">Enrutamiento basado en ubicación para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97972-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97972-118">See Also</span></span>


[<span data-ttu-id="97972-119">Planear la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97972-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


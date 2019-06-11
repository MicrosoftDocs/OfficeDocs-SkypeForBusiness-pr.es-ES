---
title: 'Lync Server 2013: Planificar el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3873e8710d6ab70212de7780ef5f34d1436df1d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="7f818-102">Planificar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f818-103">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="7f818-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="7f818-104">La información de este tema se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="7f818-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="7f818-105">El enrutamiento basado en la ubicación permite restringir el enrutamiento de llamadas entre puntos de conexión VoIP y puntos de conexión RTC en función de la ubicación de las partes en la llamada.</span><span class="sxs-lookup"><span data-stu-id="7f818-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="7f818-106">El enrutamiento basado en la ubicación es parte de la infraestructura de telefonía IP empresarial de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f818-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="7f818-107">El enrutamiento basado en la ubicación es una característica de administración de llamadas que controla cómo Lync Server 2013 CU1 dirige las llamadas.</span><span class="sxs-lookup"><span data-stu-id="7f818-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="7f818-108">Aplica reglas de autorización de llamadas si las llamadas se pueden enrutar a puntos de conexión PBX o RTC en función de la ubicación geográfica de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="7f818-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f818-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7f818-109">In This Section</span></span>

  - [<span data-ttu-id="7f818-110">Información general sobre el enrutamiento basado en la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="7f818-111">Instrucciones para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="7f818-112">Escenarios para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="7f818-113">Consideraciones técnicas para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="7f818-114">Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="7f818-115">Capacidades no compatibles con el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="7f818-116">Proceso de implementación para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="7f818-117">Enrutamiento basado en la ubicación de las conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f818-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f818-118">See Also</span></span>


[<span data-ttu-id="7f818-119">Planificación de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f818-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


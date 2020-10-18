---
title: 'Lync Server 2013: Grupo de Director escalado-equilibrador de carga de hardware'
description: 'Lync Server 2013: Grupo de Director escalado-equilibrador de carga de hardware.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 022c5afb67687149f8ba24655be2a1461d4371f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578706"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="db11b-103">Grupo de Director escalado-equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db11b-103">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db11b-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="db11b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="db11b-105">Un grupo de servidores de Director escalado, en el que se implementan varios directores para controlar la capacidad adicional y proporcionar una alta disponibilidad, requiere equilibrio de carga para distribuir la comunicación entre el cliente y el servidor a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="db11b-105">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="db11b-106">Un director hospeda servicios web muy similares a un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="db11b-106">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="db11b-107">Se requiere el equilibrio de carga de hardware para los servicios web.</span><span class="sxs-lookup"><span data-stu-id="db11b-107">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="db11b-108">En los siguientes temas se describen las consideraciones de planeación para implementar un grupo de directores mediante el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="db11b-108">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="db11b-109">Si tiene previsto usar el equilibrio de carga de hardware y el equilibrio de carga de DNS para el grupo de directores, consulte el tema [grupo de directores escalados-equilibrio de carga de DNS y equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) que describe los requisitos de planeación para esa topología.</span><span class="sxs-lookup"><span data-stu-id="db11b-109">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="db11b-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="db11b-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="db11b-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="db11b-111">In This Section</span></span>

  - [<span data-ttu-id="db11b-112">Resumen de certificado-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db11b-112">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="db11b-113">Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db11b-113">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="db11b-114">Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db11b-114">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Grupo de servidores de director escalado - Equilibrador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0faf0983830466b44c91532f4fd80d72abb37fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="51fdc-102">Grupo de servidores de director escalado - Equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51fdc-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51fdc-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="51fdc-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="51fdc-104">Un grupo de directores escalados, en el que se han implementado más de un director para manejar capacidad adicional y proporcionar una alta disponibilidad, requiere el equilibrio de carga para distribuir la comunicación entre el cliente y el servidor a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="51fdc-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="51fdc-105">Un director hospeda servicios web muy parecidos a un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="51fdc-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="51fdc-106">El equilibrio de carga de hardware es necesario para los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="51fdc-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="51fdc-107">En los siguientes temas se describen las consideraciones de planeación para implementar un grupo de directores mediante el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="51fdc-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="51fdc-108">Si tiene previsto usar el equilibrio de carga de hardware y el equilibrio de carga de DNS para el grupo de directores, consulte el tema [grupo de directores escalados: equilibrio de carga de DNS y equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) que describe los requisitos de planeación de esa topología.</span><span class="sxs-lookup"><span data-stu-id="51fdc-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="51fdc-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb] (images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="51fdc-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="51fdc-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="51fdc-110">In This Section</span></span>

  - [<span data-ttu-id="51fdc-111">Resumen de certificado - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51fdc-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="51fdc-112">Resumen de puerto - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51fdc-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="51fdc-113">Resumen DNS - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51fdc-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


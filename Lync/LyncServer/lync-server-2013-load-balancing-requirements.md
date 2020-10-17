---
title: Requisitos de equilibrio de carga de Lync Server 2013
description: Lync Server 2013 requisitos de equilibrio de carga.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a768b2cbfe444e6915c932835d3cc2abaf6a98c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550036"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="35871-103">Requisitos de equilibrio de carga para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35871-103">Load balancing requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35871-104">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="35871-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="35871-105">Si tiene grupos de servidores front-end, grupos de directores o grupos de servidores perimetrales, debe implementar el equilibrio de carga para estos grupos.</span><span class="sxs-lookup"><span data-stu-id="35871-105">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="35871-106">El equilibrio de carga distribuye el tráfico entre los servidores de los grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="35871-106">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="35871-107">Lync Server 2013 admite dos tipos de soluciones de equilibrio de carga para el tráfico de cliente a servidor: el equilibrio de carga del sistema de nombres de dominio (DNS) y el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="35871-107">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="35871-108">El equilibrio de carga de DNS ofrece varias ventajas, como una administración más sencilla, una solución de problemas más eficaz y la capacidad de aislar gran parte del tráfico de Lync Server de cualquier problema potencial del equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="35871-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="35871-109">Decida qué solución de equilibrio de carga es adecuada para cada grupo de su implementación, teniendo en cuenta las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="35871-109">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="35871-p103">La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz y el equilibrio de carga de hardware en la otra.</span><span class="sxs-lookup"><span data-stu-id="35871-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="35871-p104">Algunos tipos de tráfico requieren un equilibrador de carga de hardware. Por ejemplo, el tráfico HTTP requiere un equilibrador de carga de hardware en lugar del equilibrio de carga de DNS. El  equilibrio de carga de DNS no trabaja con tráfico web de cliente a servidor.</span><span class="sxs-lookup"><span data-stu-id="35871-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="35871-115">Para obtener más información sobre cómo elegir una solución de equilibrador de carga de hardware, consulte [requisitos del equilibrador de carga de hardware para Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35871-115">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="35871-116">Si decide usar el equilibrio de carga DNS para un grupo pero aún tiene que implementar equilibradores de carga de hardware para tráfico como el tráfico HTTP, la administración de los equilibradores de carga de hardware será mucho más sencilla.</span><span class="sxs-lookup"><span data-stu-id="35871-116">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="35871-117">Por ejemplo, la configuración del equilibrador de carga de hardware será más sencilla, ya que sólo administrará el tráfico HTTP y HTTPS, mientras que el equilibrio de carga de DNS administrará todos los demás protocolos.</span><span class="sxs-lookup"><span data-stu-id="35871-117">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="35871-118">Para obtener más información, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="35871-118">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="35871-119">Para el tráfico de servidor a servidor, Lync Server 2013 usa el equilibrio de carga consciente de la topología.</span><span class="sxs-lookup"><span data-stu-id="35871-119">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="35871-120">Los servidores leen la topología Publicada en el almacén de administración central para obtener los FQDN de los servidores en la topología y distribuyen automáticamente el tráfico entre los servidores.</span><span class="sxs-lookup"><span data-stu-id="35871-120">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="35871-121">Los administradores no necesitan configurar ni administrar este tipo de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="35871-121">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="35871-122">Si usa el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no basta con quitar las entradas de dirección IP del FQDN del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="35871-122">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="35871-123">También debe quitar la entrada DNS del equipo.</span><span class="sxs-lookup"><span data-stu-id="35871-123">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Requisitos de equilibrio de carga de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4848c78c755b95a15c28ab1f8e2555a180e22bfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="77b30-102">Requisitos de equilibrio de carga para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b30-102">Load balancing requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77b30-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="77b30-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="77b30-104">Si tiene grupos de servidores front-end, grupos de directores o grupos de servidores perimetrales, necesita implementar el equilibrio de carga para estos grupos.</span><span class="sxs-lookup"><span data-stu-id="77b30-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="77b30-105">El equilibrio de carga distribuye el tráfico entre los servidores de los grupos.</span><span class="sxs-lookup"><span data-stu-id="77b30-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="77b30-106">Lync Server 2013 admite dos tipos de soluciones de equilibrio de carga para el tráfico de cliente a servidor: equilibrio de carga del sistema de nombres de dominio (DNS) y equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="77b30-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="77b30-107">El equilibrio de carga de DNS ofrece varias ventajas, como la administración más sencilla, la solución de problemas más eficaz y la capacidad de aislar gran parte del tráfico de Lync Server de cualquier problema potencial de equilibrado de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="77b30-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="77b30-108">Decida qué solución de equilibrio de carga es adecuada para cada grupo de su implementación, teniendo en cuenta las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="77b30-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="77b30-p103">La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz y el equilibrio de carga de hardware en la otra.</span><span class="sxs-lookup"><span data-stu-id="77b30-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="77b30-p104">Algunos tipos de tráfico requieren un equilibrador de carga de hardware. Por ejemplo, el tráfico HTTP requiere un equilibrador de carga de hardware en lugar del equilibrio de carga de DNS. El equilibrio de carga de DNS no funciona con tráfico web del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="77b30-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="77b30-114">Para obtener más información sobre cómo elegir una solución de equilibrador de carga de hardware, consulte [requisitos del equilibrador de carga de hardware para Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77b30-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="77b30-115">Si decide usar el equilibrio de carga de DNS para un grupo, pero aún tiene que implementar equilibradores de carga de hardware para el tráfico, como el tráfico HTTP, la administración de los equilibradores de carga de hardware será mucho más sencilla.</span><span class="sxs-lookup"><span data-stu-id="77b30-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="77b30-116">Por ejemplo, configurar el equilibrador de carga de hardware será más sencillo, pues solamente administrará el tráfico HTTPS y HTTP, mientras que el equilibrio de carga de DNS administrará todos los demás protocolos.</span><span class="sxs-lookup"><span data-stu-id="77b30-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="77b30-117">Para obtener más información, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="77b30-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="77b30-118">Para el tráfico de servidor a servidor, Lync Server 2013 usa el equilibrio de carga que reconoce la topología.</span><span class="sxs-lookup"><span data-stu-id="77b30-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="77b30-119">Los servidores leen la topología Publicada en el almacén central de administración para obtener los FQDN de los servidores de la topología y distribuyen automáticamente el tráfico entre los servidores.</span><span class="sxs-lookup"><span data-stu-id="77b30-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="77b30-120">Los administradores no necesitan configurar ni administrar este tipo de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="77b30-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="77b30-p107">Si utiliza el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente con solo quitar las entradas de direcciones IP del FQDN del grupo de servidores. También es preciso quitar la entrada de DNS para el equipo.</span><span class="sxs-lookup"><span data-stu-id="77b30-p107">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


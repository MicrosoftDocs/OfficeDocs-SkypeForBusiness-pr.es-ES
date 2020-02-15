---
title: 'Lync Server 2013: servidor perimetral consolidado único con direcciones IP públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1867abe0cc16190650d2be303a55ecf0dd6a5efd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="5ba81-102">Servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba81-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ba81-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5ba81-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5ba81-104">Si su organización necesita admitir menos de 15.000 conexiones de cliente del servicio perimetral de acceso, 1.000 conexiones de cliente de servicio de conferencia Web de Lync Server activas y 500 sesiones perimetrales A/V concurrentes, y la alta disponibilidad del servidor perimetral no es importante, esta topología ofrece las ventajas de un menor costo de hardware y una implementación más sencilla.</span><span class="sxs-lookup"><span data-stu-id="5ba81-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="5ba81-105">Si necesita una mayor capacidad o necesita una alta disponibilidad, debe implementar una topología de servidor perimetral consolidado escalado.</span><span class="sxs-lookup"><span data-stu-id="5ba81-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="5ba81-106">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba81-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="5ba81-107">Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba81-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="5ba81-108">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba81-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5ba81-109">Cuando se usa la dirección IP pública en el servidor perimetral, la puerta de enlace predeterminada en el servidor perimetral deja de ser el firewall o enrutador, pero el enrutador o firewall en el perímetro del perímetro público, que será una dirección pública.</span><span class="sxs-lookup"><span data-stu-id="5ba81-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="5ba81-110">El proxy inverso continúa usando el enrutador o firewall asociado con la red perimetral más externa.</span><span class="sxs-lookup"><span data-stu-id="5ba81-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="5ba81-111">La diferencia entre el proxy inverso y el servidor perimetral con direcciones IP públicas es que el proxy inverso sigue usando NAT y el servidor perimetral usa una relación de ruta.</span><span class="sxs-lookup"><span data-stu-id="5ba81-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="5ba81-112">La figura no muestra los directores, una función de servidor opcional implementada en la red interna entre los servidores perimetrales y los grupos de servidores front-end o el servidor.</span><span class="sxs-lookup"><span data-stu-id="5ba81-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="5ba81-113">Para obtener más información sobre la topología para directores, consulte [componentes necesarios para el Director en Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="5ba81-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="5ba81-114">La figura representa un único proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="5ba81-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ba81-115">La figura se muestra a título orientativo y como ejemplo de direccionamiento de IP, pero no pretende representar los flujos de comunicación reales con el tráfico correcto de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="5ba81-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="5ba81-116">La figura representa una vista posible de alto nivel de tráfico.</span><span class="sxs-lookup"><span data-stu-id="5ba81-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="5ba81-117">Los detalles del flujo de tráfico según corresponden a la entrada (a los puertos de escucha) y a la salida (a los servidores o clientes de destino) se representan en el diagrama de resumen de puertos en cada escenario.</span><span class="sxs-lookup"><span data-stu-id="5ba81-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="5ba81-118">Por ejemplo, TCP 443 se define en realidad como de entrada exclusivamente (al proxy de servidor perimetral o inverso) y solo es un flujo bidireccional desde la perspectiva del protocolo (TCP).</span><span class="sxs-lookup"><span data-stu-id="5ba81-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="5ba81-119">Además, en la figura se muestra la naturaleza del tráfico a medida que cambia, cuando se produce la traducción de direcciones de red (NAT) (la dirección de destino se cambia en la entrada y la dirección de origen en la salida).</span><span class="sxs-lookup"><span data-stu-id="5ba81-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="5ba81-120">Los ejemplos de los firewalls interno y externo, y las interfaces de servidor se presentan tan solo a título de referencia.</span><span class="sxs-lookup"><span data-stu-id="5ba81-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="5ba81-121">Por último, cuando procede se presentan ejemplos de relaciones de la ruta y la puerta de enlace predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="5ba81-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="5ba81-122">Tenga en cuenta también que el diagrama usa la zona DNS <EM>. com</EM> para representar la zona DNS externa tanto para el proxy inverso como para los servidores perimetrales, y la zona DNS de <EM>.net</EM> hace referencia a la zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="5ba81-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="5ba81-123">La novedad de Microsoft Lync Server 2013 es la compatibilidad con el direccionamiento IPv6.</span><span class="sxs-lookup"><span data-stu-id="5ba81-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="5ba81-124">Parecidas en gran medida a las direcciones IPv4, las direcciones IPv6 se deben asignar de tal manera que formen parte del espacio de direcciones IPv6 asignado.</span><span class="sxs-lookup"><span data-stu-id="5ba81-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="5ba81-125">Las direcciones de este tema son solo ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5ba81-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="5ba81-126">Deberá obtener direcciones IPv6 que funcionen en la implementación, proporcionen el ámbito adecuado e interoperen con direcciones internas y externas.</span><span class="sxs-lookup"><span data-stu-id="5ba81-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="5ba81-127">Windows Server proporciona una característica que es importante para la operación de IPv6 de transición y la comunicación de IPv4 a IPv6 llamada *Dual Stack*.</span><span class="sxs-lookup"><span data-stu-id="5ba81-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="5ba81-128">La pila dual es una pila de red independiente y distinta para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="5ba81-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="5ba81-129">Es lo que hace posible asignar direcciones IPv4 e IPv6 al mismo tiempo, y permite que el servidor se comunique con otros hosts y clientes en función de requisitos particulares.</span><span class="sxs-lookup"><span data-stu-id="5ba81-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="5ba81-130">Los tipos de direcciones típicos que usará para el direccionamiento IPv6 serán las direcciones IPv6 globales (similares a las direcciones IPv4 públicas), las direcciones IPv6 locales únicas (similares a los intervalos de direcciones IPv4 privados) y las direcciones IPv6 locales de vínculo (similares a las direcciones IP privadas automáticas). direcciones en Windows Server para IPv4)</span><span class="sxs-lookup"><span data-stu-id="5ba81-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="5ba81-131">Existen tecnologías de traducción de direcciones de red (NAT) para IPv6 que hacen posible la traducción de direcciones de red de IPv6 a IPv4 (suele conocerse como NAT64) y la traducción de direcciones de red de IPv6 a IPv6 (NAT66).</span><span class="sxs-lookup"><span data-stu-id="5ba81-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="5ba81-132">La existencia de tecnologías NAT significa que los cinco escenarios presentados para los servidores perimetrales de Lync Server siguen siendo válidos.</span><span class="sxs-lookup"><span data-stu-id="5ba81-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5ba81-133">IPv6 es un tema complejo y requiere una planificación minuciosa con el equipo de red y el proveedor de Internet para asegurarse de que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionarán según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="5ba81-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="5ba81-134">Consulte los vínculos al final de este tema para ver más recursos sobre la planeación y el direccionamiento de IPv6.</span><span class="sxs-lookup"><span data-stu-id="5ba81-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="5ba81-135">**Topología de perímetro consolidado de un solo equipo con direcciones IP públicas**</span><span class="sxs-lookup"><span data-stu-id="5ba81-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="5ba81-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="5ba81-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5ba81-137">Si usa el control de admisión de llamadas (CAC), sigue siendo necesario asignar direcciones IPv4 a la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="5ba81-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="5ba81-138">El control de admisión de llamadas emplea direcciones IPv4, con lo cual deberán estar disponibles para que funcione.</span><span class="sxs-lookup"><span data-stu-id="5ba81-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5ba81-139">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ba81-139">In This Section</span></span>

  - [<span data-ttu-id="5ba81-140">Resumen de certificado-perímetro consolidado de un solo consolidado con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba81-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="5ba81-141">Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba81-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="5ba81-142">Resumen de DNS-servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba81-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ba81-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ba81-143">See Also</span></span>


[<span data-ttu-id="5ba81-144">Arquitectura de direcciones de IP versión 6</span><span class="sxs-lookup"><span data-stu-id="5ba81-144">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="5ba81-145">Formato de dirección de unidifusión global IPv6</span><span class="sxs-lookup"><span data-stu-id="5ba81-145">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="5ba81-146">Direcciones de unidifusión IPv6 locales únicas</span><span class="sxs-lookup"><span data-stu-id="5ba81-146">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


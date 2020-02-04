---
title: 'Lync Server 2013: Topología perimetral consolidada de un solo equipo con direcciones IP públicas'
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
ms.openlocfilehash: 8189d360a43887e2992b8b8abf063ef96230e06e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="d20d2-102">Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d20d2-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d20d2-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d20d2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d20d2-104">Si su organización necesita soporte técnico para menos de 15.000 conexiones de cliente del servicio perimetral de acceso, 1.000 conexiones de cliente del servicio de conferencias por Internet de Lync Server activas y 500 de concurrentes en las sesiones perimetrales A/V, y la alta disponibilidad del servidor perimetral no es importante, esta topología ofrece las ventajas de un menor costo de hardware y una implementación más simple.</span><span class="sxs-lookup"><span data-stu-id="d20d2-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="d20d2-105">Si necesita una mayor capacidad o necesita una alta disponibilidad, debe implementar una topología de servidor perimetral consolidado a escala.</span><span class="sxs-lookup"><span data-stu-id="d20d2-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="d20d2-106">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d20d2-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="d20d2-107">Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d20d2-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="d20d2-108">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d20d2-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d20d2-109">Al usar una dirección IP pública en el servidor perimetral, la puerta de enlace predeterminada en el servidor perimetral deja de ser su firewall o router, pero el enrutador o firewall del perímetro público, que será una dirección pública.</span><span class="sxs-lookup"><span data-stu-id="d20d2-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="d20d2-110">El proxy inverso continúa usando el enrutador o firewall asociado a la red perimetral más externa.</span><span class="sxs-lookup"><span data-stu-id="d20d2-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="d20d2-111">La diferencia entre el proxy inverso y el servidor perimetral con direcciones IP públicas es que el proxy inverso sigue usando NAT y el servidor perimetral usa una relación de ruta.</span><span class="sxs-lookup"><span data-stu-id="d20d2-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="d20d2-112">La figura no muestra los directores, un rol de servidor opcional implementado en la red interna entre los servidores perimetrales y los grupos de servidores front-end o el servidor.</span><span class="sxs-lookup"><span data-stu-id="d20d2-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="d20d2-113">Para obtener más información sobre la topología para directores, consulte [componentes necesarios para el director de Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="d20d2-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="d20d2-114">La figura representa un único proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d20d2-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d20d2-115">La cifra que se muestra es para la orientación y el direccionamiento IP de ejemplo, pero no tiene la intención de representar los flujos de comunicación reales con el tráfico entrante y saliente correcto.</span><span class="sxs-lookup"><span data-stu-id="d20d2-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="d20d2-116">La figura representa una vista de alto nivel del tráfico posible.</span><span class="sxs-lookup"><span data-stu-id="d20d2-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="d20d2-117">Los detalles del flujo de tráfico según pertenecen a los puertos entrante (en los que se escuchan) y salientes (a los servidores de destino o a los clientes) se representan en el diagrama de Resumen de puertos en cada escenario.</span><span class="sxs-lookup"><span data-stu-id="d20d2-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="d20d2-118">Por ejemplo, TCP 443 es realmente entrante (solo para el extremo o proxy inverso) y es solo un flujo bidireccional desde una perspectiva de protocolo (TCP).</span><span class="sxs-lookup"><span data-stu-id="d20d2-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="d20d2-119">Además, la figura muestra la naturaleza del tráfico cuando cambia cuando se produce NAT (traducción de direcciones de red) (la dirección de destino se cambia en entrante; la dirección de origen se cambia en saliente).</span><span class="sxs-lookup"><span data-stu-id="d20d2-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="d20d2-120">Ejemplo de firewall externo e interno, y las interfaces de servidor se muestran solo con fines de referencia.</span><span class="sxs-lookup"><span data-stu-id="d20d2-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="d20d2-121">Por último, se muestra ejemplo de puerta de enlace predeterminada y relaciones de ruta, cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="d20d2-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="d20d2-122">Observe también que el diagrama usa la zona DNS <EM>. com</EM> para representar la zona DNS externa tanto para el proxy inverso como con los servidores perimetrales, y la zona DNS de <EM>.net</EM> hace referencia a la zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="d20d2-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="d20d2-123">Las novedades de Microsoft Lync Server 2013 son compatibilidad con el direccionamiento IPv6.</span><span class="sxs-lookup"><span data-stu-id="d20d2-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="d20d2-124">Al igual que con el direccionamiento IPv4, las direcciones IPv6 deben asignarse de forma que las direcciones formen parte del espacio de direcciones IPv6 asignado.</span><span class="sxs-lookup"><span data-stu-id="d20d2-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="d20d2-125">Las direcciones de este tema solo son por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d20d2-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="d20d2-126">Debe adquirir direcciones IPv6 que funcionen en su implementación, proporcionar el ámbito correcto y interoperar con direcciones internas y externas.</span><span class="sxs-lookup"><span data-stu-id="d20d2-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="d20d2-127">Windows Server proporciona una característica importante para la operación de IPv6 de transición y la comunicación de IPv4 a IPv6 denominada *pila dual*.</span><span class="sxs-lookup"><span data-stu-id="d20d2-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="d20d2-128">La pila dual es una pila de red separada y distinta para IPv4 y para IPv6.</span><span class="sxs-lookup"><span data-stu-id="d20d2-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="d20d2-129">La pila dual es lo que le permite asignar direcciones IPv4 e IPv6 al mismo tiempo y permite que el servidor se comunique con otros hosts y clientes en función de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="d20d2-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="d20d2-130">Los tipos de dirección típicos que usará para el direccionamiento IPv6 serán las direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), las direcciones locales IPv6 únicas (similares a los intervalos de direcciones IPv4 privadas) y las direcciones locales del vínculo IPv6 (similares a IP privadas automáticas). direcciones en Windows Server para IPv4)</span><span class="sxs-lookup"><span data-stu-id="d20d2-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="d20d2-131">Existen tecnologías de traducción de direcciones de red (NAT) para IPv6 que permitirán NAT IPv6 a IPv4 (comúnmente denominado NAT64) y para NAT IPv6 a IPv6 (comúnmente conocido como NAT66).</span><span class="sxs-lookup"><span data-stu-id="d20d2-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="d20d2-132">La existencia de tecnologías NAT significa que los cinco escenarios presentados para los servidores perimetrales de Lync Server siguen siendo válidos.</span><span class="sxs-lookup"><span data-stu-id="d20d2-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d20d2-133">IPv6 es un tema complejo y requiere un cuidadoso planeamiento con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionen de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="d20d2-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="d20d2-134">Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6.</span><span class="sxs-lookup"><span data-stu-id="d20d2-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="d20d2-135">**Un solo borde consolidado con topología pública de direcciones IP**</span><span class="sxs-lookup"><span data-stu-id="d20d2-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="d20d2-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="d20d2-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d20d2-137">Si está usando control de admisión de llamadas (CAC), aún debe asignar direcciones IPv4 a la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="d20d2-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="d20d2-138">CAC usa direcciones IPv4 y debe tener disponibles para funcionar.</span><span class="sxs-lookup"><span data-stu-id="d20d2-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d20d2-139">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d20d2-139">In This Section</span></span>

  - [<span data-ttu-id="d20d2-140">Resumen de certificado - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d20d2-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="d20d2-141">Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d20d2-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="d20d2-142">Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d20d2-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d20d2-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="d20d2-143">See Also</span></span>


[<span data-ttu-id="d20d2-144">Arquitectura de direccionamiento de IP versión 6</span><span class="sxs-lookup"><span data-stu-id="d20d2-144">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="d20d2-145">Formato de dirección global de unidifusión IPv6</span><span class="sxs-lookup"><span data-stu-id="d20d2-145">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="d20d2-146">Direcciones de unidifusión IPv6 locales únicas</span><span class="sxs-lookup"><span data-stu-id="d20d2-146">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


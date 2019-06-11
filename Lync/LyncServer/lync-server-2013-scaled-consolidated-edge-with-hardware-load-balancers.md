---
title: 'Lync Server 2013: Servidor perimetral consolidado ampliado con equilibradores de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa5a395c8509961937af23c12763a5bf55cc326
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="5cd3d-102">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cd3d-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cd3d-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5cd3d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5cd3d-104">En la topología del grupo perimetral, dos o más servidores perimetrales se implementan como un grupo de carga equilibrada en la red perimetral del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="5cd3d-105">El equilibrio de carga de hardware se usa para el tráfico de las interfaces de los servidores perimetrales externos e internos.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="5cd3d-106">Si su organización requiere soporte técnico para más de 15.000 conexiones de cliente del servicio perimetral de acceso, 1.000 conexiones de cliente del servicio perimetral activas de conferencias web o 500 sesiones de servicio perimetral A/V activas, y la alta disponibilidad del servidor perimetral es importante, Esta topología ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="5cd3d-107">La figura no muestra los directores, un rol de servidor opcional implementado en la red interna entre los servidores perimetrales y los grupos de servidores front-end o el servidor.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="5cd3d-108">.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-108"></span></span> <span data-ttu-id="5cd3d-109">Para obtener más información sobre la topología para directores, consulte [componentes necesarios para el director de Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="5cd3d-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5cd3d-110">La cifra que se muestra es para la orientación y el direccionamiento IP de ejemplo, pero no tiene la intención de representar los flujos de comunicación reales con el tráfico entrante y saliente correcto.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="5cd3d-111">La figura representa una vista de alto nivel del tráfico posible.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="5cd3d-112">Los detalles del flujo de tráfico según pertenecen a los puertos entrante (en los que se escuchan) y salientes (a los servidores de destino o a los clientes) se representan en el diagrama de Resumen de puertos en cada escenario.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="5cd3d-113">Por ejemplo, TCP 443 es realmente entrante (solo para el servidor perimetral o proxy inverso) y es solo un flujo bidireccional desde una perspectiva de protocolo (TCP).</span><span class="sxs-lookup"><span data-stu-id="5cd3d-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="5cd3d-114">Además, la figura muestra la naturaleza del tráfico cuando cambia cuando se produce NAT (traducción de direcciones de red) (la dirección de destino se cambia en entrante; la dirección de origen se cambia en saliente).</span><span class="sxs-lookup"><span data-stu-id="5cd3d-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="5cd3d-115">Ejemplo de firewall externo e interno, y las interfaces de servidor se muestran solo con fines de referencia.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="5cd3d-116">Por último, se muestra ejemplo de puerta de enlace predeterminada y relaciones de ruta, cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="5cd3d-117">Observe también que el diagrama usa la zona DNS <EM>. com</EM> para representar la zona DNS externa tanto para el proxy inverso como con los servidores perimetrales, y la zona DNS de <EM>.net</EM> hace referencia a la zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="5cd3d-118">Las novedades de Microsoft Lync Server 2013 son compatibilidad con el direccionamiento IPv6.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="5cd3d-119">Al igual que con el direccionamiento IPv4, las direcciones IPv6 deben asignarse de forma que las direcciones formen parte del espacio de direcciones IPv6 asignado.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="5cd3d-120">Las direcciones de este tema solo son por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="5cd3d-121">Debe adquirir direcciones IPv6 que funcionen en su implementación, proporcionar el ámbito correcto y interoperar con direcciones internas y externas.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="5cd3d-122">Windows Server proporciona una característica importante para la operación de IPv6 de transición y la comunicación de IPv4 a IPv6 denominada *pila dual*.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="5cd3d-123">La pila dual es una pila de red separada y distinta para IPv4 y para IPv6.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="5cd3d-124">La pila dual es lo que le permite asignar direcciones IPv4 e IPv6 al mismo tiempo y permite que el servidor se comunique con otros hosts y clientes en función de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="5cd3d-125">Los tipos de dirección típicos que usará para el direccionamiento IPv6 serán las direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), las direcciones locales IPv6 únicas (similares a los intervalos de direcciones IPv4 privadas) y las direcciones locales del vínculo IPv6 (similares a IP privadas automáticas). direcciones en Windows Server para IPv4)</span><span class="sxs-lookup"><span data-stu-id="5cd3d-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="5cd3d-126">Existen tecnologías de traducción de direcciones de red (NAT) para IPv6 que permitirán NAT IPv6 a IPv4 (comúnmente denominado NAT64) y para NAT IPv6 a IPv6 (comúnmente conocido como NAT66).</span><span class="sxs-lookup"><span data-stu-id="5cd3d-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="5cd3d-127">La existencia de tecnologías NAT significa que los cinco escenarios presentados para los servidores perimetrales de Lync Server siguen siendo válidos.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5cd3d-128">IPv6 es un tema complejo y requiere un cuidadoso planeamiento con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionen de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="5cd3d-129">Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="5cd3d-130">**Configuración del equilibrador de carga de hardware**</span><span class="sxs-lookup"><span data-stu-id="5cd3d-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="5cd3d-131">Para obtener más información, consulte la sección "requisitos del equilibrador de carga de hardware para un borde A/V" en [componentes necesarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5cd3d-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="5cd3d-132">**Topología perimetral consolidada escalada (equilibrio de carga de hardware)**</span><span class="sxs-lookup"><span data-stu-id="5cd3d-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="5cd3d-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2] (images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="5cd3d-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5cd3d-134">Si está usando control de admisión de llamadas (CAC), aún debe asignar direcciones IPv4 a la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="5cd3d-135">CAC usa direcciones IPv4 y debe tener disponibles para funcionar.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5cd3d-136">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5cd3d-136">In This Section</span></span>

  - [<span data-ttu-id="5cd3d-137">Resumen de certificado - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cd3d-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="5cd3d-138">Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cd3d-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="5cd3d-139">Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cd3d-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5cd3d-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cd3d-140">See Also</span></span>


[<span data-ttu-id="5cd3d-141">Arquitectura de direccionamiento de IP versión 6</span><span class="sxs-lookup"><span data-stu-id="5cd3d-141">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="5cd3d-142">Formato de dirección global de unidifusión IPv6</span><span class="sxs-lookup"><span data-stu-id="5cd3d-142">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="5cd3d-143">Direcciones de unidifusión IPv6 locales únicas</span><span class="sxs-lookup"><span data-stu-id="5cd3d-143">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


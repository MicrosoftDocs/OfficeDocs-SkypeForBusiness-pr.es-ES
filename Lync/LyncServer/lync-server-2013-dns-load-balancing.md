---
title: 'Lync Server 2013: equilibrio de carga de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4248815c2e896c6c4ce36d22fd6544c298527766
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="340d9-102">Equilibrio de carga de DNS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="340d9-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="340d9-103">_**Última modificación del tema:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="340d9-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="340d9-104">Lync Server habilita el equilibrio de carga de DNS, una solución de software que puede reducir en gran medida la sobrecarga de administración para el equilibrio de carga en la red.</span><span class="sxs-lookup"><span data-stu-id="340d9-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="340d9-105">El equilibrio de carga de DNS equilibra el tráfico de red que es exclusivo de Lync Server, como el tráfico SIP y el tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="340d9-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="340d9-p102">Si implementa el equilibrio de carga de DNS, se reducirá considerablemente la sobrecarga de administración de la organización correspondiente a los equilibradores de carga de hardware. Además, se evitará la solución de problemas complejos asociados a errores de configuración de equilibradores de carga del tráfico SIP. También puede impedir que se establezcan conexiones de servidores para poder desconectar servidores. El equilibrio de carga de DNS también garantiza que los problemas relacionados con los equilibradores de carga de hardware no afecten a elementos de tráfico SIP, como el enrutamiento de llamadas básico.</span><span class="sxs-lookup"><span data-stu-id="340d9-p102">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized. Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated. You can also prevent server connections so that you can take servers offline. DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="340d9-110">Si se utiliza el equilibrio de carga de DNS también podrá adquirir equilibradores de carga de hardware a un precio más económico que si usa equilibradores de carga de hardware para todos los tipos de tráfico.</span><span class="sxs-lookup"><span data-stu-id="340d9-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="340d9-111">Debe usar equilibradores de carga que hayan superado las pruebas de calificación de interoperabilidad con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="340d9-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="340d9-112">Para obtener más información sobre las pruebas de interoperabilidad de equilibrador de carga, consulte "Lync Server [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)2010 de equilibrador de carga" en.</span><span class="sxs-lookup"><span data-stu-id="340d9-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="340d9-113">El equilibrio de carga de DNS es compatible con grupos de servidores front-end, grupos de servidores perimetrales, grupos de servidores de director y grupos de servidores de mediación independientes.</span><span class="sxs-lookup"><span data-stu-id="340d9-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="340d9-114">Equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director</span><span class="sxs-lookup"><span data-stu-id="340d9-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="340d9-p104">Puede usar el equilibrio de carga de DNS para el tráfico SIP de los grupos de servidores front-end y los grupos de servidores de director. Con el equilibrio de carga de DNS implementado, seguirá necesitando usar también equilibradores de carga de hardware para esos grupos de servidores, pero solo para el tráfico HTTPS de cliente a servidor. El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80.</span><span class="sxs-lookup"><span data-stu-id="340d9-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="340d9-118">A pesar de que seguirá necesitando equilibradores de carga de hardware para esos grupos de servidores, su instalación y administración será fundamentalmente para el tráfico HTTPS, al que están habituados los administradores de equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="340d9-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="340d9-119">Equilibrio de carga de DNS y compatibilidad con clientes y servidores más antiguos</span><span class="sxs-lookup"><span data-stu-id="340d9-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="340d9-120">El equilibrio de carga de DNS admite la conmutación por error automática solo para servidores que ejecutan Lync Server 2013 o Lync Server 2010, y para clientes de Lync 2013 y Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="340d9-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="340d9-121">Las versiones anteriores de clientes y Office Communications Server siguen conectándose a las agrupaciones que ejecutan el equilibrio de carga de DNS, pero si no pueden establecer una conexión con el primer servidor al que el equilibrio de carga DNS hace referencia a él, no pueden conmutar por error a otro servidor del grupo .</span><span class="sxs-lookup"><span data-stu-id="340d9-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="340d9-122">Además, si usa la mensajería unificada de Exchange, debe usar un mínimo de Exchange 2010 SP1 para obtener soporte técnico para el equilibrio de carga de DNS de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="340d9-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="340d9-123">Si usa alguna versión anterior de Exchange, los usuarios no tendrán capacidades de conmutación por error para estos escenarios de la mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="340d9-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="340d9-124">Reproducir el correo de voz de la empresa en su teléfono</span><span class="sxs-lookup"><span data-stu-id="340d9-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="340d9-125">Transferir llamadas de un operador automático de la mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="340d9-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="340d9-126">Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="340d9-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="340d9-127">Implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director</span><span class="sxs-lookup"><span data-stu-id="340d9-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="340d9-128">Para implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director, es necesario realizar un par de pasos adicionales con los registros de DNS y los FQDN.</span><span class="sxs-lookup"><span data-stu-id="340d9-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="340d9-129">Si un grupo de servidores usa equilibrio de carga de DNS, necesita tener dos FQDN: el FQDN normal del grupo que usa el equilibrio de carga de DNS (como, por ejemplo, pool01.contoso.com) y que se resuelve en las IP físicas de los servidores del grupo, y otro FQDN para los servicios web del grupo (como, por ejemplo, web01.contoso.com), que se resuelve como la dirección IP virtual del grupo.</span><span class="sxs-lookup"><span data-stu-id="340d9-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="340d9-130">En el generador de topología, si desea implementar el equilibrio de carga de DNS para un grupo, para crear este FQDN adicional para los servicios web del grupo, debe activar la casilla **invalidar FQDN del grupo de servicios Web internos** y escribir el FQDN, en **especificar las direcciones URL de servicios web para Esta** página de grupo.</span><span class="sxs-lookup"><span data-stu-id="340d9-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="340d9-p107">Para admitir el FQDN que usa el equilibrio de carga de DNS, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (como, por ejemplo, pool01.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Necesita incluir solo las direcciones IP de los servidores implementados actualmente.</span><span class="sxs-lookup"><span data-stu-id="340d9-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="340d9-133">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="340d9-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="340d9-134">Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="340d9-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="340d9-135">Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="340d9-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="340d9-136">Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="340d9-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="340d9-137">Equilibrio de carga de DNS en grupos de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="340d9-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="340d9-p109">Puede implementar el equilibrio de carga de DNS en grupos de servidores perimetrales. Si lo hace, necesita tener en cuenta varias consideraciones.</span><span class="sxs-lookup"><span data-stu-id="340d9-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="340d9-140">El uso del equilibrio de carga de DNS en los servidores perimetrales provoca una pérdida en la capacidad de conmutación por error, en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="340d9-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="340d9-141">Federación con organizaciones que ejecutan versiones de Office Communications Server publicadas antes de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="340d9-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="340d9-142">Intercambio de mensajes instantáneos con usuarios de servicios de mensajería instantánea (mi)\!públicos AOLand Yahoo, además de servidores y proveedores basados en XMPP, como Google Talk.</span><span class="sxs-lookup"><span data-stu-id="340d9-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="340d9-143">Actualmente, Google Talk es el único socio XMPP admitido.</span><span class="sxs-lookup"><span data-stu-id="340d9-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="340d9-144">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="340d9-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="340d9-145">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="340d9-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="340d9-146">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="340d9-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="340d9-147">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="340d9-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="340d9-148">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="340d9-148">has been announced.</span></span> <span data-ttu-id="340d9-149">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="340d9-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="340d9-150">Estos escenarios funcionarán siempre que se ejecuten correctamente todos los servidores perimetrales del grupo pero, si un servidor perimetral no está disponible, fallarán todas las solicitudes de estos escenarios que se envíen a él, en lugar de redirigirse a otro servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="340d9-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="340d9-151">Si usa la mensajería unificada de Exchange, debe usar un mínimo de 2013 de Exchange para obtener compatibilidad con el equilibrio de carga de DNS de Lync Server en Edge.</span><span class="sxs-lookup"><span data-stu-id="340d9-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="340d9-152">Si usa alguna versión anterior de Exchange, los usuarios remotos no tendrán capacidades de conmutación por error para estos escenarios de mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="340d9-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="340d9-153">Reproducir el correo de voz de la empresa en su teléfono</span><span class="sxs-lookup"><span data-stu-id="340d9-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="340d9-154">Transferir llamadas de un operador automático de la mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="340d9-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="340d9-155">Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="340d9-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="340d9-p112">La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="340d9-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="340d9-158">Implementar el equilibrio de carga de DNS en grupos de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="340d9-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="340d9-159">Para implementar el equilibrio de carga de DNS en la interfaz externa del grupo de servidores perimetrales, necesita las siguientes entradas de DNS:</span><span class="sxs-lookup"><span data-stu-id="340d9-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="340d9-p113">Para el servicio perimetral de acceso, necesita una entrada por cada servidor del grupo. Cada entrada necesita resolver el FQDN del servicio perimetral de acceso (por ejemplo, sip.contoso.com) en la dirección IP del servicio perimetral de acceso de uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="340d9-p113">For the Access Edge service, you need one entry for each server in the pool. Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="340d9-p114">Para el servicio perimetral de conferencia web, necesita una entrada por cada servidor del grupo. Cada entrada necesita resolver el FQDN del servicio perimetral de conferencia web (por ejemplo, webconf.contoso.com) en la dirección IP del servicio perimetral de conferencia web de uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="340d9-p114">For the Web Conferencing Edge service, you need one entry for each server in the pool. Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="340d9-164">Para el servicio perimetral de audio y vídeo, necesita una entrada por cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="340d9-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="340d9-165">Cada entrada debe resolver el FQDN del servicio perimetral de audio/vídeo (por ejemplo, av.contoso.com) a la dirección IP del servicio de borde A/V de uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="340d9-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="340d9-166">Para implementar el equilibrio de carga de DNS en la interfaz interna del grupo de servidores perimetrales, necesita agregar un registro A de DNS que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="340d9-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="340d9-167">Usar el equilibrio de carga de DNS en grupos de servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="340d9-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="340d9-p116">Puede usar el equilibrio de carga de DNS en grupos de servidores de mediación independientes. Todo el tráfico de medios y SIP se equilibra con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="340d9-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="340d9-170">Para implementar el equilibrio de carga de DNS en un grupo de servidores de mediación, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (por ejemplo, mediationpool1.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.).</span><span class="sxs-lookup"><span data-stu-id="340d9-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="340d9-171">Bloquear tráfico a un servidor con equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="340d9-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="340d9-p117">Si utiliza el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente con solo quitar las entradas de direcciones IP del grupo FQDN. También necesita quitar la entrada de DNS para el equipo.</span><span class="sxs-lookup"><span data-stu-id="340d9-p117">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="340d9-174">Tenga en cuenta que para el tráfico de servidor a servidor, Lync Server 2013 usa el equilibrio de carga para la topología.</span><span class="sxs-lookup"><span data-stu-id="340d9-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="340d9-175">Los servidores leen la topología Publicada en el almacén central de administración para obtener los FQDN de los servidores de la topología y distribuyen automáticamente el tráfico entre los servidores.</span><span class="sxs-lookup"><span data-stu-id="340d9-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="340d9-176">Para bloquear un servidor para que no reciba tráfico de servidor a servidor, necesita quitar el servidor de la topología.</span><span class="sxs-lookup"><span data-stu-id="340d9-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


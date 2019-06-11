---
title: 'Lync Server 2013: Requisitos del equilibrador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d5b10a91f469bf4688de06e836e0bdeffae1112
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="0bebe-102">Requisitos del equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bebe-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bebe-103">_**Última modificación del tema:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="0bebe-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="0bebe-104">La topología de borde consolidado de Lync Server 2013 escalada está optimizada para el equilibrio de carga de DNS para implementaciones nuevas que se federan principalmente con otras organizaciones que usan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bebe-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="0bebe-105">Si se requiere una alta disponibilidad para cualquiera de los siguientes escenarios, se debe usar un equilibrador de carga de hardware en los grupos de servidores perimetrales para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bebe-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="0bebe-106">Federación con organizaciones que usan Office Communications Server 2007 R2 u Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="0bebe-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="0bebe-107">Mensajería unificada de Exchange para usuarios remotos que usan la mensajería unificada de Exchange antes de Exchange 2010 con SP1</span><span class="sxs-lookup"><span data-stu-id="0bebe-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="0bebe-108">Conectividad con usuarios de mensajería instantánea (MI) pública</span><span class="sxs-lookup"><span data-stu-id="0bebe-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0bebe-p102">No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Necesita utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="0bebe-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0bebe-p103">Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna necesitará configurarse para que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno.</span><span class="sxs-lookup"><span data-stu-id="0bebe-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0bebe-113">El NAT de Return de servidor directo (DSR) no es compatible con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bebe-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="0bebe-114">Para determinar si su equilibrador de carga de hardware admite las características necesarias para Lync Server 2013, consulte "Lync Server 2010 de equilibrador de carga [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)" en.</span><span class="sxs-lookup"><span data-stu-id="0bebe-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="0bebe-115">Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="0bebe-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="0bebe-116">Estos son los requisitos del equilibrador de carga de hardware para los servidores perimetrales que ejecutan el servicio perimetral A/V:</span><span class="sxs-lookup"><span data-stu-id="0bebe-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="0bebe-p104">Deshabilitar el algoritmo de Nagle de TCP para los puertos 443 internos y externos. El algoritmo de Nagle es el proceso de combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.</span><span class="sxs-lookup"><span data-stu-id="0bebe-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="0bebe-119">Deshabilitar el algoritmo de Nagle de TCP para el intervalo de puertos externos de 50 000 a 59 999.</span><span class="sxs-lookup"><span data-stu-id="0bebe-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="0bebe-120">No utilizar NAT en el firewall interno o externo.</span><span class="sxs-lookup"><span data-stu-id="0bebe-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="0bebe-121">La interfaz interna de Edge debe estar en una red diferente a la de la interfaz externa del servidor perimetral y el enrutamiento entre ellas debe estar deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0bebe-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="0bebe-122">La interfaz externa del servidor perimetral que ejecuta el servicio de borde A/V debe usar direcciones IP enrutables públicamente y sin traducción de NAT o puerto en ninguna de las direcciones IP externas de Edge.</span><span class="sxs-lookup"><span data-stu-id="0bebe-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="0bebe-123">Requisitos del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="0bebe-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="0bebe-124">Los requisitos de afinidad basados en cookies se reducen enormemente en Lync Server 2013 para servicios Web.</span><span class="sxs-lookup"><span data-stu-id="0bebe-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="0bebe-125">Si implementa Lync Server 2013 y no va a conservar ninguno de los servidores front-end de Lync Server 2010 ni los grupos front-end, no necesita persistencia basada en cookies.</span><span class="sxs-lookup"><span data-stu-id="0bebe-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="0bebe-126">Sin embargo, si conservará de forma temporal o permanente los servidores front-end de Lync Server 2010 o las agrupaciones front end, seguirá usando la persistencia basada en cookies a medida que se implemente y se configure para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0bebe-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bebe-127"><STRONG>La utilización de la afinidad basada en cookies pese a que su implementación no la necesite</STRONG> no tiene repercusiones.</span><span class="sxs-lookup"><span data-stu-id="0bebe-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="0bebe-128">Para las implementaciones que **no utilizarán** la afinidad basada en cookies:</span><span class="sxs-lookup"><span data-stu-id="0bebe-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="0bebe-129">En la regla de publicación del proxy inverso para el puerto 4443, establezca **Reenviar encabezado de host** en True.</span><span class="sxs-lookup"><span data-stu-id="0bebe-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="0bebe-130">Esto garantizará que se reenviará la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="0bebe-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="0bebe-131">Para las implementaciones que **utilizarán** la afinidad basada en cookies:</span><span class="sxs-lookup"><span data-stu-id="0bebe-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="0bebe-p107">En la regla de publicación del proxy inverso para el puerto 4443, establezca **Reenviar encabezado de host** en True. Esto garantizará que se reenviará la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="0bebe-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="0bebe-134">La cookie del equilibrador de carga de hardware NO NECESITA estar marcada como httpOnly</span><span class="sxs-lookup"><span data-stu-id="0bebe-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="0bebe-135">La cookie del equilibrador de carga de hardware NO NECESITA tener tiempo de expiración</span><span class="sxs-lookup"><span data-stu-id="0bebe-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="0bebe-136">La cookie del equilibrador de carga de hardware NECESITA tener el nombre **MS-WSMAN** (este es el valor esperado por los servicios web y no puede modificarse)</span><span class="sxs-lookup"><span data-stu-id="0bebe-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="0bebe-p108">La cookie del equilibrador de carga de hardware NECESITA estar establecida en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en la misma conexión TCP ya había obtenido una cookie. Si el equilibrador de carga optimiza la inserción de cookies para que solo ocurra una vez por conexión TCP, la optimización NO NECESITA usarse.</span><span class="sxs-lookup"><span data-stu-id="0bebe-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bebe-139">Las configuraciones típicas de equilibrado de carga de hardware usan afinidad de dirección de origen y 20 minutos de duración de la sesión TCP, lo cual es adecuado para clientes de Lync Server y Lync 2013 porque se mantiene el estado de la sesión a través del uso del cliente o la interacción de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0bebe-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="0bebe-140">Si se implementan dispositivos móviles, es preciso que el equilibrador de carga de hardware pueda equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, necesita poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).</span><span class="sxs-lookup"><span data-stu-id="0bebe-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0bebe-p109">Los equilibradores de carga de hardware F5 tienen una característica llamada OneConnect que asegura que cada solicitud dentro de una conexión TCP tenga carga equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor del equilibrador de carga de hardware admita la misma función. Las últimas aplicaciones móviles que utilizan Apple iOS requieren la versión 1.2 de la seguridad de la capa de transporte (TLS). Para ellos, F5 proporciona una configuración específica.</span><span class="sxs-lookup"><span data-stu-id="0bebe-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="0bebe-145">Para obtener detalles sobre los equilibradores de carga de hardware de terceros, consulte<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="0bebe-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="0bebe-146">A continuación, se muestran los requisitos del equilibrador de carga de hardware para los servicios web del grupo de servidores front-end y de directores:</span><span class="sxs-lookup"><span data-stu-id="0bebe-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="0bebe-147">Para los VIP de servicios Web internos,\_establezca la persistencia de la dirección de origen (puerto interno 80, 443) en el equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="0bebe-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="0bebe-148">Para Lync Server 2013, la\_persistencia de la dirección de origen significa que siempre se envían varias conexiones provenientes de una única dirección IP a un servidor para mantener el estado de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0bebe-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="0bebe-149">Use un tiempo de espera de inactividad de TCP de 1800 segundos.</span><span class="sxs-lookup"><span data-stu-id="0bebe-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="0bebe-p111">En el firewall entre el proxy inverso y el equilibrador de carga de hardware del grupo de servidores del próximo salto, cree una regla que permita el tráfico https: en el puerto 4443, desde el proxy inverso al equilibrador de carga de hardware. El equilibrador de carga de hardware necesita configurarse para que escuche los puertos 80, 443 y 4443.</span><span class="sxs-lookup"><span data-stu-id="0bebe-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0bebe-152">Para obtener más lecturas sobre la configuración del equilibrador de carga de hardware, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumen de puerto: borde consolidado escalado con equilibradores de carga de hardware de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0bebe-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="0bebe-153">Resumen de los requisitos de afinidad del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="0bebe-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bebe-154">Ubicación de cliente/usuario</span><span class="sxs-lookup"><span data-stu-id="0bebe-154">Client/user location</span></span></th>
<th><span data-ttu-id="0bebe-155">Requisitos de afinidad del FQDN de servicios web externos</span><span class="sxs-lookup"><span data-stu-id="0bebe-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="0bebe-156">Requisitos de afinidad del FQDN de servicios web internos</span><span class="sxs-lookup"><span data-stu-id="0bebe-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bebe-157">Lync Web App (usuarios internos y externos)</span><span class="sxs-lookup"><span data-stu-id="0bebe-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="0bebe-158">Dispositivo móvil (usuarios internos y externos)</span><span class="sxs-lookup"><span data-stu-id="0bebe-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="0bebe-159">Sin afinidad</span><span class="sxs-lookup"><span data-stu-id="0bebe-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="0bebe-160">Afinidad de direcciones de origen</span><span class="sxs-lookup"><span data-stu-id="0bebe-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bebe-161">Lync Web App (solo usuarios externos)</span><span class="sxs-lookup"><span data-stu-id="0bebe-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="0bebe-162">Dispositivo móvil (usuarios internos y externos)</span><span class="sxs-lookup"><span data-stu-id="0bebe-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="0bebe-163">Sin afinidad</span><span class="sxs-lookup"><span data-stu-id="0bebe-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="0bebe-164">Afinidad de direcciones de origen</span><span class="sxs-lookup"><span data-stu-id="0bebe-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bebe-165">Lync Web App (solo para usuarios internos)</span><span class="sxs-lookup"><span data-stu-id="0bebe-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="0bebe-166">Dispositivo móvil (no implementado)</span><span class="sxs-lookup"><span data-stu-id="0bebe-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="0bebe-167">Sin afinidad</span><span class="sxs-lookup"><span data-stu-id="0bebe-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="0bebe-168">Afinidad de direcciones de origen</span><span class="sxs-lookup"><span data-stu-id="0bebe-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="0bebe-169">Supervisión de puertos para los equilibradores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="0bebe-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="0bebe-170">Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles por errores de comunicaciones o de hardware.</span><span class="sxs-lookup"><span data-stu-id="0bebe-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="0bebe-171">Por ejemplo, si se detiene el servicio servidor front-end (RTCSRV) porque se produce un error en el servidor front-end o en la agrupación front end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="0bebe-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="0bebe-172">La supervisión de puertos en ECH tiene que implementarse para supervisar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bebe-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="0bebe-173">Grupo de usuarios del servidor front-end – interfaz interna de HLB</span><span class="sxs-lookup"><span data-stu-id="0bebe-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bebe-174">Puerto/IP virtual</span><span class="sxs-lookup"><span data-stu-id="0bebe-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="0bebe-175">Puerto de nodo</span><span class="sxs-lookup"><span data-stu-id="0bebe-175">Node Port</span></span></th>
<th><span data-ttu-id="0bebe-176">Monitor/máquina de nodo</span><span class="sxs-lookup"><span data-stu-id="0bebe-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="0bebe-177">Perfil de persistencia</span><span class="sxs-lookup"><span data-stu-id="0bebe-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="0bebe-178">Notas</span><span class="sxs-lookup"><span data-stu-id="0bebe-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bebe-179">&lt;Web&gt;de Pool-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="0bebe-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="0bebe-180">443</span><span class="sxs-lookup"><span data-stu-id="0bebe-180">443</span></span></p></td>
<td><p><span data-ttu-id="0bebe-181">443</span><span class="sxs-lookup"><span data-stu-id="0bebe-181">443</span></span></p></td>
<td><p><span data-ttu-id="0bebe-182">Front-end</span><span class="sxs-lookup"><span data-stu-id="0bebe-182">Front End</span></span></p>
<p><span data-ttu-id="0bebe-183">5061</span><span class="sxs-lookup"><span data-stu-id="0bebe-183">5061</span></span></p></td>
<td><p><span data-ttu-id="0bebe-184">Origen</span><span class="sxs-lookup"><span data-stu-id="0bebe-184">Source</span></span></p></td>
<td><p><span data-ttu-id="0bebe-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0bebe-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bebe-186">&lt;Web&gt;de Pool-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="0bebe-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="0bebe-187">80</span><span class="sxs-lookup"><span data-stu-id="0bebe-187">80</span></span></p></td>
<td><p><span data-ttu-id="0bebe-188">80</span><span class="sxs-lookup"><span data-stu-id="0bebe-188">80</span></span></p></td>
<td><p><span data-ttu-id="0bebe-189">Front-end</span><span class="sxs-lookup"><span data-stu-id="0bebe-189">Front End</span></span></p>
<p><span data-ttu-id="0bebe-190">5061</span><span class="sxs-lookup"><span data-stu-id="0bebe-190">5061</span></span></p></td>
<td><p><span data-ttu-id="0bebe-191">Origen</span><span class="sxs-lookup"><span data-stu-id="0bebe-191">Source</span></span></p></td>
<td><p><span data-ttu-id="0bebe-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="0bebe-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="0bebe-193">Grupo de usuarios del servidor front-end: HLB externa</span><span class="sxs-lookup"><span data-stu-id="0bebe-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bebe-194">Puerto/IP virtual</span><span class="sxs-lookup"><span data-stu-id="0bebe-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="0bebe-195">Puerto de nodo</span><span class="sxs-lookup"><span data-stu-id="0bebe-195">Node Port</span></span></th>
<th><span data-ttu-id="0bebe-196">Monitor/máquina de nodo</span><span class="sxs-lookup"><span data-stu-id="0bebe-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="0bebe-197">Perfil de persistencia</span><span class="sxs-lookup"><span data-stu-id="0bebe-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="0bebe-198">Notas</span><span class="sxs-lookup"><span data-stu-id="0bebe-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bebe-199">&lt;Grupo&gt;web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="0bebe-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="0bebe-200">443</span><span class="sxs-lookup"><span data-stu-id="0bebe-200">443</span></span></p></td>
<td><p><span data-ttu-id="0bebe-201">4443</span><span class="sxs-lookup"><span data-stu-id="0bebe-201">4443</span></span></p></td>
<td><p><span data-ttu-id="0bebe-202">Front-end</span><span class="sxs-lookup"><span data-stu-id="0bebe-202">Front End</span></span></p>
<p><span data-ttu-id="0bebe-203">5061</span><span class="sxs-lookup"><span data-stu-id="0bebe-203">5061</span></span></p></td>
<td><p><span data-ttu-id="0bebe-204">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0bebe-204">None</span></span></p></td>
<td><p><span data-ttu-id="0bebe-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0bebe-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bebe-206">&lt;Grupo&gt;web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="0bebe-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="0bebe-207">80</span><span class="sxs-lookup"><span data-stu-id="0bebe-207">80</span></span></p></td>
<td><p><span data-ttu-id="0bebe-208">8080</span><span class="sxs-lookup"><span data-stu-id="0bebe-208">8080</span></span></p></td>
<td><p><span data-ttu-id="0bebe-209">Front-end</span><span class="sxs-lookup"><span data-stu-id="0bebe-209">Front End</span></span></p>
<p><span data-ttu-id="0bebe-210">5061</span><span class="sxs-lookup"><span data-stu-id="0bebe-210">5061</span></span></p></td>
<td><p><span data-ttu-id="0bebe-211">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0bebe-211">None</span></span></p></td>
<td><p><span data-ttu-id="0bebe-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="0bebe-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


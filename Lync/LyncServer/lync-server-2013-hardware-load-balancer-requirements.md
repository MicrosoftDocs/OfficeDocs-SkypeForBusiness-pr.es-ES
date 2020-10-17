---
title: Requisitos del equilibrador de carga de hardware de Lync Server 2013
description: Requisitos del equilibrador de carga de hardware de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552926"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="416a3-103">Requisitos del equilibrador de carga de hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="416a3-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="416a3-104">_**Última modificación del tema:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="416a3-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="416a3-105">La topología perimetral consolidada escalada 2013 de Lync Server está optimizada para el equilibrio de carga de DNS para implementaciones nuevas que se federan principalmente con otras organizaciones que usan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="416a3-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="416a3-106">En caso de que se necesite una gran disponibilidad en cualquiera de los siguientes escenarios, se deberá usar un equilibrador de carga de hardware en grupos de servidores perimetrales:</span><span class="sxs-lookup"><span data-stu-id="416a3-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="416a3-107">Federación con organizaciones que usan Office Communications Server 2007 R2 u Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="416a3-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="416a3-108">Mensajería unificada de Exchange para usuarios remotos con Exchange UM antes de Exchange 2010 con SP1</span><span class="sxs-lookup"><span data-stu-id="416a3-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="416a3-109">Conectividad con usuarios de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="416a3-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="416a3-p102">No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Debe utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="416a3-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="416a3-p103">Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna deberá configurarse de modo que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno.</span><span class="sxs-lookup"><span data-stu-id="416a3-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="416a3-114">La NAT de Direct Server Return (DSR) no es compatible con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="416a3-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="416a3-115">Para determinar si el equilibrador de carga de hardware admite las características necesarias para Lync Server 2013, consulte "Lync Server 2010 load balancer Partners" en [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="416a3-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="416a3-116">Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="416a3-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="416a3-117">A continuación, se indican los requisitos del equilibrador de carga de hardware para los servidores perimetrales que ejecutan el servicio perimetral A/V:</span><span class="sxs-lookup"><span data-stu-id="416a3-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="416a3-p104">Inhabilitar la aplicación del algoritmo de Nagle TCP para los puertos 443 internos y externos. La aplicación del algoritmo de Nagle es la combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.</span><span class="sxs-lookup"><span data-stu-id="416a3-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="416a3-120">Inhabilitar la aplicación del algoritmo de Nagle TCP para el intervalo de puertos externos de 50.000 a 59.999.</span><span class="sxs-lookup"><span data-stu-id="416a3-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="416a3-121">No usar NAT en el firewall interno o externo.</span><span class="sxs-lookup"><span data-stu-id="416a3-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="416a3-122">La interfaz interna del servidor perimetral y la interfaz externa del servidor perimetral deben estar en redes diferentes, y debe inhabilitarse el enrutamiento entre ellas.</span><span class="sxs-lookup"><span data-stu-id="416a3-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="416a3-123">La interfaz externa del servidor perimetral que ejecuta el servicio perimetral A/V debe usar direcciones IP enrutables públicamente y no NAT o traducción de puerto en ninguna de las direcciones IP externas del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="416a3-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="416a3-124">Requisitos del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="416a3-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="416a3-125">Los requisitos de afinidad basada en cookies se reducen en gran medida en Lync Server 2013 para los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="416a3-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="416a3-126">Si va a implementar Lync Server 2013 y no va a conservar ningún servidor front-end de Lync Server 2010 o grupo de servidores front-end, no necesita persistencia basada en cookies.</span><span class="sxs-lookup"><span data-stu-id="416a3-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="416a3-127">Sin embargo, si va a conservar de forma temporal o permanente los servidores front-end de Lync Server 2010 o los grupos de servidores front-end, seguirá usando la persistencia basada en cookies mientras se implementa y configura para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="416a3-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="416a3-128"><STRONG>La utilización de la afinidad basada en cookies pese a que su implementación no la necesite</STRONG> no tiene repercusiones.</span><span class="sxs-lookup"><span data-stu-id="416a3-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="416a3-129">Para las implementaciones que **no utilicen** la afinidad basada en cookies:</span><span class="sxs-lookup"><span data-stu-id="416a3-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="416a3-p106">En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.</span><span class="sxs-lookup"><span data-stu-id="416a3-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="416a3-132">Para las implementaciones que **utilicen** la afinidad basada en cookies:</span><span class="sxs-lookup"><span data-stu-id="416a3-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="416a3-p107">En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.</span><span class="sxs-lookup"><span data-stu-id="416a3-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="416a3-135">La cookie de equilibrio de carga de hardware NO DEBE estar marcada como httpOnly</span><span class="sxs-lookup"><span data-stu-id="416a3-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="416a3-136">La cookie de equilibrio de carga de hardware NO DEBE tener tiempo de expiración</span><span class="sxs-lookup"><span data-stu-id="416a3-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="416a3-137">La cookie de equilibrio de carga de hardware DEBE tener el nombre **MS-WSMAN** (este es el esperado por los servicios web y no puede modificarse)</span><span class="sxs-lookup"><span data-stu-id="416a3-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="416a3-p108">La cookie de equilibrio de carga de hardware DEBE estar establecida en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en la misma conexión TCP ya había obtenido una cookie. Si el equilibrador de carga optimiza la inserción de cookies para que solo ocurra una vez por conexión TCP, la optimización NO debe usarse.</span><span class="sxs-lookup"><span data-stu-id="416a3-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="416a3-140">Las configuraciones típicas del equilibrador de carga de hardware usan la afinidad de dirección de origen y una duración de la sesión TCP mín. TCP, que es adecuada para clientes de Lync Server y Lync 2013 porque el estado de sesión se mantiene a través del uso del cliente o la interacción de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="416a3-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="416a3-141">Si se implementan dispositivos móviles, el equilibrador de carga de hardware debe poder equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).</span><span class="sxs-lookup"><span data-stu-id="416a3-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="416a3-p109">Los equilibradores de carga de hardware F5 tienen una característica llamada OneConnect que asegura que cada solicitud dentro de una conexión TCP tenga carga equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor del equilibrador de carga de hardware admita la misma funcionalidad. Las últimas aplicaciones móviles que utilizan el sistema Apple iOS requieren el uso seguridad de capa de transporte (TLS), versión 1.2. F5 proporciona opciones de configuración específicas para este sistema.</span><span class="sxs-lookup"><span data-stu-id="416a3-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="416a3-146">Para obtener más información sobre los equilibradores de carga de hardware de terceros, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="416a3-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="416a3-147">A continuación se muestran los requisitos del equilibrador de carga de hardware para servicios web de grupo de directores y de servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="416a3-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="416a3-148">Para VIP de servicios Web internos, establezca \_ la persistencia de la dirección de origen (puerto interno 80, 443) en el equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="416a3-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="416a3-149">Para Lync Server 2013, \_ la persistencia de la dirección de origen significa que siempre se envían varias conexiones procedentes de una dirección IP a un servidor para mantener el estado de la sesión.</span><span class="sxs-lookup"><span data-stu-id="416a3-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="416a3-150">Use un tiempo de espera de inactividad TCP de 1.800 segundos.</span><span class="sxs-lookup"><span data-stu-id="416a3-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="416a3-p111">En el firewall entre el proxy inverso y el equilibrador de carga de hardware del grupo de servidores del próximo salto, cree una regla que permita el tráfico https: en el puerto 4443, del proxy inverso al equilibrador de carga de hardware. El equilibrador de carga de hardware debe configurarse de modo que escuche los puertos 80, 443 y 4443.</span><span class="sxs-lookup"><span data-stu-id="416a3-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="416a3-153">Para obtener más información sobre la configuración del equilibrador de carga de hardware, revise <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumen de puertos-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="416a3-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="416a3-154">Resumen de requisitos de afinidad del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="416a3-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="416a3-155">Ubicación de cliente/usuario</span><span class="sxs-lookup"><span data-stu-id="416a3-155">Client/user location</span></span></th>
<th><span data-ttu-id="416a3-156">Requisitos de afinidad del FQDN de servicios web externos</span><span class="sxs-lookup"><span data-stu-id="416a3-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="416a3-157">Requisitos de afinidad del FQDN de servicios web internos</span><span class="sxs-lookup"><span data-stu-id="416a3-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="416a3-158">Lync Web App (usuarios internos y externos)</span><span class="sxs-lookup"><span data-stu-id="416a3-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="416a3-159">Dispositivo móvil (usuarios internos y externos)</span><span class="sxs-lookup"><span data-stu-id="416a3-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="416a3-160">Sin afinidad</span><span class="sxs-lookup"><span data-stu-id="416a3-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="416a3-161">Afinidad de direcciones de origen</span><span class="sxs-lookup"><span data-stu-id="416a3-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="416a3-162">Lync Web App (solo usuarios externos)</span><span class="sxs-lookup"><span data-stu-id="416a3-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="416a3-163">Dispositivo móvil (usuarios internos y externos)</span><span class="sxs-lookup"><span data-stu-id="416a3-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="416a3-164">Sin afinidad</span><span class="sxs-lookup"><span data-stu-id="416a3-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="416a3-165">Afinidad de direcciones de origen</span><span class="sxs-lookup"><span data-stu-id="416a3-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="416a3-166">Lync Web App (solo usuarios internos)</span><span class="sxs-lookup"><span data-stu-id="416a3-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="416a3-167">Dispositivo móvil (no implementado)</span><span class="sxs-lookup"><span data-stu-id="416a3-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="416a3-168">Sin afinidad</span><span class="sxs-lookup"><span data-stu-id="416a3-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="416a3-169">Afinidad de direcciones de origen</span><span class="sxs-lookup"><span data-stu-id="416a3-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="416a3-170">Supervisión de puertos para los equilibradores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="416a3-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="416a3-171">Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles debido a errores de comunicaciones o de hardware.</span><span class="sxs-lookup"><span data-stu-id="416a3-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="416a3-172">Por ejemplo, si el servicio de servidor front-end (RTCSRV) se detiene debido a un error en el servidor front-end o en el grupo de servidores front-end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="416a3-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="416a3-173">La supervisión de puertos en el equilibrador de carga de hardware debe implementarse para supervisar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="416a3-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="416a3-174">Grupo de usuarios del servidor front-end – interfaz interna de HLB</span><span class="sxs-lookup"><span data-stu-id="416a3-174">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="416a3-175">Puerto/IP virtual</span><span class="sxs-lookup"><span data-stu-id="416a3-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="416a3-176">Puerto de nodo</span><span class="sxs-lookup"><span data-stu-id="416a3-176">Node Port</span></span></th>
<th><span data-ttu-id="416a3-177">Monitor/máquina de nodo</span><span class="sxs-lookup"><span data-stu-id="416a3-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="416a3-178">Perfil de persistencia</span><span class="sxs-lookup"><span data-stu-id="416a3-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="416a3-179">Notas</span><span class="sxs-lookup"><span data-stu-id="416a3-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="416a3-180">&lt;&gt;Web-int_mco_443_vs de grupo</span><span class="sxs-lookup"><span data-stu-id="416a3-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="416a3-181">443</span><span class="sxs-lookup"><span data-stu-id="416a3-181">443</span></span></p></td>
<td><p><span data-ttu-id="416a3-182">443</span><span class="sxs-lookup"><span data-stu-id="416a3-182">443</span></span></p></td>
<td><p><span data-ttu-id="416a3-183">Front-end</span><span class="sxs-lookup"><span data-stu-id="416a3-183">Front End</span></span></p>
<p><span data-ttu-id="416a3-184">5061</span><span class="sxs-lookup"><span data-stu-id="416a3-184">5061</span></span></p></td>
<td><p><span data-ttu-id="416a3-185">Origen</span><span class="sxs-lookup"><span data-stu-id="416a3-185">Source</span></span></p></td>
<td><p><span data-ttu-id="416a3-186">HTTPS</span><span class="sxs-lookup"><span data-stu-id="416a3-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="416a3-187">&lt;&gt;Web-int_mco_80_vs de grupo</span><span class="sxs-lookup"><span data-stu-id="416a3-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="416a3-188">80</span><span class="sxs-lookup"><span data-stu-id="416a3-188">80</span></span></p></td>
<td><p><span data-ttu-id="416a3-189">80</span><span class="sxs-lookup"><span data-stu-id="416a3-189">80</span></span></p></td>
<td><p><span data-ttu-id="416a3-190">Front-end</span><span class="sxs-lookup"><span data-stu-id="416a3-190">Front End</span></span></p>
<p><span data-ttu-id="416a3-191">5061</span><span class="sxs-lookup"><span data-stu-id="416a3-191">5061</span></span></p></td>
<td><p><span data-ttu-id="416a3-192">Origen</span><span class="sxs-lookup"><span data-stu-id="416a3-192">Source</span></span></p></td>
<td><p><span data-ttu-id="416a3-193">HTTP</span><span class="sxs-lookup"><span data-stu-id="416a3-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="416a3-194">Grupo de usuarios del servidor front-end: interfaz externa de HLB</span><span class="sxs-lookup"><span data-stu-id="416a3-194">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="416a3-195">Puerto/IP virtual</span><span class="sxs-lookup"><span data-stu-id="416a3-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="416a3-196">Puerto de nodo</span><span class="sxs-lookup"><span data-stu-id="416a3-196">Node Port</span></span></th>
<th><span data-ttu-id="416a3-197">Monitor/máquina de nodo</span><span class="sxs-lookup"><span data-stu-id="416a3-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="416a3-198">Perfil de persistencia</span><span class="sxs-lookup"><span data-stu-id="416a3-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="416a3-199">Notas</span><span class="sxs-lookup"><span data-stu-id="416a3-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="416a3-200">&lt;web_mco_443_vs de grupo &gt;</span><span class="sxs-lookup"><span data-stu-id="416a3-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="416a3-201">443</span><span class="sxs-lookup"><span data-stu-id="416a3-201">443</span></span></p></td>
<td><p><span data-ttu-id="416a3-202">4443</span><span class="sxs-lookup"><span data-stu-id="416a3-202">4443</span></span></p></td>
<td><p><span data-ttu-id="416a3-203">Front-end</span><span class="sxs-lookup"><span data-stu-id="416a3-203">Front End</span></span></p>
<p><span data-ttu-id="416a3-204">5061</span><span class="sxs-lookup"><span data-stu-id="416a3-204">5061</span></span></p></td>
<td><p><span data-ttu-id="416a3-205">Ninguno</span><span class="sxs-lookup"><span data-stu-id="416a3-205">None</span></span></p></td>
<td><p><span data-ttu-id="416a3-206">HTTPS</span><span class="sxs-lookup"><span data-stu-id="416a3-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="416a3-207">&lt;web_mco_80_vs de grupo &gt;</span><span class="sxs-lookup"><span data-stu-id="416a3-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="416a3-208">80</span><span class="sxs-lookup"><span data-stu-id="416a3-208">80</span></span></p></td>
<td><p><span data-ttu-id="416a3-209">8080</span><span class="sxs-lookup"><span data-stu-id="416a3-209">8080</span></span></p></td>
<td><p><span data-ttu-id="416a3-210">Front-end</span><span class="sxs-lookup"><span data-stu-id="416a3-210">Front End</span></span></p>
<p><span data-ttu-id="416a3-211">5061</span><span class="sxs-lookup"><span data-stu-id="416a3-211">5061</span></span></p></td>
<td><p><span data-ttu-id="416a3-212">Ninguno</span><span class="sxs-lookup"><span data-stu-id="416a3-212">None</span></span></p></td>
<td><p><span data-ttu-id="416a3-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="416a3-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


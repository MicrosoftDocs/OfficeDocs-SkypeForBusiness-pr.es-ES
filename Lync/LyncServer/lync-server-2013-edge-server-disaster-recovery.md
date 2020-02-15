---
title: 'Lync Server 2013: recuperación ante desastres del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cd85a769d021aae6873a50a719a6043ef72f770
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="1e143-102">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e143-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e143-103">_**Última modificación del tema:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="1e143-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="1e143-p101">Como con otros roles de servidor, la mejor manera que tiene de proporcionar alta disponibilidad para sus servidores perimetrales es implementar varios servidores perimetrales en grupos de servidores en cada sitio. Si un servidor perimetral deja de funcionar, los demás servidores del grupo de servidores continuarán proporcionando servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="1e143-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="1e143-p102">Para habilitar los procedimientos de recuperación ante desastres, debe tener grupos de servidores perimetrales implementados en sitios independientes. No tiene que emparejar explícitamente grupos de servidores perimetrales como hace con grupos de servidores front-end, pero tener varios grupos de servidores perimetrales ofrece todavía la disponibilidad de continuar si un grupo de servidores perimetrales completo dejar de funcionar. Las secciones siguientes proporcionan detalles sobre la recuperación ante desastres para las distintas funciones de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="1e143-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="1e143-109">Acceso remoto</span><span class="sxs-lookup"><span data-stu-id="1e143-109">Remote Access</span></span>

<span data-ttu-id="1e143-110">Si tiene varios sitios, cada uno con un grupo de servidores perimetrales, y se produce un error en un grupo de servidores perimetrales completo, los servicios de acceso remoto seguirán funcionando sin necesidad de acciones del administrador.</span><span class="sxs-lookup"><span data-stu-id="1e143-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="1e143-111">Al crear grupos de servidores perimetrales en sitios diferentes, no se puede usar el mismo FQDN.</span><span class="sxs-lookup"><span data-stu-id="1e143-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="1e143-112">Cada grupo de servidores perimetrales debe tener FQDN únicos (internos y externos).</span><span class="sxs-lookup"><span data-stu-id="1e143-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="1e143-113">Los grupos de servidores perimetrales no utilizan reglas de publicación de proxy inverso para comunicarse con los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1e143-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="1e143-114">La conmutación por error automática se produce cuando el cliente vuelve a consultar los registros de servicio DNS de acceso remoto, y los usuarios remotos se enrutan a los servidores perimetrales de otro sitio.</span><span class="sxs-lookup"><span data-stu-id="1e143-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="1e143-115">El cliente intenta cada FQDN de perímetro externo de acuerdo con la prioridad de los registros DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="1e143-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e143-116">Para que la conmutación por error funcione sin problemas, asegúrese de que el Firewall permite que los servidores front-end de todos los grupos se comuniquen con todos los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="1e143-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="1e143-117">Federación</span><span class="sxs-lookup"><span data-stu-id="1e143-117">Federation</span></span>

<span data-ttu-id="1e143-118">Para las relaciones de Federación con otras organizaciones que ejecutan Lync Server, las solicitudes de Federación de entrada seguirán funcionando siempre que tenga soluciones como GTM de DNS geográfico.</span><span class="sxs-lookup"><span data-stu-id="1e143-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="1e143-119">Es importante comprender que la conmutación por error de Federación no proporciona conmutación por error con prioridad en los registros SRV.</span><span class="sxs-lookup"><span data-stu-id="1e143-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="1e143-120">Una solución proporcionada anteriormente puede ayudarle a proporcionar capacidades de recuperación ante desastres para la Federación entrante.</span><span class="sxs-lookup"><span data-stu-id="1e143-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="1e143-121">La federación saliente siempre se configura a través de un grupo de servidores perimetrales publicado o un servidor perimetral de la organización.</span><span class="sxs-lookup"><span data-stu-id="1e143-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="1e143-122">Si este grupo de servidores perimetrales ha quedado inactivo, debe usar el Generador de topologías para cambiar la ruta de federación saliente para que use un grupo de servidores perimetrales que se está ejecutando todavía.</span><span class="sxs-lookup"><span data-stu-id="1e143-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="1e143-123">Para obtener más información, consulte [conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server en Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="1e143-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="1e143-124">Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="1e143-124">XMPP Federation</span></span>

<span data-ttu-id="1e143-125">Para la federación XMPP, se producirá un error tanto en el tráfico entrante como en el saliente si el grupo de servidores perimetrales que está designado como la puerta de enlace de federación XMPP deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="1e143-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="1e143-126">Para que la federación XMPP vuelva a funcionar, debe cambiar la federación de XMPP para que use un grupo de servidores perimetrales diferente.</span><span class="sxs-lookup"><span data-stu-id="1e143-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="1e143-127">Para obtener más información, consulte [conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="1e143-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="1e143-128">Se produce un error en el grupo de servidores perimetrales pero el grupo de servidores front-end todavía se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="1e143-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="1e143-129">Si se produce un error en un grupo de servidores perimetrales en un sitio, pero el grupo de servidores front-end de ese sitio todavía se está ejecutando, tendrá que cambiar el grupo de servidores front-end para que use un grupo de servidores perimetrales diferente en un sitio diferente mientras que el primer grupo de servidores perimetrales ha dejado de funcionar.</span><span class="sxs-lookup"><span data-stu-id="1e143-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="1e143-130">Para obtener más información, consulte [cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="1e143-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


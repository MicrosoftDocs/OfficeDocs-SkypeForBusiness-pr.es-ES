---
title: 'Lync Server 2013: Recuperación ante desastres del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="b07a5-102">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b07a5-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b07a5-103">_**Última modificación del tema:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="b07a5-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="b07a5-104">Al igual que con otros roles de servidor, la mejor manera de proporcionar alta disponibilidad para los servidores perimetrales es implementar varios servidores perimetrales en grupos en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="b07a5-104">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site.</span></span> <span data-ttu-id="b07a5-105">Si un servidor perimetral deja de funcionar, los otros servidores del grupo seguirán proporcionando servicios de extremo.</span><span class="sxs-lookup"><span data-stu-id="b07a5-105">If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="b07a5-106">Para habilitar los procedimientos de recuperación ante desastres, debe disponer de grupos de servidores perimetrales separados en sitios diferentes.</span><span class="sxs-lookup"><span data-stu-id="b07a5-106">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites.</span></span> <span data-ttu-id="b07a5-107">No es necesario emparejar de manera explícita las agrupaciones periféricas como se hace con los grupos de aplicaciones para el usuario, pero tener varios grupos de límites aún proporciona la disponibilidad para funcionar si se produce la baja de un grupo de bordes completo.</span><span class="sxs-lookup"><span data-stu-id="b07a5-107">You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down.</span></span> <span data-ttu-id="b07a5-108">En las siguientes secciones se proporcionan detalles sobre la recuperación de desastres para las distintas funciones de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="b07a5-108">The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="b07a5-109">Acceso remoto</span><span class="sxs-lookup"><span data-stu-id="b07a5-109">Remote Access</span></span>

<span data-ttu-id="b07a5-110">Si tiene varios sitios, cada uno con un grupo de servidores perimetrales y se produce un error en una agrupación perimetral completa, los servicios de acceso remoto seguirán funcionando sin necesidad de acción de administrador.</span><span class="sxs-lookup"><span data-stu-id="b07a5-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="b07a5-111">Al crear grupos de borde en diferentes sitios, no se puede usar el mismo FQDN.</span><span class="sxs-lookup"><span data-stu-id="b07a5-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="b07a5-112">Cada grupo perimetral debe tener FQDN únicos (internos y externos).</span><span class="sxs-lookup"><span data-stu-id="b07a5-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="b07a5-113">Los conjuntos de bordes no usan reglas de publicación de proxy invertida para hablar con los servidores de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b07a5-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="b07a5-114">La conmutación por error automática se produce cuando el cliente vuelve a consultar los registros del servicio DNS de acceso remoto y los usuarios remotos se enrutan a los servidores perimetrales de otro sitio.</span><span class="sxs-lookup"><span data-stu-id="b07a5-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="b07a5-115">El cliente intenta cada FQDN de borde externo según la prioridad de los registros SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="b07a5-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b07a5-116">Para que la conmutación por error funcione sin problemas, asegúrese de que el Firewall permite que los servidores front-end de cada grupo se comuniquen con todos los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="b07a5-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="b07a5-117">Federación</span><span class="sxs-lookup"><span data-stu-id="b07a5-117">Federation</span></span>

<span data-ttu-id="b07a5-118">Para las relaciones de Federación con otras organizaciones que ejecutan Lync Server, las solicitudes de Federación entrante seguirán funcionando siempre y cuando tenga soluciones como el DNS geográfica GTM.</span><span class="sxs-lookup"><span data-stu-id="b07a5-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="b07a5-119">Es importante comprender que la conmutación por error de la Federación no proporciona la conmutación por error con prioridad en los registros SRV.</span><span class="sxs-lookup"><span data-stu-id="b07a5-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="b07a5-120">Una solución proporcionada anteriormente puede ayudarle a proporcionar capacidades de recuperación ante desastres para la Federación entrante.</span><span class="sxs-lookup"><span data-stu-id="b07a5-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="b07a5-121">La Federación saliente siempre se configura a través de un grupo perimetral publicado o un servidor perimetral en la organización.</span><span class="sxs-lookup"><span data-stu-id="b07a5-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="b07a5-122">Si este grupo de límites ha desaparecido, debe usar el generador de topología para cambiar la ruta de Federación saliente para usar un grupo de límites que aún se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="b07a5-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="b07a5-123">Para obtener más información, consulte [conmutación por error del grupo perimetral usado para la Federación de Lync Server en Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="b07a5-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="b07a5-124">Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="b07a5-124">XMPP Federation</span></span>

<span data-ttu-id="b07a5-125">Para la Federación XMPP, se producirá un error en el tráfico entrante y saliente si el grupo perimetral designado como la puerta de enlace de Federación XMPP deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="b07a5-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="b07a5-126">Para hacer que la Federación XMPP vuelva a funcionar, debe cambiar la Federación de XMPP para usar un grupo de borde diferente.</span><span class="sxs-lookup"><span data-stu-id="b07a5-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="b07a5-127">Para obtener más información, consulte [conmutación por error del grupo perimetral usado para la Federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="b07a5-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="b07a5-128">El grupo Edge falla pero el grupo de servidores front-end aún se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="b07a5-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="b07a5-129">Si se produce un error en un grupo de límites del sitio, pero el grupo de servidores front-end de ese sitio aún se está ejecutando, tendrá que cambiar el grupo de servidores front-end para usar un grupo de borde diferente en un sitio diferente mientras el primer grupo perimetral esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="b07a5-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="b07a5-130">Para obtener más información, vea [cambiar el grupo perimetral asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b07a5-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


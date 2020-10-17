---
title: 'Lync Server 2013: configurar interfaces de red para servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7eee448ffd5176797ebfbb0fb43afc4c9e41a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509827"
---
# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="d4fd2-102">Configurar interfaces de red para servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4fd2-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4fd2-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d4fd2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d4fd2-p101">Cada servidor perimetral es un equipo de host múltiple con interfaces orientadas interna y externamente. La configuración del adaptador de sistema de nombres de dominio (DNS) depende de si hay servidores DNS en la red perimetral. Si existen servidores DNS en el perímetro, deben tener una zona que contenga uno o más registros A de DNS para el servidor o el grupo de servidores del próximo salto (es decir, un director o un grupo de servidores front-end designado) y para consultas externas deben hacer referencia a búsquedas de nombres a otros servidores DNS públicos. Si no existen servidores DNS en el perímetro, los servidores perimetrales usan servidores DNS externos para resolver las búsquedas de nombres en Internet y cada servidor perimetral usa un HOST para resolver los nombres de servidor del próximo salto en las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-p101">Each Edge Server is a multihomed computer with external and internal facing interfaces. The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network. If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers. If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="d4fd2-109">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="d4fd2-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d4fd2-110">Por razones de seguridad, es recomendable que los servidores perimetrales no tengan acceso a un servidor DNS ubicado en la red interna.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="d4fd2-111">Para configurar interfaces con servidores DNS en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="d4fd2-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="d4fd2-112">Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz orientada internamente y otro para la interfaz orientada externamente.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4fd2-113">Las subredes internas y externas no deben ser enrutables entre sí.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="d4fd2-p102">En la interfaz externa, configure tres direcciones IP estáticas en la subred de la red perimetral externa (denominada red perimetral o subred filtrada) y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar a un par de servidores DNS perimetrales.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-p102">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall. Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4fd2-116">Se puede usar solamente una dirección IP para esta interfaz, pero para hacerlo debe cambiar las asignaciones de puerto a valores no estándar.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="d4fd2-117">Debe determinar esto cuando cree la topología en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="d4fd2-p104">En la interfaz interna, configure una dirección IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS perimetrales.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-p104">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="d4fd2-120">Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas en las que residen los clientes, Lync Server 2013 y los servidores de mensajería unificada (MU) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="d4fd2-121">Para configurar interfaces sin servidores DNS en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="d4fd2-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="d4fd2-122">Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz orientada internamente y otro para la interfaz orientada externamente.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4fd2-123">Las subredes internas y externas no deben ser enrutables entre sí.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="d4fd2-p105">En la interfaz externa, configure tres direcciones IP estáticas en la subred de red perimetral externa y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS externos.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-p105">On the external interface, configure three static IP addresses on the external perimeter network subnet. You also configure the default gateway on the external interface. For example, define the Internet-facing router or the external firewall as the default gateway. Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4fd2-128">Es posible, pero no se recomienda, usar tan solo una dirección IP para la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="d4fd2-129">Para permitir que esto funcione, debe cambiar las asignaciones de puerto a valores no estándar y fuera del puerto predeterminado 443 que suele ser "compatible con firewall" para la comunicación con el cliente.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="d4fd2-130">La configuración de la dirección IP y la configuración del puerto se determinan al crear la topología en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="d4fd2-p107">En la interfaz interna, configure una dirección IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. Deje la configuración del adaptador DNS vacía.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-p107">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="d4fd2-133">Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes o servidores de Lync que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="d4fd2-134">Edite el archivo HOST en cada servidor perimetral para que contenga un registro para el servidor del próximo salto o IP virtual (VIP) (el registro será el director, el servidor Standard Edition o un grupo de servidores front-end que se haya configurado como la dirección del próximo salto del servidor perimetral en el generador de topologías).</span><span class="sxs-lookup"><span data-stu-id="d4fd2-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="d4fd2-135">Si usa el equilibrio de carga de DNS, incluya una línea para cada miembro del grupo de servidores del próximo salto.</span><span class="sxs-lookup"><span data-stu-id="d4fd2-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


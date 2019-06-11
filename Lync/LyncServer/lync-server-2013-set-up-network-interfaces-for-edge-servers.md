---
title: 'Lync Server 2013: Configurar interfaces de red para servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7263c2d7cad3cf1339351f2cb5f90b15a9fa0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="de086-102">Configurar interfaces de red para servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de086-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de086-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="de086-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="de086-104">Cada servidor perimetral es un equipo de host múltiple con interfaces externas e internas.</span><span class="sxs-lookup"><span data-stu-id="de086-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="de086-105">La configuración del sistema de nombres de dominio (DNS) del adaptador depende de si hay servidores DNS en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="de086-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="de086-106">Si los servidores DNS existen en el perímetro, deben tener una zona que contenga uno o más registros A de DNS para el siguiente servidor o grupo de servidores (es decir, un director o un grupo de servidores front-end designados) y para las consultas externas que hacen referencia a otros servidores DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="de086-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="de086-107">Si no hay servidores DNS en el perímetro, los servidores perimetrales usan servidores DNS externos para resolver búsquedas de nombres de Internet, y cada servidor perimetral usa un HOST para resolver los nombres de servidor del próximo salto en direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="de086-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="de086-109">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="de086-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="de086-110">Por razones de seguridad, le recomendamos que no tenga acceso a los servidores perimetrales a un servidor DNS ubicado en la red interna.</span><span class="sxs-lookup"><span data-stu-id="de086-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="de086-111">Para configurar interfaces con servidores DNS en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="de086-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="de086-112">Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="de086-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="de086-113">Las subredes internas y externas no deben ser enrutables entre sí.</span><span class="sxs-lookup"><span data-stu-id="de086-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="de086-114">En la interfaz externa, configure tres direcciones IP estáticas en la red perimetral externa (también denominada subred DMZ, zona desmilitarizada y subred filtrada) y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo.</span><span class="sxs-lookup"><span data-stu-id="de086-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="de086-115">Configure los parámetros DNS del adaptador para que apunten a un par de servidores DNS perimetrales.</span><span class="sxs-lookup"><span data-stu-id="de086-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de086-116">Es posible usar como mínimo una dirección IP para esta interfaz, pero para ello tendrá que cambiar las asignaciones de puertos a valores no estándar.</span><span class="sxs-lookup"><span data-stu-id="de086-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="de086-117">Esto se determina al crear la topología en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="de086-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="de086-118">En la interfaz interna, configure una dirección IP estática en la subred de la red perimetral interna y no establezca una puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de086-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="de086-119">Configure los parámetros DNS del adaptador para que apunten a al menos un servidor DNS, preferiblemente un par de servidores DNS perimetrales.</span><span class="sxs-lookup"><span data-stu-id="de086-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="de086-120">Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes, Lync Server 2013 y los servidores de mensajería unificada de Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="de086-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="de086-121">Para configurar interfaces sin servidores DNS en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="de086-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="de086-122">Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="de086-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="de086-123">Las subredes internas y externas no deben ser enrutables entre sí.</span><span class="sxs-lookup"><span data-stu-id="de086-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="de086-124">En la interfaz externa, configure tres direcciones IP estáticas en la subred de la red perimetral externa.</span><span class="sxs-lookup"><span data-stu-id="de086-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="de086-125">También puede configurar la puerta de enlace predeterminada en la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="de086-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="de086-126">Por ejemplo, defina el enrutador orientado a Internet o el firewall externo como puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de086-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="de086-127">Configure los parámetros de DNS para que apunten a un servidor DNS, preferiblemente a un par de servidores DNS externos.</span><span class="sxs-lookup"><span data-stu-id="de086-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de086-128">Es posible, pero no recomendable, usar como mínimo una dirección IP para la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="de086-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="de086-129">Para que esto funcione, debe cambiar las asignaciones de puertos a valores no estándar y fuera del puerto predeterminado 443, que suele ser "compatible con el firewall" para la comunicación de clientes.</span><span class="sxs-lookup"><span data-stu-id="de086-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="de086-130">La configuración de la dirección IP y la configuración del puerto se determinan al crear la topología en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="de086-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="de086-131">En la interfaz interna, configure una dirección IP estática en la subred de la red perimetral interna y no establezca una puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de086-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="de086-132">Deje vacía la configuración del DNS del adaptador.</span><span class="sxs-lookup"><span data-stu-id="de086-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="de086-133">Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes o servidores de Lync que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de086-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="de086-134">Edite el archivo HOST en cada servidor perimetral para que contenga un registro para el servidor del próximo salto o IP virtual (VIP) (el registro será el director, el servidor Standard Edition o un grupo de servidores front-end que se haya configurado como la dirección del próximo salto del servidor perimetral en el generador de topología).</span><span class="sxs-lookup"><span data-stu-id="de086-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="de086-135">Si está usando el equilibrio de carga de DNS, incluya una línea para cada miembro del grupo de próximos saltos.</span><span class="sxs-lookup"><span data-stu-id="de086-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


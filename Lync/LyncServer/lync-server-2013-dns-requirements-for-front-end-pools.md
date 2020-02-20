---
title: 'Lync Server 2013: requisitos de DNS para grupos de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18c5b7d16cf5bb7fe13c68a025e9033899c62c4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="dcc10-102">Requisitos de DNS para grupos de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc10-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcc10-103">_**Última modificación del tema:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="dcc10-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="dcc10-104">En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dcc10-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="dcc10-105">Registros DNS para grupos de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="dcc10-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="dcc10-106">En la tabla siguiente se especifican los requisitos de DNS para una implementación de grupo de servidores front-end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcc10-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="dcc10-107">Requisitos de DNS para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="dcc10-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcc10-108">Escenario de implementación</span><span class="sxs-lookup"><span data-stu-id="dcc10-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="dcc10-109">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="dcc10-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcc10-110">Grupo de servidores front-end con varios servidores front-end y un equilibrador de carga de hardware (independientemente de si el equilibrio de carga de DNS también está implementado en ese grupo)</span><span class="sxs-lookup"><span data-stu-id="dcc10-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="dcc10-111">Cuando se usa el equilibrio de carga de DNS y un equilibrador de carga de hardware, es necesario hospedar los registros (A).</span><span class="sxs-lookup"><span data-stu-id="dcc10-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="dcc10-112">Cree un registro A interno que resuelva el nombre de dominio completo (FQDN) del grupo de servidores front-end para el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="dcc10-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="dcc10-113">Cree un registro de host (A) interno para los servicios Web internos en la dirección IP virtual (VIP) del equilibrador de carga.</span><span class="sxs-lookup"><span data-stu-id="dcc10-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="dcc10-114">Debe usar el nombre de servicios Web internos tal como se define en Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="dcc10-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="dcc10-115">Por ejemplo, si usa el equilibrio de carga de DNS y el equilibrio de carga de hardware, tendría un registro A para cada servidor front-end de un grupo de servidores para el equilibrio de carga de DNS y un registro A para los servicios Web internos que apuntan a la IP virtual del equilibrador de carga de hardware. :</span><span class="sxs-lookup"><span data-stu-id="dcc10-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcc10-116">Equilibrio de carga de DNS: dirección IP de Pool01.contoso.net del grupo de 10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="dcc10-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="dcc10-117">Cada servidor front-end también tendrá un registro A distinto:</span><span class="sxs-lookup"><span data-stu-id="dcc10-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="dcc10-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="dcc10-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="dcc10-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="dcc10-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="dcc10-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="dcc10-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="dcc10-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="dcc10-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="dcc10-122">Equilibrio de carga de hardware: WebInternal.contoso.net Dirección IP de HLB VIP 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="dcc10-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="dcc10-123">Todo el tráfico, excepto el tráfico HTTP/HTTPS, usará el registro Pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="dcc10-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="dcc10-124">El tráfico HTTP/HTTPS usará la dirección de servicios Web internos definida de 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="dcc10-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcc10-125">Grupo de servidores front-end con equilibrio de carga de DNS implementado</span><span class="sxs-lookup"><span data-stu-id="dcc10-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="dcc10-126">Un conjunto de registros A internos que resuelven el FQDN del grupo de servidores en la dirección IP de cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="dcc10-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="dcc10-127">Debe haber un registro A para cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="dcc10-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcc10-128">Grupo de servidores front-end con equilibrio de carga de DNS implementado</span><span class="sxs-lookup"><span data-stu-id="dcc10-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="dcc10-129">Un conjunto de registros A internos que resuelven el FQDN de cada servidor del grupo en la dirección IP del servidor.</span><span class="sxs-lookup"><span data-stu-id="dcc10-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="dcc10-130">Para obtener más información, consulte <a href="lync-server-2013-dns-load-balancing.md">equilibrio de carga de DNS en Lync Server 2013</a> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="dcc10-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcc10-131">Grupo de servidores front-end con un solo servidor front-end y una base de datos back-end dedicada, pero sin equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="dcc10-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="dcc10-132">Un registro A interno que resuelve el FQDN del grupo de servidores front-end en la dirección IP del único servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="dcc10-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcc10-133">Inicio de sesión automático de clientes</span><span class="sxs-lookup"><span data-stu-id="dcc10-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="dcc10-134">Para cada dominio SIP compatible, un registro SRV para _sipinternaltls. _tcp. &lt;dominio&gt; a través del puerto 5061 que se asigna al FQDN del grupo de servidores front-end que autentica y redirige las solicitudes de inicio de sesión de los clientes.</span><span class="sxs-lookup"><span data-stu-id="dcc10-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="dcc10-135">Para obtener más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcc10-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcc10-136">Detección del servicio web de actualización de dispositivos mediante dispositivos de comunicaciones unificadas (UC)</span><span class="sxs-lookup"><span data-stu-id="dcc10-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="dcc10-137">Un registro A interno con el nombre ucupdates-R2. &lt;Dominio&gt; SIP que se resuelve en la dirección IP del grupo de servidores front-end que hospeda el servicio Web de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dcc10-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="dcc10-138">En la situación en la que un dispositivo UC está activado, pero un usuario nunca ha iniciado sesión en el dispositivo, el registro A permite que el dispositivo detecte el grupo de servidores front-end que hospeda el servicio Web de actualización de dispositivos y obtenga actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="dcc10-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="dcc10-139">De lo contrario, los dispositivos obtienen esta información a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="dcc10-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="dcc10-140">Si tiene una implementación existente del servicio Web de actualización de dispositivos en Lync Server 2010, ya ha creado un registro A interno con el nombre ucupdates. &lt;Dominio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="dcc10-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="dcc10-141">Para Microsoft Office Communications Server 2007 R2, debe crear un registro A de DNS adicional con el nombre ucupdates-R2. &lt;Dominio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="dcc10-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcc10-142">Un proxy inverso para admitir el tráfico HTTP</span><span class="sxs-lookup"><span data-stu-id="dcc10-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="dcc10-143">Un registro A externo que resuelva el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="dcc10-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="dcc10-144">Los clientes y los dispositivos de comunicaciones unificadas usan este registro para conectarse al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="dcc10-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="dcc10-145">Para obtener más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar los requisitos de DNS para Lync Server 2013</a> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="dcc10-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dcc10-146">En la siguiente tabla se muestra un ejemplo de los registros DNS necesarios para el FQDN interno de la granja de servidores Web.</span><span class="sxs-lookup"><span data-stu-id="dcc10-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="dcc10-147">Registros DNS de ejemplo para el FQDN de la granja de servidores Web interno</span><span class="sxs-lookup"><span data-stu-id="dcc10-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcc10-148">FQDN de granja de servidores Web interno</span><span class="sxs-lookup"><span data-stu-id="dcc10-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="dcc10-149">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="dcc10-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="dcc10-150">Registros A de DNS</span><span class="sxs-lookup"><span data-stu-id="dcc10-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcc10-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dcc10-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dcc10-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dcc10-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dcc10-153">Registro A de DNS para ee-pool.contoso.com que se resuelve en la dirección VIP del equilibrador de carga usado por los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dcc10-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="dcc10-154">Registro A de DNS para webcon.contoso.com que se resuelve en la dirección VIP del equilibrador de carga usado por los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dcc10-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcc10-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dcc10-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dcc10-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dcc10-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dcc10-157">Registro A de DNS para ee-pool.contoso.com que se resuelve en la dirección IP virtual (VIP) del equilibrador de carga usado por los servidores front-end de Enterprise Edition en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dcc10-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="dcc10-158">Tenga en cuenta que si usa el equilibrio de carga de DNS en este grupo, el grupo de servidores front-end y la granja de servidores web interna no pueden tener el mismo FQDN.</span><span class="sxs-lookup"><span data-stu-id="dcc10-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


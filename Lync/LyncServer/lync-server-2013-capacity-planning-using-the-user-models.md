---
title: Lync Server 2013 planear la capacidad con los modelos de usuario
description: Lync Server 2013 la planeación de capacidad con los modelos de usuario.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b710f7ec88dd75c872d704f2169fa2f161fc186
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544416"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="acaba-103">Planeación de la capacidad para Lync Server 2013 mediante los modelos de usuario</span><span class="sxs-lookup"><span data-stu-id="acaba-103">Capacity planning for Lync Server 2013 using the user models</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acaba-104">_**Última modificación del tema:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="acaba-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="acaba-105">En esta sección se proporcionan instrucciones sobre cuántos servidores se necesitan en un sitio para el número de usuarios de ese sitio, según el uso descrito en [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-105">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="acaba-106">Plataforma de hardware probada</span><span class="sxs-lookup"><span data-stu-id="acaba-106">Tested Hardware Platform</span></span>

<span data-ttu-id="acaba-107">Todas las recomendaciones de implementación y los resultados de rendimiento de esta sección se basan en las pruebas de rendimiento en los servidores que ejecutan el hardware descrito en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="acaba-107">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="acaba-108">Le recomendamos que use hardware similar.</span><span class="sxs-lookup"><span data-stu-id="acaba-108">We recommend that you use similar hardware.</span></span> <span data-ttu-id="acaba-109">Si usa un hardware menos eficaz, puede tener problemas de funcionalidad o un rendimiento deficiente.</span><span class="sxs-lookup"><span data-stu-id="acaba-109">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="acaba-110">Tenga en cuenta que estas recomendaciones de hardware son más altas que las de las versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="acaba-110">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="acaba-111">Hardware usado en las pruebas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="acaba-111">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acaba-112">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="acaba-112">Hardware component</span></span></th>
<th><span data-ttu-id="acaba-113">Recomendado</span><span class="sxs-lookup"><span data-stu-id="acaba-113">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acaba-114">CPU</span><span class="sxs-lookup"><span data-stu-id="acaba-114">CPU</span></span></p></td>
<td><p><span data-ttu-id="acaba-115">Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior.</span><span class="sxs-lookup"><span data-stu-id="acaba-115">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="acaba-116">Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="acaba-116">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-117">Memoria</span><span class="sxs-lookup"><span data-stu-id="acaba-117">Memory</span></span></p></td>
<td><p><span data-ttu-id="acaba-118">32 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="acaba-118">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acaba-119">Disco</span><span class="sxs-lookup"><span data-stu-id="acaba-119">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="acaba-120">8 o más unidades de disco duro 10.000-RPM con al menos 72 GB de espacio libre en disco.</span><span class="sxs-lookup"><span data-stu-id="acaba-120">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="acaba-121">Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.</span><span class="sxs-lookup"><span data-stu-id="acaba-121">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="acaba-122">- O</span><span class="sxs-lookup"><span data-stu-id="acaba-122">- OR -</span></span></p></li>
<li><p><span data-ttu-id="acaba-123">Unidades de estado sólido (SSD) con rendimiento igual al de 8 unidades de disco mecánicas de 10.000 rpm.</span><span class="sxs-lookup"><span data-stu-id="acaba-123">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-124">Red</span><span class="sxs-lookup"><span data-stu-id="acaba-124">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="acaba-125">1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</span><span class="sxs-lookup"><span data-stu-id="acaba-125">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="acaba-126">Resumen de los resultados</span><span class="sxs-lookup"><span data-stu-id="acaba-126">Summary of Results</span></span>

<span data-ttu-id="acaba-127">La tabla siguiente resume estas recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="acaba-127">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acaba-128">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="acaba-128">Server role</span></span></th>
<th><span data-ttu-id="acaba-129">Cantidad máxima de usuarios admitidos</span><span class="sxs-lookup"><span data-stu-id="acaba-129">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acaba-130">Grupo de servidores front-end con doce servidores front-end y un servidor back-end o un par reflejado de servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-130">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="acaba-131">80.000 usuarios únicos con sesión iniciada simultáneamente, más el 50% de puntos de presencia (MPOP) que representan instancias no móviles, más el 40% de usuarios habilitados para movilidad para un total de 152.000 puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="acaba-131">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-132">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="acaba-132">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="acaba-133">El servicio de conferencia A/V proporcionado por un grupo de servidores front-end es compatible con las conferencias del grupo suponiendo un tamaño máximo de conferencia de 250 usuarios y solo una conferencia grande en ejecución cada vez.</span><span class="sxs-lookup"><span data-stu-id="acaba-133">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="acaba-134">Además, puede admitir conferencias grandes de entre 250 y 1000 usuarios mediante la implementación de un grupo de servidores front-end independiente con dos servidores front-end para hospedar las conferencias grandes.</span><span class="sxs-lookup"><span data-stu-id="acaba-134">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="acaba-135">Para obtener más información, consulte <A href="lync-server-2013-supporting-large-meetings.md">Supporting Large Meetings Using Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acaba-135">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acaba-136">Un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="acaba-136">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="acaba-137">12.000 usuarios remotos simultáneos</span><span class="sxs-lookup"><span data-stu-id="acaba-137">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-138">Un director</span><span class="sxs-lookup"><span data-stu-id="acaba-138">One Director</span></span></p></td>
<td><p><span data-ttu-id="acaba-139">12.000 usuarios remotos simultáneos</span><span class="sxs-lookup"><span data-stu-id="acaba-139">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acaba-140">Supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="acaba-140">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="acaba-141">En Lync Server 2013, los servicios front-end de supervisión y archivado ahora se ejecutan en cada servidor front-end, en lugar de en roles de servidor independientes.</span><span class="sxs-lookup"><span data-stu-id="acaba-141">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="acaba-142">La supervisión y el archivado siguen requiriendo sus propios almacenes de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="acaba-142">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="acaba-143">Si también ejecuta Exchange 2013, puede mantener los datos de archivado en Exchange, en lugar de hacerlo en una base de datos SQL dedicada.</span><span class="sxs-lookup"><span data-stu-id="acaba-143">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-144">Un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="acaba-144">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="acaba-145">El servidor de mediación combinado con el servidor front-end se ejecuta en cada servidor front-end de un grupo de servidores y debe proporcionar suficiente capacidad para los usuarios del grupo.</span><span class="sxs-lookup"><span data-stu-id="acaba-145">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="acaba-146">Para un servidor de mediación independiente, consulte la sección "servidor de mediación" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="acaba-146">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acaba-147">Un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="acaba-147">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="acaba-148">Se recomienda encarecidamente que si usa servidores Standard Edition para hospedar usuarios, use siempre dos servidores, emparejados con las recomendaciones de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="acaba-148">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="acaba-149">Cada servidor del par puede hospedar hasta 2.500 usuarios y, si se produce un error en un servidor, el servidor restante puede admitir 5.000 usuarios en un escenario de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="acaba-149">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="acaba-150">Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede sufrir más de 2.500 usuarios por servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-150">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="acaba-151">En este caso, considere la posibilidad de agregar más servidores Standard Edition o de migrar a Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="acaba-151">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="acaba-152">Servidor front-end</span><span class="sxs-lookup"><span data-stu-id="acaba-152">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acaba-153">Los grupos de servidores extendidos no son compatibles con este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-153">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="acaba-154">En un grupo de servidores front-end, debe disponer de un servidor front-end para cada 6.660 usuarios alojados en el grupo de servidores, suponiendo que la tecnología Hyper-Threading está habilitada en todos los servidores del grupo y que el hardware del servidor cumple con las recomendaciones de las [plataformas de hardware del servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-154">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="acaba-155">El número máximo de usuarios en un grupo de servidores front-end es de 80.000, suponiendo que la tecnología Hyper-Threading está habilitada en todos los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="acaba-155">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="acaba-156">Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-156">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="acaba-157">Cuando calcule el número de usuarios de un grupo de servidores front-end, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia asociados a este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-157">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="acaba-158">Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente a los demás servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="acaba-158">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="acaba-159">Por ejemplo, si tiene 30.000 usuarios y cinco servidores front-end, entonces si un servidor no está disponible, las conexiones de 6000 usuarios deben transferirse a los otros cuatro servidores.</span><span class="sxs-lookup"><span data-stu-id="acaba-159">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="acaba-160">Los cuatro servidores restantes tendrán 7500 usuarios, que es un número mayor que el recomendado.</span><span class="sxs-lookup"><span data-stu-id="acaba-160">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="acaba-161">Si en su lugar ha empezado con seis servidores front-end para los usuarios de 30.000 y, posteriormente, uno dejó de estar disponible, se moverá un total de 5000 usuarios a los cinco servidores restantes.</span><span class="sxs-lookup"><span data-stu-id="acaba-161">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="acaba-162">Estos cinco servidores tendrán cada host 6000 usuarios, que se encuentra en el intervalo recomendado.</span><span class="sxs-lookup"><span data-stu-id="acaba-162">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="acaba-163">La cantidad máxima de usuarios en un grupo de servidores front-end es 80.000.</span><span class="sxs-lookup"><span data-stu-id="acaba-163">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="acaba-164">El número máximo de servidores front-end en un grupo es de 12.</span><span class="sxs-lookup"><span data-stu-id="acaba-164">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="acaba-165">Para un grupo de servidores front-end con 80.000 usuarios, doce servidores front-end son suficientes para el rendimiento, en implementaciones típicas que sigan los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-165">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="acaba-166">Las implementaciones diseñadas para admitir la conmutación por error de recuperación ante desastres suponen que se puede hospedar un máximo de 40.000 usuarios en cada uno de los dos grupos de servidores front-end emparejados, en los que cada grupo tiene suficientes servidores front-end para acomodar a los usuarios en ambos grupos, en caso de que un grupo necesite conmutar por error al otro.</span><span class="sxs-lookup"><span data-stu-id="acaba-166">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="acaba-167">El número de usuarios que un grupo de servidores front-end concreto admite con un buen rendimiento puede diferir de estos números por los motivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="acaba-167">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="acaba-168">El hardware de los servidores front-end no cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-168">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="acaba-169">Si el uso de su organización difiere en gran medida de los modelos de usuario, por ejemplo, con un tráfico de conferencias significativamente mayor.</span><span class="sxs-lookup"><span data-stu-id="acaba-169">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="acaba-170">En Lync Server 2013, las bases de datos de presencia ahora están hospedadas en los servidores front-end, a diferencia de Lync Server 2010, donde se hospedan en el servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-170">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="acaba-171">Esto significa que el rendimiento de disco y la capacidad de los servidores front-end no se verán comprometidos con las recomendaciones enumeradas anteriormente en esta sección y en las <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync Server 2013</A>, independientemente del número de usuarios hospedados en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-171">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="acaba-172">En la tabla siguiente se muestra el ancho de banda medio para mensajería instantánea y presencia, según el modelo de usuario, como se define en los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-172">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acaba-173">Ancho de banda medio por usuario</span><span class="sxs-lookup"><span data-stu-id="acaba-173">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="acaba-174">Requisitos de ancho de banda por servidor front-end con 6.660 usuarios</span><span class="sxs-lookup"><span data-stu-id="acaba-174">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acaba-175">1,3 Kbps</span><span class="sxs-lookup"><span data-stu-id="acaba-175">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="acaba-176">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="acaba-176">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="acaba-177">Para mejorar el rendimiento de los medios en los servidores front-end de conferencias A/V y servidores de mediación colocalizados, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-177">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="acaba-178">El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-178">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="acaba-179">Para obtener más información, vea "mejoras en el ajuste de escala en lado de recepción en Windows Server 2008" en <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="acaba-179">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="acaba-180">Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="acaba-180">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="acaba-181">Máximos de conferencia</span><span class="sxs-lookup"><span data-stu-id="acaba-181">Conferencing Maximums</span></span>

<span data-ttu-id="acaba-182">Dado el modelo de usuario que establece que el 5% de los usuarios de un grupo de servidores puede estar en una conferencia en cualquier momento dado, un grupo de 80.000 usuarios podría tener unos 4.000 usuarios en conferencias en un determinado momento.</span><span class="sxs-lookup"><span data-stu-id="acaba-182">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="acaba-183">Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de MI; otras, de MI con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes.</span><span class="sxs-lookup"><span data-stu-id="acaba-183">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="acaba-184">No hay ningún límite fijo para el número real de conferencias permitidas y el uso real determinará el rendimiento real.</span><span class="sxs-lookup"><span data-stu-id="acaba-184">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="acaba-185">Por ejemplo, si su organización tiene muchas más conferencias de modo combinado de lo que supone el modelo de usuario, probablemente necesite implementar más servidores front-end o servidores de conferencia A/V del número recomendado en este documento.</span><span class="sxs-lookup"><span data-stu-id="acaba-185">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="acaba-186">Para obtener más información sobre los supuestos del modelo de usuario, vea [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-186">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="acaba-187">El tamaño máximo de conferencia compatible hospedado en un grupo de servidores front-end de Lync Server 2013 normal que también hospeda a los usuarios es de 250 participantes.</span><span class="sxs-lookup"><span data-stu-id="acaba-187">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="acaba-188">Mientras está ocurriendo una conferencia de 250 usuarios, el grupo todavía admite otras conferencias, de modo que un total del 5% de los usuarios del grupo está en conferencias simultáneas.</span><span class="sxs-lookup"><span data-stu-id="acaba-188">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="acaba-189">Por ejemplo, en un grupo de doce servidores front-end y 80.000 usuarios, mientras se está produciendo la Conferencia 250-User, Lync Server admite 3.750 otros usuarios que participen en conferencias más pequeñas.</span><span class="sxs-lookup"><span data-stu-id="acaba-189">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="acaba-190">Independientemente del número de usuarios alojados en el grupo de servidores front-end o del servidor Standard Edition, Lync Server admite un mínimo de 125 otros usuarios que participan en conferencias más pequeñas en el mismo grupo o servidor que hospeda una conferencia 250-User.</span><span class="sxs-lookup"><span data-stu-id="acaba-190">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="acaba-191">Para habilitar las conferencias entre los usuarios de 250 y 1000, puede configurar un grupo de servidores front-end independiente solo para hospedar esas conferencias.</span><span class="sxs-lookup"><span data-stu-id="acaba-191">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="acaba-192">Este grupo de servidores front-end no hospedará ningún usuario.</span><span class="sxs-lookup"><span data-stu-id="acaba-192">This Front End pool will not host any users.</span></span> <span data-ttu-id="acaba-193">Para obtener más información, consulte [Supporting Large Meetings Using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-193">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="acaba-194">Si su organización tiene muchas más conferencias de modo mixto del que se supone en el modelo de usuario, es posible que deba implementar más servidores front-end que las recomendaciones de este documento (hasta un límite de 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="acaba-194">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="acaba-195">Para obtener más información sobre los supuestos del modelo de usuario, vea [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-195">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="acaba-196">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="acaba-196">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acaba-197">Los grupos de servidores extendidos no son compatibles con este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-197">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="acaba-198">Debe implementar un servidor perimetral para cada 12.000 usuarios remotos que tendrán acceso a un sitio de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="acaba-198">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="acaba-199">Como mínimo, se recomienda el uso de dos servidores perimetrales para obtener alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="acaba-199">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="acaba-200">En estas recomendaciones se presupone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-200">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="acaba-201">Cuando calcule el número de usuarios de los servidores perimetrales, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.</span><span class="sxs-lookup"><span data-stu-id="acaba-201">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acaba-202">Para mejorar el rendimiento del servicio de conferencia A/V en los servidores perimetrales, debe habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="acaba-202">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="acaba-203">El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-203">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="acaba-204">Para obtener más información, vea "mejoras en el ajuste de escala en lado de recepción en Windows Server 2008" en <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="acaba-204">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="acaba-205">Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="acaba-205">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="acaba-206">Director</span><span class="sxs-lookup"><span data-stu-id="acaba-206">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acaba-207">Los grupos de servidores extendidos no son compatibles con este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-207">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="acaba-208">Si implementa el rol de servidor Director, le recomendamos que implemente un director por cada 12.000 usuarios remotos que tendrán acceso a un sitio de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="acaba-208">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="acaba-209">Como mínimo, se recomienda el uso de dos directores para obtener alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="acaba-209">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="acaba-210">En estas recomendaciones se presupone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-210">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="acaba-211">Cuando calcule el número de usuarios de los directores, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.</span><span class="sxs-lookup"><span data-stu-id="acaba-211">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="acaba-212">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="acaba-212">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acaba-213">Los grupos de servidores extendidos no son compatibles con este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-213">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="acaba-214">Si combinar servidor de mediación con el servidor front-end, el servidor de mediación se ejecuta en todos los servidores front-end del grupo y debe proporcionar suficiente capacidad para los usuarios del grupo.</span><span class="sxs-lookup"><span data-stu-id="acaba-214">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="acaba-215">Si implementa un grupo de servidores de mediación independiente, entonces el número de servidores de mediación que se van a implementar depende de muchos factores, como el hardware usado para el servidor de mediación, el número de usuarios de VoIP que tiene, el número de puertas de enlace que controla cada grupo de servidores de mediación, el tráfico de horas de disponibilidad a través de dichas puertas de enlace y el</span><span class="sxs-lookup"><span data-stu-id="acaba-215">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="acaba-216">En las tablas siguientes se proporciona una guía para conocer cuántas llamadas simultáneas puede controlar un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumpla los requisitos de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) y que la tecnología Hyper-Threading esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="acaba-216">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="acaba-217">Para obtener más información sobre la escalabilidad del servidor de mediación, consulte [Estimating Voice Usage and Traffic for Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) y [Deployment Guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-217">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="acaba-218">En las tablas siguientes se supone que el uso se resume en los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-218">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="acaba-219">Capacidad de un servidor de mediación independiente: 70% de usuarios internos, 30% de usuarios externos con capacidad de llamada sin desvío (transcodificación multimedia realizada por el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="acaba-219">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acaba-220">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="acaba-220">Server hardware</span></span></th>
<th><span data-ttu-id="acaba-221">Número máximo de llamadas</span><span class="sxs-lookup"><span data-stu-id="acaba-221">Maximum number of calls</span></span></th>
<th><span data-ttu-id="acaba-222">Número máximo de líneas T1</span><span class="sxs-lookup"><span data-stu-id="acaba-222">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="acaba-223">Número máximo de líneas E1</span><span class="sxs-lookup"><span data-stu-id="acaba-223">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acaba-224">Procesador dual, núcleo hexadecimal, CPU Hyper-threaded de 2,26 GHz <strong>con la tecnología Hyper-Threading deshabilitada</strong>, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</span><span class="sxs-lookup"><span data-stu-id="acaba-224">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="acaba-225">1100</span><span class="sxs-lookup"><span data-stu-id="acaba-225">1100</span></span></p></td>
<td><p><span data-ttu-id="acaba-226">46</span><span class="sxs-lookup"><span data-stu-id="acaba-226">46</span></span></p></td>
<td><p><span data-ttu-id="acaba-227">35</span><span class="sxs-lookup"><span data-stu-id="acaba-227">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-228">Procesador dual, núcleo hexadecimal, CPU Hyper-threaded de 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</span><span class="sxs-lookup"><span data-stu-id="acaba-228">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="acaba-229">1500</span><span class="sxs-lookup"><span data-stu-id="acaba-229">1500</span></span></p></td>
<td><p><span data-ttu-id="acaba-230">63</span><span class="sxs-lookup"><span data-stu-id="acaba-230">63</span></span></p></td>
<td><p><span data-ttu-id="acaba-231">47</span><span class="sxs-lookup"><span data-stu-id="acaba-231">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="acaba-232">Aunque se utilizaron servidores con 32 GB de memoria para la prueba, se pueden utilizar servidores con 16 GB de memoria como servidores de mediación independientes y son suficientes para ofrecer el rendimiento mostrado en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="acaba-232">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="acaba-233">Capacidad del servidor de mediación (servidor de mediación combinado con el servidor front-end) 70% de usuarios internos, 30% de usuarios externos, capacidad de llamada sin omisiones (procesamiento de medios realizado por el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="acaba-233">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acaba-234">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="acaba-234">Server hardware</span></span></th>
<th><span data-ttu-id="acaba-235">Número máximo de llamadas</span><span class="sxs-lookup"><span data-stu-id="acaba-235">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acaba-236">Procesador dual, núcleo hexadecimal, CPU Hyper-threaded de 2,26 GHz, con 32 GB de memoria y 2 tarjetas adaptadoras de red de 1 GB.</span><span class="sxs-lookup"><span data-stu-id="acaba-236">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="acaba-237">150</span><span class="sxs-lookup"><span data-stu-id="acaba-237">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="acaba-238">Este número es mucho menor que los números del servidor de mediación independiente, ya que el servidor front-end tiene que administrar otras características y funciones para los usuarios de 6600 que se hospedan en él, además de la transcodificación necesaria para las llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="acaba-238">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="acaba-239">Para mejorar el rendimiento del servidor de mediación, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de los servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="acaba-239">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="acaba-240">El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-240">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="acaba-241">Para obtener más información, vea "mejoras en el ajuste de escala en lado de recepción en Windows Server 2008" en <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="acaba-241">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="acaba-242">Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="acaba-242">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="acaba-243">Servidor back-end</span><span class="sxs-lookup"><span data-stu-id="acaba-243">Back End Server</span></span>

<span data-ttu-id="acaba-244">En Lync Server 2013, las bases de datos de presencia se encuentran en los servidores front-end en lugar de en el servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-244">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="acaba-245">Esto ha dado como resultado un requisito mucho más sencillo para cada servidor back-end en Lync Server 2013, equivalente al requisito de hardware para el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-245">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="acaba-246">Compare esto con Lync Server 2010, donde era necesario que el servidor back-end fuera un servidor mucho más importante con 25 discos.</span><span class="sxs-lookup"><span data-stu-id="acaba-246">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="acaba-247">Sin embargo, la carga de trabajo de los servidores back-end todavía es tal que no se deben superar las recomendaciones de hardware enumeradas anteriormente en esta sección y en las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-247">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="acaba-248">Para proporcionar alta disponibilidad del servidor back-end, se recomienda implementar la creación de reflejos del servidor.</span><span class="sxs-lookup"><span data-stu-id="acaba-248">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="acaba-249">Para obtener más información, vea [back end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="acaba-249">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="acaba-250">Supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="acaba-250">Monitoring and Archiving</span></span>

<span data-ttu-id="acaba-251">En Lync Server 2013, si implementa la supervisión o el archivado, la funcionalidad front-end de estos servicios se ejecuta en los servidores front-end, en lugar de en roles de servidor independientes.</span><span class="sxs-lookup"><span data-stu-id="acaba-251">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="acaba-252">La supervisión y el archivado siguen usando su propio almacén de base de datos, independiente del almacén back-end.</span><span class="sxs-lookup"><span data-stu-id="acaba-252">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="acaba-253">Como alternativa, si tiene implementado Exchange 2013, puede almacenar datos de archivado de mensajes instantáneos en Exchange en lugar de hacerlo en un almacén de SQL dedicado.</span><span class="sxs-lookup"><span data-stu-id="acaba-253">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="acaba-254">En la tabla siguiente se indica aproximadamente cuánto almacenamiento de base de datos se necesita por usuario y día para la supervisión y archivado de datos.</span><span class="sxs-lookup"><span data-stu-id="acaba-254">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="acaba-255"><strong>CDR (supervisión)</strong></span><span class="sxs-lookup"><span data-stu-id="acaba-255"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="acaba-256"><strong>QoE (supervisión)</strong></span><span class="sxs-lookup"><span data-stu-id="acaba-256"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="acaba-257"><strong>Archivado</strong></span><span class="sxs-lookup"><span data-stu-id="acaba-257"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-258">Espacio en disco necesario por usuario y por día</span><span class="sxs-lookup"><span data-stu-id="acaba-258">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="acaba-259">49 KB</span><span class="sxs-lookup"><span data-stu-id="acaba-259">49 KB</span></span></p></td>
<td><p><span data-ttu-id="acaba-260">28 KB</span><span class="sxs-lookup"><span data-stu-id="acaba-260">28 KB</span></span></p></td>
<td><p><span data-ttu-id="acaba-261">57 KB</span><span class="sxs-lookup"><span data-stu-id="acaba-261">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="acaba-262">Microsoft usó el hardware de la siguiente tabla para el servidor de bases de datos para la supervisión y el archivado durante las pruebas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="acaba-262">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="acaba-263">Las pruebas recopilaron los datos de dos grupos de servidores front-end, cada uno de los cuales contenía 80.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="acaba-263">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="acaba-264">Hardware usado en las pruebas de rendimiento de supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="acaba-264">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acaba-265">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="acaba-265">Hardware component</span></span></th>
<th><span data-ttu-id="acaba-266">Recomendado</span><span class="sxs-lookup"><span data-stu-id="acaba-266">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acaba-267">CPU</span><span class="sxs-lookup"><span data-stu-id="acaba-267">CPU</span></span></p></td>
<td><p><span data-ttu-id="acaba-268">Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior.</span><span class="sxs-lookup"><span data-stu-id="acaba-268">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-269">Memoria</span><span class="sxs-lookup"><span data-stu-id="acaba-269">Memory</span></span></p></td>
<td><p><span data-ttu-id="acaba-270">48 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="acaba-270">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acaba-271">Disco</span><span class="sxs-lookup"><span data-stu-id="acaba-271">Disk</span></span></p></td>
<td><p><span data-ttu-id="acaba-272">unidades de disco duro 25 10.000-RPM con 300 GB en cada disco, con la siguiente configuración</span><span class="sxs-lookup"><span data-stu-id="acaba-272">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acaba-273"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="acaba-273"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="acaba-274"><strong>Configuración de RAID</strong></span><span class="sxs-lookup"><span data-stu-id="acaba-274"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="acaba-275"><strong>Número de discos</strong></span><span class="sxs-lookup"><span data-stu-id="acaba-275"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-276">CDR, QoE y archivos de datos de la base de datos de archivado en una única unidad</span><span class="sxs-lookup"><span data-stu-id="acaba-276">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="acaba-277">1 + 0</span><span class="sxs-lookup"><span data-stu-id="acaba-277">1+0</span></span></p></td>
<td><p><span data-ttu-id="acaba-278">16 </span><span class="sxs-lookup"><span data-stu-id="acaba-278">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acaba-279">El archivo de registro de la base de datos CDR</span><span class="sxs-lookup"><span data-stu-id="acaba-279">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="acaba-280">1</span><span class="sxs-lookup"><span data-stu-id="acaba-280">1</span></span></p></td>
<td><p><span data-ttu-id="acaba-281">segundo</span><span class="sxs-lookup"><span data-stu-id="acaba-281">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-282">El archivo de registro de la base de datos QoE</span><span class="sxs-lookup"><span data-stu-id="acaba-282">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="acaba-283">1</span><span class="sxs-lookup"><span data-stu-id="acaba-283">1</span></span></p></td>
<td><p><span data-ttu-id="acaba-284">segundo</span><span class="sxs-lookup"><span data-stu-id="acaba-284">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acaba-285">Archivo de registro de la base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="acaba-285">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="acaba-286">1</span><span class="sxs-lookup"><span data-stu-id="acaba-286">1</span></span></p></td>
<td><p><span data-ttu-id="acaba-287">segundo</span><span class="sxs-lookup"><span data-stu-id="acaba-287">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acaba-288">Red</span><span class="sxs-lookup"><span data-stu-id="acaba-288">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="acaba-289">1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</span><span class="sxs-lookup"><span data-stu-id="acaba-289">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="acaba-290">En esta sección</span><span class="sxs-lookup"><span data-stu-id="acaba-290">In This Section</span></span>

  - [<span data-ttu-id="acaba-291">Estimar el uso de voz y el tráfico para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acaba-291">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="acaba-292">Instrucciones de implementación para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acaba-292">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


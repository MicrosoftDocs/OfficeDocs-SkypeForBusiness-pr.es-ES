---
title: Lync Server 2013 planeamiento de capacidad con los modelos de usuario
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
ms.openlocfilehash: cd9b3861e4c84b8df7585ad5cfbdfd5a82359282
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="fedd3-102">Planificación de capacidad para Lync Server 2013 con los modelos de usuario</span><span class="sxs-lookup"><span data-stu-id="fedd3-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fedd3-103">_**Última modificación del tema:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="fedd3-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="fedd3-104">Esta sección proporciona instrucciones sobre cuántos servidores necesita en un sitio para el número de usuarios de ese sitio, según el uso descrito en modelos de [usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="fedd3-105">Plataforma de hardware probada</span><span class="sxs-lookup"><span data-stu-id="fedd3-105">Tested Hardware Platform</span></span>

<span data-ttu-id="fedd3-106">Todos los resultados de rendimiento y las recomendaciones de implementación de esta sección se basan en pruebas de rendimiento en servidores que ejecutan el hardware que se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="fedd3-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="fedd3-107">Le recomendamos que use hardware similar.</span><span class="sxs-lookup"><span data-stu-id="fedd3-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="fedd3-108">Si usa un hardware menos eficaz, puede tener problemas de funcionalidad o un rendimiento deficiente.</span><span class="sxs-lookup"><span data-stu-id="fedd3-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="fedd3-109">Tenga en cuenta que estas recomendaciones de hardware son superiores a las de las versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fedd3-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="fedd3-110">Hardware usado en pruebas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="fedd3-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fedd3-111">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="fedd3-111">Hardware component</span></span></th>
<th><span data-ttu-id="fedd3-112">Recomendado</span><span class="sxs-lookup"><span data-stu-id="fedd3-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-113">CPU</span><span class="sxs-lookup"><span data-stu-id="fedd3-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="fedd3-114">Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior</span><span class="sxs-lookup"><span data-stu-id="fedd3-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="fedd3-115">Los procesadores Intel Itanium no son compatibles con los roles de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fedd3-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-116">Memoria</span><span class="sxs-lookup"><span data-stu-id="fedd3-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="fedd3-117">32 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="fedd3-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-118">Disco</span><span class="sxs-lookup"><span data-stu-id="fedd3-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fedd3-119">8 o más unidades de disco duro de 10 000 RPM con al menos 72 GB de espacio libre en disco.</span><span class="sxs-lookup"><span data-stu-id="fedd3-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="fedd3-120">Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.</span><span class="sxs-lookup"><span data-stu-id="fedd3-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="fedd3-121">-Ni</span><span class="sxs-lookup"><span data-stu-id="fedd3-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="fedd3-122">Unidades de estado sólido (SSD) con un rendimiento igual al de 8 unidades de disco duro mecánicas de 10.000 rpm.</span><span class="sxs-lookup"><span data-stu-id="fedd3-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-123">Red</span><span class="sxs-lookup"><span data-stu-id="fedd3-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fedd3-124">1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</span><span class="sxs-lookup"><span data-stu-id="fedd3-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="fedd3-125">Resumen de los resultados</span><span class="sxs-lookup"><span data-stu-id="fedd3-125">Summary of Results</span></span>

<span data-ttu-id="fedd3-126">En la tabla siguiente se resumen estas recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="fedd3-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fedd3-127">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="fedd3-127">Server role</span></span></th>
<th><span data-ttu-id="fedd3-128">Cantidad máxima de usuarios admitidos</span><span class="sxs-lookup"><span data-stu-id="fedd3-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-129">Grupo front-end con doce servidores front-end y un servidor back-end o un par espejeado de servidores back end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="fedd3-130">80.000 usuarios únicos con sesión iniciada simultáneamente, más un 50% de múltiples puntos de presencia (MPOP) que representan instancias no móviles, más un 40% de los usuarios habilitados para movilidad, lo que hace un total de 152.000 extremos.</span><span class="sxs-lookup"><span data-stu-id="fedd3-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-131">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="fedd3-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="fedd3-132">El servicio de conferencia A/V suministrado por un grupo de servidores front-end admite las conferencias de la agrupación suponiendo un tamaño máximo de conferencia de usuarios de 250 y solo una de estas conferencias de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="fedd3-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fedd3-133">Además, puede admitir conferencias grandes de usuarios de 250 y 1000 implementando un grupo de servidores front-end independiente con dos servidores front-end para hospedar las grandes conferencias.</span><span class="sxs-lookup"><span data-stu-id="fedd3-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="fedd3-134">Para obtener más información, consulte <A href="lync-server-2013-supporting-large-meetings.md">compatibilidad con reuniones grandes con Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fedd3-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-135">Un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fedd3-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="fedd3-136">12.000 usuarios remotos simultáneos</span><span class="sxs-lookup"><span data-stu-id="fedd3-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-137">Un director</span><span class="sxs-lookup"><span data-stu-id="fedd3-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="fedd3-138">12.000 usuarios remotos simultáneos</span><span class="sxs-lookup"><span data-stu-id="fedd3-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-139">Supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="fedd3-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="fedd3-140">En Lync Server 2013, los servicios front-end de supervisión y archivado se ejecutan ahora en cada servidor front-end, en lugar de en roles de servidor diferentes.</span><span class="sxs-lookup"><span data-stu-id="fedd3-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="fedd3-141">Los servicios de supervisión y archivado aún necesitan sus propios almacenes de base de datos.</span><span class="sxs-lookup"><span data-stu-id="fedd3-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="fedd3-142">Si también ejecuta Exchange 2013, puede mantener los datos de archivado en Exchange, en lugar de hacerlo en una base de datos SQL dedicada.</span><span class="sxs-lookup"><span data-stu-id="fedd3-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-143">Un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="fedd3-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fedd3-144">El servidor de mediación en el servidor front-end se ejecuta en todos los servidores front end de un grupo y debe proporcionar la capacidad suficiente para los usuarios del grupo.</span><span class="sxs-lookup"><span data-stu-id="fedd3-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="fedd3-145">Para el servidor de mediación independiente, consulte la sección "servidor de media", más adelante en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="fedd3-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-146">Un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="fedd3-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="fedd3-147">Le recomendamos encarecidamente que si usa servidores Standard Edition para hospedar usuarios, siempre use dos servidores, emparejados mediante las recomendaciones de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fedd3-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="fedd3-148">Cada servidor del par puede hospedar hasta 2500 usuarios y, si uno de los servidores produce errores, el otro servidor puede admitir 5000 usuarios en un escenario de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="fedd3-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="fedd3-149">Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede verse afectado con más de 2500 usuarios por servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="fedd3-150">En este caso, debe considerar la posibilidad de agregar servidores Standard Edition o de ir a Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fedd3-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="fedd3-151">Servidor front-end</span><span class="sxs-lookup"><span data-stu-id="fedd3-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-152">No se admiten agrupaciones extendidas para este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fedd3-153">En un grupo de servidores front-end, debe disponer de un servidor front-end para cada 6.660 usuarios alojados en el grupo, suponiendo que Hyper-Threading está habilitado en todos los servidores del grupo, y que el hardware del servidor cumpla con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="fedd3-154">La cantidad máxima de usuarios de un grupo de servidores front-end es de 80.000, suponiendo que Hyper-Threading está habilitado en todos los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="fedd3-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="fedd3-155">Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="fedd3-156">Cuando se tiene en cuenta el número de usuarios en un grupo de servidores front-end, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y los servidores de sucursal con supervivencia que estén asociados a este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="fedd3-157">Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente al resto de los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="fedd3-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="fedd3-158">Por ejemplo, si tiene 30.000 usuarios y cinco servidores front-end, entonces si un servidor no está disponible, las conexiones de los usuarios de 6000 deben transferirse a los otros cuatro servidores.</span><span class="sxs-lookup"><span data-stu-id="fedd3-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="fedd3-159">Cada uno de los cuatro servidores restantes tendrá 7500 usuarios, que es un número mayor que el recomendado.</span><span class="sxs-lookup"><span data-stu-id="fedd3-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="fedd3-160">Si en su lugar ha empezado con seis servidores front-end para los usuarios de 30.000 y, posteriormente, uno de ellos no estaba disponible, se moverá un total de 5000 usuarios a los cinco servidores restantes.</span><span class="sxs-lookup"><span data-stu-id="fedd3-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="fedd3-161">Estos cinco servidores usarán a cada uno de los usuarios 6000, que se encuentra en el intervalo recomendado.</span><span class="sxs-lookup"><span data-stu-id="fedd3-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="fedd3-162">El número máximo de usuarios en un grupo de servidores front-end es de 80.000.</span><span class="sxs-lookup"><span data-stu-id="fedd3-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="fedd3-163">La cantidad máxima de servidores frontales en un grupo es de 12.</span><span class="sxs-lookup"><span data-stu-id="fedd3-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="fedd3-164">En el caso de un grupo de servidores front-end con usuarios de 80.000, doce servidores front-end son suficientes para el rendimiento, en las implementaciones típicas que siguen los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="fedd3-165">Las implementaciones diseñadas para admitir la conmutación por error de recuperación ante desastres suponen que se puede hospedar un máximo de 40.000 usuarios en cada uno de los dos grupos de aplicaciones para usuario emparejados, en el que cada grupo tiene suficientes servidores frontales para acomodar a los usuarios en los dos grupos si es necesario que se produzca un error en un bloque a la otra.</span><span class="sxs-lookup"><span data-stu-id="fedd3-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="fedd3-166">El número de usuarios admitidos por un buen rendimiento de un grupo de servidores front-end determinado puede diferir de estos números por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="fedd3-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="fedd3-167">El hardware de los servidores front-end no cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="fedd3-168">El uso de su organización difiere significativamente de los modelos de usuario, como, por ejemplo, mucho más tráfico de conferencias.</span><span class="sxs-lookup"><span data-stu-id="fedd3-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fedd3-169">En Lync Server 2013, las bases de datos de presencia ahora se encuentran en los servidores de aplicaciones para el usuario, a diferencia de Lync Server 2010, donde se hospedan en el servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="fedd3-170">Esto significa que el rendimiento de disco y la capacidad de los servidores front-end no deben verse comprometidos en las recomendaciones mencionadas anteriormente en esta sección y en las <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync Server 2013</A>, independientemente del número de usuarios alojados en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="fedd3-171">En la tabla siguiente se muestra el ancho de banda medio para mensajería instantánea y presencia, dado el modelo de usuario, según se define en los [modelos de usuario de Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fedd3-172">Ancho de banda medio por usuario</span><span class="sxs-lookup"><span data-stu-id="fedd3-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="fedd3-173">Requisitos de ancho de banda por servidor front-end con usuarios de 6.660</span><span class="sxs-lookup"><span data-stu-id="fedd3-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-174">1,3 Kbps</span><span class="sxs-lookup"><span data-stu-id="fedd3-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="fedd3-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="fedd3-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-176">Para mejorar el rendimiento de los medios de la funcionalidad de servidor de mediación y conferencias A/V, en los servidores front-end, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="fedd3-177">RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="fedd3-178">Para obtener más información, consulte "mejoras de escala en el lado de recepción en Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>Server 2008" en.</span><span class="sxs-lookup"><span data-stu-id="fedd3-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="fedd3-179">Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="fedd3-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="fedd3-180">Máximos de conferencia</span><span class="sxs-lookup"><span data-stu-id="fedd3-180">Conferencing Maximums</span></span>

<span data-ttu-id="fedd3-181">Dado el modelo de usuario en el que un 5% de los usuarios de un grupo puede estar en una conferencia en un momento dado, un grupo de usuarios de 80.000 podría tener unos 4.000 usuarios en conferencias al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fedd3-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="fedd3-182">Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de mensajería instantánea; otras, de mensajería instantánea con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes.</span><span class="sxs-lookup"><span data-stu-id="fedd3-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="fedd3-183">No hay un límite rígido para el número real de conferencias permitidas y el uso real determina el rendimiento real.</span><span class="sxs-lookup"><span data-stu-id="fedd3-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="fedd3-184">Por ejemplo, si su organización tiene muchas más conferencias de modo mixto de lo que se supone en el modelo de usuario, es posible que tenga que implementar más servidores front-end o servidores de conferencia A/V con las recomendaciones de este documento.</span><span class="sxs-lookup"><span data-stu-id="fedd3-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="fedd3-185">Para obtener más información sobre los supuestos en el modelo de usuario, consulte [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="fedd3-186">El tamaño máximo de conferencia admitido hospedado por un grupo de front-end de Lync Server 2013 que también hospeda usuarios es de 250 participantes.</span><span class="sxs-lookup"><span data-stu-id="fedd3-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="fedd3-187">Mientras se celebra una conferencia de 250 usuarios, el grupo puede admitir también otras conferencias, con un total del 5 % de los usuarios del grupo en conferencias simultáneas.</span><span class="sxs-lookup"><span data-stu-id="fedd3-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="fedd3-188">Por ejemplo, en un grupo de doce servidores front-end y usuarios de 80.000, mientras se celebra la Conferencia 250-User, Lync Server admite 3.750 usuarios que participen en conferencias más pequeñas.</span><span class="sxs-lookup"><span data-stu-id="fedd3-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="fedd3-189">Independientemente del número de usuarios alojados en el grupo de servidores front-end o del servidor Standard Edition, Lync Server admite un mínimo de 125 otros usuarios que participen en conferencias más pequeñas en el mismo Pool o servidor que hospeda una conferencia 250-usuario.</span><span class="sxs-lookup"><span data-stu-id="fedd3-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="fedd3-190">Para habilitar conferencias con usuarios de 250 y 1000, puede configurar un grupo de servidores front-end independiente solo para hospedar esas conferencias.</span><span class="sxs-lookup"><span data-stu-id="fedd3-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="fedd3-191">Este grupo de servidores front-end no alojará ningún usuario.</span><span class="sxs-lookup"><span data-stu-id="fedd3-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="fedd3-192">Para obtener más información, consulte [compatibilidad con reuniones grandes con Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="fedd3-193">Si su organización tiene muchas más conferencias de modo mixto de lo que se supone en el modelo de usuario, es posible que tenga que implementar más servidores front-end que las recomendaciones de este documento (hasta un límite de 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="fedd3-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="fedd3-194">Para obtener más información sobre los supuestos en el modelo de usuario, consulte [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="fedd3-195">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fedd3-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-196">No se admiten agrupaciones extendidas para este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fedd3-197">Debe implementar un servidor perimetral para cada 12.000 usuarios remotos que tengan acceso a un sitio al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fedd3-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="fedd3-198">Como mínimo, recomendamos dos servidores perimetrales para una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fedd3-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="fedd3-199">En estas recomendaciones se supone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="fedd3-200">Cuando tenga en cuenta el número de usuarios de los servidores perimetrales, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y los servidores de sucursal con la supervivencia que están asociados a un grupo de servidores front-end en este sitio.</span><span class="sxs-lookup"><span data-stu-id="fedd3-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-201">Para mejorar el rendimiento del servicio perimetral de conferencia A/V en los servidores perimetrales, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="fedd3-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="fedd3-202">RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="fedd3-203">Para obtener más información, consulte "mejoras de escala en el lado de recepción en Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>Server 2008" en.</span><span class="sxs-lookup"><span data-stu-id="fedd3-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="fedd3-204">Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="fedd3-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="fedd3-205">Director</span><span class="sxs-lookup"><span data-stu-id="fedd3-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-206">No se admiten agrupaciones extendidas para este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fedd3-207">Si implementa el rol de servidor Director, se recomienda implementar un director por cada 12.000 usuarios remotos que tengan acceso a un sitio al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fedd3-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="fedd3-208">Como mínimo, recomendamos dos directores para una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fedd3-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="fedd3-209">En estas recomendaciones se supone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="fedd3-210">Cuando tenga en cuenta la cantidad de usuarios para los directores, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y en los servidores de sucursal con la supervivencia que están asociados a un grupo de servidores front-end en este sitio.</span><span class="sxs-lookup"><span data-stu-id="fedd3-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="fedd3-211">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="fedd3-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-212">No se admiten agrupaciones extendidas para este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fedd3-213">Si Collocate Server Mediation with front end Server, Media Server se ejecuta en todos los servidores front end del grupo y debe proporcionar la capacidad suficiente para los usuarios del grupo.</span><span class="sxs-lookup"><span data-stu-id="fedd3-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="fedd3-214">Si implementa un grupo de servidores de mediación independiente, entonces la cantidad de servidores de mediación que se van a implementar depende de muchos factores, incluido el hardware usado para el servidor de mediación, el número de usuarios de VoIP que tiene, el número de puertas de enlace y el número de puertas de enlace de cada grupo de servidores de mediación controles, el tráfico de horas ocupado a través de estas puertas de enlace y el porcentaje de llamadas con medios que omiten el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fedd3-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="fedd3-215">En las siguientes tablas se ofrecen instrucciones sobre cuántas llamadas simultáneas puede controlar un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumpla los requisitos de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) y que la tecnología Hyper-Threading esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="fedd3-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="fedd3-216">Para obtener más información sobre la escalabilidad del servidor de mediación, consulte [estimar el uso de voz y el tráfico para Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) y las [directrices de implementación para servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="fedd3-217">En todas las tablas siguientes se supone el uso tal como se resume en los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="fedd3-218">Capacidad de servidor de mediación independiente: 70% usuarios internos, 30% usuarios externos con capacidad de llamada sin derivación (transcodificación multimedia realizada por el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="fedd3-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fedd3-219">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="fedd3-219">Server hardware</span></span></th>
<th><span data-ttu-id="fedd3-220">Número máximo de llamadas</span><span class="sxs-lookup"><span data-stu-id="fedd3-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="fedd3-221">Número máximo de líneas T1</span><span class="sxs-lookup"><span data-stu-id="fedd3-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="fedd3-222">Número máximo de líneas E1</span><span class="sxs-lookup"><span data-stu-id="fedd3-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-223">Procesador dual, seis núcleos, CPU con Hyper-Threading a 2,26 GHz <strong>con la tecnología Hyper-Threading deshabilitada</strong>, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</span><span class="sxs-lookup"><span data-stu-id="fedd3-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="fedd3-224">1100</span><span class="sxs-lookup"><span data-stu-id="fedd3-224">1100</span></span></p></td>
<td><p><span data-ttu-id="fedd3-225">46</span><span class="sxs-lookup"><span data-stu-id="fedd3-225">46</span></span></p></td>
<td><p><span data-ttu-id="fedd3-226">35</span><span class="sxs-lookup"><span data-stu-id="fedd3-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-227">Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</span><span class="sxs-lookup"><span data-stu-id="fedd3-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="fedd3-228">1500</span><span class="sxs-lookup"><span data-stu-id="fedd3-228">1500</span></span></p></td>
<td><p><span data-ttu-id="fedd3-229">63</span><span class="sxs-lookup"><span data-stu-id="fedd3-229">63</span></span></p></td>
<td><p><span data-ttu-id="fedd3-230">47</span><span class="sxs-lookup"><span data-stu-id="fedd3-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-231">Aunque los servidores con 32 GB de memoria se usan para pruebas de rendimiento, los servidores con 16 GB de memoria son compatibles con el servidor de mediación independiente y son suficientes para proporcionar el rendimiento que se muestra en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="fedd3-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="fedd3-232">Capacidad del servidor de mediación (servidor de mediación en el servidor front-end) 70% usuarios internos, 30% de los usuarios externos, capacidad de llamada sin omisión (procesamiento de multimedia realizado por el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="fedd3-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fedd3-233">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="fedd3-233">Server hardware</span></span></th>
<th><span data-ttu-id="fedd3-234">Número máximo de llamadas</span><span class="sxs-lookup"><span data-stu-id="fedd3-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-235">Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y 4 tarjetas adaptadoras de red de 1 GB.</span><span class="sxs-lookup"><span data-stu-id="fedd3-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="fedd3-236">150</span><span class="sxs-lookup"><span data-stu-id="fedd3-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-237">Este número es mucho menor que los números del servidor de mediación independiente porque el servidor front-end tiene que manejar otras características y funciones para los usuarios de 6600 alojados en ella, además de la transcodificación necesaria para las llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="fedd3-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fedd3-238">Para mejorar el rendimiento del servidor de mediación, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="fedd3-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="fedd3-239">RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="fedd3-240">Para obtener más información, consulte "mejoras de escala en el lado de recepción en Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>Server 2008" en.</span><span class="sxs-lookup"><span data-stu-id="fedd3-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="fedd3-241">Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="fedd3-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="fedd3-242">Servidor back-end</span><span class="sxs-lookup"><span data-stu-id="fedd3-242">Back End Server</span></span>

<span data-ttu-id="fedd3-243">En Lync Server 2013, las bases de datos de presencia se encuentran en los servidores front-end en lugar de en el servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="fedd3-244">Esto ha provocado un requisito mucho más sencillo para cada servidor back-end en Lync Server 2013, equivalente al requisito de hardware para el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="fedd3-245">Compare esto con Lync Server 2010, en el que el servidor back-end debe ser un servidor mucho más importante con 25 discos.</span><span class="sxs-lookup"><span data-stu-id="fedd3-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="fedd3-246">Sin embargo, la carga de trabajo de los servidores de servicios de fondo sigue siendo tal que no es posible cumplir con las recomendaciones de hardware enumeradas anteriormente en esta sección y en las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="fedd3-247">Para ofrecer una alta disponibilidad de su servidor back-end, recomendamos implementar el reflejo de servidor.</span><span class="sxs-lookup"><span data-stu-id="fedd3-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="fedd3-248">Para obtener más información, consulte [back end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="fedd3-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="fedd3-249">Supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="fedd3-249">Monitoring and Archiving</span></span>

<span data-ttu-id="fedd3-250">En Lync Server 2013, si implementa la supervisión o el archivado, la funcionalidad front-end de estos servicios se ejecuta en los servidores front-end, en lugar de en roles de servidor diferentes.</span><span class="sxs-lookup"><span data-stu-id="fedd3-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="fedd3-251">La supervisión y el archivado siguen usando su propia tienda de bases de datos, independiente de la tienda back-end.</span><span class="sxs-lookup"><span data-stu-id="fedd3-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="fedd3-252">Como alternativa, si tiene Exchange 2013 implementado, puede almacenar datos de archivado de mensajes instantáneos en Exchange en lugar de en una tienda SQL dedicada.</span><span class="sxs-lookup"><span data-stu-id="fedd3-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="fedd3-253">En la tabla siguiente se indica cuánto almacenamiento de base de datos se necesita aproximadamente por usuario y por día para los datos de supervisión y archivado.</span><span class="sxs-lookup"><span data-stu-id="fedd3-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="fedd3-254"><strong>CDR (Supervisión)</strong></span><span class="sxs-lookup"><span data-stu-id="fedd3-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="fedd3-255"><strong>QoE (Supervisión)</strong></span><span class="sxs-lookup"><span data-stu-id="fedd3-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="fedd3-256"><strong>Archivado</strong></span><span class="sxs-lookup"><span data-stu-id="fedd3-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-257">Espacio en disco necesario por usuario y por día</span><span class="sxs-lookup"><span data-stu-id="fedd3-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="fedd3-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="fedd3-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="fedd3-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="fedd3-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="fedd3-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="fedd3-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fedd3-261">Durante las pruebas de rendimiento, Microsoft usó el hardware de la tabla siguiente para el servidor de bases de datos de supervisión y archivado.</span><span class="sxs-lookup"><span data-stu-id="fedd3-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="fedd3-262">Las pruebas recopilaron los datos de dos grupos de servidores front-end, cada uno de los cuales contiene 80.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="fedd3-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="fedd3-263">Hardware utilizado en las pruebas de rendimiento de supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="fedd3-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fedd3-264">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="fedd3-264">Hardware component</span></span></th>
<th><span data-ttu-id="fedd3-265">Recomendado</span><span class="sxs-lookup"><span data-stu-id="fedd3-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-266">CPU</span><span class="sxs-lookup"><span data-stu-id="fedd3-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="fedd3-267">Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior</span><span class="sxs-lookup"><span data-stu-id="fedd3-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-268">Memoria</span><span class="sxs-lookup"><span data-stu-id="fedd3-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="fedd3-269">48 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="fedd3-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-270">Disco</span><span class="sxs-lookup"><span data-stu-id="fedd3-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="fedd3-271">25 discos duros de 10.000 r.p.m. con 300 GB en cada disco, con la siguiente configuración</span><span class="sxs-lookup"><span data-stu-id="fedd3-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="fedd3-272"><strong>Unidad</strong></span><span class="sxs-lookup"><span data-stu-id="fedd3-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="fedd3-273"><strong>Configuración RAID</strong></span><span class="sxs-lookup"><span data-stu-id="fedd3-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fedd3-274"><strong>Número de discos</strong></span><span class="sxs-lookup"><span data-stu-id="fedd3-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-275">Archivos de datos de las bases de datos de CDR, QoE y archivado, en una sola unidad</span><span class="sxs-lookup"><span data-stu-id="fedd3-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="fedd3-276">1+0</span><span class="sxs-lookup"><span data-stu-id="fedd3-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="fedd3-277">apartado</span><span class="sxs-lookup"><span data-stu-id="fedd3-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-278">Archivo de registro de la base de datos CDR</span><span class="sxs-lookup"><span data-stu-id="fedd3-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="fedd3-279">1</span><span class="sxs-lookup"><span data-stu-id="fedd3-279">1</span></span></p></td>
<td><p><span data-ttu-id="fedd3-280">1</span><span class="sxs-lookup"><span data-stu-id="fedd3-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-281">Archivo de registro de la base de datos QoE</span><span class="sxs-lookup"><span data-stu-id="fedd3-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="fedd3-282">1</span><span class="sxs-lookup"><span data-stu-id="fedd3-282">1</span></span></p></td>
<td><p><span data-ttu-id="fedd3-283">1</span><span class="sxs-lookup"><span data-stu-id="fedd3-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fedd3-284">Archivo de registro de la base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="fedd3-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="fedd3-285">1</span><span class="sxs-lookup"><span data-stu-id="fedd3-285">1</span></span></p></td>
<td><p><span data-ttu-id="fedd3-286">1</span><span class="sxs-lookup"><span data-stu-id="fedd3-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fedd3-287">Red</span><span class="sxs-lookup"><span data-stu-id="fedd3-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fedd3-288">1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</span><span class="sxs-lookup"><span data-stu-id="fedd3-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fedd3-289">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fedd3-289">In This Section</span></span>

  - [<span data-ttu-id="fedd3-290">Estimar el uso de voz y el tráfico para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fedd3-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="fedd3-291">Instrucciones de implementación para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fedd3-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


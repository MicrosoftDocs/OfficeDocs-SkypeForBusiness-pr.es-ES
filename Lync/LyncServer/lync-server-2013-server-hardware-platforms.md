---
title: Plataformas de hardware de servidor de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a1dddb7fe87ebc877ed16048a42a17760c2053
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="d2087-102">Plataformas de hardware de servidor para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2087-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2087-103">_**Última modificación del tema:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="d2087-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="d2087-104">Los roles de servidor de Lync Server 2013 y los equipos que ejecutan herramientas administrativas de Lync Server requieren hardware de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d2087-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="d2087-105">El hardware específico que se usa para la implementación de Lync Server 2013 puede variar en función de los requisitos de tamaño y uso.</span><span class="sxs-lookup"><span data-stu-id="d2087-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="d2087-106">En esta sección se describe el hardware recomendado.</span><span class="sxs-lookup"><span data-stu-id="d2087-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="d2087-107">Aunque se trata de recomendaciones y no de requisitos, el uso de hardware que no cumpla estas recomendaciones puede repercutir considerablemente en el rendimiento y ocasionar otros problemas.</span><span class="sxs-lookup"><span data-stu-id="d2087-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="d2087-108">Plataforma de hardware recomendada</span><span class="sxs-lookup"><span data-stu-id="d2087-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="d2087-109">Para obtener el mejor rendimiento, se recomienda ejecutar Lync Server en servidores con hardware que cumpla los requisitos de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2087-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="d2087-110">Si usa un hardware menos eficaz, puede tener problemas de funcionalidad o un rendimiento deficiente.</span><span class="sxs-lookup"><span data-stu-id="d2087-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="d2087-111">Tenga en cuenta que estos requisitos de hardware son superiores a los de las versiones anteriores de Lync Server, principalmente porque en Lync Server 2013, todos los servidores front-end ejecutan SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d2087-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2087-112">La formación de equipos NIC es compatible y debe ser transparente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2087-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="d2087-113">Para obtener más información, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server o Lync Server y equipos de adaptadores de red</A>.</span><span class="sxs-lookup"><span data-stu-id="d2087-113">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="d2087-114">Hardware recomendado para los servidores front-end, los servidores back-end, los servidores Standard Edition, los servidores de chat persistentes, el almacén de chat persistente y el almacén de cumplimiento de chat persistente (roles de servidor back-end para el servidor de chat persistente)</span><span class="sxs-lookup"><span data-stu-id="d2087-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2087-115">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="d2087-115">Hardware component</span></span></th>
<th><span data-ttu-id="d2087-116">Recomendado</span><span class="sxs-lookup"><span data-stu-id="d2087-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2087-117">CPU</span><span class="sxs-lookup"><span data-stu-id="d2087-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="d2087-118">procesador dual de 64 bits, HEX-Core, 2,26 gigahercios (GHz) o superior.</span><span class="sxs-lookup"><span data-stu-id="d2087-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="d2087-119">Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="d2087-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2087-120">Memoria</span><span class="sxs-lookup"><span data-stu-id="d2087-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="d2087-121">32 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="d2087-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2087-122">Disco</span><span class="sxs-lookup"><span data-stu-id="d2087-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d2087-123">8 o más unidades de disco duro (HHD) de 10.000 RPM con al menos 72 GB de espacio libre en disco.</span><span class="sxs-lookup"><span data-stu-id="d2087-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="d2087-124">Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.</span><span class="sxs-lookup"><span data-stu-id="d2087-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="d2087-125">-O</span><span class="sxs-lookup"><span data-stu-id="d2087-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="d2087-126">Unidades de estado sólido (SSD) con rendimiento igual al de 8 unidades de disco mecánicas de 10.000 rpm.</span><span class="sxs-lookup"><span data-stu-id="d2087-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2087-127">Red</span><span class="sxs-lookup"><span data-stu-id="d2087-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d2087-128">1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendado, que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</span><span class="sxs-lookup"><span data-stu-id="d2087-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d2087-129">No se admiten las configuraciones dual o multitarjeta para los servidores front-end, los servidores back-end, los servidores Standard Edition y los servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d2087-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="d2087-130">ILO/DRAC/etc. las conexiones que no se exponen al sistema operativo y que se usan para supervisar y administrar el hardware del servidor no constituyen un servidor de host múltiple y, por lo tanto, son compatibles.</span><span class="sxs-lookup"><span data-stu-id="d2087-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="d2087-131">Hardware recomendado para los servidores perimetrales, los servidores de mediación autónomos y los Directores</span><span class="sxs-lookup"><span data-stu-id="d2087-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2087-132">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="d2087-132">Hardware component</span></span></th>
<th><span data-ttu-id="d2087-133">Recomendado</span><span class="sxs-lookup"><span data-stu-id="d2087-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2087-134">CPU</span><span class="sxs-lookup"><span data-stu-id="d2087-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d2087-135">procesador dual de 64 bits, cuatro núcleos, 2,0 gigahercios (GHz) o superior.</span><span class="sxs-lookup"><span data-stu-id="d2087-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="d2087-136">-O</span><span class="sxs-lookup"><span data-stu-id="d2087-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="d2087-137">procesador de 4 vías de 64 bits, de doble núcleo, de 2,0 GHz o superior.</span><span class="sxs-lookup"><span data-stu-id="d2087-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="d2087-138">Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="d2087-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2087-139">Memoria</span><span class="sxs-lookup"><span data-stu-id="d2087-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="d2087-140">16 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="d2087-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2087-141">Disco</span><span class="sxs-lookup"><span data-stu-id="d2087-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d2087-142">4 o más unidades de disco duro de 10.000 RPM con al menos 72 GB de espacio libre en disco.</span><span class="sxs-lookup"><span data-stu-id="d2087-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="d2087-143">Los discos deben estar en una configuración RAID 1 2x.</span><span class="sxs-lookup"><span data-stu-id="d2087-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="d2087-144">-O</span><span class="sxs-lookup"><span data-stu-id="d2087-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="d2087-145">Unidades de estado sólido (SSD) con un rendimiento igual al de 4 unidades de disco duro mecánicas de 10.000 rpm.</span><span class="sxs-lookup"><span data-stu-id="d2087-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2087-146">Red</span><span class="sxs-lookup"><span data-stu-id="d2087-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d2087-147">1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendado, que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</span><span class="sxs-lookup"><span data-stu-id="d2087-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="d2087-148">2 las interfaces de red son necesarias en los servidores perimetrales y son compatibles con los servidores de mediación independientes.</span><span class="sxs-lookup"><span data-stu-id="d2087-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="d2087-149">Las configuraciones dual o multitarjeta no son compatibles con los directores.</span><span class="sxs-lookup"><span data-stu-id="d2087-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="d2087-150">ILO/DRAC/etc. las conexiones que no se exponen al sistema operativo y que se usan para supervisar y administrar el hardware del servidor no constituyen un servidor de host múltiple y, por lo tanto, son compatibles.</span><span class="sxs-lookup"><span data-stu-id="d2087-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="d2087-151">Los servidores perimetrales requerirán dos interfaces de red que sean adaptadores de red de puerto dual, 1 Gbps o superior (o dos adaptadores de red emparejados, para un total de cuatro, cada par se integra con una sola dirección MAC y una sola dirección IP, para un total de dos pares).</span><span class="sxs-lookup"><span data-stu-id="d2087-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="d2087-152">Se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para permitir la configuración de una dirección IP de RTC específica en los servidores de mediación independientes.</span><span class="sxs-lookup"><span data-stu-id="d2087-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


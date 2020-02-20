---
title: 'Lync Server 2013: selección de una topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b91fc332c5eff86cd23393492bcd760bbda18db3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="137ab-102">Elección de una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137ab-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="137ab-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="137ab-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="137ab-104">Al elegir una topología, puede usar una de las siguientes opciones compatibles:</span><span class="sxs-lookup"><span data-stu-id="137ab-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="137ab-105">A menos que se indique lo contrario, si tiene experiencia con Microsoft Lync Server 2010, encontrará que la guía no se modifica en gran medida.</span><span class="sxs-lookup"><span data-stu-id="137ab-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="137ab-106">Servidor perimetral consolidado único con direcciones IP privadas y NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137ab-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="137ab-107">Servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137ab-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="137ab-108">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137ab-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="137ab-109">Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137ab-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="137ab-110">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137ab-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="137ab-p101">La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="137ab-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="137ab-113">En la tabla siguiente se resumen las funciones disponibles en las topologías de Microsoft Lync Server 2013 compatibles.</span><span class="sxs-lookup"><span data-stu-id="137ab-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="137ab-114">Los encabezados de columna indican la funcionalidad disponible con una opción de configuración perimetral determinada.</span><span class="sxs-lookup"><span data-stu-id="137ab-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="137ab-115">Si tomamos la opción perimetral escalada (DNS con equilibro de carga) como ejemplo, veremos que admite una alta disponibilidad, puede usar direcciones IP privadas no enrutables (con NAT) o direcciones IP públicas enrutables asignadas a las interfaces perimetrales externas y reduce el costo dado que no necesita un equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="137ab-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="137ab-116">Los escenarios de conmutación por error perimetral compatibles con el equilibrio de carga de DNS son sesiones de punto a punto de Lync a Lync, sesiones de conferencia de Lync, sesiones de Lync a RTC y Office 365.</span><span class="sxs-lookup"><span data-stu-id="137ab-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="137ab-117">Los escenarios de conmutación por error perimetral que no se benefician del equilibrio de carga de DNS son la conmutación por error de la mensajería unificada de Exchange para usuarios remotos (UM) (antes de Exchange 2010 SP1), conectividad de mensajería instantánea pública (mi) y Federación con servidores que ejecutan Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="137ab-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="137ab-118">Resumen de opciones de topología de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="137ab-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="137ab-119">Topología</span><span class="sxs-lookup"><span data-stu-id="137ab-119">Topology</span></span></th>
<th><span data-ttu-id="137ab-120">Alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="137ab-120">High availability</span></span></th>
<th><span data-ttu-id="137ab-121">Registros A DNS adicionales necesarios para el servidor perimetral externo del grupo</span><span class="sxs-lookup"><span data-stu-id="137ab-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="137ab-122">Conmutación por error perimetral para sesiones de Lync a Lync</span><span class="sxs-lookup"><span data-stu-id="137ab-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="137ab-123">Conmutación por error para sesiones de Federación de Lync a Lync EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="137ab-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="137ab-124">Perimetral simple usando NAT</span><span class="sxs-lookup"><span data-stu-id="137ab-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="137ab-125">No</span><span class="sxs-lookup"><span data-stu-id="137ab-125">No</span></span></p></td>
<td><p><span data-ttu-id="137ab-126">No</span><span class="sxs-lookup"><span data-stu-id="137ab-126">No</span></span></p></td>
<td><p><span data-ttu-id="137ab-127">No</span><span class="sxs-lookup"><span data-stu-id="137ab-127">No</span></span></p></td>
<td><p><span data-ttu-id="137ab-128">No</span><span class="sxs-lookup"><span data-stu-id="137ab-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137ab-129">Perimetral simple usando IP pública</span><span class="sxs-lookup"><span data-stu-id="137ab-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="137ab-130">No</span><span class="sxs-lookup"><span data-stu-id="137ab-130">No</span></span></p></td>
<td><p><span data-ttu-id="137ab-131">No</span><span class="sxs-lookup"><span data-stu-id="137ab-131">No</span></span></p></td>
<td><p><span data-ttu-id="137ab-132">No</span><span class="sxs-lookup"><span data-stu-id="137ab-132">No</span></span></p></td>
<td><p><span data-ttu-id="137ab-133">No</span><span class="sxs-lookup"><span data-stu-id="137ab-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137ab-134">Perimetral escalada (con equilibrio de carga DNS) usando NAT</span><span class="sxs-lookup"><span data-stu-id="137ab-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="137ab-135">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="137ab-136">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="137ab-137">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137ab-138">Perimetral escalada (con equilibrio de carga DNS) usando IP pública</span><span class="sxs-lookup"><span data-stu-id="137ab-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="137ab-139">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="137ab-140">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="137ab-141">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137ab-142">Perimetral escalada (equil. carga hardware)</span><span class="sxs-lookup"><span data-stu-id="137ab-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="137ab-143">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="137ab-144">No (un registro A DNS por VIP)</span><span class="sxs-lookup"><span data-stu-id="137ab-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="137ab-145">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="137ab-146">Sí</span><span class="sxs-lookup"><span data-stu-id="137ab-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="137ab-147">**\*** La conmutación por error para la conectividad de mensajería instantánea pública (mi) y la Federación con servidores que ejecutan Office Communications Server no están disponibles con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="137ab-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="137ab-148">La conmutación por error de mensajería unificada de Exchange (usuario remoto) mediante el equilibrio de carga de DNS requiere Exchange Server 2010 SP1 o una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="137ab-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="137ab-149">Las topologías de perimetral simple y perimetral escalada (con equilibrio de carga DNS) pueden usar:</span><span class="sxs-lookup"><span data-stu-id="137ab-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="137ab-150">Direcciones IP públicas enrutables</span><span class="sxs-lookup"><span data-stu-id="137ab-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="137ab-151">Dirección IP privada no enrutable si se usa la traducción de direcciones de red (NAT) simétrica</span><span class="sxs-lookup"><span data-stu-id="137ab-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="137ab-152">Si usa una dirección IP pública o una dirección IP privada con NAT, seguirá usando el mismo número de direcciones IP en función de la opción de configuración en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="137ab-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="137ab-153">Puede configurar el servidor perimetral para usar una dirección IP única con puertos distintos por servicio, o usar direcciones IP distintas por servicio, pero use el mismo puerto (de forma predeterminada, TCP 443).</span><span class="sxs-lookup"><span data-stu-id="137ab-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="137ab-154">Si decide usar direcciones IP privadas no enrutables con NAT:</span><span class="sxs-lookup"><span data-stu-id="137ab-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="137ab-155">Debe usar direcciones IP privadas enrutables en las tres interfaces externas</span><span class="sxs-lookup"><span data-stu-id="137ab-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="137ab-156">Debe configurar NAT simétrica para tráfico entrante y saliente</span><span class="sxs-lookup"><span data-stu-id="137ab-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="137ab-157">La topología perimetral escalada (equil. carga hardware) debe usar direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="137ab-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="137ab-158">Lync Server 2013 admite la colocación de interfaces externas perimetrales de acceso, conferencia web y a/V detrás de un enrutador o firewall que realiza la traducción de direcciones de red (NAT) para topologías de servidor perimetral consolidado simples y escaladas.</span><span class="sxs-lookup"><span data-stu-id="137ab-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="137ab-p106">El uso de NAT para todas las interfaces externas perimetrales requiere el uso del equilibrio de carga de DNS. En comparación con el uso de equilibradores de carga de hardware, el uso de equilibrio de carga de DNS sin NAT permite reducir el número de la dirección IP pública por servidor perimetral en un grupo de servidores perimetrales, como se describe en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="137ab-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="137ab-161">Lync Server 2013 el perímetro consolidado escalado (con equilibrio de carga DNS) requiere tres direcciones IP públicas para cada servidor perimetral en un grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="137ab-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="137ab-162">Lync Server 2013 servidor perimetral consolidado escalado (equilibrio de carga de hardware) requiere tres direcciones IP públicas para las direcciones IP virtuales del equilibrador de carga (un requisito de tiempo que no aumenta a medida que se agregan más servidores perimetrales al grupo) más tres direcciones IP públicas por Servidor perimetral en un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="137ab-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="137ab-163">Requisitos de dirección IP para servidor perimetral consolidado escalado (dirección IP por rol)</span><span class="sxs-lookup"><span data-stu-id="137ab-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="137ab-164">Número de servidores perimetrales por grupo</span><span class="sxs-lookup"><span data-stu-id="137ab-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="137ab-165">Número de direcciones IP necesarias Lync Server 2013 (con equilibrio de carga DNS)</span><span class="sxs-lookup"><span data-stu-id="137ab-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="137ab-166">Número de direcciones IP necesarias Lync Server 2013 (equilibrio de carga de hardware)</span><span class="sxs-lookup"><span data-stu-id="137ab-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="137ab-167">segundo</span><span class="sxs-lookup"><span data-stu-id="137ab-167">2</span></span></p></td>
<td><p><span data-ttu-id="137ab-168">6 </span><span class="sxs-lookup"><span data-stu-id="137ab-168">6</span></span></p></td>
<td><p><span data-ttu-id="137ab-169">3 (1 por VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="137ab-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137ab-170">3</span><span class="sxs-lookup"><span data-stu-id="137ab-170">3</span></span></p></td>
<td><p><span data-ttu-id="137ab-171">9 </span><span class="sxs-lookup"><span data-stu-id="137ab-171">9</span></span></p></td>
<td><p><span data-ttu-id="137ab-172">3 (1 por VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="137ab-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137ab-173">4</span><span class="sxs-lookup"><span data-stu-id="137ab-173">4</span></span></p></td>
<td><p><span data-ttu-id="137ab-174">12</span><span class="sxs-lookup"><span data-stu-id="137ab-174">12</span></span></p></td>
<td><p><span data-ttu-id="137ab-175">3 (1 por VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="137ab-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137ab-176">2,5</span><span class="sxs-lookup"><span data-stu-id="137ab-176">5</span></span></p></td>
<td><p><span data-ttu-id="137ab-177">15 </span><span class="sxs-lookup"><span data-stu-id="137ab-177">15</span></span></p></td>
<td><p><span data-ttu-id="137ab-178">3 (1 por VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="137ab-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="137ab-179">Requisitos de dirección IP para servidor perimetral consolidado escalado (dirección IP única para todos los roles)</span><span class="sxs-lookup"><span data-stu-id="137ab-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="137ab-180">Número de servidores perimetrales por grupo</span><span class="sxs-lookup"><span data-stu-id="137ab-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="137ab-181">Número de direcciones IP necesarias Lync Server 2013 (con equilibrio de carga DNS)</span><span class="sxs-lookup"><span data-stu-id="137ab-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="137ab-182">Número de direcciones IP necesarias Lync Server 2013 (equilibrio de carga de hardware)</span><span class="sxs-lookup"><span data-stu-id="137ab-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="137ab-183">segundo</span><span class="sxs-lookup"><span data-stu-id="137ab-183">2</span></span></p></td>
<td><p><span data-ttu-id="137ab-184">segundo</span><span class="sxs-lookup"><span data-stu-id="137ab-184">2</span></span></p></td>
<td><p><span data-ttu-id="137ab-185">1 (1 por VIP) + 2</span><span class="sxs-lookup"><span data-stu-id="137ab-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137ab-186">3</span><span class="sxs-lookup"><span data-stu-id="137ab-186">3</span></span></p></td>
<td><p><span data-ttu-id="137ab-187">3</span><span class="sxs-lookup"><span data-stu-id="137ab-187">3</span></span></p></td>
<td><p><span data-ttu-id="137ab-188">1 (1 por VIP) + 3</span><span class="sxs-lookup"><span data-stu-id="137ab-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137ab-189">4</span><span class="sxs-lookup"><span data-stu-id="137ab-189">4</span></span></p></td>
<td><p><span data-ttu-id="137ab-190">4</span><span class="sxs-lookup"><span data-stu-id="137ab-190">4</span></span></p></td>
<td><p><span data-ttu-id="137ab-191">1 (1 por VIP) + 4</span><span class="sxs-lookup"><span data-stu-id="137ab-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137ab-192">2,5</span><span class="sxs-lookup"><span data-stu-id="137ab-192">5</span></span></p></td>
<td><p><span data-ttu-id="137ab-193">2,5</span><span class="sxs-lookup"><span data-stu-id="137ab-193">5</span></span></p></td>
<td><p><span data-ttu-id="137ab-194">1 (1 por VIP) + 5</span><span class="sxs-lookup"><span data-stu-id="137ab-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="137ab-p107">Los principales aspectos a la hora de decantarse por una topología son la alta disponibilidad y el equilibrio de carga. El requisito de alta disponibilidad influye en la decisión del equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="137ab-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="137ab-197">**Alta disponibilidad**   Si necesita una alta disponibilidad, implemente al menos dos servidores perimetrales en un grupo.</span><span class="sxs-lookup"><span data-stu-id="137ab-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="137ab-198">Un solo grupo de servidores perimetrales admitirá hasta doce servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="137ab-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="137ab-199">En caso de que se requiera más capacidad, se pueden implementar varios grupos perimetrales.</span><span class="sxs-lookup"><span data-stu-id="137ab-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="137ab-200">Como norma general, un 10% de una base de usuarios determinada necesitará acceso externo.</span><span class="sxs-lookup"><span data-stu-id="137ab-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="137ab-201">El generador de topologías le permitirá configurar hasta veinte servidores perimetrales en un único grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="137ab-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="137ab-202">El número máximo de servidores perimetrales probados y admitidos en un grupo de servidores es de 12 y el generador de topologías que permite un número mayor que 12 no debe interpretarse como compatibilidad implícita para más de doce servidores perimetrales en un único grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="137ab-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="137ab-203">**Equilibrio de carga de hardware**   El equilibrio de carga de hardware se admite para equilibrar la carga de los servidores perimetrales de Lync Server 2013 al usar direcciones IP enrutables públicamente para las interfaces externas del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="137ab-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="137ab-204">Por ejemplo, este método podría usarse en situaciones en las que se necesita conmutación por error para cualquiera de las siguientes aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="137ab-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="137ab-205">Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="137ab-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="137ab-206">Federación con compañías que ejecutan Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="137ab-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="137ab-207">Acceso externo a la mensajería unificada de Exchange 2007 o de Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="137ab-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="137ab-208">El equilibrio de carga de DNS para Exchange 2010 SP1 y las versiones más recientes son compatibles con la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="137ab-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="137ab-p111">Estas tres aplicaciones pueden seguir funcionando, pero no reparan en el equilibrio de carga DNS y solo se conectarán al primer servidor perimetral del grupo, de modo que si este no se encuentra disponible, la conexión no se establecerá. Por ejemplo, si hay varios servidores perimetrales en un grupo con los que se controla la carga de tráfico federado, solo un proxy de acceso recibirá el tráfico realmente, mientras que el resto permanecerá inactivo.</span><span class="sxs-lookup"><span data-stu-id="137ab-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="137ab-212">Se recomienda usar el equilibrio de carga de DNS si está federando con compañías mediante Lync Server 2010 y Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="137ab-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="137ab-213">Tenga en cuenta que hay un impacto significativo en el rendimiento si la mayoría de los socios federados usan Office Communications Server 2007 o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="137ab-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="137ab-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="137ab-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>


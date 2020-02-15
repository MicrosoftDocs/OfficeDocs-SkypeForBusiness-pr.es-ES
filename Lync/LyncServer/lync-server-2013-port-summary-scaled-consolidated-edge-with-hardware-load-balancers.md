---
title: Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cad84208df5129b3a10c1e80aa28442ebcbd44
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="15a33-102">Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a33-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15a33-103">_**Última modificación del tema:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="15a33-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="15a33-104">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="15a33-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="15a33-105">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="15a33-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="15a33-106">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="15a33-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="15a33-107">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="15a33-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="15a33-108">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="15a33-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="15a33-109">**Servidor perimetral consolidado ampliado con equilibrio de carga de hardware**</span><span class="sxs-lookup"><span data-stu-id="15a33-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="15a33-110">![Puertos y protocolos de red perimetral del servidor perimetral](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Puertos y protocolos de red perimetral del servidor perimetral")</span><span class="sxs-lookup"><span data-stu-id="15a33-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="15a33-111">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="15a33-111">Port and Protocol Details</span></span>

<span data-ttu-id="15a33-112">Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.</span><span class="sxs-lookup"><span data-stu-id="15a33-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="15a33-p103">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.</span><span class="sxs-lookup"><span data-stu-id="15a33-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="15a33-115">Resumen de Firewall para servidor perimetral consolidado escalado, carga equilibrada de hardware: interfaz externa – nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="15a33-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15a33-116">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="15a33-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="15a33-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="15a33-117">Source IP address</span></span></th>
<th><span data-ttu-id="15a33-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="15a33-118">Destination IP address</span></span></th>
<th><span data-ttu-id="15a33-119">Notas</span><span class="sxs-lookup"><span data-stu-id="15a33-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15a33-120">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="15a33-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="15a33-121">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-122">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-123">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="15a33-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-124">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="15a33-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="15a33-125">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-126">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-127">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="15a33-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-128">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="15a33-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="15a33-129">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-130">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-131">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="15a33-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-132">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="15a33-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="15a33-133">Dirección IP del servicio perimetral del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="15a33-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-134">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-135">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a33-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-136">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="15a33-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="15a33-137">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-138">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-139">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="15a33-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-140">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="15a33-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="15a33-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-141">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-142">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-143">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="15a33-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-144">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="15a33-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="15a33-145">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-145">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-146">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-147">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="15a33-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="15a33-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="15a33-149">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-150">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-151">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="15a33-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="15a33-152">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="15a33-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="15a33-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="15a33-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-154">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-155">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-156">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="15a33-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-158">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-159">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-160">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-162">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-163">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-163">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-164">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="15a33-165">Resumen de Firewall para servidor perimetral consolidado escalado, carga equilibrada de hardware: nodo 1 de interfaz interna y nodo 2</span><span class="sxs-lookup"><span data-stu-id="15a33-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15a33-166">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="15a33-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="15a33-167">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="15a33-167">Source IP address</span></span></th>
<th><span data-ttu-id="15a33-168">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="15a33-168">Destination IP address</span></span></th>
<th><span data-ttu-id="15a33-169">Notas</span><span class="sxs-lookup"><span data-stu-id="15a33-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15a33-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="15a33-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="15a33-171">Cualquiera (puede definirse como dirección del servidor front-end o dirección IP virtual del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="15a33-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="15a33-172">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-173">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="15a33-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="15a33-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="15a33-175">Cualquiera (puede definirse como la IP o el grupo de servidores front-end Server que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="15a33-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="15a33-176">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-177">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="15a33-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="15a33-179">Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</span><span class="sxs-lookup"><span data-stu-id="15a33-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="15a33-180">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-181">Tráfico de conferencia web de la implementación interna a la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="15a33-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="15a33-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="15a33-183">Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</span><span class="sxs-lookup"><span data-stu-id="15a33-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="15a33-184">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-185">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="15a33-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-187">Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</span><span class="sxs-lookup"><span data-stu-id="15a33-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="15a33-188">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-189">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="15a33-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="15a33-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="15a33-191">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-191">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-192">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-193">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="15a33-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="15a33-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="15a33-195">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-195">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-196">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-197">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="15a33-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="15a33-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="15a33-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-199">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-200">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-201">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="15a33-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15a33-202">Los equilibradores de carga de hardware tienen requisitos específicos cuando se implementan para proporcionar disponibilidad y equilibrio de carga para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15a33-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="15a33-203">Los requisitos se definen en la figura y las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="15a33-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="15a33-204">Los proveedores de terceros pueden usar terminología diferente para los requisitos que se definen aquí.</span><span class="sxs-lookup"><span data-stu-id="15a33-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="15a33-205">Será necesario asignar los requisitos de Lync Server a las características y opciones de configuración proporcionadas por el proveedor del equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="15a33-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="15a33-206">Al configurar equilibradores de carga de hardware, tenga en cuenta los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="15a33-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="15a33-207">La traducción de direcciones de red de origen (SNAT) se puede configurar en el equilibrador de carga de hardware (HLB) para el servicio perimetral de acceso y el servicio perimetral de conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="15a33-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="15a33-208">No se puede configurar SNAT en el servicio perimetral A/V: el servicio perimetral A/V debe responder con la dirección real del servidor, no la IP virtual (VIP) de HLB, para un recorrido sencillo de UDP sobre NAT (STUN)/Traversal mediante la NAT de retransmisión (TURN)/Federation TURN (FTURN) para que funcione correctamente</span><span class="sxs-lookup"><span data-stu-id="15a33-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="15a33-209">Si el cliente envía una solicitud a HLB, la respuesta debe volver de la dirección VIP HLB</span><span class="sxs-lookup"><span data-stu-id="15a33-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="15a33-210">Si el cliente envía una solicitud al servidor perimetral, la respuesta debe volver de la IP del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="15a33-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="15a33-211">Las direcciones IP públicas se usan en cada interfaz de servidor y en las direcciones VIP de HLB, y los requisitos de dirección IP pública son N + 1, donde hay una dirección IP pública para cada interfaz de servidor real y otra para cada VIP de HLB.</span><span class="sxs-lookup"><span data-stu-id="15a33-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="15a33-212">Si tiene 2 servidores perimetrales en el grupo, se obtendrán 9 direcciones IP públicas, donde 3 se usan para los VIP de HLB y una para cada interfaz del servidor perimetral (un total de seis para los servidores)</span><span class="sxs-lookup"><span data-stu-id="15a33-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="15a33-213">Para el servicio perimetral de acceso y el servicio perimetral de conferencia web (y el uso de NAT en el HLB), el cliente se pone en contacto con la VIP, la VIP cambia la dirección IP de origen del cliente a su propia dirección IP.</span><span class="sxs-lookup"><span data-stu-id="15a33-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="15a33-214">La interfaz del servidor dirige la dirección de retorno a la VIP, la VIP cambia la dirección de origen de la dirección IP de la interfaz del servidor y envía el paquete al cliente.</span><span class="sxs-lookup"><span data-stu-id="15a33-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="15a33-215">En el caso del servicio perimetral a/V, la VIP no debe cambiar la dirección IP de origen y la dirección del servidor real se devuelve al cliente directamente; no puede configurar NAT en el HLB para el tráfico audiovisual</span><span class="sxs-lookup"><span data-stu-id="15a33-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="15a33-216">Si el cliente envía una solicitud a la VIP de HLB, la respuesta debe volver de la VIP de HLB.</span><span class="sxs-lookup"><span data-stu-id="15a33-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="15a33-217">Si el cliente envía una solicitud a la IP perimetral, la respuesta debe devolverse a la dirección IP del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="15a33-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="15a33-218">Para AV, el firewall externo mantendrá la dirección IP pública del servidor real para todos los paquetes</span><span class="sxs-lookup"><span data-stu-id="15a33-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="15a33-219">Una vez establecida, la comunicación del cliente con el servicio perimetral a/V es al servidor real, no a la HLB</span><span class="sxs-lookup"><span data-stu-id="15a33-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="15a33-220">El perímetro interno de los servidores internos y los clientes debe enrutarse, y las rutas persistentes se establecen para todas las redes internas que hospedan servidores o clientes.</span><span class="sxs-lookup"><span data-stu-id="15a33-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="15a33-221">La VIP del servicio perimetral de acceso HLB funcionará como puerta de enlace predeterminada para cada interfaz del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="15a33-222">Para obtener más información sobre la planeación y la funcionalidad de NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos del equilibrador de carga de hardware para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="15a33-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="15a33-223">![Detalles de protocolos y puertos del servidor perimetral](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalles de protocolos y puertos del servidor perimetral")</span><span class="sxs-lookup"><span data-stu-id="15a33-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="15a33-224">Configuración de puertos externos necesaria para servidor perimetral consolidado ampliado, carga equilibrada de hardware: IP virtuales de interfaz externa</span><span class="sxs-lookup"><span data-stu-id="15a33-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15a33-225">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="15a33-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="15a33-226">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="15a33-226">Source IP address</span></span></th>
<th><span data-ttu-id="15a33-227">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="15a33-227">Destination IP address</span></span></th>
<th><span data-ttu-id="15a33-228">Notas</span><span class="sxs-lookup"><span data-stu-id="15a33-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15a33-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="15a33-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="15a33-230">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-230">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-231">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="15a33-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="15a33-232">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="15a33-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="15a33-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="15a33-234">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="15a33-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="15a33-235">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-235">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-236">El servicio Proxy XMPP envía tráfico a los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="15a33-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-237">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-238">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-238">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-239">Dirección VIP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="15a33-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-240">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="15a33-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-241">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="15a33-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="15a33-242">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-242">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-243">Dirección VIP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="15a33-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-244">Señalización SIP, federada y conectividad de mensajería instantánea pública con SIP</span><span class="sxs-lookup"><span data-stu-id="15a33-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-245">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="15a33-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="15a33-246">Dirección VIP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="15a33-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-247">Socio federado</span><span class="sxs-lookup"><span data-stu-id="15a33-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="15a33-248">Señalización SIP, federada y conectividad de mensajería instantánea pública con SIP</span><span class="sxs-lookup"><span data-stu-id="15a33-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-249">Conferencia web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-250">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-250">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-251">Dirección VIP pública del servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-252">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="15a33-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="15a33-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="15a33-254">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-254">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-255">Dirección VIP pública del servicio perimetral A/V del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="15a33-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-256">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="15a33-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-258">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-258">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-259">Dirección VIP pública del servicio perimetral A/V del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="15a33-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="15a33-260">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="15a33-261">Resumen de Firewall para servidor perimetral consolidado ampliado, carga equilibrada de hardware: IP virtuales de interfaz interna</span><span class="sxs-lookup"><span data-stu-id="15a33-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15a33-262">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="15a33-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="15a33-263">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="15a33-263">Source IP address</span></span></th>
<th><span data-ttu-id="15a33-264">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="15a33-264">Destination IP address</span></span></th>
<th><span data-ttu-id="15a33-265">Notas</span><span class="sxs-lookup"><span data-stu-id="15a33-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15a33-266">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="15a33-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="15a33-267">Cualquiera (puede definirse como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="15a33-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="15a33-268">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-269">Tráfico SIP saliente (del Director, la dirección IP virtual del grupo de directores, el servidor front-end o la dirección IP virtual del grupo de servidores front-end) a la VIP de perímetro interno</span><span class="sxs-lookup"><span data-stu-id="15a33-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-270">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="15a33-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="15a33-271">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-272">Cualquiera (puede definirse como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="15a33-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="15a33-273">Tráfico SIP entrante (Director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="15a33-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="15a33-275">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="15a33-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="15a33-276">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-277">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="15a33-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="15a33-279">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-279">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-280">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-281">Ruta de acceso preferida para la transferencia de multimedia de A/V entre usuarios internos y externos</span><span class="sxs-lookup"><span data-stu-id="15a33-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a33-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-283">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-283">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-284">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-285">Ruta de conmutación por recuperación para transferencia de multimedia de A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorios</span><span class="sxs-lookup"><span data-stu-id="15a33-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a33-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="15a33-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="15a33-287">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15a33-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="15a33-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a33-288">Any</span></span></p></td>
<td><p><span data-ttu-id="15a33-289">Ruta de conmutación por recuperación para transferencia de multimedia de A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorios</span><span class="sxs-lookup"><span data-stu-id="15a33-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


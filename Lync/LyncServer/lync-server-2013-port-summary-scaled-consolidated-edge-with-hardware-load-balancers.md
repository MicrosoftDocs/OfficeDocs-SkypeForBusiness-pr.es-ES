---
title: Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="da3b5-102">Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da3b5-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da3b5-103">_**Última modificación del tema:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="da3b5-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="da3b5-104">La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="da3b5-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="da3b5-105">La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="da3b5-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="da3b5-106">Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="da3b5-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="da3b5-107">Además de IPv4, el servidor EDGE ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="da3b5-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="da3b5-108">Para mayor claridad, solo se usa IPv4 en los escenarios.</span><span class="sxs-lookup"><span data-stu-id="da3b5-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="da3b5-109">**Borde consolidado escalado mediante el equilibrio de carga de hardware**</span><span class="sxs-lookup"><span data-stu-id="da3b5-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="da3b5-110">![Puertos y protocolos de red perimetral de servidores perimetrales] (images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Puertos y protocolos de red perimetral de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="da3b5-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="da3b5-111">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="da3b5-111">Port and Protocol Details</span></span>

<span data-ttu-id="da3b5-112">Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="da3b5-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="da3b5-113">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="da3b5-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="da3b5-114">En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.</span><span class="sxs-lookup"><span data-stu-id="da3b5-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="da3b5-115">Resumen del firewall para el perímetro consolidado con escala, equilibrio de carga de hardware: interfaz externa-nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="da3b5-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da3b5-116">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="da3b5-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da3b5-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="da3b5-117">Source IP address</span></span></th>
<th><span data-ttu-id="da3b5-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="da3b5-118">Destination IP address</span></span></th>
<th><span data-ttu-id="da3b5-119">Notas</span><span class="sxs-lookup"><span data-stu-id="da3b5-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="da3b5-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="da3b5-121">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-122">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-123">Comprobación y recuperación de CRL o revocación de certificados</span><span class="sxs-lookup"><span data-stu-id="da3b5-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-124">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="da3b5-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="da3b5-125">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-126">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-127">Consulta DNS a través de TCP</span><span class="sxs-lookup"><span data-stu-id="da3b5-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-128">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="da3b5-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="da3b5-129">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-130">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-131">Consulta DNS a través de UDP</span><span class="sxs-lookup"><span data-stu-id="da3b5-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-132">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="da3b5-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da3b5-133">Dirección IP del servicio Edge del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="da3b5-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-134">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-135">Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da3b5-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-136">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="da3b5-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da3b5-137">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-138">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-139">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="da3b5-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-140">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="da3b5-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da3b5-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-141">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-142">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-143">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="da3b5-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-144">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="da3b5-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da3b5-145">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-145">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-146">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-147">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="da3b5-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da3b5-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da3b5-149">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-150">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-151">3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="da3b5-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="da3b5-152">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="da3b5-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da3b5-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da3b5-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-154">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-155">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-156">STUN/TURN negociación de candidatos a través de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da3b5-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-158">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-159">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-160">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-162">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-163">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-163">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-164">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="da3b5-165">Resumen del firewall para el perímetro consolidado con escala, equilibrio de carga de hardware: nodo 1 de interfaz interna y nodo 2</span><span class="sxs-lookup"><span data-stu-id="da3b5-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da3b5-166">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="da3b5-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da3b5-167">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="da3b5-167">Source IP address</span></span></th>
<th><span data-ttu-id="da3b5-168">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="da3b5-168">Destination IP address</span></span></th>
<th><span data-ttu-id="da3b5-169">Notas</span><span class="sxs-lookup"><span data-stu-id="da3b5-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="da3b5-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="da3b5-171">Cualquiera (se puede definir como la dirección del servidor front-end o la dirección IP virtual del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="da3b5-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-172">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-173">Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="da3b5-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="da3b5-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-175">Cualquiera (puede definirse como la IP o el grupo de servidores front-end Server que contiene el almacén central de administración)</span><span class="sxs-lookup"><span data-stu-id="da3b5-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-176">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-177">Replicación de los cambios del almacén de administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="da3b5-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="da3b5-179">Any (se puede definir como IP de Director, IP de servidor front end o IP virtual de grupo)</span><span class="sxs-lookup"><span data-stu-id="da3b5-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-180">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-181">Tráfico de conferencias web de la implementación interna a la interfaz de servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="da3b5-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da3b5-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da3b5-183">Any (se puede definir como IP de Director, IP de servidor front end o IP virtual de grupo)</span><span class="sxs-lookup"><span data-stu-id="da3b5-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-184">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-185">Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="da3b5-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-187">Any (se puede definir como IP de Director, IP de servidor front end o IP virtual de grupo)</span><span class="sxs-lookup"><span data-stu-id="da3b5-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-188">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-189">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="da3b5-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="da3b5-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="da3b5-191">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-191">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-192">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-193">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="da3b5-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="da3b5-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="da3b5-195">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-195">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-196">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-197">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="da3b5-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="da3b5-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="da3b5-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-199">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-200">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-201">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="da3b5-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="da3b5-202">Los equilibradores de carga de hardware tienen requisitos específicos cuando se implementan para proporcionar disponibilidad y equilibrio de carga para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da3b5-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="da3b5-203">Los requisitos se definen en la siguiente ilustración y tablas.</span><span class="sxs-lookup"><span data-stu-id="da3b5-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="da3b5-204">Los proveedores de terceros pueden usar terminología diferente para los requisitos que se definen aquí.</span><span class="sxs-lookup"><span data-stu-id="da3b5-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="da3b5-205">Será necesario asignar los requisitos de Lync Server a las características y opciones de configuración proporcionadas por el proveedor de equilibrador de carga del hardware.</span><span class="sxs-lookup"><span data-stu-id="da3b5-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="da3b5-206">Al configurar equilibradores de carga de hardware, tenga en cuenta los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="da3b5-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="da3b5-207">La traducción de direcciones de red de origen (SNAT) se puede configurar en el equilibrio de carga de hardware (HLB) para el servicio perimetral de Access y el servicio perimetral de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="da3b5-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="da3b5-208">SNAT no se puede configurar en el servicio perimetral A/V: el servicio perimetral A/V debe responder con la dirección real del servidor, no con la IP virtual de HLB (VIP), para un recorrido simple de UDP sobre NAT (STUN)/Traversal mediante la opción de retransmisión NAT (TURN)/Federation (FAPAGAR) para funcionar correctamente</span><span class="sxs-lookup"><span data-stu-id="da3b5-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="da3b5-209">Si el cliente envía una solicitud al HLB, la respuesta debe devolverse a la dirección VIP de HLB.</span><span class="sxs-lookup"><span data-stu-id="da3b5-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="da3b5-210">Si el cliente envía una solicitud al borde, la respuesta debe volver de la IP de borde.</span><span class="sxs-lookup"><span data-stu-id="da3b5-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="da3b5-211">Las direcciones IP públicas se usan en cada interfaz de servidor y en los VIP de la HLB, y los requisitos de dirección IP pública son N + 1, donde hay una dirección IP pública para cada interfaz de servidor real y otra para cada VIP de HLB.</span><span class="sxs-lookup"><span data-stu-id="da3b5-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="da3b5-212">Cuando tiene dos servidores perimetrales en el grupo, se producen 9 direcciones IP públicas, donde 3 se usan para los VIP de HLB y una para cada interfaz de servidor perimetral (un total de seis para los servidores)</span><span class="sxs-lookup"><span data-stu-id="da3b5-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="da3b5-213">Para el servicio perimetral de Access y el servicio perimetral de conferencias web, (y uso de NAT en la HLB) el cliente se conecta a la dirección VIP, la VIP cambia la dirección IP de origen del cliente a su propia dirección IP.</span><span class="sxs-lookup"><span data-stu-id="da3b5-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="da3b5-214">La interfaz de servidor dirige la dirección de remite a la dirección VIP, la VIP cambia la dirección de origen de la dirección IP de la interfaz del servidor y envía el paquete al cliente.</span><span class="sxs-lookup"><span data-stu-id="da3b5-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="da3b5-215">Para el servicio perimetral A/V, la dirección VIP no debe cambiar la dirección IP de origen, y la dirección del servidor real se devuelve directamente al cliente; no puede configurar NAT en el HLB para el tráfico audiovisual</span><span class="sxs-lookup"><span data-stu-id="da3b5-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="da3b5-216">Si el cliente envía una solicitud a la dirección VIP de HLB, la respuesta debe regresar a la HLB VIP</span><span class="sxs-lookup"><span data-stu-id="da3b5-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="da3b5-217">Si el cliente envía una solicitud a la IP de borde, la respuesta debe devolverse a la IP de borde.</span><span class="sxs-lookup"><span data-stu-id="da3b5-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="da3b5-218">Para AV, el firewall externo retendrá la dirección IP pública real del servidor para todos los paquetes</span><span class="sxs-lookup"><span data-stu-id="da3b5-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="da3b5-219">Una vez que se haya establecido, la comunicación entre el cliente y el servicio perimetral a/V es al servidor real, no a la HLB</span><span class="sxs-lookup"><span data-stu-id="da3b5-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="da3b5-220">El borde interno de los servidores internos y los clientes debe enrutarse y se establecen rutas persistentes para todas las redes internas que hospedan servidores o clientes.</span><span class="sxs-lookup"><span data-stu-id="da3b5-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="da3b5-221">La dirección VIP del servicio perimetral de acceso de HLB actuará como puerta de enlace predeterminada para cada interfaz de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="da3b5-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="da3b5-222">Para obtener más información sobre el planeamiento y la funcionalidad de NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos del equilibrador de carga de hardware para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="da3b5-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="da3b5-223">![Detalles de los puertos y protocolos del servidor perimetral] (images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalles de los puertos y protocolos del servidor perimetral")</span><span class="sxs-lookup"><span data-stu-id="da3b5-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="da3b5-224">Configuración de puertos externos necesaria para el perímetro consolidado con escala, equilibrio de carga de hardware: IPs virtual de interfaz externa</span><span class="sxs-lookup"><span data-stu-id="da3b5-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da3b5-225">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="da3b5-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da3b5-226">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="da3b5-226">Source IP address</span></span></th>
<th><span data-ttu-id="da3b5-227">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="da3b5-227">Destination IP address</span></span></th>
<th><span data-ttu-id="da3b5-228">Notas</span><span class="sxs-lookup"><span data-stu-id="da3b5-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="da3b5-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="da3b5-230">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-230">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-231">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="da3b5-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-232">El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="da3b5-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="da3b5-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="da3b5-234">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="da3b5-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-235">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-235">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-236">El servicio Proxy XMPP envía tráfico a los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="da3b5-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-237">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-238">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-238">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-239">Dirección VIP pública de servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="da3b5-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-240">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="da3b5-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-241">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da3b5-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da3b5-242">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-242">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-243">Dirección VIP pública de servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="da3b5-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-244">Señalización SIP, Federación y conectividad de mensajería instantánea pública con SIP</span><span class="sxs-lookup"><span data-stu-id="da3b5-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-245">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da3b5-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da3b5-246">Dirección VIP pública de servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="da3b5-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-247">Socio federado</span><span class="sxs-lookup"><span data-stu-id="da3b5-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="da3b5-248">Señalización SIP, Federación y conectividad de mensajería instantánea pública con SIP</span><span class="sxs-lookup"><span data-stu-id="da3b5-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-249">Conferencias web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-250">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-250">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-251">Dirección VIP pública del servicio perimetral de conferencias web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-252">Medios de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="da3b5-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da3b5-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da3b5-254">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-254">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-255">Dirección VIP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-256">STUN/TURN negociación de candidatos a través de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da3b5-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-258">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-258">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-259">Dirección VIP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="da3b5-260">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="da3b5-261">Resumen del firewall para la tecnología perimetral consolidada con escala, equilibrio de carga de hardware: interfaz IP virtual interna</span><span class="sxs-lookup"><span data-stu-id="da3b5-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da3b5-262">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="da3b5-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da3b5-263">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="da3b5-263">Source IP address</span></span></th>
<th><span data-ttu-id="da3b5-264">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="da3b5-264">Destination IP address</span></span></th>
<th><span data-ttu-id="da3b5-265">Notas</span><span class="sxs-lookup"><span data-stu-id="da3b5-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-266">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da3b5-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da3b5-267">Cualquiera (se puede definir como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="da3b5-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-268">Interfaz VIP interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-269">Tráfico SIP saliente (de Director, grupo de directores, dirección IP virtual, servidor front-end o dirección IP virtual del grupo de servidores front-end) hasta VIP interna</span><span class="sxs-lookup"><span data-stu-id="da3b5-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-270">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da3b5-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da3b5-271">Interfaz VIP interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-272">Cualquiera (se puede definir como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="da3b5-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-273">Tráfico SIP entrante (Director, grupo de directores, dirección IP virtual, servidor front-end o dirección IP virtual del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="da3b5-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="da3b5-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="da3b5-275">Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="da3b5-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="da3b5-276">Interfaz VIP interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-277">Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="da3b5-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da3b5-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da3b5-279">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-279">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-280">Interfaz VIP interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-281">Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos</span><span class="sxs-lookup"><span data-stu-id="da3b5-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da3b5-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-283">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-283">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-284">Interfaz VIP interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-285">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="da3b5-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da3b5-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da3b5-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da3b5-287">Interfaz VIP interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="da3b5-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="da3b5-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="da3b5-288">Any</span></span></p></td>
<td><p><span data-ttu-id="da3b5-289">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="da3b5-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


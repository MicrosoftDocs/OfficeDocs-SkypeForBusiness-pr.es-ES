---
title: Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware
description: Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware.
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
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564596"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="c4ba1-103">Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4ba1-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4ba1-104">_**Última modificación del tema:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="c4ba1-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="c4ba1-105">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="c4ba1-106">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="c4ba1-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="c4ba1-107">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="c4ba1-108">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="c4ba1-109">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="c4ba1-110">**Servidor perimetral consolidado ampliado con equilibrio de carga de hardware**</span><span class="sxs-lookup"><span data-stu-id="c4ba1-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="c4ba1-111">![Puertos y protocolos de red perimetral del servidor perimetral](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Puertos y protocolos de red perimetral del servidor perimetral")</span><span class="sxs-lookup"><span data-stu-id="c4ba1-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="c4ba1-112">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="c4ba1-112">Port and Protocol Details</span></span>

<span data-ttu-id="c4ba1-113">Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="c4ba1-p103">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="c4ba1-116">Resumen de Firewall para servidor perimetral consolidado escalado, carga equilibrada de hardware: interfaz externa – nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba1-117">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="c4ba1-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c4ba1-118">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="c4ba1-118">Source IP address</span></span></th>
<th><span data-ttu-id="c4ba1-119">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="c4ba1-119">Destination IP address</span></span></th>
<th><span data-ttu-id="c4ba1-120">Notas</span><span class="sxs-lookup"><span data-stu-id="c4ba1-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-121">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c4ba1-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-122">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-123">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-124">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="c4ba1-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-125">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="c4ba1-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-126">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-127">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-128">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="c4ba1-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-129">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="c4ba1-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-130">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-131">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-132">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="c4ba1-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-133">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c4ba1-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-134">Dirección IP del servicio perimetral del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="c4ba1-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-135">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-135">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-136">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-137">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c4ba1-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-138">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-139">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-140">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-141">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c4ba1-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-142">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-143">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-144">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c4ba1-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-145">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c4ba1-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-146">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-146">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-147">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-148">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c4ba1-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-149">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c4ba1-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-150">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-151">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-151">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-152">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="c4ba1-153">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-154">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c4ba1-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-155">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-155">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-156">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-157">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c4ba1-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-158">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-159">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-159">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-160">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-161">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-162">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-163">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-164">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-165">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="c4ba1-166">Resumen de Firewall para servidor perimetral consolidado escalado, carga equilibrada de hardware: nodo 1 de interfaz interna y nodo 2</span><span class="sxs-lookup"><span data-stu-id="c4ba1-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba1-167">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="c4ba1-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c4ba1-168">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="c4ba1-168">Source IP address</span></span></th>
<th><span data-ttu-id="c4ba1-169">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="c4ba1-169">Destination IP address</span></span></th>
<th><span data-ttu-id="c4ba1-170">Notas</span><span class="sxs-lookup"><span data-stu-id="c4ba1-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c4ba1-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-172">Cualquiera (puede definirse como dirección del servidor front-end o dirección IP virtual del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-173">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-174">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="c4ba1-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-176">Cualquiera (puede definirse como la IP o el grupo de servidores front-end Server que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-177">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-178">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="c4ba1-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-180">Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-181">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-182">Tráfico de conferencia web de la implementación interna a la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="c4ba1-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-183">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c4ba1-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-184">Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-185">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-186">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="c4ba1-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-187">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-188">Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-189">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-190">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="c4ba1-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c4ba1-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-192">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-192">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-193">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-194">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c4ba1-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-196">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-196">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-197">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-198">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c4ba1-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-200">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-200">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-201">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-202">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4ba1-203">Los equilibradores de carga de hardware tienen requisitos específicos cuando se implementan para proporcionar disponibilidad y equilibrio de carga para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="c4ba1-204">Los requisitos se definen en la figura y las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="c4ba1-205">Los proveedores de terceros pueden usar terminología diferente para los requisitos que se definen aquí.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="c4ba1-206">Será necesario asignar los requisitos de Lync Server a las características y opciones de configuración proporcionadas por el proveedor del equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="c4ba1-207">Al configurar equilibradores de carga de hardware, tenga en cuenta los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="c4ba1-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="c4ba1-208">La traducción de direcciones de red de origen (SNAT) se puede configurar en el equilibrador de carga de hardware (HLB) para el servicio perimetral de acceso y el servicio perimetral de conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="c4ba1-209">No se puede configurar SNAT en el servicio perimetral A/V: el servicio perimetral A/V debe responder con la dirección real del servidor, no la IP virtual (VIP) de HLB, para un recorrido sencillo de UDP sobre NAT (STUN)/Traversal mediante la NAT de retransmisión (TURN)/Federation TURN (FTURN) para que funcione correctamente</span><span class="sxs-lookup"><span data-stu-id="c4ba1-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="c4ba1-210">Si el cliente envía una solicitud a HLB, la respuesta debe volver de la dirección VIP HLB</span><span class="sxs-lookup"><span data-stu-id="c4ba1-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="c4ba1-211">Si el cliente envía una solicitud al servidor perimetral, la respuesta debe volver de la IP del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="c4ba1-212">Las direcciones IP públicas se usan en cada interfaz de servidor y en las direcciones VIP de HLB, y los requisitos de dirección IP pública son N + 1, donde hay una dirección IP pública para cada interfaz de servidor real y otra para cada VIP de HLB.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="c4ba1-213">Si tiene 2 servidores perimetrales en el grupo, se obtendrán 9 direcciones IP públicas, donde 3 se usan para los VIP de HLB y una para cada interfaz del servidor perimetral (un total de seis para los servidores)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="c4ba1-214">Para el servicio perimetral de acceso y el servicio perimetral de conferencia web (y el uso de NAT en el HLB), el cliente se pone en contacto con la VIP, la VIP cambia la dirección IP de origen del cliente a su propia dirección IP.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="c4ba1-215">La interfaz del servidor dirige la dirección de retorno a la VIP, la VIP cambia la dirección de origen de la dirección IP de la interfaz del servidor y envía el paquete al cliente.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="c4ba1-216">En el caso del servicio perimetral a/V, la VIP no debe cambiar la dirección IP de origen y la dirección del servidor real se devuelve al cliente directamente; no puede configurar NAT en el HLB para el tráfico audiovisual</span><span class="sxs-lookup"><span data-stu-id="c4ba1-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="c4ba1-217">Si el cliente envía una solicitud a la VIP de HLB, la respuesta debe volver de la VIP de HLB.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="c4ba1-218">Si el cliente envía una solicitud a la IP perimetral, la respuesta debe devolverse a la dirección IP del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="c4ba1-219">Para AV, el firewall externo mantendrá la dirección IP pública del servidor real para todos los paquetes</span><span class="sxs-lookup"><span data-stu-id="c4ba1-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="c4ba1-220">Una vez establecida, la comunicación del cliente con el servicio perimetral a/V es al servidor real, no a la HLB</span><span class="sxs-lookup"><span data-stu-id="c4ba1-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="c4ba1-221">El perímetro interno de los servidores internos y los clientes debe enrutarse, y las rutas persistentes se establecen para todas las redes internas que hospedan servidores o clientes.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="c4ba1-222">La VIP del servicio perimetral de acceso HLB funcionará como puerta de enlace predeterminada para cada interfaz del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c4ba1-223">Para obtener más información sobre la planeación y la funcionalidad de NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos del equilibrador de carga de hardware para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c4ba1-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c4ba1-224">![Detalles de protocolos y puertos del servidor perimetral](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalles de protocolos y puertos del servidor perimetral")</span><span class="sxs-lookup"><span data-stu-id="c4ba1-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="c4ba1-225">Configuración de puertos externos necesaria para servidor perimetral consolidado ampliado, carga equilibrada de hardware: IP virtuales de interfaz externa</span><span class="sxs-lookup"><span data-stu-id="c4ba1-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba1-226">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="c4ba1-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c4ba1-227">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="c4ba1-227">Source IP address</span></span></th>
<th><span data-ttu-id="c4ba1-228">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="c4ba1-228">Destination IP address</span></span></th>
<th><span data-ttu-id="c4ba1-229">Notas</span><span class="sxs-lookup"><span data-stu-id="c4ba1-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c4ba1-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-231">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-231">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-232">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-233">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="c4ba1-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c4ba1-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-235">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-236">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-236">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-237">El servicio Proxy XMPP envía tráfico a los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="c4ba1-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-238">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-239">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-239">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-240">Dirección VIP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="c4ba1-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-241">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="c4ba1-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-242">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c4ba1-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-243">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-243">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-244">Dirección VIP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="c4ba1-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-245">Señalización SIP, federada y conectividad de mensajería instantánea pública con SIP</span><span class="sxs-lookup"><span data-stu-id="c4ba1-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-246">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c4ba1-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-247">Dirección VIP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="c4ba1-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-248">Socio federado</span><span class="sxs-lookup"><span data-stu-id="c4ba1-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-249">Señalización SIP, federada y conectividad de mensajería instantánea pública con SIP</span><span class="sxs-lookup"><span data-stu-id="c4ba1-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-250">Conferencia web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-251">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-251">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-252">Dirección VIP pública del servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-253">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="c4ba1-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-254">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c4ba1-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-255">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-255">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-256">Dirección VIP pública del servicio perimetral A/V del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="c4ba1-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-257">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c4ba1-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-258">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-259">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-259">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-260">Dirección VIP pública del servicio perimetral A/V del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="c4ba1-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-261">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="c4ba1-262">Resumen de Firewall para servidor perimetral consolidado ampliado, carga equilibrada de hardware: IP virtuales de interfaz interna</span><span class="sxs-lookup"><span data-stu-id="c4ba1-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba1-263">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="c4ba1-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c4ba1-264">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="c4ba1-264">Source IP address</span></span></th>
<th><span data-ttu-id="c4ba1-265">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="c4ba1-265">Destination IP address</span></span></th>
<th><span data-ttu-id="c4ba1-266">Notas</span><span class="sxs-lookup"><span data-stu-id="c4ba1-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-267">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c4ba1-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-268">Cualquiera (puede definirse como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-269">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-270">Tráfico SIP saliente (del Director, la dirección IP virtual del grupo de directores, el servidor front-end o la dirección IP virtual del grupo de servidores front-end) a la VIP de perímetro interno</span><span class="sxs-lookup"><span data-stu-id="c4ba1-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-271">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c4ba1-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-272">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-273">Cualquiera (puede definirse como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-274">Tráfico SIP entrante (Director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="c4ba1-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-276">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="c4ba1-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-277">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-278">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-279">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c4ba1-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-280">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-280">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-281">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-282">Ruta de acceso preferida para la transferencia de multimedia de A/V entre usuarios internos y externos</span><span class="sxs-lookup"><span data-stu-id="c4ba1-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba1-283">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-284">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-284">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-285">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-286">Ruta de conmutación por recuperación para transferencia de multimedia de A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorios</span><span class="sxs-lookup"><span data-stu-id="c4ba1-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba1-287">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c4ba1-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-288">Interfaz VIP interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4ba1-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-289">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="c4ba1-289">Any</span></span></p></td>
<td><p><span data-ttu-id="c4ba1-290">Ruta de conmutación por recuperación para transferencia de multimedia de A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorios</span><span class="sxs-lookup"><span data-stu-id="c4ba1-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


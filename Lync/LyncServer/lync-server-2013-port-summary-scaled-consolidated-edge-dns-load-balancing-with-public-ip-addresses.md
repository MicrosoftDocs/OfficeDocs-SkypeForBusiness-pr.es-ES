---
title: 'Lync Server 2013: Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas'
description: 'Lync Server 2013: Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8090435485b4b6a183702a608b139cec91ae26a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563926"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="3ec32-103">Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ec32-103">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ec32-104">_**Última modificación del tema:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="3ec32-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="3ec32-105">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3ec32-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="3ec32-106">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="3ec32-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="3ec32-107">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="3ec32-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="3ec32-108">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="3ec32-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="3ec32-109">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="3ec32-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="3ec32-110">**Red perimetral empresarial para servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas**</span><span class="sxs-lookup"><span data-stu-id="3ec32-110">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="3ec32-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="3ec32-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3ec32-112">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="3ec32-112">Port and Protocol Details</span></span>

<span data-ttu-id="3ec32-113">Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.</span><span class="sxs-lookup"><span data-stu-id="3ec32-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="3ec32-p103">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.</span><span class="sxs-lookup"><span data-stu-id="3ec32-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="3ec32-116">Resumen de Firewall para servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas: interfaz externa – nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="3ec32-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ec32-117">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ec32-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ec32-118">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="3ec32-118">Source IP address</span></span></th>
<th><span data-ttu-id="3ec32-119">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="3ec32-119">Destination IP address</span></span></th>
<th><span data-ttu-id="3ec32-120">Notas</span><span class="sxs-lookup"><span data-stu-id="3ec32-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3ec32-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3ec32-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-122">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-123">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="3ec32-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3ec32-124">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="3ec32-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-125">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3ec32-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3ec32-126">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-127">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-128">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="3ec32-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-129">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="3ec32-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="3ec32-130">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-131">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-132">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="3ec32-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-133">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="3ec32-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="3ec32-134">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-135">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-135">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-136">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="3ec32-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-137">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3ec32-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-138">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-139">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-140">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="3ec32-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-141">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ec32-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ec32-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-142">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-143">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-144">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="3ec32-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-145">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ec32-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ec32-146">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-147">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-148">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="3ec32-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-149">Conferencia web/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-149">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3ec32-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-150">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-151">Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-152">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="3ec32-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3ec32-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3ec32-154">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-154">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-155">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-155">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-156">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ec32-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3ec32-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3ec32-158">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-159">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-159">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-160">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3ec32-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3ec32-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3ec32-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-162">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-163">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-164">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3ec32-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3ec32-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3ec32-166">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-166">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-167">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-168">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3ec32-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ec32-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3ec32-170">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-171">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-172">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="3ec32-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="3ec32-173">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="3ec32-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ec32-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3ec32-175">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-175">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-176">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-177">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ec32-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3ec32-179">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-179">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-180">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-181">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3ec32-183">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3ec32-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-184">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-185">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="3ec32-186">Resumen de firewall para topología perimetral consolidada escalada, equilibrio de carga DNS con direcciones IP públicas: interfaz interna – Nodo 1 y Nodo 2 (Ejemplo)</span><span class="sxs-lookup"><span data-stu-id="3ec32-186">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ec32-187">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ec32-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ec32-188">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="3ec32-188">Source IP address</span></span></th>
<th><span data-ttu-id="3ec32-189">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="3ec32-189">Destination IP address</span></span></th>
<th><span data-ttu-id="3ec32-190">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ec32-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3ec32-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3ec32-192">Cualquiera (puede definirse como dirección del servidor front-end o dirección IP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="3ec32-192">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="3ec32-193">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-194">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="3ec32-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ec32-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ec32-196">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="3ec32-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3ec32-197">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-198">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ec32-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ec32-200">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-201">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="3ec32-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3ec32-202">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="3ec32-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="3ec32-204">Cualquiera (puede definirse como una dirección IP de servidor front-end o cada dirección IP de servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="3ec32-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="3ec32-205">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-206">Tráfico de conferencia web desde el servidor front-end o cada servidor front-end si en un grupo de servidores, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="3ec32-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="3ec32-208">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="3ec32-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="3ec32-209">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-210">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ec32-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3ec32-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-212">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-213">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-214">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="3ec32-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3ec32-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-216">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-217">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-218">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="3ec32-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3ec32-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3ec32-220">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo de servidores que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="3ec32-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="3ec32-221">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-222">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3ec32-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3ec32-224">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-224">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-225">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-226">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="3ec32-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3ec32-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3ec32-228">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-228">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-229">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-230">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="3ec32-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3ec32-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3ec32-232">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-232">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-233">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3ec32-234">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="3ec32-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="3ec32-235">Resumen del firewall para federación</span><span class="sxs-lookup"><span data-stu-id="3ec32-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ec32-236">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ec32-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ec32-237">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="3ec32-237">Source IP address</span></span></th>
<th><span data-ttu-id="3ec32-238">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="3ec32-238">Destination IP address</span></span></th>
<th><span data-ttu-id="3ec32-239">Notas</span><span class="sxs-lookup"><span data-stu-id="3ec32-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-240">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ec32-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ec32-241">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="3ec32-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-242">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-242">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-243">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="3ec32-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3ec32-244">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="3ec32-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ec32-245">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ec32-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ec32-246">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="3ec32-246">Source IP address</span></span></th>
<th><span data-ttu-id="3ec32-247">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="3ec32-247">Destination IP address</span></span></th>
<th><span data-ttu-id="3ec32-248">Notas</span><span class="sxs-lookup"><span data-stu-id="3ec32-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-249">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ec32-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ec32-250">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="3ec32-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3ec32-251">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3ec32-252">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="3ec32-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-253">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ec32-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ec32-254">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3ec32-255">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="3ec32-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3ec32-256">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="3ec32-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-257">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ec32-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3ec32-258">Clientes</span><span class="sxs-lookup"><span data-stu-id="3ec32-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="3ec32-259">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3ec32-260">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="3ec32-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3ec32-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3ec32-262">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3ec32-263">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ec32-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3ec32-264">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="3ec32-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ec32-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3ec32-266">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3ec32-267">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ec32-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3ec32-268">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ec32-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ec32-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3ec32-270">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ec32-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3ec32-271">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3ec32-272">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ec32-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="3ec32-273">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="3ec32-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ec32-274">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ec32-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ec32-275">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="3ec32-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="3ec32-276">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="3ec32-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3ec32-277">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ec32-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3ec32-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3ec32-279">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-279">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-280">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-281">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3ec32-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3ec32-282">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="3ec32-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec32-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3ec32-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3ec32-284">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3ec32-285">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-285">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-286">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3ec32-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3ec32-287">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="3ec32-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec32-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3ec32-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3ec32-289">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ec32-289">Any</span></span></p></td>
<td><p><span data-ttu-id="3ec32-290">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="3ec32-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="3ec32-291">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end a la dirección IP interna del servidor perimetral o la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="3ec32-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


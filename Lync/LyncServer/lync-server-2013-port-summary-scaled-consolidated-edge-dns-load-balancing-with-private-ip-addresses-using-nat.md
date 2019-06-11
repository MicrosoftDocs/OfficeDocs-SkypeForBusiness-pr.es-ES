---
title: 'Lync Server 2013: Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="e1db2-102">Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1db2-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1db2-103">_**Última modificación del tema:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="e1db2-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="e1db2-104">La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e1db2-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="e1db2-105">La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="e1db2-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="e1db2-106">Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="e1db2-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="e1db2-107">Además de IPv4, el servidor EDGE ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="e1db2-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="e1db2-108">Para mayor claridad, solo se usa IPv4 en los escenarios.</span><span class="sxs-lookup"><span data-stu-id="e1db2-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="e1db2-109">**Red perimetral empresarial para el perímetro consolidado con direcciones IP privadas mediante NAT**</span><span class="sxs-lookup"><span data-stu-id="e1db2-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="e1db2-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead] (images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="e1db2-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e1db2-111">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="e1db2-111">Port and Protocol Details</span></span>

<span data-ttu-id="e1db2-112">Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="e1db2-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="e1db2-113">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="e1db2-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="e1db2-114">En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.</span><span class="sxs-lookup"><span data-stu-id="e1db2-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="e1db2-115">Resumen de Firewall para Edge consolidado, equilibrio de carga de DNS con direcciones IP privadas mediante NAT: interfaz externa-nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="e1db2-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1db2-116">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="e1db2-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e1db2-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="e1db2-117">Source IP address</span></span></th>
<th><span data-ttu-id="e1db2-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="e1db2-118">Destination IP address</span></span></th>
<th><span data-ttu-id="e1db2-119">Notas</span><span class="sxs-lookup"><span data-stu-id="e1db2-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e1db2-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e1db2-121">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-121">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-122">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="e1db2-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-123">El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="e1db2-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e1db2-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e1db2-125">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="e1db2-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-126">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-127">El servicio Proxy XMPP envía tráfico a los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="e1db2-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e1db2-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e1db2-129">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-130">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-131">Comprobación y recuperación de CRL o revocación de certificados</span><span class="sxs-lookup"><span data-stu-id="e1db2-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-132">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="e1db2-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="e1db2-133">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-135">Consulta DNS a través de TCP</span><span class="sxs-lookup"><span data-stu-id="e1db2-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-136">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="e1db2-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="e1db2-137">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-138">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-139">Consulta DNS a través de UDP</span><span class="sxs-lookup"><span data-stu-id="e1db2-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-140">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e1db2-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-141">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-142">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-143">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="e1db2-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-144">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e1db2-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e1db2-145">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-145">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-146">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-147">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="e1db2-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-148">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e1db2-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e1db2-149">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-150">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-151">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="e1db2-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-152">Conferencias web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e1db2-153">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-153">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-154">Servicio perimetral de conferencias web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-155">Medios de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="e1db2-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-156">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="e1db2-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e1db2-157">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-158">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-159">Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1db2-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-160">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="e1db2-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e1db2-161">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-162">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-163">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e1db2-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-164">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="e1db2-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e1db2-165">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-165">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-166">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-167">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e1db2-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-168">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="e1db2-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e1db2-169">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-169">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-170">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-171">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e1db2-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e1db2-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e1db2-173">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-174">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-175">3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e1db2-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="e1db2-176">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="e1db2-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e1db2-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e1db2-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-178">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-179">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-180">STUN/TURN negociación de candidatos a través de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e1db2-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e1db2-182">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-182">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-183">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-184">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e1db2-186">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-187">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-187">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-188">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="e1db2-189">Resumen de Firewall para Edge consolidado con escala, equilibrio de carga de DNS con direcciones IP privadas mediante NAT: interfaz interna-nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="e1db2-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1db2-190">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="e1db2-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e1db2-191">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="e1db2-191">Source IP address</span></span></th>
<th><span data-ttu-id="e1db2-192">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="e1db2-192">Destination IP address</span></span></th>
<th><span data-ttu-id="e1db2-193">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1db2-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e1db2-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e1db2-195">Cualquiera (se puede definir como la dirección del servidor front-end o la dirección IP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="e1db2-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-196">Dirección IP de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e1db2-197">Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="e1db2-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e1db2-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e1db2-199">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="e1db2-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-200">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-201">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e1db2-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e1db2-203">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-204">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="e1db2-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-205">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="e1db2-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="e1db2-207">Cualquiera (se puede definir como la dirección IP del servidor front-end o cada dirección IP del servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="e1db2-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-208">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-209">Tráfico de conferencias web desde el servidor front-end o cada servidor front-end si se está en un grupo, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="e1db2-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="e1db2-211">Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="e1db2-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-212">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-213">Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="e1db2-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e1db2-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e1db2-215">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-215">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-216">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-217">Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="e1db2-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e1db2-219">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-219">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-220">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-221">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="e1db2-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e1db2-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e1db2-223">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="e1db2-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="e1db2-224">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-225">Replicación de los cambios del almacén de administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e1db2-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e1db2-227">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-227">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-228">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-229">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="e1db2-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e1db2-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e1db2-231">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-231">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-232">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-233">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="e1db2-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e1db2-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e1db2-235">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-235">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-236">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e1db2-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e1db2-237">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="e1db2-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="e1db2-238">Resumen del firewall para la Federación</span><span class="sxs-lookup"><span data-stu-id="e1db2-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1db2-239">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="e1db2-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e1db2-240">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="e1db2-240">Source IP address</span></span></th>
<th><span data-ttu-id="e1db2-241">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="e1db2-241">Destination IP address</span></span></th>
<th><span data-ttu-id="e1db2-242">Notas</span><span class="sxs-lookup"><span data-stu-id="e1db2-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-243">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e1db2-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e1db2-244">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="e1db2-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e1db2-245">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-245">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-246">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="e1db2-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e1db2-247">Resumen del firewall: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="e1db2-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1db2-248">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="e1db2-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e1db2-249">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="e1db2-249">Source IP address</span></span></th>
<th><span data-ttu-id="e1db2-250">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="e1db2-250">Destination IP address</span></span></th>
<th><span data-ttu-id="e1db2-251">Notas</span><span class="sxs-lookup"><span data-stu-id="e1db2-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-252">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e1db2-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e1db2-253">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="e1db2-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e1db2-254">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-255">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="e1db2-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-256">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e1db2-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e1db2-257">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-258">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="e1db2-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e1db2-259">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="e1db2-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-260">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e1db2-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e1db2-261">Clientes</span><span class="sxs-lookup"><span data-stu-id="e1db2-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="e1db2-262">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-263">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="e1db2-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-264">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="e1db2-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e1db2-265">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-266">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e1db2-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e1db2-267">Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="e1db2-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e1db2-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e1db2-269">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-270">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e1db2-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e1db2-271">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e1db2-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e1db2-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e1db2-273">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e1db2-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e1db2-274">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e1db2-275">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e1db2-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e1db2-276">Resumen de Firewall para el protocolo de presencia y mensajería extensible</span><span class="sxs-lookup"><span data-stu-id="e1db2-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1db2-277">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="e1db2-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e1db2-278">Origen (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="e1db2-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="e1db2-279">Destino (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="e1db2-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e1db2-280">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1db2-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e1db2-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e1db2-282">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-282">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-283">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e1db2-284">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="e1db2-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e1db2-285">Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</span><span class="sxs-lookup"><span data-stu-id="e1db2-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1db2-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e1db2-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e1db2-287">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e1db2-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-288">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-289">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="e1db2-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e1db2-290">Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</span><span class="sxs-lookup"><span data-stu-id="e1db2-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1db2-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e1db2-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e1db2-292">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e1db2-292">Any</span></span></p></td>
<td><p><span data-ttu-id="e1db2-293">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="e1db2-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="e1db2-294">Tráfico de XMPP interno de la puerta de enlace XMPP en el servidor front-end o grupo front-end a la dirección IP interna del servidor perimetral o a la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="e1db2-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


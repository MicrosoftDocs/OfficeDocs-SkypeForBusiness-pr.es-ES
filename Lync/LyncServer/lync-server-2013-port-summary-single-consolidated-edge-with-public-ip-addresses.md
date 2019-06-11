---
title: Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="d3422-102">Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3422-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3422-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d3422-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d3422-104">La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d3422-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="d3422-105">La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="d3422-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="d3422-106">Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="d3422-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d3422-107">La información de planeación del proxy inverso y la Federación se encuentra en [escenarios de inverso de proxy en Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) , así como en la [planeación de la Federación de SIP, la Federación de XMPP y la mensajería instantánea pública en las secciones de Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d3422-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="d3422-108">Además de IPv4, el servidor EDGE ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="d3422-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="d3422-109">Para mayor claridad, solo se usa IPv4 en los escenarios.</span><span class="sxs-lookup"><span data-stu-id="d3422-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="d3422-110">**Red perimetral empresarial para un solo borde consolidado con direccionamiento IP público**</span><span class="sxs-lookup"><span data-stu-id="d3422-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="d3422-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847] (images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="d3422-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="d3422-112">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="d3422-112">Port and Protocol Details</span></span>

<span data-ttu-id="d3422-113">Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="d3422-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="d3422-114">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="d3422-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="d3422-115">En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.</span><span class="sxs-lookup"><span data-stu-id="d3422-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="d3422-116">Resumen del firewall para un solo borde consolidado con direcciones IP públicas: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="d3422-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3422-117">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="d3422-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d3422-118">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d3422-118">Source IP address</span></span></th>
<th><span data-ttu-id="d3422-119">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d3422-119">Destination IP address</span></span></th>
<th><span data-ttu-id="d3422-120">Notas</span><span class="sxs-lookup"><span data-stu-id="d3422-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3422-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d3422-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d3422-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-122">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-123">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="d3422-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="d3422-124">El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="d3422-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="d3422-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="d3422-126">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-127">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-128">Comprobación y recuperación de CRL o revocación de certificados</span><span class="sxs-lookup"><span data-stu-id="d3422-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-129">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="d3422-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="d3422-130">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-131">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-132">Consulta DNS a través de TCP</span><span class="sxs-lookup"><span data-stu-id="d3422-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-133">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="d3422-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="d3422-134">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-135">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-135">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-136">Consulta DNS a través de UDP</span><span class="sxs-lookup"><span data-stu-id="d3422-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-137">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d3422-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-138">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-139">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-140">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="d3422-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-141">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d3422-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d3422-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-142">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-143">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-144">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="d3422-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-145">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d3422-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d3422-146">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-147">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-148">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="d3422-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-149">Conferencias web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d3422-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-150">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-151">Dirección IP pública del servicio perimetral de conferencias web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-152">Medios de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="d3422-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-153">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="d3422-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d3422-154">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-155">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-155">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-156">Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3422-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-157">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="d3422-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d3422-158">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-159">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-159">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-160">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="d3422-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-161">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="d3422-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d3422-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-162">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-163">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-164">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="d3422-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-165">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="d3422-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d3422-166">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-166">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-167">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-168">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="d3422-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d3422-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d3422-170">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-171">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-172">3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="d3422-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="d3422-173">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="d3422-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d3422-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d3422-175">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-175">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-176">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-177">STUN/TURN negociación de candidatos a través de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d3422-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d3422-179">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-179">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-180">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-181">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d3422-183">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-184">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-185">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="d3422-186">Resumen del firewall para un solo borde consolidado con direcciones IP públicas: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="d3422-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3422-187">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="d3422-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d3422-188">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d3422-188">Source IP address</span></span></th>
<th><span data-ttu-id="d3422-189">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d3422-189">Destination IP address</span></span></th>
<th><span data-ttu-id="d3422-190">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3422-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3422-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d3422-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d3422-192">Cualquiera (puede definirse como IP de servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="d3422-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="d3422-193">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-194">Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="d3422-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d3422-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d3422-196">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="d3422-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d3422-197">IP del servidor perimetral o grupo que contiene la interfaz interna</span><span class="sxs-lookup"><span data-stu-id="d3422-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-198">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d3422-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d3422-200">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-201">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección de grupo frontal)</span><span class="sxs-lookup"><span data-stu-id="d3422-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="d3422-202">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="d3422-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="d3422-204">Cualquiera (se puede definir como la dirección IP del servidor front-end o cada dirección IP del servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="d3422-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="d3422-205">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-206">Tráfico de conferencias web desde el servidor front-end o cada servidor front-end si se está en un grupo, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="d3422-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="d3422-208">Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="d3422-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="d3422-209">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-210">Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="d3422-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d3422-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d3422-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-212">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-213">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-214">Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="d3422-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d3422-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-216">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-217">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-218">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="d3422-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="d3422-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="d3422-220">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="d3422-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="d3422-221">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-222">Replicación de los cambios del almacén de administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="d3422-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="d3422-224">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-224">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-225">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-226">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="d3422-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="d3422-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="d3422-228">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-228">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-229">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-230">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="d3422-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="d3422-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="d3422-232">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-232">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-233">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="d3422-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d3422-234">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="d3422-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="d3422-235">Resumen del firewall para la Federación</span><span class="sxs-lookup"><span data-stu-id="d3422-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3422-236">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="d3422-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d3422-237">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d3422-237">Source IP address</span></span></th>
<th><span data-ttu-id="d3422-238">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d3422-238">Destination IP address</span></span></th>
<th><span data-ttu-id="d3422-239">Notas</span><span class="sxs-lookup"><span data-stu-id="d3422-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3422-240">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d3422-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d3422-241">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="d3422-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-242">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-242">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-243">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="d3422-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="d3422-244">Resumen del firewall: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="d3422-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3422-245">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="d3422-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d3422-246">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d3422-246">Source IP address</span></span></th>
<th><span data-ttu-id="d3422-247">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d3422-247">Destination IP address</span></span></th>
<th><span data-ttu-id="d3422-248">Notas</span><span class="sxs-lookup"><span data-stu-id="d3422-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3422-249">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d3422-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d3422-250">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="d3422-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d3422-251">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d3422-252">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="d3422-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-253">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d3422-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d3422-254">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d3422-255">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="d3422-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d3422-256">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="d3422-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-257">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d3422-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d3422-258">Clientes</span><span class="sxs-lookup"><span data-stu-id="d3422-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="d3422-259">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d3422-260">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="d3422-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-261">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="d3422-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d3422-262">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d3422-263">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d3422-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d3422-264">Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="d3422-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d3422-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d3422-266">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d3422-267">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d3422-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d3422-268">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d3422-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d3422-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d3422-270">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d3422-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d3422-271">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d3422-272">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d3422-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d3422-273">Resumen de Firewall para el protocolo de presencia y mensajería extensible</span><span class="sxs-lookup"><span data-stu-id="d3422-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3422-274">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="d3422-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d3422-275">Origen (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="d3422-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="d3422-276">Destino (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="d3422-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="d3422-277">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3422-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3422-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d3422-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d3422-279">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-279">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-280">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-281">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="d3422-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d3422-282">Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</span><span class="sxs-lookup"><span data-stu-id="d3422-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3422-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d3422-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d3422-284">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d3422-285">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-285">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-286">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="d3422-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d3422-287">Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</span><span class="sxs-lookup"><span data-stu-id="d3422-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3422-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d3422-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d3422-289">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3422-289">Any</span></span></p></td>
<td><p><span data-ttu-id="d3422-290">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="d3422-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="d3422-291">Tráfico de XMPP interno de la puerta de enlace XMPP en el servidor front-end o grupo front-end a la dirección IP interna del servidor perimetral o a la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="d3422-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


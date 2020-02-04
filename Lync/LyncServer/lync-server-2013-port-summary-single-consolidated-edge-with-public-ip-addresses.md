---
title: Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ad4d6dc9b7eda2e476068d5fae4a40d066a0d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="55746-102">Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55746-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55746-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="55746-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="55746-104">La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="55746-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="55746-105">La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="55746-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="55746-106">Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="55746-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="55746-107">La información de planeación del proxy inverso y la Federación se encuentra en [escenarios de inverso de proxy en Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) , así como en la [planeación de la Federación de SIP, la Federación de XMPP y la mensajería instantánea pública en las secciones de Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="55746-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="55746-108">Además de IPv4, el servidor EDGE ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="55746-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="55746-109">Para mayor claridad, solo se usa IPv4 en los escenarios.</span><span class="sxs-lookup"><span data-stu-id="55746-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="55746-110">**Red perimetral empresarial para un solo borde consolidado con direccionamiento IP público**</span><span class="sxs-lookup"><span data-stu-id="55746-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="55746-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="55746-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="55746-112">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="55746-112">Port and Protocol Details</span></span>

<span data-ttu-id="55746-113">Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="55746-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="55746-114">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="55746-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="55746-115">En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.</span><span class="sxs-lookup"><span data-stu-id="55746-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="55746-116">Resumen del firewall para un solo borde consolidado con direcciones IP públicas: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="55746-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55746-117">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="55746-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55746-118">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="55746-118">Source IP address</span></span></th>
<th><span data-ttu-id="55746-119">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="55746-119">Destination IP address</span></span></th>
<th><span data-ttu-id="55746-120">Notas</span><span class="sxs-lookup"><span data-stu-id="55746-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55746-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="55746-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="55746-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-122">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-123">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="55746-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="55746-124">El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="55746-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="55746-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="55746-126">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-127">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-128">Comprobación y recuperación de CRL o revocación de certificados</span><span class="sxs-lookup"><span data-stu-id="55746-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-129">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="55746-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="55746-130">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-131">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-132">Consulta DNS a través de TCP</span><span class="sxs-lookup"><span data-stu-id="55746-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-133">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="55746-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="55746-134">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-135">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-135">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-136">Consulta DNS a través de UDP</span><span class="sxs-lookup"><span data-stu-id="55746-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-137">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55746-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-138">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-139">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-140">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="55746-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-141">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55746-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55746-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-142">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-143">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-144">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="55746-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-145">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55746-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55746-146">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-147">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-148">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="55746-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-149">Conferencias web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55746-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-150">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-151">Dirección IP pública del servicio perimetral de conferencias web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-152">Medios de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="55746-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-153">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="55746-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55746-154">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-155">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-155">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-156">Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55746-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-157">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="55746-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55746-158">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-159">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-159">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-160">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="55746-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-161">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="55746-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55746-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-162">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-163">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-164">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="55746-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-165">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="55746-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55746-166">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-166">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-167">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-168">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="55746-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55746-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55746-170">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-171">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-172">3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="55746-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="55746-173">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="55746-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55746-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55746-175">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-175">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-176">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-177">STUN/TURN negociación de candidatos a través de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55746-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55746-179">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-179">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-180">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-181">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55746-183">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-184">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-185">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="55746-186">Resumen del firewall para un solo borde consolidado con direcciones IP públicas: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="55746-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55746-187">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="55746-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55746-188">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="55746-188">Source IP address</span></span></th>
<th><span data-ttu-id="55746-189">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="55746-189">Destination IP address</span></span></th>
<th><span data-ttu-id="55746-190">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55746-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55746-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="55746-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="55746-192">Cualquiera (puede definirse como IP de servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="55746-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="55746-193">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-194">Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="55746-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55746-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55746-196">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="55746-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="55746-197">IP del servidor perimetral o grupo que contiene la interfaz interna</span><span class="sxs-lookup"><span data-stu-id="55746-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-198">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55746-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55746-200">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-201">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección de grupo frontal)</span><span class="sxs-lookup"><span data-stu-id="55746-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="55746-202">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="55746-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="55746-204">Cualquiera (se puede definir como la dirección IP del servidor front-end o cada dirección IP del servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="55746-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="55746-205">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-206">Tráfico de conferencias web desde el servidor front-end o cada servidor front-end si se está en un grupo, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="55746-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="55746-208">Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="55746-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="55746-209">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-210">Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="55746-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55746-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55746-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-212">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-213">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-214">Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="55746-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55746-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-216">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-217">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-218">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="55746-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="55746-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="55746-220">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="55746-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="55746-221">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-222">Replicación de los cambios del almacén de administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="55746-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="55746-224">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-224">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-225">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-226">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="55746-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="55746-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="55746-228">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-228">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-229">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-230">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="55746-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="55746-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="55746-232">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-232">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-233">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="55746-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55746-234">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="55746-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="55746-235">Resumen del firewall para la Federación</span><span class="sxs-lookup"><span data-stu-id="55746-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55746-236">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="55746-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55746-237">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="55746-237">Source IP address</span></span></th>
<th><span data-ttu-id="55746-238">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="55746-238">Destination IP address</span></span></th>
<th><span data-ttu-id="55746-239">Notas</span><span class="sxs-lookup"><span data-stu-id="55746-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55746-240">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55746-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55746-241">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="55746-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-242">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-242">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-243">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="55746-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="55746-244">Resumen del firewall: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="55746-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55746-245">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="55746-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55746-246">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="55746-246">Source IP address</span></span></th>
<th><span data-ttu-id="55746-247">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="55746-247">Destination IP address</span></span></th>
<th><span data-ttu-id="55746-248">Notas</span><span class="sxs-lookup"><span data-stu-id="55746-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55746-249">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55746-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55746-250">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="55746-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="55746-251">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="55746-252">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="55746-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-253">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55746-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55746-254">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="55746-255">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="55746-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="55746-256">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="55746-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-257">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55746-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55746-258">Clientes</span><span class="sxs-lookup"><span data-stu-id="55746-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="55746-259">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="55746-260">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="55746-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-261">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="55746-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55746-262">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="55746-263">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="55746-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="55746-264">Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="55746-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55746-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55746-266">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="55746-267">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="55746-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="55746-268">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="55746-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55746-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55746-270">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="55746-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="55746-271">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="55746-272">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="55746-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="55746-273">Resumen de Firewall para el protocolo de presencia y mensajería extensible</span><span class="sxs-lookup"><span data-stu-id="55746-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55746-274">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="55746-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55746-275">Origen (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="55746-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="55746-276">Destino (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="55746-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="55746-277">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55746-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55746-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="55746-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="55746-279">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-279">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-280">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-281">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="55746-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="55746-282">Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</span><span class="sxs-lookup"><span data-stu-id="55746-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55746-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="55746-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="55746-284">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="55746-285">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-285">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-286">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="55746-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="55746-287">Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</span><span class="sxs-lookup"><span data-stu-id="55746-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55746-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="55746-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="55746-289">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="55746-289">Any</span></span></p></td>
<td><p><span data-ttu-id="55746-290">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="55746-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="55746-291">Tráfico de XMPP interno de la puerta de enlace XMPP en el servidor front-end o grupo front-end a la dirección IP interna del servidor perimetral o a la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="55746-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


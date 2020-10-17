---
title: Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas
description: Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas.
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
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566406"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="081a9-103">Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="081a9-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="081a9-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="081a9-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="081a9-105">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="081a9-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="081a9-106">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="081a9-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="081a9-107">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="081a9-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="081a9-108">La información de planeación para el proxy inverso y la Federación se encuentra en [escenarios de proxy inverso en Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) y [planeación de SIP, Federación de XMPP y mensajería instantánea pública en las secciones de Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="081a9-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="081a9-109">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="081a9-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="081a9-110">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="081a9-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="081a9-111">**Red perimetral empresarial para un solo servidor perimetral consolidado con direccionamiento IP público**</span><span class="sxs-lookup"><span data-stu-id="081a9-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="081a9-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="081a9-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="081a9-113">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="081a9-113">Port and Protocol Details</span></span>

<span data-ttu-id="081a9-114">Se recomienda abrir únicamente los puertos necesarios para admitir la funcionalidad para la que se proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="081a9-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="081a9-115">Para acceso remoto que funcione con cualquier servicio perimetral, es obligatorio permitir que el tráfico SIP fluya en ambas direcciones, tal como se muestra en la figura Tráfico perimetral entrante/saliente.</span><span class="sxs-lookup"><span data-stu-id="081a9-115">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="081a9-116">Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.</span><span class="sxs-lookup"><span data-stu-id="081a9-116">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="081a9-117">Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP públicas: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="081a9-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="081a9-118">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="081a9-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="081a9-119">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="081a9-119">Source IP address</span></span></th>
<th><span data-ttu-id="081a9-120">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="081a9-120">Destination IP address</span></span></th>
<th><span data-ttu-id="081a9-121">Notas</span><span class="sxs-lookup"><span data-stu-id="081a9-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="081a9-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="081a9-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="081a9-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-123">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-124">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="081a9-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="081a9-125">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="081a9-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-126">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="081a9-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="081a9-127">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-128">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-128">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-129">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="081a9-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-130">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="081a9-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="081a9-131">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-132">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-133">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="081a9-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-134">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="081a9-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="081a9-135">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-136">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-136">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-137">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="081a9-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-138">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="081a9-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-139">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-140">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-141">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="081a9-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-142">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="081a9-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="081a9-143">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-143">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-144">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-145">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="081a9-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-146">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="081a9-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="081a9-147">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-148">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-149">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="081a9-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-150">Conferencia web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="081a9-151">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-151">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-152">Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-153">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="081a9-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-154">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="081a9-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="081a9-155">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-156">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-156">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-157">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="081a9-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-158">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="081a9-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="081a9-159">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-160">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-160">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-161">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="081a9-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-162">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="081a9-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="081a9-163">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-163">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-164">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-165">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="081a9-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-166">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="081a9-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="081a9-167">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-167">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-168">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-169">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="081a9-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-170">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="081a9-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="081a9-171">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-172">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-172">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-173">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="081a9-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="081a9-174">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="081a9-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-175">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="081a9-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="081a9-176">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-176">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-177">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-178">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="081a9-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-179">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="081a9-180">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-180">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-181">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-182">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-183">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="081a9-184">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-185">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-185">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-186">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="081a9-187">Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP públicas: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="081a9-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="081a9-188">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="081a9-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="081a9-189">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="081a9-189">Source IP address</span></span></th>
<th><span data-ttu-id="081a9-190">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="081a9-190">Destination IP address</span></span></th>
<th><span data-ttu-id="081a9-191">Comentarios</span><span class="sxs-lookup"><span data-stu-id="081a9-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="081a9-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="081a9-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="081a9-193">Cualquiera (puede definirse como IP del servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="081a9-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="081a9-194">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-195">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="081a9-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="081a9-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="081a9-197">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="081a9-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="081a9-198">IP del servidor perimetral o grupo de servidores que contiene la interfaz interna</span><span class="sxs-lookup"><span data-stu-id="081a9-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-199">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="081a9-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="081a9-201">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-202">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección de grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="081a9-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="081a9-203">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="081a9-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="081a9-205">Cualquiera (puede definirse como una dirección IP de servidor front-end o cada dirección IP de servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="081a9-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="081a9-206">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-207">Tráfico de conferencia web desde el servidor front-end o cada servidor front-end si en un grupo de servidores, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="081a9-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="081a9-209">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="081a9-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="081a9-210">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-211">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="081a9-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="081a9-213">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-213">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-214">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-215">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="081a9-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="081a9-217">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-217">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-218">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-219">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="081a9-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="081a9-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="081a9-221">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo de servidores que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="081a9-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="081a9-222">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-223">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="081a9-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="081a9-225">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-225">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-226">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-227">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="081a9-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="081a9-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="081a9-229">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-229">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-230">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-231">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="081a9-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="081a9-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="081a9-233">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-233">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-234">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="081a9-235">Controlador del servicio de registro centralizado con el shell de administración de Lync Server y los cmdlets del servicio de registro centralizado, la línea de comandos de ClsController (ClsController.exe) o los comandos y la colección de registros del agente (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="081a9-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="081a9-236">Resumen del firewall para federación</span><span class="sxs-lookup"><span data-stu-id="081a9-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="081a9-237">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="081a9-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="081a9-238">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="081a9-238">Source IP address</span></span></th>
<th><span data-ttu-id="081a9-239">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="081a9-239">Destination IP address</span></span></th>
<th><span data-ttu-id="081a9-240">Notas</span><span class="sxs-lookup"><span data-stu-id="081a9-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="081a9-241">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="081a9-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="081a9-242">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="081a9-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-243">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-243">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-244">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="081a9-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="081a9-245">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="081a9-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="081a9-246">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="081a9-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="081a9-247">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="081a9-247">Source IP address</span></span></th>
<th><span data-ttu-id="081a9-248">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="081a9-248">Destination IP address</span></span></th>
<th><span data-ttu-id="081a9-249">Notas</span><span class="sxs-lookup"><span data-stu-id="081a9-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="081a9-250">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="081a9-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="081a9-251">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="081a9-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="081a9-252">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="081a9-253">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="081a9-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-254">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="081a9-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="081a9-255">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="081a9-256">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="081a9-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="081a9-257">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="081a9-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-258">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="081a9-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="081a9-259">Clientes</span><span class="sxs-lookup"><span data-stu-id="081a9-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="081a9-260">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="081a9-261">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="081a9-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-262">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="081a9-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="081a9-263">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="081a9-264">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="081a9-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="081a9-265">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="081a9-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-266">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="081a9-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="081a9-267">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="081a9-268">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="081a9-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="081a9-269">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="081a9-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-270">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="081a9-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="081a9-271">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="081a9-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="081a9-272">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="081a9-273">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="081a9-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="081a9-274">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="081a9-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="081a9-275">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="081a9-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="081a9-276">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="081a9-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="081a9-277">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="081a9-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="081a9-278">Comentarios</span><span class="sxs-lookup"><span data-stu-id="081a9-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="081a9-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="081a9-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="081a9-280">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-280">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-281">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-282">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="081a9-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="081a9-283">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="081a9-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081a9-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="081a9-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="081a9-285">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="081a9-286">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-286">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-287">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="081a9-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="081a9-288">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="081a9-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="081a9-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="081a9-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="081a9-290">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="081a9-290">Any</span></span></p></td>
<td><p><span data-ttu-id="081a9-291">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="081a9-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="081a9-292">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end a la dirección IP interna del servidor perimetral o la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="081a9-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


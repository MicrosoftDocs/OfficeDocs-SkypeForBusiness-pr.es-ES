---
title: Resumen de puerto - Perímetro consolidado de un solo equipo con direcciones IP privadas mediante NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a425a07bf5ff615fb4766d50f21c6467512d110e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="8fe9d-102">Resumen de puerto - Perímetro consolidado de un solo equipo con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fe9d-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fe9d-103">_**Última modificación del tema:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="8fe9d-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="8fe9d-104">La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="8fe9d-105">La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="8fe9d-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="8fe9d-106">Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="8fe9d-107">Además de IPv4, el servidor EDGE ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="8fe9d-108">Para mayor claridad, solo se usa IPv4 en los escenarios.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="8fe9d-109">**Perímetro de red para un único servidor consolidado con direccionamiento IP privado con NAT**</span><span class="sxs-lookup"><span data-stu-id="8fe9d-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="8fe9d-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="8fe9d-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="8fe9d-111">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="8fe9d-111">Port and Protocol Details</span></span>

<span data-ttu-id="8fe9d-112">Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="8fe9d-113">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="8fe9d-114">En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="8fe9d-115">Resumen del firewall para un solo borde consolidado con direcciones IP privadas que usan NAT: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="8fe9d-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fe9d-116">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="8fe9d-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8fe9d-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="8fe9d-117">Source IP address</span></span></th>
<th><span data-ttu-id="8fe9d-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="8fe9d-118">Destination IP address</span></span></th>
<th><span data-ttu-id="8fe9d-119">Notas</span><span class="sxs-lookup"><span data-stu-id="8fe9d-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8fe9d-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-121">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-121">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-122">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-123">El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="8fe9d-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="8fe9d-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-125">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-126">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-127">Comprobación y recuperación de CRL o revocación de certificados</span><span class="sxs-lookup"><span data-stu-id="8fe9d-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-128">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="8fe9d-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-129">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-130">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-131">Consulta DNS a través de TCP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-132">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="8fe9d-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-133">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-134">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-135">Consulta DNS a través de UDP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-136">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-137">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-137">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-138">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-139">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="8fe9d-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-140">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8fe9d-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-141">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-142">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-143">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-144">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8fe9d-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-145">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-146">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-146">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-147">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-148">Conferencias web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-149">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-150">Servicio perimetral de conferencias web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-151">Medios de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="8fe9d-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-152">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="8fe9d-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-153">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-154">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-155">Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-156">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="8fe9d-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-157">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-158">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-159">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-160">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="8fe9d-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-161">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-161">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-162">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-163">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8fe9d-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-164">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="8fe9d-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-165">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-165">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-166">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-167">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8fe9d-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8fe9d-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-169">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-170">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-171">3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="8fe9d-172">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8fe9d-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-174">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-175">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-176">STUN/TURN negociación de candidatos a través de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8fe9d-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-178">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-179">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-180">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-182">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-183">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-183">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-184">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="8fe9d-185">Resumen del firewall para un solo borde consolidado con direcciones IP privadas que usan NAT: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="8fe9d-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fe9d-186">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="8fe9d-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8fe9d-187">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="8fe9d-187">Source IP address</span></span></th>
<th><span data-ttu-id="8fe9d-188">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="8fe9d-188">Destination IP address</span></span></th>
<th><span data-ttu-id="8fe9d-189">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fe9d-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8fe9d-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-191">Cualquiera (puede definirse como IP de servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-192">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-193">Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="8fe9d-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8fe9d-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-195">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-196">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-197">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8fe9d-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-199">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-200">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-201">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="8fe9d-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-203">Cualquiera (se puede definir como la dirección IP del servidor front-end o cada dirección IP del servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-204">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-205">Tráfico de conferencias web desde el servidor front-end o cada servidor front-end si se está en un grupo, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="8fe9d-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-207">Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-208">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-209">Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="8fe9d-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8fe9d-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-211">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-211">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-212">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-213">Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="8fe9d-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-215">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-215">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-216">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-217">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="8fe9d-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-219">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-220">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-221">Replicación de los cambios del almacén de administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8fe9d-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-223">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-223">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-224">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-225">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="8fe9d-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8fe9d-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-227">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-227">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-228">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-229">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="8fe9d-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8fe9d-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-231">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-231">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-232">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="8fe9d-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-233">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="8fe9d-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="8fe9d-234">Resumen del firewall para la Federación</span><span class="sxs-lookup"><span data-stu-id="8fe9d-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fe9d-235">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="8fe9d-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8fe9d-236">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="8fe9d-236">Source IP address</span></span></th>
<th><span data-ttu-id="8fe9d-237">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="8fe9d-237">Destination IP address</span></span></th>
<th><span data-ttu-id="8fe9d-238">Notas</span><span class="sxs-lookup"><span data-stu-id="8fe9d-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-239">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8fe9d-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-240">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="8fe9d-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-241">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-241">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-242">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="8fe9d-243">Resumen del firewall: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="8fe9d-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fe9d-244">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="8fe9d-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8fe9d-245">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="8fe9d-245">Source IP address</span></span></th>
<th><span data-ttu-id="8fe9d-246">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="8fe9d-246">Destination IP address</span></span></th>
<th><span data-ttu-id="8fe9d-247">Notas</span><span class="sxs-lookup"><span data-stu-id="8fe9d-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-248">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8fe9d-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-249">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="8fe9d-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-250">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-251">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-252">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8fe9d-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-253">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-254">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="8fe9d-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-255">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-256">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8fe9d-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="8fe9d-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-258">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-259">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="8fe9d-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-260">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="8fe9d-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-261">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-262">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8fe9d-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-263">Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8fe9d-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-265">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-266">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8fe9d-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-267">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8fe9d-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8fe9d-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-269">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8fe9d-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-270">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-271">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8fe9d-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8fe9d-272">Resumen de Firewall para el protocolo de presencia y mensajería extensible</span><span class="sxs-lookup"><span data-stu-id="8fe9d-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fe9d-273">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="8fe9d-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8fe9d-274">Origen (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="8fe9d-275">Destino (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="8fe9d-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="8fe9d-276">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fe9d-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8fe9d-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-278">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-278">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-279">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-280">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8fe9d-281">Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</span><span class="sxs-lookup"><span data-stu-id="8fe9d-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe9d-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8fe9d-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-283">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-284">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-284">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-285">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="8fe9d-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8fe9d-286">Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</span><span class="sxs-lookup"><span data-stu-id="8fe9d-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe9d-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8fe9d-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8fe9d-288">Any</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-289">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="8fe9d-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="8fe9d-290">Tráfico de XMPP interno de la puerta de enlace XMPP en el servidor front-end o grupo front-end a la dirección IP interna del servidor perimetral o a la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="8fe9d-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


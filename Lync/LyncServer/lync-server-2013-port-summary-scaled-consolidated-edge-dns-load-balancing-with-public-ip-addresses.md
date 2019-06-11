---
title: 'Lync Server 2013: Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2095df7ebd68265d135a8b174ce2d1d3ae76ca5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="b749e-102">Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b749e-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b749e-103">_**Última modificación del tema:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="b749e-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="b749e-104">La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b749e-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b749e-105">La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="b749e-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b749e-106">Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="b749e-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="b749e-107">Además de IPv4, el servidor EDGE ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="b749e-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b749e-108">Para mayor claridad, solo se usa IPv4 en los escenarios.</span><span class="sxs-lookup"><span data-stu-id="b749e-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b749e-109">**Red perimetral empresarial para la tecnología perimetral consolidada, equilibrio de carga DNS con direcciones IP públicas**</span><span class="sxs-lookup"><span data-stu-id="b749e-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="b749e-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead] (images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="b749e-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b749e-111">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="b749e-111">Port and Protocol Details</span></span>

<span data-ttu-id="b749e-112">Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="b749e-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b749e-113">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="b749e-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="b749e-114">En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.</span><span class="sxs-lookup"><span data-stu-id="b749e-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="b749e-115">Resumen del firewall para la tecnología perimetral consolidada, equilibrio de carga DNS con direcciones IP públicas: interfaz externa-nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="b749e-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b749e-116">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="b749e-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b749e-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="b749e-117">Source IP address</span></span></th>
<th><span data-ttu-id="b749e-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="b749e-118">Destination IP address</span></span></th>
<th><span data-ttu-id="b749e-119">Notas</span><span class="sxs-lookup"><span data-stu-id="b749e-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b749e-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b749e-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b749e-121">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-121">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-122">Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="b749e-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b749e-123">El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="b749e-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b749e-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b749e-125">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-126">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-127">Comprobación y recuperación de CRL o revocación de certificados</span><span class="sxs-lookup"><span data-stu-id="b749e-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-128">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b749e-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b749e-129">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-130">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-131">Consulta DNS a través de TCP</span><span class="sxs-lookup"><span data-stu-id="b749e-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-132">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b749e-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b749e-133">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-134">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-135">Consulta DNS a través de UDP</span><span class="sxs-lookup"><span data-stu-id="b749e-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-136">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b749e-137">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-137">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-138">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-139">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="b749e-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-140">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b749e-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b749e-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-141">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-142">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-143">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="b749e-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-144">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b749e-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b749e-145">Dirección IP pública del servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-146">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-146">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-147">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="b749e-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-148">Conferencias web/PSOM (TLS) TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b749e-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-149">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-150">Dirección IP pública del servicio perimetral de conferencias web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-151">Medios de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="b749e-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-152">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="b749e-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b749e-153">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-154">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-155">Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b749e-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-156">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="b749e-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b749e-157">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-158">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-159">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="b749e-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-160">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="b749e-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b749e-161">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-161">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-162">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-163">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="b749e-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-164">A/V/RTP/UDP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="b749e-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b749e-165">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-165">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-166">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-167">Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="b749e-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b749e-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b749e-169">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-170">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-171">3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b749e-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b749e-172">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="b749e-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b749e-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b749e-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-174">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-175">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-176">STUN/TURN negociación de candidatos a través de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b749e-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b749e-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-178">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-179">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-180">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b749e-182">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b749e-183">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-183">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-184">STUN/TURN negociación de candidatos por TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="b749e-185">Resumen del firewall para la tecnología perimetral consolidada, equilibrio de carga DNS con direcciones IP públicas: interfaz interna – nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="b749e-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b749e-186">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="b749e-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b749e-187">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="b749e-187">Source IP address</span></span></th>
<th><span data-ttu-id="b749e-188">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="b749e-188">Destination IP address</span></span></th>
<th><span data-ttu-id="b749e-189">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b749e-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b749e-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b749e-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b749e-191">Cualquiera (se puede definir como la dirección del servidor front-end o la dirección IP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="b749e-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b749e-192">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-193">Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="b749e-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b749e-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b749e-195">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="b749e-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b749e-196">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-197">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b749e-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b749e-199">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-200">Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="b749e-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b749e-201">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b749e-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b749e-203">Cualquiera (se puede definir como la dirección IP del servidor front-end o cada dirección IP del servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="b749e-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b749e-204">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-205">Tráfico de conferencias web desde el servidor front-end o cada servidor front-end si se está en un grupo, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b749e-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b749e-207">Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="b749e-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b749e-208">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-209">Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="b749e-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b749e-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b749e-211">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-211">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-212">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-213">Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="b749e-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b749e-215">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-215">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-216">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-217">Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="b749e-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b749e-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b749e-219">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="b749e-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b749e-220">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-221">Replicación de los cambios del almacén de administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b749e-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b749e-223">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-223">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-224">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-225">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="b749e-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b749e-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b749e-227">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-227">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-228">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-229">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="b749e-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b749e-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b749e-231">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-231">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-232">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="b749e-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b749e-233">Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</span><span class="sxs-lookup"><span data-stu-id="b749e-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b749e-234">Resumen del firewall para la Federación</span><span class="sxs-lookup"><span data-stu-id="b749e-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b749e-235">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="b749e-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b749e-236">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="b749e-236">Source IP address</span></span></th>
<th><span data-ttu-id="b749e-237">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="b749e-237">Destination IP address</span></span></th>
<th><span data-ttu-id="b749e-238">Notas</span><span class="sxs-lookup"><span data-stu-id="b749e-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b749e-239">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b749e-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b749e-240">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="b749e-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-241">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-241">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-242">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="b749e-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b749e-243">Resumen del firewall: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="b749e-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b749e-244">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="b749e-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b749e-245">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="b749e-245">Source IP address</span></span></th>
<th><span data-ttu-id="b749e-246">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="b749e-246">Destination IP address</span></span></th>
<th><span data-ttu-id="b749e-247">Notas</span><span class="sxs-lookup"><span data-stu-id="b749e-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b749e-248">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b749e-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b749e-249">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="b749e-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b749e-250">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b749e-251">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="b749e-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-252">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b749e-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b749e-253">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b749e-254">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="b749e-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b749e-255">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="b749e-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-256">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b749e-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b749e-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="b749e-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="b749e-258">Servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b749e-259">Tráfico SIP de cliente a servidor para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="b749e-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-260">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="b749e-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b749e-261">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b749e-262">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b749e-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b749e-263">Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="b749e-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b749e-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b749e-265">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b749e-266">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b749e-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b749e-267">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b749e-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b749e-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b749e-269">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b749e-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b749e-270">Servidor perimetral A/V servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b749e-271">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b749e-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b749e-272">Resumen de Firewall para el protocolo de presencia y mensajería extensible</span><span class="sxs-lookup"><span data-stu-id="b749e-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b749e-273">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="b749e-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b749e-274">Origen (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="b749e-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="b749e-275">Destino (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="b749e-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b749e-276">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b749e-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b749e-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b749e-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b749e-278">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-278">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-279">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-280">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="b749e-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b749e-281">Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</span><span class="sxs-lookup"><span data-stu-id="b749e-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b749e-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b749e-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b749e-283">Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b749e-284">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-284">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-285">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="b749e-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b749e-286">Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</span><span class="sxs-lookup"><span data-stu-id="b749e-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b749e-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b749e-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b749e-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b749e-288">Any</span></span></p></td>
<td><p><span data-ttu-id="b749e-289">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="b749e-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="b749e-290">Tráfico de XMPP interno de la puerta de enlace XMPP en el servidor front-end o grupo front-end a la dirección IP interna del servidor perimetral o a la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="b749e-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


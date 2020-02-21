---
title: 'Lync Server 2013: Resumen de puertos-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c26dfe63e468d7b8d6f4ae557c0b84af2ffceaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="4c85b-102">Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c85b-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c85b-103">_**Última modificación del tema:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="4c85b-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="4c85b-104">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4c85b-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="4c85b-105">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="4c85b-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="4c85b-106">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4c85b-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="4c85b-107">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="4c85b-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="4c85b-108">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="4c85b-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="4c85b-109">**Red perimetral empresarial para servidor perimetral consolidado escalado con direcciones IP privadas mediante NAT**</span><span class="sxs-lookup"><span data-stu-id="4c85b-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="4c85b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="4c85b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="4c85b-111">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="4c85b-111">Port and Protocol Details</span></span>

<span data-ttu-id="4c85b-112">Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.</span><span class="sxs-lookup"><span data-stu-id="4c85b-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="4c85b-p103">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.</span><span class="sxs-lookup"><span data-stu-id="4c85b-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="4c85b-115">Resumen de Firewall para servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT: interfaz externa – nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="4c85b-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c85b-116">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="4c85b-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4c85b-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="4c85b-117">Source IP address</span></span></th>
<th><span data-ttu-id="4c85b-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="4c85b-118">Destination IP address</span></span></th>
<th><span data-ttu-id="4c85b-119">Notas</span><span class="sxs-lookup"><span data-stu-id="4c85b-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4c85b-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4c85b-121">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-121">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-122">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="4c85b-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-123">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="4c85b-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4c85b-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4c85b-125">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="4c85b-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-127">El servicio Proxy XMPP envía tráfico a los contactos XMPP en las federaciones XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="4c85b-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-128">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="4c85b-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="4c85b-129">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-130">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-131">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="4c85b-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-132">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="4c85b-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="4c85b-133">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-135">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="4c85b-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-136">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="4c85b-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="4c85b-137">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-139">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="4c85b-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-140">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4c85b-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-142">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-143">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="4c85b-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-144">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4c85b-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4c85b-145">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-145">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-146">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-147">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="4c85b-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-148">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4c85b-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4c85b-149">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-150">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-151">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="4c85b-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-152">Conferencia web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4c85b-153">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-153">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-154">Servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-155">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="4c85b-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-156">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="4c85b-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4c85b-157">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-159">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c85b-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-160">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="4c85b-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4c85b-161">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-162">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-163">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="4c85b-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-164">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="4c85b-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4c85b-165">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-165">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-166">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-167">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="4c85b-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-168">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="4c85b-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4c85b-169">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-169">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-170">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-171">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="4c85b-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4c85b-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4c85b-173">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-175">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="4c85b-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="4c85b-176">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="4c85b-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4c85b-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4c85b-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-179">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-180">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4c85b-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4c85b-182">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-182">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-183">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-184">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4c85b-186">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-187">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-187">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-188">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="4c85b-189">Resumen de Firewall para servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT: interfaz interna – nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="4c85b-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c85b-190">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="4c85b-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4c85b-191">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="4c85b-191">Source IP address</span></span></th>
<th><span data-ttu-id="4c85b-192">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="4c85b-192">Destination IP address</span></span></th>
<th><span data-ttu-id="4c85b-193">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c85b-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4c85b-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4c85b-195">Cualquiera (puede definirse como dirección del servidor front-end o dirección IP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="4c85b-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-196">Dirección IP de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4c85b-197">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="4c85b-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4c85b-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4c85b-199">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="4c85b-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-200">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-201">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4c85b-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4c85b-203">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-204">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="4c85b-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-205">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="4c85b-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="4c85b-207">Cualquiera (puede definirse como una dirección IP de servidor front-end o cada dirección IP de servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="4c85b-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-208">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-209">Tráfico de conferencia web desde el servidor front-end o cada servidor front-end si en un grupo de servidores, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="4c85b-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="4c85b-211">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="4c85b-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-212">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-213">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4c85b-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4c85b-215">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-215">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-216">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-217">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="4c85b-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4c85b-219">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-219">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-220">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-221">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="4c85b-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="4c85b-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="4c85b-223">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo de servidores que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="4c85b-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="4c85b-224">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-225">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="4c85b-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="4c85b-227">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-227">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-228">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-229">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="4c85b-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="4c85b-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="4c85b-231">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-231">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-232">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-233">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="4c85b-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="4c85b-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="4c85b-235">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-235">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-236">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c85b-237">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="4c85b-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="4c85b-238">Resumen del firewall para federación</span><span class="sxs-lookup"><span data-stu-id="4c85b-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c85b-239">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="4c85b-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4c85b-240">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="4c85b-240">Source IP address</span></span></th>
<th><span data-ttu-id="4c85b-241">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="4c85b-241">Destination IP address</span></span></th>
<th><span data-ttu-id="4c85b-242">Notas</span><span class="sxs-lookup"><span data-stu-id="4c85b-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-243">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4c85b-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4c85b-244">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="4c85b-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4c85b-245">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-245">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-246">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="4c85b-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="4c85b-247">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="4c85b-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c85b-248">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="4c85b-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4c85b-249">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="4c85b-249">Source IP address</span></span></th>
<th><span data-ttu-id="4c85b-250">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="4c85b-250">Destination IP address</span></span></th>
<th><span data-ttu-id="4c85b-251">Notas</span><span class="sxs-lookup"><span data-stu-id="4c85b-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-252">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4c85b-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4c85b-253">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="4c85b-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4c85b-254">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-255">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="4c85b-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-256">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4c85b-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4c85b-257">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-258">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="4c85b-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4c85b-259">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="4c85b-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-260">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4c85b-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4c85b-261">Clientes</span><span class="sxs-lookup"><span data-stu-id="4c85b-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="4c85b-262">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-263">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="4c85b-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-264">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="4c85b-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4c85b-265">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-266">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4c85b-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4c85b-267">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="4c85b-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4c85b-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4c85b-269">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-270">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4c85b-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4c85b-271">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4c85b-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4c85b-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4c85b-273">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4c85b-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4c85b-274">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4c85b-275">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4c85b-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4c85b-276">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="4c85b-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c85b-277">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="4c85b-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4c85b-278">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="4c85b-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="4c85b-279">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="4c85b-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="4c85b-280">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c85b-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4c85b-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4c85b-282">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-282">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-283">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4c85b-284">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="4c85b-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4c85b-285">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="4c85b-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c85b-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4c85b-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4c85b-287">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4c85b-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-288">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-289">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="4c85b-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4c85b-290">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="4c85b-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c85b-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4c85b-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4c85b-292">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4c85b-292">Any</span></span></p></td>
<td><p><span data-ttu-id="4c85b-293">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="4c85b-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="4c85b-294">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end a la dirección IP interna del servidor perimetral o la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="4c85b-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


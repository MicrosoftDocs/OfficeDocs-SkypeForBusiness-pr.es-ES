---
title: 'Lync Server 2013: Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas'
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
ms.openlocfilehash: 0a2bbae2168362e8591b4dcdb765ae0d4cca85b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="d65aa-102">Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d65aa-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d65aa-103">_**Última modificación del tema:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="d65aa-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="d65aa-104">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d65aa-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="d65aa-105">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="d65aa-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="d65aa-106">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d65aa-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="d65aa-107">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="d65aa-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="d65aa-108">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="d65aa-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="d65aa-109">**Red perimetral empresarial para servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas**</span><span class="sxs-lookup"><span data-stu-id="d65aa-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="d65aa-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="d65aa-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="d65aa-111">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="d65aa-111">Port and Protocol Details</span></span>

<span data-ttu-id="d65aa-112">Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.</span><span class="sxs-lookup"><span data-stu-id="d65aa-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="d65aa-p103">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.</span><span class="sxs-lookup"><span data-stu-id="d65aa-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="d65aa-115">Resumen de Firewall para servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas: interfaz externa – nodo 1 y nodo 2 (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="d65aa-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d65aa-116">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="d65aa-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d65aa-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d65aa-117">Source IP address</span></span></th>
<th><span data-ttu-id="d65aa-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d65aa-118">Destination IP address</span></span></th>
<th><span data-ttu-id="d65aa-119">Notas</span><span class="sxs-lookup"><span data-stu-id="d65aa-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d65aa-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d65aa-121">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-121">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-122">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="d65aa-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="d65aa-123">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="d65aa-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-124">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="d65aa-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="d65aa-125">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-126">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-127">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="d65aa-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-128">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="d65aa-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="d65aa-129">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-130">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-131">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="d65aa-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-132">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="d65aa-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="d65aa-133">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-134">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-135">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="d65aa-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-136">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d65aa-137">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-137">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-138">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-139">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="d65aa-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-140">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d65aa-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d65aa-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-141">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-142">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-143">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="d65aa-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-144">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d65aa-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d65aa-145">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-146">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-146">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-147">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="d65aa-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-148">Conferencia web/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d65aa-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-149">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-150">Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-151">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="d65aa-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d65aa-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d65aa-153">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-154">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-155">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d65aa-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d65aa-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d65aa-157">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-158">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-159">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="d65aa-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d65aa-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d65aa-161">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-161">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-162">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-163">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="d65aa-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d65aa-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d65aa-165">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-165">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-166">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-167">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="d65aa-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d65aa-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d65aa-169">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-170">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-171">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="d65aa-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="d65aa-172">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="d65aa-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d65aa-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d65aa-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-174">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-175">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-176">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d65aa-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d65aa-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-178">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-179">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-180">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d65aa-182">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d65aa-183">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-183">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-184">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="d65aa-185">Resumen de firewall para topología perimetral consolidada escalada, equilibrio de carga DNS con direcciones IP públicas: interfaz interna – Nodo 1 y Nodo 2 (Ejemplo)</span><span class="sxs-lookup"><span data-stu-id="d65aa-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d65aa-186">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="d65aa-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d65aa-187">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d65aa-187">Source IP address</span></span></th>
<th><span data-ttu-id="d65aa-188">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d65aa-188">Destination IP address</span></span></th>
<th><span data-ttu-id="d65aa-189">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d65aa-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d65aa-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d65aa-191">Cualquiera (puede definirse como dirección del servidor front-end o dirección IP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="d65aa-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="d65aa-192">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-193">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="d65aa-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d65aa-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d65aa-195">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="d65aa-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d65aa-196">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-197">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d65aa-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d65aa-199">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-200">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="d65aa-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d65aa-201">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="d65aa-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="d65aa-203">Cualquiera (puede definirse como una dirección IP de servidor front-end o cada dirección IP de servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="d65aa-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="d65aa-204">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-205">Tráfico de conferencia web desde el servidor front-end o cada servidor front-end si en un grupo de servidores, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="d65aa-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="d65aa-207">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="d65aa-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="d65aa-208">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-209">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d65aa-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d65aa-211">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-211">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-212">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-213">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="d65aa-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d65aa-215">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-215">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-216">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-217">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="d65aa-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="d65aa-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="d65aa-219">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo de servidores que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="d65aa-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="d65aa-220">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-221">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="d65aa-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="d65aa-223">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-223">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-224">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-225">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="d65aa-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="d65aa-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="d65aa-227">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-227">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-228">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-229">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="d65aa-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="d65aa-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="d65aa-231">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-231">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-232">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d65aa-233">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="d65aa-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="d65aa-234">Resumen del firewall para federación</span><span class="sxs-lookup"><span data-stu-id="d65aa-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d65aa-235">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="d65aa-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d65aa-236">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d65aa-236">Source IP address</span></span></th>
<th><span data-ttu-id="d65aa-237">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d65aa-237">Destination IP address</span></span></th>
<th><span data-ttu-id="d65aa-238">Notas</span><span class="sxs-lookup"><span data-stu-id="d65aa-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-239">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d65aa-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d65aa-240">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="d65aa-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-241">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-241">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-242">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="d65aa-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="d65aa-243">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="d65aa-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d65aa-244">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="d65aa-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d65aa-245">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="d65aa-245">Source IP address</span></span></th>
<th><span data-ttu-id="d65aa-246">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="d65aa-246">Destination IP address</span></span></th>
<th><span data-ttu-id="d65aa-247">Notas</span><span class="sxs-lookup"><span data-stu-id="d65aa-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-248">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d65aa-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d65aa-249">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="d65aa-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d65aa-250">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d65aa-251">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="d65aa-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-252">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d65aa-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d65aa-253">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d65aa-254">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="d65aa-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d65aa-255">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="d65aa-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-256">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d65aa-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d65aa-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="d65aa-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="d65aa-258">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d65aa-259">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="d65aa-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d65aa-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d65aa-261">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d65aa-262">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d65aa-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d65aa-263">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="d65aa-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d65aa-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d65aa-265">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d65aa-266">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d65aa-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d65aa-267">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d65aa-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d65aa-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d65aa-269">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d65aa-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d65aa-270">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d65aa-271">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d65aa-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d65aa-272">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="d65aa-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d65aa-273">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="d65aa-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d65aa-274">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="d65aa-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="d65aa-275">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="d65aa-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="d65aa-276">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d65aa-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d65aa-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d65aa-278">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-278">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-279">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-280">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="d65aa-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d65aa-281">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="d65aa-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65aa-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d65aa-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d65aa-283">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d65aa-284">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-284">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-285">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="d65aa-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d65aa-286">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="d65aa-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65aa-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d65aa-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d65aa-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d65aa-288">Any</span></span></p></td>
<td><p><span data-ttu-id="d65aa-289">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="d65aa-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="d65aa-290">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end a la dirección IP interna del servidor perimetral o la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="d65aa-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


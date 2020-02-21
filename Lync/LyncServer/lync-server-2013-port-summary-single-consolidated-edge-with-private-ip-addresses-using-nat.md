---
title: Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP privadas con NAT
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
ms.openlocfilehash: 870732df847d589ebb24751977babc8182d79a3f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="cf567-102">Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf567-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf567-103">_**Última modificación del tema:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="cf567-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="cf567-104">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cf567-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="cf567-105">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="cf567-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="cf567-106">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="cf567-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="cf567-107">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="cf567-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="cf567-108">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="cf567-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="cf567-109">**Perímetro de red de un solo servidor perimetral consolidado con direccionamiento IP privado mediante NAT**</span><span class="sxs-lookup"><span data-stu-id="cf567-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="cf567-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="cf567-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="cf567-111">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="cf567-111">Port and Protocol Details</span></span>

<span data-ttu-id="cf567-112">Se recomienda abrir únicamente los puertos necesarios para admitir la funcionalidad para la que se proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="cf567-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="cf567-113">Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente.</span><span class="sxs-lookup"><span data-stu-id="cf567-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="cf567-114">En otra forma, los mensajes SIP hacia y desde el servicio perimetral de acceso están relacionados con la mensajería instantánea (mi), la presencia, la conferencia Web, el audio/vídeo (A/V) y la Federación.</span><span class="sxs-lookup"><span data-stu-id="cf567-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="cf567-115">Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP privadas mediante NAT: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="cf567-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf567-116">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="cf567-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf567-117">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="cf567-117">Source IP address</span></span></th>
<th><span data-ttu-id="cf567-118">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="cf567-118">Destination IP address</span></span></th>
<th><span data-ttu-id="cf567-119">Notas</span><span class="sxs-lookup"><span data-stu-id="cf567-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf567-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf567-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf567-121">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-121">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-122">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="cf567-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="cf567-123">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="cf567-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-124">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="cf567-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="cf567-125">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-126">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-127">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="cf567-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-128">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="cf567-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="cf567-129">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-130">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-130">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-131">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="cf567-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-132">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="cf567-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="cf567-133">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-134">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-135">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="cf567-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-136">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf567-137">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-137">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-138">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-139">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="cf567-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-140">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf567-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf567-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-141">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-142">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-143">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="cf567-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-144">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf567-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf567-145">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-146">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-146">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-147">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="cf567-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-148">Conferencia web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf567-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-149">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-150">Servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-151">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="cf567-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="cf567-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf567-153">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-154">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-155">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf567-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="cf567-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf567-157">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-158">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-159">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="cf567-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="cf567-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf567-161">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-161">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-162">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-163">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="cf567-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="cf567-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf567-165">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-165">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-166">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-167">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="cf567-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf567-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf567-169">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-170">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-171">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="cf567-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="cf567-172">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="cf567-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf567-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf567-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-174">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-175">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-176">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf567-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf567-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-178">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-179">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-180">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf567-182">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-183">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-183">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-184">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="cf567-185">Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP privadas mediante NAT: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="cf567-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf567-186">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="cf567-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf567-187">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="cf567-187">Source IP address</span></span></th>
<th><span data-ttu-id="cf567-188">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="cf567-188">Destination IP address</span></span></th>
<th><span data-ttu-id="cf567-189">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf567-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf567-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="cf567-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="cf567-191">Cualquiera (puede definirse como IP del servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="cf567-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="cf567-192">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-193">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="cf567-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf567-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf567-195">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="cf567-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="cf567-196">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-197">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf567-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf567-199">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-200">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="cf567-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="cf567-201">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="cf567-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="cf567-203">Cualquiera (puede definirse como una dirección IP de servidor front-end o cada dirección IP de servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="cf567-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="cf567-204">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-205">Tráfico de conferencia web desde el servidor front-end o cada servidor front-end si en un grupo de servidores, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="cf567-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="cf567-207">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="cf567-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="cf567-208">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-209">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf567-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf567-211">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-211">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-212">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-213">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="cf567-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf567-215">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-215">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-216">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-217">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="cf567-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="cf567-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="cf567-219">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo de servidores que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="cf567-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="cf567-220">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-221">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="cf567-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="cf567-223">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-223">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-224">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-225">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="cf567-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="cf567-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="cf567-227">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-227">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-228">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-229">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="cf567-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="cf567-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="cf567-231">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-231">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-232">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf567-233">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="cf567-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="cf567-234">Resumen del firewall para federación</span><span class="sxs-lookup"><span data-stu-id="cf567-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf567-235">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="cf567-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf567-236">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="cf567-236">Source IP address</span></span></th>
<th><span data-ttu-id="cf567-237">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="cf567-237">Destination IP address</span></span></th>
<th><span data-ttu-id="cf567-238">Notas</span><span class="sxs-lookup"><span data-stu-id="cf567-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf567-239">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf567-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf567-240">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="cf567-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf567-241">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-241">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-242">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="cf567-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="cf567-243">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="cf567-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf567-244">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="cf567-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf567-245">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="cf567-245">Source IP address</span></span></th>
<th><span data-ttu-id="cf567-246">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="cf567-246">Destination IP address</span></span></th>
<th><span data-ttu-id="cf567-247">Notas</span><span class="sxs-lookup"><span data-stu-id="cf567-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf567-248">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf567-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf567-249">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="cf567-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cf567-250">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-251">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="cf567-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-252">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf567-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf567-253">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-254">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="cf567-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cf567-255">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="cf567-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-256">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf567-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf567-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="cf567-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="cf567-258">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-259">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="cf567-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="cf567-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf567-261">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-262">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="cf567-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf567-263">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="cf567-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf567-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf567-265">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-266">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="cf567-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf567-267">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="cf567-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf567-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf567-269">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="cf567-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf567-270">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf567-271">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="cf567-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="cf567-272">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="cf567-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf567-273">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="cf567-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf567-274">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="cf567-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="cf567-275">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="cf567-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="cf567-276">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf567-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf567-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf567-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf567-278">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-278">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-279">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cf567-280">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="cf567-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cf567-281">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="cf567-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf567-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf567-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf567-283">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cf567-284">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-284">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-285">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="cf567-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cf567-286">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="cf567-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf567-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="cf567-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="cf567-288">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cf567-288">Any</span></span></p></td>
<td><p><span data-ttu-id="cf567-289">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="cf567-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="cf567-290">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end a la dirección IP interna del servidor perimetral o la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="cf567-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


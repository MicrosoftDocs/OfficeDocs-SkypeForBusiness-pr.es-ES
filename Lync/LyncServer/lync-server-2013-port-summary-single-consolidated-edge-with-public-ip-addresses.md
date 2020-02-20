---
title: Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas
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
ms.openlocfilehash: 2c307ff7318a426610cf371a3d6f55591a7c6ed0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="dbe5f-102">Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbe5f-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbe5f-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dbe5f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dbe5f-104">La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="dbe5f-105">La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="dbe5f-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="dbe5f-106">Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="dbe5f-107">La información de planeación para el proxy inverso y la Federación se encuentra en [escenarios de proxy inverso en Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) y [planeación de SIP, Federación de XMPP y mensajería instantánea pública en las secciones de Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="dbe5f-108">Además de IPv4, el servidor perimetral ahora es compatible con IPv6.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="dbe5f-109">En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="dbe5f-110">**Red perimetral empresarial para un solo servidor perimetral consolidado con direccionamiento IP público**</span><span class="sxs-lookup"><span data-stu-id="dbe5f-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="dbe5f-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="dbe5f-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="dbe5f-112">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="dbe5f-112">Port and Protocol Details</span></span>

<span data-ttu-id="dbe5f-113">Se recomienda abrir únicamente los puertos necesarios para admitir la funcionalidad para la que se proporciona acceso externo.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="dbe5f-114">Para acceso remoto que funcione con cualquier servicio perimetral, es obligatorio permitir que el tráfico SIP fluya en ambas direcciones, tal como se muestra en la figura Tráfico perimetral entrante/saliente.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="dbe5f-115">Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="dbe5f-116">Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP públicas: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="dbe5f-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbe5f-117">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="dbe5f-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbe5f-118">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="dbe5f-118">Source IP address</span></span></th>
<th><span data-ttu-id="dbe5f-119">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="dbe5f-119">Destination IP address</span></span></th>
<th><span data-ttu-id="dbe5f-120">Notas</span><span class="sxs-lookup"><span data-stu-id="dbe5f-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="dbe5f-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-122">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-123">Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-124">El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-125">Acceso/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="dbe5f-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-126">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-127">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-128">Revocación de certificados/Comprobación y recuperación de CRL</span><span class="sxs-lookup"><span data-stu-id="dbe5f-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-129">Acceso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="dbe5f-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-130">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-131">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-132">Consulta de DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-133">Acceso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="dbe5f-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-134">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-135">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-135">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-136">Consulta de DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-137">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-138">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-139">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-140">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="dbe5f-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-141">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbe5f-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-142">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-143">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-144">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-145">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbe5f-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-146">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-147">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-148">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-149">Conferencia web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-150">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-151">Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-152">Medios de conferencia web</span><span class="sxs-lookup"><span data-stu-id="dbe5f-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbe5f-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-154">Dirección IP pública del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-155">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-155">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-156">Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbe5f-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-158">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-159">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-159">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-160">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="dbe5f-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbe5f-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-162">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-163">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-164">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbe5f-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-166">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-166">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-167">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-168">Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbe5f-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-170">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-171">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-172">3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="dbe5f-173">Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbe5f-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-175">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-175">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-176">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-177">Negociación STUN/TURN de candidatos sobre UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbe5f-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-179">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-179">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-180">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-181">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-183">Dirección IP pública del servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-184">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-185">Negociación STUN/TURN de candidatos sobre TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="dbe5f-186">Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP públicas: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="dbe5f-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbe5f-187">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="dbe5f-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbe5f-188">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="dbe5f-188">Source IP address</span></span></th>
<th><span data-ttu-id="dbe5f-189">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="dbe5f-189">Destination IP address</span></span></th>
<th><span data-ttu-id="dbe5f-190">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbe5f-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="dbe5f-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-192">Cualquiera (puede definirse como IP del servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-193">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-194">Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="dbe5f-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbe5f-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-196">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-197">IP del servidor perimetral o grupo de servidores que contiene la interfaz interna</span><span class="sxs-lookup"><span data-stu-id="dbe5f-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-198">Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbe5f-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-200">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-201">Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección de grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-202">Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end) de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="dbe5f-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-204">Cualquiera (puede definirse como una dirección IP de servidor front-end o cada dirección IP de servidor front-end en un grupo de servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-205">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-206">Tráfico de conferencia web desde el servidor front-end o cada servidor front-end si en un grupo de servidores, a la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="dbe5f-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-208">Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-209">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-210">Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbe5f-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-212">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-213">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-214">Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="dbe5f-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-216">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-217">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-218">Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="dbe5f-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-220">Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo de servidores que contiene el almacén de administración central)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-221">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-222">Replicación de los cambios del almacén de Administración central al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="dbe5f-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-224">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-224">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-225">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-226">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="dbe5f-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-228">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-228">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-229">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-230">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="dbe5f-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-232">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-232">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-233">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-234">Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="dbe5f-235">Resumen del firewall para federación</span><span class="sxs-lookup"><span data-stu-id="dbe5f-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbe5f-236">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="dbe5f-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbe5f-237">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="dbe5f-237">Source IP address</span></span></th>
<th><span data-ttu-id="dbe5f-238">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="dbe5f-238">Destination IP address</span></span></th>
<th><span data-ttu-id="dbe5f-239">Notas</span><span class="sxs-lookup"><span data-stu-id="dbe5f-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-240">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbe5f-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-241">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="dbe5f-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-242">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-242">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-243">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="dbe5f-244">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="dbe5f-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbe5f-245">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="dbe5f-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbe5f-246">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="dbe5f-246">Source IP address</span></span></th>
<th><span data-ttu-id="dbe5f-247">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="dbe5f-247">Destination IP address</span></span></th>
<th><span data-ttu-id="dbe5f-248">Notas</span><span class="sxs-lookup"><span data-stu-id="dbe5f-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-249">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbe5f-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-250">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="dbe5f-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-251">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-252">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-253">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbe5f-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-254">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-255">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="dbe5f-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-256">Para conectividad de mensajería instantánea pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="dbe5f-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-257">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbe5f-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-258">Clientes</span><span class="sxs-lookup"><span data-stu-id="dbe5f-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-259">Servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-260">Tráfico SIP de cliente a servidor para acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="dbe5f-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbe5f-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-262">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-263">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dbe5f-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-264">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbe5f-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-266">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-267">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dbe5f-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-268">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dbe5f-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbe5f-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-270">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dbe5f-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-271">Servicio perimetral A/V del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-272">Obligatorio para la conectividad de MI pública con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dbe5f-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="dbe5f-273">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="dbe5f-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbe5f-274">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="dbe5f-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbe5f-275">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="dbe5f-276">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="dbe5f-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="dbe5f-277">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbe5f-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="dbe5f-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-279">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-279">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-280">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-281">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="dbe5f-282">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe5f-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="dbe5f-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-284">Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-285">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-285">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-286">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="dbe5f-287">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="dbe5f-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe5f-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="dbe5f-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-289">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="dbe5f-289">Any</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-290">Cada IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="dbe5f-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="dbe5f-291">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end a la dirección IP interna del servidor perimetral o la dirección IP interna de cada miembro del grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="dbe5f-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


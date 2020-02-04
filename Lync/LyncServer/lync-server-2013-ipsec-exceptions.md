---
title: Excepciones IPsec de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="e4b21-102">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4b21-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4b21-103">_**Última modificación del tema:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="e4b21-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="e4b21-104">En el caso de redes empresariales en las que se ha implementado la seguridad de protocolo de Internet (consulte IETF RFC 4301-4309), debe deshabilitarse IPsec en el rango de puertos que se usan para la entrega de video de audio, vídeo y panorámica.</span><span class="sxs-lookup"><span data-stu-id="e4b21-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="e4b21-105">Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios por la negociación de IPsec.</span><span class="sxs-lookup"><span data-stu-id="e4b21-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="e4b21-106">En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.</span><span class="sxs-lookup"><span data-stu-id="e4b21-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="e4b21-107">Excepciones de IPsec recomendadas</span><span class="sxs-lookup"><span data-stu-id="e4b21-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4b21-108">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="e4b21-108">Rule name</span></span></th>
<th><span data-ttu-id="e4b21-109">IP de origen</span><span class="sxs-lookup"><span data-stu-id="e4b21-109">Source IP</span></span></th>
<th><span data-ttu-id="e4b21-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="e4b21-110">Destination IP</span></span></th>
<th><span data-ttu-id="e4b21-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="e4b21-111">Protocol</span></span></th>
<th><span data-ttu-id="e4b21-112">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="e4b21-112">Source port</span></span></th>
<th><span data-ttu-id="e4b21-113">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="e4b21-113">Destination port</span></span></th>
<th><span data-ttu-id="e4b21-114">Requisito de autenticación</span><span class="sxs-lookup"><span data-stu-id="e4b21-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-115">Servidor perimetral A/V interno entrante</span><span class="sxs-lookup"><span data-stu-id="e4b21-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-116">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-117">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="e4b21-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="e4b21-118">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-119">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-119">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-120">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-120">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-121">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b21-122">Servidor perimetral A/V externo entrante</span><span class="sxs-lookup"><span data-stu-id="e4b21-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-123">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-124">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="e4b21-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="e4b21-125">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-126">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-126">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-127">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-128">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-129">Servidor perimetral A/V interno saliente</span><span class="sxs-lookup"><span data-stu-id="e4b21-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-130">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="e4b21-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="e4b21-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="e4b21-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-133">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-133">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-135">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b21-136">Servidor perimetral A/V externo saliente</span><span class="sxs-lookup"><span data-stu-id="e4b21-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-137">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="e4b21-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="e4b21-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-138">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-139">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-140">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-140">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-141">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-142">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-143">Servidor de mediación entrante</span><span class="sxs-lookup"><span data-stu-id="e4b21-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-144">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-145">Servidores</span><span class="sxs-lookup"><span data-stu-id="e4b21-145">Mediation</span></span></p>
<p><span data-ttu-id="e4b21-146">de mediación</span><span class="sxs-lookup"><span data-stu-id="e4b21-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="e4b21-147">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-148">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-148">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-149">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-150">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b21-151">Servidor de mediación saliente</span><span class="sxs-lookup"><span data-stu-id="e4b21-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-152">Servidores</span><span class="sxs-lookup"><span data-stu-id="e4b21-152">Mediation</span></span></p>
<p><span data-ttu-id="e4b21-153">de mediación</span><span class="sxs-lookup"><span data-stu-id="e4b21-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="e4b21-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-154">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-155">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-156">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-156">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-157">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-157">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-158">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-159">Operador de conferencia entrante</span><span class="sxs-lookup"><span data-stu-id="e4b21-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-160">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-160">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-161">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="e4b21-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="e4b21-162">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-163">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-163">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-164">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-165">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b21-166">Operador de conferencia saliente</span><span class="sxs-lookup"><span data-stu-id="e4b21-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-167">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="e4b21-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="e4b21-168">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-168">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-169">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-170">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-170">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-171">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-172">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-173">Servidor de conferencia A/V entrante</span><span class="sxs-lookup"><span data-stu-id="e4b21-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-174">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-175">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e4b21-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e4b21-176">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-177">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-177">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-178">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-179">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b21-180">Salida de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="e4b21-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-181">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e4b21-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e4b21-182">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-182">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-183">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-184">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-184">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-185">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-185">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-186">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-187">Exchange entrante</span><span class="sxs-lookup"><span data-stu-id="e4b21-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-188">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-188">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-189">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="e4b21-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="e4b21-190">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-191">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-191">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-192">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-192">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-193">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b21-194">Servidores de aplicaciones compartidas entrantes</span><span class="sxs-lookup"><span data-stu-id="e4b21-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-195">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-195">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-196">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="e4b21-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="e4b21-197">TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-198">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-198">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-199">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-200">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-201">Servidor de aplicaciones compartidas saliente</span><span class="sxs-lookup"><span data-stu-id="e4b21-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-202">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="e4b21-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="e4b21-203">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-203">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-204">TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-205">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-205">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-206">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-206">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-207">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b21-208">Exchange saliente</span><span class="sxs-lookup"><span data-stu-id="e4b21-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="e4b21-209">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="e4b21-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="e4b21-210">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-210">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-211">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="e4b21-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-212">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-212">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-213">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-213">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-214">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b21-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="e4b21-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="e4b21-216">Cualquiera </span><span class="sxs-lookup"><span data-stu-id="e4b21-216">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-217">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-217">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-218">UDP</span><span class="sxs-lookup"><span data-stu-id="e4b21-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="e4b21-219">Intervalo de puertos de medios especificado</span><span class="sxs-lookup"><span data-stu-id="e4b21-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="e4b21-220">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e4b21-220">Any</span></span></p></td>
<td><p><span data-ttu-id="e4b21-221">No autenticar</span><span class="sxs-lookup"><span data-stu-id="e4b21-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


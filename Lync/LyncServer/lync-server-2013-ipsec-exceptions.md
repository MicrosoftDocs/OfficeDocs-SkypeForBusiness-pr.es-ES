---
title: Excepciones IPsec de Lync Server 2013
description: Excepciones de IPsec de Lync Server 2013.
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
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575006"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="60762-103">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60762-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60762-104">_**Última modificación del tema:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="60762-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="60762-p101">En aquellas redes empresariales donde el protocolo de seguridad de Internet o IPsec (consulte IETF RFC 4301-4309) está implementado, IPsec se debe deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.</span><span class="sxs-lookup"><span data-stu-id="60762-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="60762-107">En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.</span><span class="sxs-lookup"><span data-stu-id="60762-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="60762-108">Excepciones de IPsec recomendadas</span><span class="sxs-lookup"><span data-stu-id="60762-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="60762-109">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="60762-109">Rule name</span></span></th>
<th><span data-ttu-id="60762-110">IP de origen</span><span class="sxs-lookup"><span data-stu-id="60762-110">Source IP</span></span></th>
<th><span data-ttu-id="60762-111">IP de destino</span><span class="sxs-lookup"><span data-stu-id="60762-111">Destination IP</span></span></th>
<th><span data-ttu-id="60762-112">Protocolo</span><span class="sxs-lookup"><span data-stu-id="60762-112">Protocol</span></span></th>
<th><span data-ttu-id="60762-113">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="60762-113">Source port</span></span></th>
<th><span data-ttu-id="60762-114">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="60762-114">Destination port</span></span></th>
<th><span data-ttu-id="60762-115">Requisito de autenticación</span><span class="sxs-lookup"><span data-stu-id="60762-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60762-116">Servidor perimetral A/V interno entrante</span><span class="sxs-lookup"><span data-stu-id="60762-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="60762-117">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-117">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-118">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="60762-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="60762-119">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-120">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-120">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-121">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-121">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-122">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60762-123">Servidor perimetral A/V externo entrante</span><span class="sxs-lookup"><span data-stu-id="60762-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="60762-124">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-124">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-125">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="60762-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="60762-126">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-127">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-128">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-128">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-129">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60762-130">Servidor perimetral A/V interno saliente</span><span class="sxs-lookup"><span data-stu-id="60762-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="60762-131">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="60762-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="60762-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-132">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-133">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="60762-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-134">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-135">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-135">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-136">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60762-137">Servidor perimetral A/V externo saliente</span><span class="sxs-lookup"><span data-stu-id="60762-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="60762-138">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="60762-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="60762-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-139">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-140">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-141">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-142">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-143">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60762-144">Servidor de mediación entrante</span><span class="sxs-lookup"><span data-stu-id="60762-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="60762-145">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-145">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-146">Remedio</span><span class="sxs-lookup"><span data-stu-id="60762-146">Mediation</span></span></p>
<p><span data-ttu-id="60762-147">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="60762-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="60762-148">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-149">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-150">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-150">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-151">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60762-152">Servidor de mediación saliente</span><span class="sxs-lookup"><span data-stu-id="60762-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="60762-153">Remedio</span><span class="sxs-lookup"><span data-stu-id="60762-153">Mediation</span></span></p>
<p><span data-ttu-id="60762-154">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="60762-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="60762-155">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-155">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-156">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-157">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-157">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-158">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-159">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60762-160">Operador de conferencia entrante</span><span class="sxs-lookup"><span data-stu-id="60762-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="60762-161">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-161">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-162">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="60762-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="60762-163">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-164">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-165">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-165">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-166">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60762-167">Operador de conferencia saliente</span><span class="sxs-lookup"><span data-stu-id="60762-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="60762-168">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="60762-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="60762-169">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-169">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-170">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-171">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-172">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-172">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-173">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60762-174">Servidor de conferencia A/V entrante</span><span class="sxs-lookup"><span data-stu-id="60762-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="60762-175">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-175">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-176">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="60762-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="60762-177">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-178">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-179">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-179">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-180">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60762-181">Salida de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="60762-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="60762-182">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="60762-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="60762-183">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-183">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-184">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-185">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-185">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-186">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-186">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-187">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60762-188">Exchange entrante</span><span class="sxs-lookup"><span data-stu-id="60762-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="60762-189">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-189">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-190">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="60762-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="60762-191">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-192">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-192">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-193">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-193">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-194">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60762-195">Servidores de aplicaciones compartidas entrantes</span><span class="sxs-lookup"><span data-stu-id="60762-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="60762-196">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-196">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-197">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="60762-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="60762-198">TCP</span><span class="sxs-lookup"><span data-stu-id="60762-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-199">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-200">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-200">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-201">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60762-202">Servidor de aplicaciones compartidas saliente</span><span class="sxs-lookup"><span data-stu-id="60762-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="60762-203">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="60762-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="60762-204">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-204">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-205">TCP</span><span class="sxs-lookup"><span data-stu-id="60762-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-206">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-206">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-207">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-207">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-208">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60762-209">Exchange saliente</span><span class="sxs-lookup"><span data-stu-id="60762-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="60762-210">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="60762-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="60762-211">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-211">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-212">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="60762-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="60762-213">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-213">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-214">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-214">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-215">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60762-216">Clientes</span><span class="sxs-lookup"><span data-stu-id="60762-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="60762-217">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-217">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-218">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-218">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-219">UDP</span><span class="sxs-lookup"><span data-stu-id="60762-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="60762-220">Intervalo de puertos de medios especificado</span><span class="sxs-lookup"><span data-stu-id="60762-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="60762-221">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="60762-221">Any</span></span></p></td>
<td><p><span data-ttu-id="60762-222">No autenticar</span><span class="sxs-lookup"><span data-stu-id="60762-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: db7291674485dec30211d88e2739b0da89fb334f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="0ca74-102">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ca74-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ca74-103">_**Última modificación del tema:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="0ca74-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="0ca74-p101">En aquellas redes empresariales donde el protocolo de seguridad de Internet o IPsec (consulte IETF RFC 4301-4309) está implementado, IPsec se debe deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.</span><span class="sxs-lookup"><span data-stu-id="0ca74-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="0ca74-106">En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.</span><span class="sxs-lookup"><span data-stu-id="0ca74-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="0ca74-107">Excepciones de IPsec recomendadas</span><span class="sxs-lookup"><span data-stu-id="0ca74-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="0ca74-108">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="0ca74-108">Rule name</span></span></th>
<th><span data-ttu-id="0ca74-109">IP de origen</span><span class="sxs-lookup"><span data-stu-id="0ca74-109">Source IP</span></span></th>
<th><span data-ttu-id="0ca74-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="0ca74-110">Destination IP</span></span></th>
<th><span data-ttu-id="0ca74-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="0ca74-111">Protocol</span></span></th>
<th><span data-ttu-id="0ca74-112">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="0ca74-112">Source port</span></span></th>
<th><span data-ttu-id="0ca74-113">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="0ca74-113">Destination port</span></span></th>
<th><span data-ttu-id="0ca74-114">Requisito de autenticación</span><span class="sxs-lookup"><span data-stu-id="0ca74-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-115">Servidor perimetral A/V interno entrante</span><span class="sxs-lookup"><span data-stu-id="0ca74-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-116">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-117">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="0ca74-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0ca74-118">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-119">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-119">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-120">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-120">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-121">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca74-122">Servidor perimetral A/V externo entrante</span><span class="sxs-lookup"><span data-stu-id="0ca74-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-123">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-124">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="0ca74-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0ca74-125">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-126">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-127">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-128">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-129">Servidor perimetral A/V interno saliente</span><span class="sxs-lookup"><span data-stu-id="0ca74-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-130">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="0ca74-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0ca74-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-131">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="0ca74-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-133">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-133">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-134">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-135">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca74-136">Servidor perimetral A/V externo saliente</span><span class="sxs-lookup"><span data-stu-id="0ca74-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-137">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="0ca74-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0ca74-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-138">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-139">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-140">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-140">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-141">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-142">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-143">Servidor de mediación entrante</span><span class="sxs-lookup"><span data-stu-id="0ca74-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-144">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-145">Remedio</span><span class="sxs-lookup"><span data-stu-id="0ca74-145">Mediation</span></span></p>
<p><span data-ttu-id="0ca74-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="0ca74-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0ca74-147">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-148">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-149">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-150">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca74-151">Servidor de mediación saliente</span><span class="sxs-lookup"><span data-stu-id="0ca74-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-152">Remedio</span><span class="sxs-lookup"><span data-stu-id="0ca74-152">Mediation</span></span></p>
<p><span data-ttu-id="0ca74-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="0ca74-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0ca74-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-154">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-155">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-156">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-156">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-157">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-157">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-158">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-159">Operador de conferencia entrante</span><span class="sxs-lookup"><span data-stu-id="0ca74-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-160">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-160">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-161">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="0ca74-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0ca74-162">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-163">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-163">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-164">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-165">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca74-166">Operador de conferencia saliente</span><span class="sxs-lookup"><span data-stu-id="0ca74-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-167">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="0ca74-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0ca74-168">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-168">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-169">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-170">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-171">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-172">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-173">Servidor de conferencia A/V entrante</span><span class="sxs-lookup"><span data-stu-id="0ca74-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-174">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-175">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0ca74-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0ca74-176">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-177">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-177">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-178">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-179">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca74-180">Salida de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="0ca74-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-181">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0ca74-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0ca74-182">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-182">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-183">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-184">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-185">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-185">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-186">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-187">Exchange entrante</span><span class="sxs-lookup"><span data-stu-id="0ca74-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-188">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-188">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-189">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="0ca74-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0ca74-190">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-191">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-191">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-192">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-192">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-193">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca74-194">Servidores de aplicaciones compartidas entrantes</span><span class="sxs-lookup"><span data-stu-id="0ca74-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-195">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-195">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-196">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="0ca74-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0ca74-197">TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-198">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-198">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-199">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-200">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-201">Servidor de aplicaciones compartidas saliente</span><span class="sxs-lookup"><span data-stu-id="0ca74-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-202">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="0ca74-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0ca74-203">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-203">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-204">TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-205">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-205">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-206">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-206">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-207">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca74-208">Exchange saliente</span><span class="sxs-lookup"><span data-stu-id="0ca74-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ca74-209">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="0ca74-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0ca74-210">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-210">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-211">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0ca74-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-212">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-213">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-213">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-214">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca74-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="0ca74-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="0ca74-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-216">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-217">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-217">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-218">UDP</span><span class="sxs-lookup"><span data-stu-id="0ca74-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="0ca74-219">Intervalo de puertos de medios especificado</span><span class="sxs-lookup"><span data-stu-id="0ca74-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="0ca74-220">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0ca74-220">Any</span></span></p></td>
<td><p><span data-ttu-id="0ca74-221">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0ca74-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514157"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="8bd29-102">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd29-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bd29-103">_**Última modificación del tema:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="8bd29-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="8bd29-p101">En aquellas redes empresariales donde el protocolo de seguridad de Internet o IPsec (consulte IETF RFC 4301-4309) está implementado, IPsec se debe deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.</span><span class="sxs-lookup"><span data-stu-id="8bd29-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="8bd29-106">En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.</span><span class="sxs-lookup"><span data-stu-id="8bd29-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="8bd29-107">Excepciones de IPsec recomendadas</span><span class="sxs-lookup"><span data-stu-id="8bd29-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="8bd29-108">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="8bd29-108">Rule name</span></span></th>
<th><span data-ttu-id="8bd29-109">IP de origen</span><span class="sxs-lookup"><span data-stu-id="8bd29-109">Source IP</span></span></th>
<th><span data-ttu-id="8bd29-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="8bd29-110">Destination IP</span></span></th>
<th><span data-ttu-id="8bd29-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="8bd29-111">Protocol</span></span></th>
<th><span data-ttu-id="8bd29-112">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="8bd29-112">Source port</span></span></th>
<th><span data-ttu-id="8bd29-113">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="8bd29-113">Destination port</span></span></th>
<th><span data-ttu-id="8bd29-114">Requisito de autenticación</span><span class="sxs-lookup"><span data-stu-id="8bd29-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-115">Servidor perimetral A/V interno entrante</span><span class="sxs-lookup"><span data-stu-id="8bd29-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-116">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-117">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="8bd29-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="8bd29-118">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-119">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-119">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-120">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-120">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-121">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd29-122">Servidor perimetral A/V externo entrante</span><span class="sxs-lookup"><span data-stu-id="8bd29-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-123">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-124">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="8bd29-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="8bd29-125">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-126">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-127">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-128">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-129">Servidor perimetral A/V interno saliente</span><span class="sxs-lookup"><span data-stu-id="8bd29-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-130">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="8bd29-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="8bd29-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-131">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-132">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="8bd29-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-133">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-133">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-134">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-135">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd29-136">Servidor perimetral A/V externo saliente</span><span class="sxs-lookup"><span data-stu-id="8bd29-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-137">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="8bd29-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="8bd29-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-138">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-139">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-140">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-140">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-141">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-142">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-143">Servidor de mediación entrante</span><span class="sxs-lookup"><span data-stu-id="8bd29-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-144">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-145">Remedio</span><span class="sxs-lookup"><span data-stu-id="8bd29-145">Mediation</span></span></p>
<p><span data-ttu-id="8bd29-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="8bd29-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="8bd29-147">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-148">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-149">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-150">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd29-151">Servidor de mediación saliente</span><span class="sxs-lookup"><span data-stu-id="8bd29-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-152">Remedio</span><span class="sxs-lookup"><span data-stu-id="8bd29-152">Mediation</span></span></p>
<p><span data-ttu-id="8bd29-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="8bd29-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="8bd29-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-154">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-155">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-156">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-156">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-157">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-157">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-158">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-159">Operador de conferencia entrante</span><span class="sxs-lookup"><span data-stu-id="8bd29-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-160">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-160">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-161">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="8bd29-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="8bd29-162">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-163">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-163">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-164">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-165">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd29-166">Operador de conferencia saliente</span><span class="sxs-lookup"><span data-stu-id="8bd29-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-167">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="8bd29-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="8bd29-168">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-168">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-169">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-170">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-171">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-172">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-173">Servidor de conferencia A/V entrante</span><span class="sxs-lookup"><span data-stu-id="8bd29-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-174">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-175">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="8bd29-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8bd29-176">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-177">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-177">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-178">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-179">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd29-180">Salida de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="8bd29-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-181">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="8bd29-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8bd29-182">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-182">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-183">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-184">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-185">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-185">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-186">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-187">Exchange entrante</span><span class="sxs-lookup"><span data-stu-id="8bd29-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-188">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-188">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-189">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="8bd29-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="8bd29-190">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-191">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-191">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-192">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-192">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-193">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd29-194">Servidores de aplicaciones compartidas entrantes</span><span class="sxs-lookup"><span data-stu-id="8bd29-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-195">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-195">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-196">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="8bd29-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="8bd29-197">TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-198">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-198">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-199">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-200">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-201">Servidor de aplicaciones compartidas saliente</span><span class="sxs-lookup"><span data-stu-id="8bd29-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-202">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="8bd29-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="8bd29-203">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-203">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-204">TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-205">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-205">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-206">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-206">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-207">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd29-208">Exchange saliente</span><span class="sxs-lookup"><span data-stu-id="8bd29-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="8bd29-209">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="8bd29-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="8bd29-210">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-210">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-211">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="8bd29-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-212">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-213">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-213">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-214">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd29-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="8bd29-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="8bd29-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-216">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-217">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-217">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-218">UDP</span><span class="sxs-lookup"><span data-stu-id="8bd29-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="8bd29-219">Intervalo de puertos de medios especificado</span><span class="sxs-lookup"><span data-stu-id="8bd29-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="8bd29-220">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8bd29-220">Any</span></span></p></td>
<td><p><span data-ttu-id="8bd29-221">No autenticar</span><span class="sxs-lookup"><span data-stu-id="8bd29-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="0f94a-102">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f94a-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f94a-103">_**Última modificación del tema:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="0f94a-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="0f94a-p101">En aquellas redes empresariales donde el protocolo de seguridad de Internet o IPsec (consulte IETF RFC 4301-4309) está implementado, IPsec se debe deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.</span><span class="sxs-lookup"><span data-stu-id="0f94a-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="0f94a-106">En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.</span><span class="sxs-lookup"><span data-stu-id="0f94a-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="0f94a-107">Excepciones de IPsec recomendadas</span><span class="sxs-lookup"><span data-stu-id="0f94a-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="0f94a-108">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="0f94a-108">Rule name</span></span></th>
<th><span data-ttu-id="0f94a-109">IP de origen</span><span class="sxs-lookup"><span data-stu-id="0f94a-109">Source IP</span></span></th>
<th><span data-ttu-id="0f94a-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="0f94a-110">Destination IP</span></span></th>
<th><span data-ttu-id="0f94a-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="0f94a-111">Protocol</span></span></th>
<th><span data-ttu-id="0f94a-112">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="0f94a-112">Source port</span></span></th>
<th><span data-ttu-id="0f94a-113">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="0f94a-113">Destination port</span></span></th>
<th><span data-ttu-id="0f94a-114">Requisito de autenticación</span><span class="sxs-lookup"><span data-stu-id="0f94a-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-115">Servidor perimetral A/V interno entrante</span><span class="sxs-lookup"><span data-stu-id="0f94a-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-116">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-117">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="0f94a-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0f94a-118">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-119">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-119">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-120">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-120">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-121">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f94a-122">Servidor perimetral A/V externo entrante</span><span class="sxs-lookup"><span data-stu-id="0f94a-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-123">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-124">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="0f94a-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0f94a-125">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-126">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-127">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-128">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-129">Servidor perimetral A/V interno saliente</span><span class="sxs-lookup"><span data-stu-id="0f94a-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-130">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="0f94a-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0f94a-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-131">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="0f94a-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-133">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-133">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-134">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-135">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f94a-136">Servidor perimetral A/V externo saliente</span><span class="sxs-lookup"><span data-stu-id="0f94a-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-137">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="0f94a-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0f94a-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-138">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-139">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-140">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-140">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-141">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-142">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-143">Servidor de mediación entrante</span><span class="sxs-lookup"><span data-stu-id="0f94a-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-144">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-145">Remedio</span><span class="sxs-lookup"><span data-stu-id="0f94a-145">Mediation</span></span></p>
<p><span data-ttu-id="0f94a-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="0f94a-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0f94a-147">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-148">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-149">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-150">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f94a-151">Servidor de mediación saliente</span><span class="sxs-lookup"><span data-stu-id="0f94a-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-152">Remedio</span><span class="sxs-lookup"><span data-stu-id="0f94a-152">Mediation</span></span></p>
<p><span data-ttu-id="0f94a-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="0f94a-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0f94a-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-154">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-155">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-156">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-156">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-157">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-157">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-158">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-159">Operador de conferencia entrante</span><span class="sxs-lookup"><span data-stu-id="0f94a-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-160">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-160">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-161">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="0f94a-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0f94a-162">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-163">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-163">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-164">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-165">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f94a-166">Operador de conferencia saliente</span><span class="sxs-lookup"><span data-stu-id="0f94a-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-167">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="0f94a-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0f94a-168">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-168">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-169">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-170">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-171">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-172">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-173">Servidor de conferencia A/V entrante</span><span class="sxs-lookup"><span data-stu-id="0f94a-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-174">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-175">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0f94a-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0f94a-176">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-177">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-177">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-178">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-179">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f94a-180">Salida de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="0f94a-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-181">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0f94a-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0f94a-182">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-182">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-183">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-184">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-185">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-185">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-186">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-187">Exchange entrante</span><span class="sxs-lookup"><span data-stu-id="0f94a-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-188">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-188">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-189">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="0f94a-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0f94a-190">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-191">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-191">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-192">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-192">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-193">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f94a-194">Servidores de aplicaciones compartidas entrantes</span><span class="sxs-lookup"><span data-stu-id="0f94a-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-195">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-195">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-196">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="0f94a-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0f94a-197">TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-198">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-198">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-199">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-200">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-201">Servidor de aplicaciones compartidas saliente</span><span class="sxs-lookup"><span data-stu-id="0f94a-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-202">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="0f94a-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0f94a-203">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-203">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-204">TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-205">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-205">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-206">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-206">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-207">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f94a-208">Exchange saliente</span><span class="sxs-lookup"><span data-stu-id="0f94a-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="0f94a-209">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="0f94a-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0f94a-210">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-210">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-211">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="0f94a-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-212">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-213">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-213">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-214">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f94a-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="0f94a-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="0f94a-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-216">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-217">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-217">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-218">UDP</span><span class="sxs-lookup"><span data-stu-id="0f94a-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="0f94a-219">Intervalo de puertos de medios especificado</span><span class="sxs-lookup"><span data-stu-id="0f94a-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="0f94a-220">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="0f94a-220">Any</span></span></p></td>
<td><p><span data-ttu-id="0f94a-221">No autenticar</span><span class="sxs-lookup"><span data-stu-id="0f94a-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


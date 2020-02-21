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
ms.openlocfilehash: bd649cea823ce13460de924ffc49741b3ca5c6d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="ab3c5-102">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab3c5-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab3c5-103">_**Última modificación del tema:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="ab3c5-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="ab3c5-p101">En aquellas redes empresariales donde el protocolo de seguridad de Internet o IPsec (consulte IETF RFC 4301-4309) está implementado, IPsec se debe deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.</span><span class="sxs-lookup"><span data-stu-id="ab3c5-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="ab3c5-106">En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ab3c5-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="ab3c5-107">Excepciones de IPsec recomendadas</span><span class="sxs-lookup"><span data-stu-id="ab3c5-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="ab3c5-108">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="ab3c5-108">Rule name</span></span></th>
<th><span data-ttu-id="ab3c5-109">IP de origen</span><span class="sxs-lookup"><span data-stu-id="ab3c5-109">Source IP</span></span></th>
<th><span data-ttu-id="ab3c5-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="ab3c5-110">Destination IP</span></span></th>
<th><span data-ttu-id="ab3c5-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="ab3c5-111">Protocol</span></span></th>
<th><span data-ttu-id="ab3c5-112">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="ab3c5-112">Source port</span></span></th>
<th><span data-ttu-id="ab3c5-113">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="ab3c5-113">Destination port</span></span></th>
<th><span data-ttu-id="ab3c5-114">Requisito de autenticación</span><span class="sxs-lookup"><span data-stu-id="ab3c5-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-115">Servidor perimetral A/V interno entrante</span><span class="sxs-lookup"><span data-stu-id="ab3c5-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-116">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-117">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="ab3c5-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-118">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-119">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-119">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-120">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-120">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-121">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c5-122">Servidor perimetral A/V externo entrante</span><span class="sxs-lookup"><span data-stu-id="ab3c5-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-123">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-124">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="ab3c5-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-125">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-127">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-127">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-128">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-129">Servidor perimetral A/V interno saliente</span><span class="sxs-lookup"><span data-stu-id="ab3c5-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-130">Servidor perimetral A/V interno</span><span class="sxs-lookup"><span data-stu-id="ab3c5-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-131">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-133">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-133">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-135">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c5-136">Servidor perimetral A/V externo saliente</span><span class="sxs-lookup"><span data-stu-id="ab3c5-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-137">Servidor perimetral A/V externo</span><span class="sxs-lookup"><span data-stu-id="ab3c5-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-138">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-139">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-140">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-140">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-141">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-142">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-143">Servidor de mediación entrante</span><span class="sxs-lookup"><span data-stu-id="ab3c5-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-144">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-145">Remedio</span><span class="sxs-lookup"><span data-stu-id="ab3c5-145">Mediation</span></span></p>
<p><span data-ttu-id="ab3c5-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="ab3c5-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-147">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-148">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-149">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-149">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-150">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c5-151">Servidor de mediación saliente</span><span class="sxs-lookup"><span data-stu-id="ab3c5-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-152">Remedio</span><span class="sxs-lookup"><span data-stu-id="ab3c5-152">Mediation</span></span></p>
<p><span data-ttu-id="ab3c5-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="ab3c5-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-154">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-155">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-156">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-156">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-157">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-157">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-158">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-159">Operador de conferencia entrante</span><span class="sxs-lookup"><span data-stu-id="ab3c5-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-160">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-160">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-161">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="ab3c5-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-162">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-163">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-163">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-164">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-165">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c5-166">Operador de conferencia saliente</span><span class="sxs-lookup"><span data-stu-id="ab3c5-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-167">Servidor front-end que ejecuta operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="ab3c5-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-168">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-168">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-169">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-170">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-170">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-171">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-172">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-173">Servidor de conferencia A/V entrante</span><span class="sxs-lookup"><span data-stu-id="ab3c5-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-174">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-174">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-175">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="ab3c5-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-176">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-177">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-177">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-178">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-178">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-179">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c5-180">Salida de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="ab3c5-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-181">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="ab3c5-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-182">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-182">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-183">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-184">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-184">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-185">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-185">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-186">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-187">Exchange entrante</span><span class="sxs-lookup"><span data-stu-id="ab3c5-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-188">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-188">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-189">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="ab3c5-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-190">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-191">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-191">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-192">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-192">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-193">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c5-194">Servidores de aplicaciones compartidas entrantes</span><span class="sxs-lookup"><span data-stu-id="ab3c5-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-195">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-195">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-196">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="ab3c5-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-197">TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-198">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-198">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-199">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-199">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-200">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-201">Servidor de aplicaciones compartidas saliente</span><span class="sxs-lookup"><span data-stu-id="ab3c5-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-202">Servidores de aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="ab3c5-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-203">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-203">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-204">TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-205">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-205">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-206">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-206">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-207">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c5-208">Exchange saliente</span><span class="sxs-lookup"><span data-stu-id="ab3c5-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-209">Mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="ab3c5-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-210">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-210">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-211">UDP y TCP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-212">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-212">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-213">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-213">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-214">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c5-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="ab3c5-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-216">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-216">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-217">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-217">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-218">UDP</span><span class="sxs-lookup"><span data-stu-id="ab3c5-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-219">Intervalo de puertos de medios especificado</span><span class="sxs-lookup"><span data-stu-id="ab3c5-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-220">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ab3c5-220">Any</span></span></p></td>
<td><p><span data-ttu-id="ab3c5-221">No autenticar</span><span class="sxs-lookup"><span data-stu-id="ab3c5-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


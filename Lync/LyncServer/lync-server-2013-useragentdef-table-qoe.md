---
title: 'Lync Server 2013: tabla UserAgentDef (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adfe05a24d2a45cf5d6d279b29d77b1c7654012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="41e7d-102">Tabla UserAgentDef (QoE) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41e7d-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41e7d-103">_**Última modificación del tema:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="41e7d-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="41e7d-104">La tabla UserAgentDef asigna los identificadores de agente de usuario a los nombres descriptivos del agente.</span><span class="sxs-lookup"><span data-stu-id="41e7d-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="41e7d-105">Los agentes de usuario son clientes de software que se usan para conectarse a Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41e7d-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41e7d-106">UAType</span><span class="sxs-lookup"><span data-stu-id="41e7d-106">UAType</span></span></th>
<th><span data-ttu-id="41e7d-107">UAName</span><span class="sxs-lookup"><span data-stu-id="41e7d-107">UAName</span></span></th>
<th><span data-ttu-id="41e7d-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="41e7d-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-109">1</span><span class="sxs-lookup"><span data-stu-id="41e7d-109">1</span></span></p></td>
<td><p><span data-ttu-id="41e7d-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="41e7d-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="41e7d-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="41e7d-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-112">2</span><span class="sxs-lookup"><span data-stu-id="41e7d-112">2</span></span></p></td>
<td><p><span data-ttu-id="41e7d-113">MCU de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="41e7d-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="41e7d-114">MCU de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="41e7d-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-115">4</span><span class="sxs-lookup"><span data-stu-id="41e7d-115">4</span></span></p></td>
<td><p><span data-ttu-id="41e7d-116">OC</span><span class="sxs-lookup"><span data-stu-id="41e7d-116">OC</span></span></p></td>
<td><p><span data-ttu-id="41e7d-117">OC</span><span class="sxs-lookup"><span data-stu-id="41e7d-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-118">4,8</span><span class="sxs-lookup"><span data-stu-id="41e7d-118">8</span></span></p></td>
<td><p><span data-ttu-id="41e7d-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="41e7d-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="41e7d-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="41e7d-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-121">apartado</span><span class="sxs-lookup"><span data-stu-id="41e7d-121">16</span></span></p></td>
<td><p><span data-ttu-id="41e7d-122">LMC</span><span class="sxs-lookup"><span data-stu-id="41e7d-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="41e7d-123">LMC</span><span class="sxs-lookup"><span data-stu-id="41e7d-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-124">32</span><span class="sxs-lookup"><span data-stu-id="41e7d-124">32</span></span></p></td>
<td><p><span data-ttu-id="41e7d-125">DVT</span><span class="sxs-lookup"><span data-stu-id="41e7d-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="41e7d-126">DVT</span><span class="sxs-lookup"><span data-stu-id="41e7d-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-127">64</span><span class="sxs-lookup"><span data-stu-id="41e7d-127">64</span></span></p></td>
<td><p><span data-ttu-id="41e7d-128">MM</span><span class="sxs-lookup"><span data-stu-id="41e7d-128">MM</span></span></p></td>
<td><p><span data-ttu-id="41e7d-129">MM</span><span class="sxs-lookup"><span data-stu-id="41e7d-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-130">64</span><span class="sxs-lookup"><span data-stu-id="41e7d-130">64</span></span></p></td>
<td><p><span data-ttu-id="41e7d-131">MC</span><span class="sxs-lookup"><span data-stu-id="41e7d-131">MC</span></span></p></td>
<td><p><span data-ttu-id="41e7d-132">MM</span><span class="sxs-lookup"><span data-stu-id="41e7d-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-133">128</span><span class="sxs-lookup"><span data-stu-id="41e7d-133">128</span></span></p></td>
<td><p><span data-ttu-id="41e7d-134">Operador</span><span class="sxs-lookup"><span data-stu-id="41e7d-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="41e7d-135">Operador</span><span class="sxs-lookup"><span data-stu-id="41e7d-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-136">256</span><span class="sxs-lookup"><span data-stu-id="41e7d-136">256</span></span></p></td>
<td><p><span data-ttu-id="41e7d-137">Conferencing_Announcement_Service_ 1.0</span><span class="sxs-lookup"><span data-stu-id="41e7d-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="41e7d-138">ENTIDAD</span><span class="sxs-lookup"><span data-stu-id="41e7d-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-139">512</span><span class="sxs-lookup"><span data-stu-id="41e7d-139">512</span></span></p></td>
<td><p><span data-ttu-id="41e7d-140">Conferencing_Attendant_ 1.0</span><span class="sxs-lookup"><span data-stu-id="41e7d-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="41e7d-141">CAA</span><span class="sxs-lookup"><span data-stu-id="41e7d-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-142">512</span><span class="sxs-lookup"><span data-stu-id="41e7d-142">512</span></span></p></td>
<td><p><span data-ttu-id="41e7d-143">Conference_Auto_Attendant_ 1.0</span><span class="sxs-lookup"><span data-stu-id="41e7d-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="41e7d-144">CAA</span><span class="sxs-lookup"><span data-stu-id="41e7d-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-145">1024</span><span class="sxs-lookup"><span data-stu-id="41e7d-145">1024</span></span></p></td>
<td><p><span data-ttu-id="41e7d-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="41e7d-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="41e7d-147">RGS</span><span class="sxs-lookup"><span data-stu-id="41e7d-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-148">1032</span><span class="sxs-lookup"><span data-stu-id="41e7d-148">1032</span></span></p></td>
<td><p><span data-ttu-id="41e7d-149">Call_Park_Service_ 1.0</span><span class="sxs-lookup"><span data-stu-id="41e7d-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="41e7d-150">CP</span><span class="sxs-lookup"><span data-stu-id="41e7d-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-151">1040</span><span class="sxs-lookup"><span data-stu-id="41e7d-151">1040</span></span></p></td>
<td><p><span data-ttu-id="41e7d-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="41e7d-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="41e7d-153">CUYA</span><span class="sxs-lookup"><span data-stu-id="41e7d-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-154">2048</span><span class="sxs-lookup"><span data-stu-id="41e7d-154">2048</span></span></p></td>
<td><p><span data-ttu-id="41e7d-155">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="41e7d-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="41e7d-156">CCS</span><span class="sxs-lookup"><span data-stu-id="41e7d-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-157">16386</span><span class="sxs-lookup"><span data-stu-id="41e7d-157">16386</span></span></p></td>
<td><p><span data-ttu-id="41e7d-158">Notifica</span><span class="sxs-lookup"><span data-stu-id="41e7d-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="41e7d-159">Notifica</span><span class="sxs-lookup"><span data-stu-id="41e7d-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-160">16387</span><span class="sxs-lookup"><span data-stu-id="41e7d-160">16387</span></span></p></td>
<td><p><span data-ttu-id="41e7d-161">CWA</span><span class="sxs-lookup"><span data-stu-id="41e7d-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="41e7d-162">CWA</span><span class="sxs-lookup"><span data-stu-id="41e7d-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-163">16388</span><span class="sxs-lookup"><span data-stu-id="41e7d-163">16388</span></span></p></td>
<td><p><span data-ttu-id="41e7d-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="41e7d-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="41e7d-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="41e7d-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-166">16389</span><span class="sxs-lookup"><span data-stu-id="41e7d-166">16389</span></span></p></td>
<td><p><span data-ttu-id="41e7d-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="41e7d-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="41e7d-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="41e7d-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-169">16393</span><span class="sxs-lookup"><span data-stu-id="41e7d-169">16393</span></span></p></td>
<td><p><span data-ttu-id="41e7d-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="41e7d-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="41e7d-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="41e7d-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-172">16395</span><span class="sxs-lookup"><span data-stu-id="41e7d-172">16395</span></span></p></td>
<td><p><span data-ttu-id="41e7d-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="41e7d-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="41e7d-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="41e7d-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-175">16396</span><span class="sxs-lookup"><span data-stu-id="41e7d-175">16396</span></span></p></td>
<td><p><span data-ttu-id="41e7d-176">San</span><span class="sxs-lookup"><span data-stu-id="41e7d-176">ST</span></span></p></td>
<td><p><span data-ttu-id="41e7d-177">San</span><span class="sxs-lookup"><span data-stu-id="41e7d-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-178">16397</span><span class="sxs-lookup"><span data-stu-id="41e7d-178">16397</span></span></p></td>
<td><p><span data-ttu-id="41e7d-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="41e7d-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="41e7d-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="41e7d-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-181">16398</span><span class="sxs-lookup"><span data-stu-id="41e7d-181">16398</span></span></p></td>
<td><p><span data-ttu-id="41e7d-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="41e7d-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-184">16399</span><span class="sxs-lookup"><span data-stu-id="41e7d-184">16399</span></span></p></td>
<td><p><span data-ttu-id="41e7d-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="41e7d-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-187">16400</span><span class="sxs-lookup"><span data-stu-id="41e7d-187">16400</span></span></p></td>
<td><p><span data-ttu-id="41e7d-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="41e7d-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-190">16401</span><span class="sxs-lookup"><span data-stu-id="41e7d-190">16401</span></span></p></td>
<td><p><span data-ttu-id="41e7d-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="41e7d-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-193">16402</span><span class="sxs-lookup"><span data-stu-id="41e7d-193">16402</span></span></p></td>
<td><p><span data-ttu-id="41e7d-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="41e7d-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="41e7d-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-196">16403</span><span class="sxs-lookup"><span data-stu-id="41e7d-196">16403</span></span></p></td>
<td><p><span data-ttu-id="41e7d-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="41e7d-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="41e7d-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="41e7d-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-199">16404</span><span class="sxs-lookup"><span data-stu-id="41e7d-199">16404</span></span></p></td>
<td><p><span data-ttu-id="41e7d-200">INFORMÁTICO</span><span class="sxs-lookup"><span data-stu-id="41e7d-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="41e7d-201">INFORMÁTICO</span><span class="sxs-lookup"><span data-stu-id="41e7d-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-202">16405</span><span class="sxs-lookup"><span data-stu-id="41e7d-202">16405</span></span></p></td>
<td><p><span data-ttu-id="41e7d-203">LWA</span><span class="sxs-lookup"><span data-stu-id="41e7d-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="41e7d-204">LWA</span><span class="sxs-lookup"><span data-stu-id="41e7d-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-205">16406</span><span class="sxs-lookup"><span data-stu-id="41e7d-205">16406</span></span></p></td>
<td><p><span data-ttu-id="41e7d-206">Access</span><span class="sxs-lookup"><span data-stu-id="41e7d-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="41e7d-207">Access</span><span class="sxs-lookup"><span data-stu-id="41e7d-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-208">16407</span><span class="sxs-lookup"><span data-stu-id="41e7d-208">16407</span></span></p></td>
<td><p><span data-ttu-id="41e7d-209">AOC</span><span class="sxs-lookup"><span data-stu-id="41e7d-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="41e7d-210">AOC</span><span class="sxs-lookup"><span data-stu-id="41e7d-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-211">16408</span><span class="sxs-lookup"><span data-stu-id="41e7d-211">16408</span></span></p></td>
<td><p><span data-ttu-id="41e7d-212">GCC</span><span class="sxs-lookup"><span data-stu-id="41e7d-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="41e7d-213">GCC</span><span class="sxs-lookup"><span data-stu-id="41e7d-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-214">16409</span><span class="sxs-lookup"><span data-stu-id="41e7d-214">16409</span></span></p></td>
<td><p><span data-ttu-id="41e7d-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="41e7d-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="41e7d-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="41e7d-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-217">16410</span><span class="sxs-lookup"><span data-stu-id="41e7d-217">16410</span></span></p></td>
<td><p><span data-ttu-id="41e7d-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="41e7d-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="41e7d-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="41e7d-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e7d-220">32769</span><span class="sxs-lookup"><span data-stu-id="41e7d-220">32769</span></span></p></td>
<td><p><span data-ttu-id="41e7d-221">Puerta</span><span class="sxs-lookup"><span data-stu-id="41e7d-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="41e7d-222">Puerta</span><span class="sxs-lookup"><span data-stu-id="41e7d-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41e7d-223">32770</span><span class="sxs-lookup"><span data-stu-id="41e7d-223">32770</span></span></p></td>
<td><p><span data-ttu-id="41e7d-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="41e7d-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="41e7d-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="41e7d-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


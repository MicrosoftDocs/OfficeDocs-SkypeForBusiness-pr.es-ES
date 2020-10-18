---
title: 'Lync Server 2013: vista de AudioStreamDetail'
description: 'Lync Server 2013: vista de AudioStreamDetail.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573056"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="8d0cb-103">Vista AudioStreamDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d0cb-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d0cb-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8d0cb-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8d0cb-105">La vista AudioStreamDetail almacena información sobre cada secuencia de audio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="8d0cb-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d0cb-107">Columna</span><span class="sxs-lookup"><span data-stu-id="8d0cb-107">Column</span></span></th>
<th><span data-ttu-id="8d0cb-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d0cb-108">Data Type</span></span></th>
<th><span data-ttu-id="8d0cb-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d0cb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="8d0cb-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8d0cb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-112">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="8d0cb-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-114">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-114">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-115">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-116">StreamId</span><span class="sxs-lookup"><span data-stu-id="8d0cb-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-117">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-117">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-118">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="8d0cb-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-120">datetime</span><span class="sxs-lookup"><span data-stu-id="8d0cb-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-121">Fecha y hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="8d0cb-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-123">datetime</span><span class="sxs-lookup"><span data-stu-id="8d0cb-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-124">Fecha y hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="8d0cb-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-126">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-126">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-127">Categoría del cuadro de diálogo: 0 es el segmento del servidor de mediación de Lync. 1 es el servidor de mediación a la pierna de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="8d0cb-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-129">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-129">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-130">Marca que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="8d0cb-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-132">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-132">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-133">Si está presente, indica por qué no se omitió una llamada incluso si coinciden los identificadores de omisión.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-133">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="8d0cb-134">Solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="8d0cb-134">Only one value is defined:</span></span></p>
<p><span data-ttu-id="8d0cb-135">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="8d0cb-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-137">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-137">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-138">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="8d0cb-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-141">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="8d0cb-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-144">FQDN del grupo de destinatarios de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-145">Caller</span><span class="sxs-lookup"><span data-stu-id="8d0cb-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-147">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-148">Destinatario</span><span class="sxs-lookup"><span data-stu-id="8d0cb-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-150">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="8d0cb-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-153">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8d0cb-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-155">smallint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-156">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="8d0cb-157">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8d0cb-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-160">Categoría del agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="8d0cb-161">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="8d0cb-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-164">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8d0cb-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-166">smallint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-167">Tipo de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-167">Type of callee’s user agent.</span></span> <span data-ttu-id="8d0cb-168">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8d0cb-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-171">Categoría de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-171">Category of callee’s user agent.</span></span> <span data-ttu-id="8d0cb-172">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-175">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-178">Nombre del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-179">CallerOS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-181">Sistema operativo (SO) del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-183">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-184">Sistema operativo (SO) del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="8d0cb-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-186">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-187">Nombre de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="8d0cb-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-189">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-190">Nombre de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="8d0cb-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-192">smallint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-193">Número de núcleos de CPU en el extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="8d0cb-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-195">smallint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-196">Número de núcleos de CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="8d0cb-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-198">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-198">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-199">Velocidad del procesador de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="8d0cb-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-201">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-201">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-202">Velocidad del procesador de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="8d0cb-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-205">Indica si el sistema del autor de la llamada se está ejecutando en un entorno visualizado.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8d0cb-206">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="8d0cb-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-209">Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8d0cb-210">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="8d0cb-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8d0cb-212">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-212">Correlation key.</span></span> <span data-ttu-id="8d0cb-213">Referencia de la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="8d0cb-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-216">Información sobre la ruta de medios, como directa o retransmitida.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="8d0cb-217">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8d0cb-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-219">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-219">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-p111">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8d0cb-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-223">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-223">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-p112">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-226">Transport</span><span class="sxs-lookup"><span data-stu-id="8d0cb-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-228">Tipo de transporte: 0 es UDP y 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="8d0cb-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-231">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-231">IP address of the caller.</span></span> <span data-ttu-id="8d0cb-232">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="8d0cb-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-234">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-234">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-235">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="8d0cb-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-237">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-237">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-238">Indica si el autor de la llamada está dentro de la red del intervalo: 1 significa que el autor de la llamada está dentro de la red de la empresa, 0 significa que el autor de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="8d0cb-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-241">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-241">IP address of the callee.</span></span> <span data-ttu-id="8d0cb-242">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="8d0cb-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-244">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-244">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-245">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="8d0cb-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-247">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-247">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-248">Indica si el destinatario de la llamada está dentro de la red del intervalo: 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="8d0cb-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-250">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-251">Nombre del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="8d0cb-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-253">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-254">Nombre del país o región del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="8d0cb-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-256">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-257">Nombre del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="8d0cb-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-259">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8d0cb-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-260">Nombre del país o la región del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8d0cb-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-263">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="8d0cb-264">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="8d0cb-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-266">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-266">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-267">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8d0cb-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-270">Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="8d0cb-271">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="8d0cb-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-273">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-273">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-274">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8d0cb-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-276">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-277">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="8d0cb-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-279">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-280">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8d0cb-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-282">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-283">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="8d0cb-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-285">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-286">Nombre del controlador dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8d0cb-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-288">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-289">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="8d0cb-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-291">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-292">Nombre de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8d0cb-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-294">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-295">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="8d0cb-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-297">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-298">Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="8d0cb-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-301">Tipo de conexión de red del autor de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="8d0cb-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-303">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-303">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-304">Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="8d0cb-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-306">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-307">Velocidad del vínculo de red del extremo del autor de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="8d0cb-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-310">Tipo de conexión de red del destinatario de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="8d0cb-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-312">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-312">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-313">Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="8d0cb-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-315">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-316">Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-318">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-319">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="8d0cb-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-321">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-321">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-322">Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.).</span><span class="sxs-lookup"><span data-stu-id="8d0cb-322">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="8d0cb-323">No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-323">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="8d0cb-324">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda</span><span class="sxs-lookup"><span data-stu-id="8d0cb-324">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="8d0cb-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-326">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-326">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-327">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="8d0cb-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="8d0cb-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-329">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-329">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-330">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="8d0cb-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-332">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-333">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="8d0cb-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-335">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-336">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-337">Densidad</span><span class="sxs-lookup"><span data-stu-id="8d0cb-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-338">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-339">Densidad media de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="8d0cb-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-341">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-341">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-342">Duración media de la pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="8d0cb-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-344">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-345">Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="8d0cb-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-347">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-347">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-348">Duración media de brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="8d0cb-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-350">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-350">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-351">Número de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-352">Ancho de banda más</span><span class="sxs-lookup"><span data-stu-id="8d0cb-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-353">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-353">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-354">Previsiones de ancho de banda de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="8d0cb-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-356">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-357">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-357">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="8d0cb-358">El intervalo es de 0,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-358">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="8d0cb-359">Esta métrica muestra la cantidad de MOS de red que se redujo debido a la vibración y pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-359">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="8d0cb-360">Para una calidad aceptable, debe ser inferior a 0,5.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-360">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="8d0cb-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-362">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-363">Degradación de MOS de red máxima durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="8d0cb-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-365">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-366">Degradación de MOS de red causada por la vibración.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="8d0cb-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-368">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-369">Degradación de MOS de red causada por la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="8d0cb-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-371">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-371">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-372">El códec de audio usado para la llamada, al que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="8d0cb-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-374">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-374">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-375">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-377">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-377">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-378">Nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-378">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="8d0cb-379">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-379">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-380">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-380">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="8d0cb-381">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-381">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-383">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-383">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-384">Nivel de señal de audio para el audio que el autor de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-384">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="8d0cb-385">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-385">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-386">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-386">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="8d0cb-387">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-387">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-389">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-389">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-390">El nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-390">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="8d0cb-391">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-391">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-392">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-392">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="8d0cb-393">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-393">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-395">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-395">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-396">El nivel de ruido de audio del control de ganancia posterior analógico para el audio que ha recibido la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-396">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="8d0cb-397">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-397">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-398">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-398">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="8d0cb-399">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-399">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="8d0cb-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-401">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-401">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-402">Devolución de pérdida eco mejora para el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-402">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="8d0cb-403">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-403">The unit for this metric is dB.</span></span> <span data-ttu-id="8d0cb-404">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-404">Lower values represent less echo.</span></span> <span data-ttu-id="8d0cb-405">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-405">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8d0cb-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-407">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-407">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-408">Media de problemas por cinco minutos para la representación del altavoz del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-408">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="8d0cb-409">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-409">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="8d0cb-410">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-410">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8d0cb-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-412">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-412">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-413">Media de problemas por cinco minutos para la captura del micrófono del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-413">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="8d0cb-414">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-414">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="8d0cb-415">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-415">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="8d0cb-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-417">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-418">Tasa de desplazamiento del reloj del dispositivo de micrófono del autor de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="8d0cb-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-420">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-421">Tasa de desplazamiento del reloj del dispositivo de altavoz del autor de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="8d0cb-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-423">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-424">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="8d0cb-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-426">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-427">Promedio del error de marca de tiempo de la secuencia de representación del altavoz del autor de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="8d0cb-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-429">smallint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-430">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="8d0cb-431">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="8d0cb-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-434">Causas de un evento de Eco para el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="8d0cb-435">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="8d0cb-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-437">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-438">Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-438">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="8d0cb-439">Si se usa el casco, el valor debería ser bajo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-439">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="8d0cb-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-441">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-442">Porcentaje de tiempo en que se detecta el eco en la secuencia enviada del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-442">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="8d0cb-443">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-443">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-445">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-445">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-446">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-446">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="8d0cb-447">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-447">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8d0cb-448">Para obtener una buena calidad, el intervalo aceptable debe ser de-30 a-18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-448">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-450">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-450">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-451">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-451">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="8d0cb-452">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-452">This applies only to the Mediation Server.</span></span> <span data-ttu-id="8d0cb-453">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-453">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8d0cb-454">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-454">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="8d0cb-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-456">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-456">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-457">Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-459">float</span><span class="sxs-lookup"><span data-stu-id="8d0cb-459">float</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-460">Cuadrado raíz medio (RMS) de la señal entrante al autor de la llamada durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-462">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-462">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-463">Representa el nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-463">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="8d0cb-464">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-464">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-465">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-465">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="8d0cb-466">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-466">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-468">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-468">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-469">Nivel de señal de audio para el audio que el destinatario de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-469">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="8d0cb-470">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-470">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-471">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-471">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="8d0cb-472">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-472">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-474">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-474">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-475">Nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-475">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="8d0cb-476">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-476">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-477">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-477">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="8d0cb-478">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-478">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-480">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-480">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-481">Nivel de ruido de audio del control de ganancia posterior analógico para el audio que el destinatario de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-481">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="8d0cb-482">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-482">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8d0cb-483">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-483">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="8d0cb-484">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-484">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="8d0cb-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-486">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-486">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-487">Devolución de pérdida de Eco para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-487">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="8d0cb-488">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-488">The unit for this metric is dB.</span></span> <span data-ttu-id="8d0cb-489">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-489">Lower values represent less echo.</span></span> <span data-ttu-id="8d0cb-490">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-490">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8d0cb-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-492">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-492">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-493">Media de problemas por cinco minutos para la representación del altavoz del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-493">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="8d0cb-494">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-494">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="8d0cb-495">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-495">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8d0cb-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-497">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-497">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-498">Media de problemas por cinco minutos para la captura del micrófono del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-498">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="8d0cb-499">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-499">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="8d0cb-500">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-500">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="8d0cb-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-502">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-503">Tasa de desplazamiento del reloj del dispositivo de micrófono del destinatario de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="8d0cb-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-505">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-506">Tasa de desplazamiento del reloj del dispositivo de altavoz del destinatario de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="8d0cb-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-508">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-509">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="8d0cb-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-511">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-512">Promedio del error de marca de tiempo de la secuencia de representación del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="8d0cb-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-514">smallint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-515">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="8d0cb-516">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="8d0cb-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d0cb-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-519">Causas de un evento echo para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="8d0cb-520">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="8d0cb-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-522">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-523">Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-523">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="8d0cb-524">Si se usa el casco, el valor debería ser bajo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-524">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="8d0cb-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-526">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-527">Porcentaje de tiempo en que se detecta eco en la secuencia enviada del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-527">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="8d0cb-528">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-528">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-530">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-530">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-531">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-531">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="8d0cb-532">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-532">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8d0cb-533">Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-533">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8d0cb-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-535">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-535">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-536">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-536">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="8d0cb-537">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-537">This applies only to the Mediation Server.</span></span> <span data-ttu-id="8d0cb-538">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-538">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8d0cb-539">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-539">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="8d0cb-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-541">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-541">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-542">Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-544">float</span><span class="sxs-lookup"><span data-stu-id="8d0cb-544">float</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-545">Cuadrado raíz medio (RMS) de la señal entrante al destinatario de la llamada durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="8d0cb-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-547">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-548">Relación media de muestras ocultas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="8d0cb-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-550">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-551">Relación media de muestras extendidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="8d0cb-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-553">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-554">Relación media de muestras comprimidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-555">Vuelta</span><span class="sxs-lookup"><span data-stu-id="8d0cb-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-556">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-556">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-557">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="8d0cb-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-559">entero</span><span class="sxs-lookup"><span data-stu-id="8d0cb-559">int</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-560">Tiempo de ida y vuelta máximo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-562">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-563">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-563">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="8d0cb-564">Esta métrica depende de la pérdida de paquetes, la vibración y el códec que se usan.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-564">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="8d0cb-565">El intervalo es de 1,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-565">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-567">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-568">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-570">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-571">Puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="8d0cb-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-573">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-574">SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="8d0cb-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-576">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-577">Puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y la captura de las características del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="8d0cb-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-579">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-580">RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0cb-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="8d0cb-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-582">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-582">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-583">Indica si se usó el FEC de audio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0cb-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="8d0cb-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-585">bit</span><span class="sxs-lookup"><span data-stu-id="8d0cb-585">bit</span></span></p></td>
<td><p><span data-ttu-id="8d0cb-586">Indica la dirección de la información de identificación p-asserted; 1 significa que la dirección de la secuencia proviene del autor de la llamada al destinatario de la llamada; 0 significa que la dirección de la secuencia es del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


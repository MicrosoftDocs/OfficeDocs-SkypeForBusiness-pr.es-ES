---
title: 'Lync Server 2013: vista AudioStreamDetail'
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
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="0e378-102">Vista AudioStreamDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e378-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e378-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0e378-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0e378-104">La vista AudioStreamDetail almacena información acerca de cada secuencia de audio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0e378-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="0e378-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e378-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e378-106">Columna</span><span class="sxs-lookup"><span data-stu-id="0e378-106">Column</span></span></th>
<th><span data-ttu-id="0e378-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0e378-107">Data Type</span></span></th>
<th><span data-ttu-id="0e378-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="0e378-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e378-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="0e378-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="0e378-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0e378-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e378-111">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0e378-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="0e378-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="0e378-113">int</span><span class="sxs-lookup"><span data-stu-id="0e378-113">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-114">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0e378-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="0e378-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="0e378-116">int</span><span class="sxs-lookup"><span data-stu-id="0e378-116">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-117">IDENTIFICADOR exclusivo dentro de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="0e378-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="0e378-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="0e378-119">datetime</span><span class="sxs-lookup"><span data-stu-id="0e378-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e378-120">Hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0e378-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="0e378-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="0e378-122">datetime</span><span class="sxs-lookup"><span data-stu-id="0e378-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e378-123">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0e378-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="0e378-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="0e378-125">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-125">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-126">Categoría de cuadro de diálogo: 0 es el servidor de Lync para el servidor de mediación; 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="0e378-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="0e378-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="0e378-128">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-128">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-129">Marcador que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="0e378-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="0e378-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="0e378-131">int</span><span class="sxs-lookup"><span data-stu-id="0e378-131">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-132">Si está presente, indica por qué no se omitió una llamada aunque los identificadores de omisión coincidan.</span><span class="sxs-lookup"><span data-stu-id="0e378-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="0e378-133">Solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="0e378-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="0e378-134">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0e378-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="0e378-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="0e378-136">int</span><span class="sxs-lookup"><span data-stu-id="0e378-136">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-137">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="0e378-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="0e378-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0e378-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-140">FQDN del grupo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0e378-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="0e378-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="0e378-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0e378-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-143">FQDN del grupo de destinatarios de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-144">Autor de llamada</span><span class="sxs-lookup"><span data-stu-id="0e378-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="0e378-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0e378-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0e378-146">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-147">Destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="0e378-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="0e378-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0e378-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0e378-149">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="0e378-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0e378-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0e378-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-152">Cadena de agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0e378-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0e378-154">smallint</span><span class="sxs-lookup"><span data-stu-id="0e378-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="0e378-155">Tipo del agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="0e378-156">Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0e378-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0e378-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0e378-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0e378-159">Categoría del agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="0e378-160">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="0e378-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0e378-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0e378-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-163">Cadena de agente de usuario de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0e378-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0e378-165">smallint</span><span class="sxs-lookup"><span data-stu-id="0e378-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="0e378-166">Tipo de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-166">Type of callee’s user agent.</span></span> <span data-ttu-id="0e378-167">Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0e378-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0e378-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0e378-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0e378-170">Categoría del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-170">Category of callee’s user agent.</span></span> <span data-ttu-id="0e378-171">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0e378-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0e378-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0e378-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-174">Nombre del punto de conexión de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="0e378-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0e378-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0e378-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-177">Nombre del extremo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="0e378-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="0e378-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-180">Sistema operativo (SO) del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="0e378-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="0e378-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-183">Sistema operativo (SO) del extremo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="0e378-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="0e378-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-186">Nombre de la CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="0e378-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="0e378-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-189">Nombre de la CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="0e378-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="0e378-191">smallint</span><span class="sxs-lookup"><span data-stu-id="0e378-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="0e378-192">Número de núcleos de CPU en el extremo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="0e378-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="0e378-194">smallint</span><span class="sxs-lookup"><span data-stu-id="0e378-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="0e378-195">Número de núcleos de la CPU en el punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="0e378-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="0e378-197">int</span><span class="sxs-lookup"><span data-stu-id="0e378-197">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-198">Velocidad del procesador de CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="0e378-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="0e378-200">int</span><span class="sxs-lookup"><span data-stu-id="0e378-200">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-201">Velocidad del procesador de CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="0e378-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="0e378-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-204">Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="0e378-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="0e378-205">Para obtener más información, consulte la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="0e378-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="0e378-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-208">Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="0e378-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="0e378-209">Para obtener más información, consulte la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="0e378-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e378-211">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="0e378-211">Correlation key.</span></span> <span data-ttu-id="0e378-212">Se hace referencia a ellos desde la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0e378-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="0e378-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="0e378-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-215">Información sobre la ruta multimedia, como Direct o retransmitida.</span><span class="sxs-lookup"><span data-stu-id="0e378-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="0e378-216">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="0e378-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="0e378-218">int</span><span class="sxs-lookup"><span data-stu-id="0e378-218">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-219">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="0e378-220">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="0e378-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="0e378-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="0e378-222">int</span><span class="sxs-lookup"><span data-stu-id="0e378-222">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-223">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="0e378-224">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="0e378-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-225">Transport</span><span class="sxs-lookup"><span data-stu-id="0e378-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="0e378-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-227">Tipo de transporte: 0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="0e378-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="0e378-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0e378-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="0e378-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0e378-230">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-230">IP address of the caller.</span></span> <span data-ttu-id="0e378-231">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="0e378-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="0e378-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="0e378-233">int</span><span class="sxs-lookup"><span data-stu-id="0e378-233">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-234">Puerto usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="0e378-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="0e378-236">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-236">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-237">Indica si la persona que llama está dentro de la red de intervalos: 1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="0e378-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="0e378-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0e378-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="0e378-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0e378-240">Dirección IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0e378-240">IP address of the callee.</span></span> <span data-ttu-id="0e378-241">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="0e378-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="0e378-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="0e378-243">int</span><span class="sxs-lookup"><span data-stu-id="0e378-243">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-244">Puerto usado por el destinatario.</span><span class="sxs-lookup"><span data-stu-id="0e378-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="0e378-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="0e378-246">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-246">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-247">Indica si el destinatario de la llamada está dentro de la red de intervalos: 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="0e378-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="0e378-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="0e378-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-250">Nombre del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="0e378-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="0e378-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-253">Nombre del país o de la región del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="0e378-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="0e378-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-256">Nombre del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="0e378-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="0e378-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0e378-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0e378-259">Nombre del país o región del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="0e378-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0e378-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="0e378-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0e378-262">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="0e378-263">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="0e378-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="0e378-265">int</span><span class="sxs-lookup"><span data-stu-id="0e378-265">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-266">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="0e378-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0e378-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="0e378-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0e378-269">Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="0e378-270">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="0e378-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="0e378-272">int</span><span class="sxs-lookup"><span data-stu-id="0e378-272">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-273">Puerto usado en el servicio de borde A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="0e378-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="0e378-275">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-276">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="0e378-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="0e378-278">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-279">Nombre del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="0e378-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0e378-281">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-282">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="0e378-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="0e378-284">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-285">Nombre del controlador del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="0e378-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="0e378-287">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-288">Nombre del dispositivo de captura de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="0e378-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="0e378-290">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-291">Nombre del dispositivo de representación de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="0e378-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0e378-293">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-294">Nombre del controlador del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="0e378-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="0e378-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0e378-296">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="0e378-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e378-297">Nombre del controlador del dispositivo de representación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="0e378-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="0e378-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-300">Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="0e378-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="0e378-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="0e378-302">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-302">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-303">Indica si la persona que llama se conecta a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="0e378-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="0e378-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="0e378-305">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="0e378-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="0e378-306">Velocidad de vínculo de red para el punto final de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="0e378-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="0e378-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="0e378-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-309">Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="0e378-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="0e378-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="0e378-311">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-311">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-312">Indica si la persona que llama se conecta a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="0e378-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="0e378-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="0e378-314">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="0e378-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="0e378-315">Velocidad de vínculo de red para el punto final de la persona que llama en bps.</span><span class="sxs-lookup"><span data-stu-id="0e378-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="0e378-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="0e378-317">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-318">OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="0e378-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="0e378-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="0e378-320">int</span><span class="sxs-lookup"><span data-stu-id="0e378-320">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-321">El ancho de banda real aplicado a la transmisión de la parte de envío dada proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="0e378-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="0e378-322">Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="0e378-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="0e378-323">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda</span><span class="sxs-lookup"><span data-stu-id="0e378-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="0e378-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="0e378-325">int</span><span class="sxs-lookup"><span data-stu-id="0e378-325">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-326">Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="0e378-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="0e378-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="0e378-328">int</span><span class="sxs-lookup"><span data-stu-id="0e378-328">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-329">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="0e378-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="0e378-331">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="0e378-332">Tasa promedio de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="0e378-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="0e378-334">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="0e378-335">Pérdida máxima de paquetes observadas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="0e378-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="0e378-337">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0e378-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="0e378-338">Densidad promedio de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="0e378-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="0e378-340">int</span><span class="sxs-lookup"><span data-stu-id="0e378-340">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-341">Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="0e378-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="0e378-343">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0e378-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="0e378-344">Densidad media de pérdida de paquetes entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="0e378-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="0e378-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="0e378-346">int</span><span class="sxs-lookup"><span data-stu-id="0e378-346">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-347">Duración media de los huecos entre las ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="0e378-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="0e378-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="0e378-349">int</span><span class="sxs-lookup"><span data-stu-id="0e378-349">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-350">Recuento de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="0e378-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-351">Ancho de banda más</span><span class="sxs-lookup"><span data-stu-id="0e378-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="0e378-352">int</span><span class="sxs-lookup"><span data-stu-id="0e378-352">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-353">Cálculo de ancho de banda para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="0e378-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="0e378-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="0e378-355">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-356">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="0e378-357">El intervalo está comprendido entre 0,0 y 5,0.</span><span class="sxs-lookup"><span data-stu-id="0e378-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="0e378-358">Esta métrica muestra el monto que se redujo en el MOS de red debido a la vibración y a la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="0e378-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="0e378-359">Para una calidad aceptable, debe ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="0e378-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="0e378-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="0e378-361">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-362">La degradación de OP máxima de red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="0e378-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="0e378-364">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-365">Degradación de MOS de red causada por vibración.</span><span class="sxs-lookup"><span data-stu-id="0e378-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="0e378-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="0e378-367">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-368">Degradación de MOS de red causada por pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="0e378-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="0e378-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="0e378-370">int</span><span class="sxs-lookup"><span data-stu-id="0e378-370">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-371">El códec de audio usado para la llamada, al que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0e378-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="0e378-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="0e378-373">int</span><span class="sxs-lookup"><span data-stu-id="0e378-373">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-374">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="0e378-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-376">int</span><span class="sxs-lookup"><span data-stu-id="0e378-376">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-377">Nivel posterior de señal de audio de control de ganancia analógica para el audio enviado por la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="0e378-378">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-379">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="0e378-380">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-382">int</span><span class="sxs-lookup"><span data-stu-id="0e378-382">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-383">Nivel de señal de audio del audio recibido por la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="0e378-384">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-385">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="0e378-386">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-388">int</span><span class="sxs-lookup"><span data-stu-id="0e378-388">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-389">El nivel de ruido de audio de control de ganancia posterior analógico para el audio enviado por la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="0e378-390">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-391">Para obtener una calidad aceptable, debe ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="0e378-392">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-394">int</span><span class="sxs-lookup"><span data-stu-id="0e378-394">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-395">El nivel de ruido de audio de control de ganancia posterior analógico para el audio recibido por la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="0e378-396">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-397">Para obtener una calidad aceptable, debe ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="0e378-398">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="0e378-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="0e378-400">int</span><span class="sxs-lookup"><span data-stu-id="0e378-400">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-401">Return echo Return Enhancement para la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="0e378-402">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="0e378-402">The unit for this metric is dB.</span></span> <span data-ttu-id="0e378-403">Los valores más bajos representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="0e378-403">Lower values represent less echo.</span></span> <span data-ttu-id="0e378-404">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0e378-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0e378-406">int</span><span class="sxs-lookup"><span data-stu-id="0e378-406">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-407">Promedio de problemas por cinco minutos para la representación del altavoz de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="0e378-408">Para obtener una buena calidad, debe ser inferior a un período de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="0e378-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="0e378-409">No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="0e378-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0e378-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0e378-411">int</span><span class="sxs-lookup"><span data-stu-id="0e378-411">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-412">Promedio de problemas por cinco minutos para la captura de micrófono de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="0e378-413">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="0e378-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="0e378-414">No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="0e378-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="0e378-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="0e378-416">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-417">Tasa de desplazamiento del reloj del dispositivo de la persona que llama, en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0e378-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="0e378-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="0e378-419">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-420">Velocidad de desplazamiento del reloj del dispositivo de altavoz del autor de la llamada, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0e378-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="0e378-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="0e378-422">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-423">Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="0e378-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="0e378-425">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-426">Promedio del error de marca de tiempo de la secuencia de representación de altavoces de la persona que llama, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="0e378-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="0e378-428">smallint</span><span class="sxs-lookup"><span data-stu-id="0e378-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="0e378-429">El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="0e378-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="0e378-430">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="0e378-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="0e378-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-433">Causas de un evento de Eco para el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="0e378-434">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="0e378-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="0e378-436">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-437">Porcentaje de tiempo en que se detecta eco en el flujo de captura de micrófono de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="0e378-438">Si se usa un auricular, el valor debe ser bajo.</span><span class="sxs-lookup"><span data-stu-id="0e378-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="0e378-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="0e378-440">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-441">Porcentaje de tiempo durante el que se detecta eco en el flujo enviado de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="0e378-442">Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="0e378-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-444">int</span><span class="sxs-lookup"><span data-stu-id="0e378-444">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-445">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0e378-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="0e378-446">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="0e378-447">Para obtener una buena calidad, el rango aceptable debe ser de-30 a-18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-449">int</span><span class="sxs-lookup"><span data-stu-id="0e378-449">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-450">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="0e378-451">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0e378-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="0e378-452">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="0e378-453">Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="0e378-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="0e378-455">int</span><span class="sxs-lookup"><span data-stu-id="0e378-455">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-456">Control automático de ganancia (AGC) en el servidor de mediación aplicado al audio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="0e378-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="0e378-458">float</span><span class="sxs-lookup"><span data-stu-id="0e378-458">float</span></span></p></td>
<td><p><span data-ttu-id="0e378-459">Cuadrado principal raíz (RMS) de la señal entrante al autor de la llamada durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-461">int</span><span class="sxs-lookup"><span data-stu-id="0e378-461">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-462">Representa el nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="0e378-463">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-464">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="0e378-465">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-467">int</span><span class="sxs-lookup"><span data-stu-id="0e378-467">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-468">Nivel de señal de audio del audio recibido por el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="0e378-469">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-470">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="0e378-471">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-473">int</span><span class="sxs-lookup"><span data-stu-id="0e378-473">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-474">El nivel de ruido de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="0e378-475">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-476">Para obtener una calidad aceptable, debe ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="0e378-477">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-479">int</span><span class="sxs-lookup"><span data-stu-id="0e378-479">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-480">El nivel de ruido de audio de control de ganancia posterior analógico para el audio recibido.</span><span class="sxs-lookup"><span data-stu-id="0e378-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="0e378-481">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="0e378-482">Para obtener una calidad aceptable, debe ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="0e378-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="0e378-483">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="0e378-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="0e378-485">int</span><span class="sxs-lookup"><span data-stu-id="0e378-485">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-486">Return echo Return Enhancement para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="0e378-487">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="0e378-487">The unit for this metric is dB.</span></span> <span data-ttu-id="0e378-488">Los valores más bajos representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="0e378-488">Lower values represent less echo.</span></span> <span data-ttu-id="0e378-489">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="0e378-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0e378-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0e378-491">int</span><span class="sxs-lookup"><span data-stu-id="0e378-491">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-492">Promedio de problemas por cinco minutos para la representación del altavoz de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="0e378-493">Para obtener una buena calidad, debe ser inferior a un período de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="0e378-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="0e378-494">No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="0e378-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0e378-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0e378-496">int</span><span class="sxs-lookup"><span data-stu-id="0e378-496">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-497">Promedio de problemas por cinco minutos para la captura de micrófono de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="0e378-498">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="0e378-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="0e378-499">No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="0e378-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="0e378-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="0e378-501">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-502">Tasa de desplazamiento del reloj del dispositivo de micrófono del destinatario, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0e378-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="0e378-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="0e378-504">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-505">Tasa de desplazamiento del reloj del dispositivo de altavoz de la llamada, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0e378-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="0e378-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="0e378-507">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-508">Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="0e378-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="0e378-510">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-511">Promedio del error de marca de tiempo del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="0e378-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="0e378-513">smallint</span><span class="sxs-lookup"><span data-stu-id="0e378-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="0e378-514">El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="0e378-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="0e378-515">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="0e378-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="0e378-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e378-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e378-518">Causas de un evento de Eco para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="0e378-519">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e378-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="0e378-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="0e378-521">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-522">Porcentaje de tiempo durante el que se detecta eco en el flujo de captura de micrófono de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="0e378-523">Si se usa un auricular, el valor debe ser bajo.</span><span class="sxs-lookup"><span data-stu-id="0e378-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="0e378-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="0e378-525">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-526">Porcentaje de tiempo durante el que se detecta eco en el flujo enviado de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="0e378-527">Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="0e378-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-529">int</span><span class="sxs-lookup"><span data-stu-id="0e378-529">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-530">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0e378-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="0e378-531">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="0e378-532">Para obtener una buena calidad, el rango aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0e378-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0e378-534">int</span><span class="sxs-lookup"><span data-stu-id="0e378-534">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-535">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="0e378-536">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0e378-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="0e378-537">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="0e378-538">Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="0e378-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="0e378-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="0e378-540">int</span><span class="sxs-lookup"><span data-stu-id="0e378-540">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-541">Control automático de ganancia (AGC) en el servidor de mediación aplicado al audio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="0e378-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="0e378-543">float</span><span class="sxs-lookup"><span data-stu-id="0e378-543">float</span></span></p></td>
<td><p><span data-ttu-id="0e378-544">Cuadrado de la media raíz (RMS) de la señal entrante para el destinatario durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="0e378-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="0e378-546">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-547">Relación media entre las muestras ocultas generadas por la corrección de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="0e378-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="0e378-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="0e378-549">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-550">Relación media de muestras extendidas generadas por la recuperación de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="0e378-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="0e378-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="0e378-552">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="0e378-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-553">Relación media de muestras comprimidas generadas por la corrección de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="0e378-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="0e378-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="0e378-555">int</span><span class="sxs-lookup"><span data-stu-id="0e378-555">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-556">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="0e378-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="0e378-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="0e378-558">int</span><span class="sxs-lookup"><span data-stu-id="0e378-558">int</span></span></p></td>
<td><p><span data-ttu-id="0e378-559">Tiempo máximo de ida y vuelta para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="0e378-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="0e378-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="0e378-561">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-562">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="0e378-563">Esta métrica depende de la pérdida del paquete, de la vibración y del códec usado.</span><span class="sxs-lookup"><span data-stu-id="0e378-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="0e378-564">El intervalo está comprendido entre 1,0 y 5,0.</span><span class="sxs-lookup"><span data-stu-id="0e378-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="0e378-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="0e378-566">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-567">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="0e378-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="0e378-569">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-570">Puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluyendo el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="0e378-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="0e378-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="0e378-572">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-573">SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="0e378-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="0e378-575">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-576">Puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluido el nivel de voz, nivel de ruido, códec, condiciones de red y características de dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="0e378-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="0e378-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="0e378-578">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e378-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0e378-579">RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e378-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="0e378-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="0e378-581">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-581">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-582">Indica si se usó el audio FEC para la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e378-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e378-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="0e378-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="0e378-584">bit</span><span class="sxs-lookup"><span data-stu-id="0e378-584">bit</span></span></p></td>
<td><p><span data-ttu-id="0e378-585">Indica la dirección de la información identificada por p; 1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada. 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="0e378-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


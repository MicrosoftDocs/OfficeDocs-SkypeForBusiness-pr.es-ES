---
title: 'Lync Server 2013: vista de VideoStreamDetail'
description: 'Lync Server 2013: vista de VideoStreamDetail.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567976"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="babf5-103">Vista VideoStreamDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="babf5-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="babf5-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="babf5-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="babf5-105">La vista VideoStreamDetail almacena información de todas las secuencias de vídeo en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="babf5-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="babf5-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="babf5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="babf5-107">Columna</span><span class="sxs-lookup"><span data-stu-id="babf5-107">Column</span></span></th>
<th><span data-ttu-id="babf5-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="babf5-108">Data Type</span></span></th>
<th><span data-ttu-id="babf5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="babf5-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="babf5-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="babf5-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="babf5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="babf5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="babf5-112">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="babf5-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="babf5-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="babf5-114">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-114">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-115">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="babf5-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="babf5-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="babf5-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="babf5-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="babf5-118">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="babf5-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-119">StreamId</span><span class="sxs-lookup"><span data-stu-id="babf5-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="babf5-120">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-120">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-121">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="babf5-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="babf5-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="babf5-123">datetime</span><span class="sxs-lookup"><span data-stu-id="babf5-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="babf5-124">Fecha y hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="babf5-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="babf5-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="babf5-126">datetime</span><span class="sxs-lookup"><span data-stu-id="babf5-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="babf5-127">Fecha y hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="babf5-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="babf5-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="babf5-129">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-129">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-130">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="babf5-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="babf5-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-133">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="babf5-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="babf5-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="babf5-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-136">FQDN del grupo de destinatarios de llamadas.</span><span class="sxs-lookup"><span data-stu-id="babf5-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-137">Caller</span><span class="sxs-lookup"><span data-stu-id="babf5-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="babf5-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="babf5-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="babf5-139">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-140">Destinatario</span><span class="sxs-lookup"><span data-stu-id="babf5-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="babf5-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="babf5-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="babf5-142">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="babf5-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="babf5-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-145">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="babf5-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="babf5-147">smallint</span><span class="sxs-lookup"><span data-stu-id="babf5-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="babf5-148">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-148">Type of caller’s user agent.</span></span> <span data-ttu-id="babf5-149">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="babf5-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="babf5-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="babf5-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="babf5-152">Categoría de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-152">Category of caller’s user agent.</span></span> <span data-ttu-id="babf5-153">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="babf5-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="babf5-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-156">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="babf5-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="babf5-158">smallint</span><span class="sxs-lookup"><span data-stu-id="babf5-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="babf5-159">Tipo de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-159">Type of callee’s user agent.</span></span> <span data-ttu-id="babf5-160">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener información.</span><span class="sxs-lookup"><span data-stu-id="babf5-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="babf5-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="babf5-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="babf5-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="babf5-163">Categoría de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-163">Category of callee’s user agent.</span></span> <span data-ttu-id="babf5-164">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="babf5-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="babf5-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-167">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="babf5-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="babf5-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-170">Nombre del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-171">CallerOS</span><span class="sxs-lookup"><span data-stu-id="babf5-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="babf5-172">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-173">Sistema operativo (SO) del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="babf5-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="babf5-175">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-176">Sistema operativo (SO) del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="babf5-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="babf5-178">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-179">Nombre de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="babf5-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="babf5-181">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-182">Nombre de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="babf5-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="babf5-184">smallint</span><span class="sxs-lookup"><span data-stu-id="babf5-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="babf5-185">Número de núcleos de CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="babf5-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="babf5-187">smallint</span><span class="sxs-lookup"><span data-stu-id="babf5-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="babf5-188">Número de núcleos de CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="babf5-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="babf5-190">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-190">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-191">Velocidad del procesador de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="babf5-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="babf5-193">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-193">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-194">Velocidad del procesador de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="babf5-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="babf5-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="babf5-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="babf5-197">Indica si el sistema del autor de la llamada se está ejecutando en un entorno visualizado.</span><span class="sxs-lookup"><span data-stu-id="babf5-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="babf5-198">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="babf5-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="babf5-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="babf5-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="babf5-201">Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="babf5-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="babf5-202">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="babf5-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="babf5-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="babf5-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="babf5-205">Información sobre la ruta de medios, como directa o retransmitida.</span><span class="sxs-lookup"><span data-stu-id="babf5-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="babf5-206">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="babf5-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="babf5-208">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-208">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-p109">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="babf5-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="babf5-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="babf5-212">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-212">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-p110">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="babf5-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-215">Transport</span><span class="sxs-lookup"><span data-stu-id="babf5-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="babf5-216">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-216">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-217">Tipo de transporte: 0 es UDP y 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="babf5-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="babf5-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="babf5-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="babf5-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="babf5-220">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-220">IP address of the caller.</span></span> <span data-ttu-id="babf5-221">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="babf5-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="babf5-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="babf5-223">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-223">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-224">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="babf5-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="babf5-226">bit</span><span class="sxs-lookup"><span data-stu-id="babf5-226">bit</span></span></p></td>
<td><p><span data-ttu-id="babf5-p112">Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</span><span class="sxs-lookup"><span data-stu-id="babf5-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="babf5-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="babf5-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="babf5-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="babf5-231">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-231">IP address of the callee.</span></span> <span data-ttu-id="babf5-232">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="babf5-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="babf5-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="babf5-234">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-234">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-235">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="babf5-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="babf5-237">bit</span><span class="sxs-lookup"><span data-stu-id="babf5-237">bit</span></span></p></td>
<td><p><span data-ttu-id="babf5-238">Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el destinatario de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</span><span class="sxs-lookup"><span data-stu-id="babf5-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="babf5-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="babf5-240">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-241">Nombre del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="babf5-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="babf5-243">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-244">Nombre del país o región del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="babf5-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="babf5-246">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-247">Nombre del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="babf5-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="babf5-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="babf5-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="babf5-250">Nombre del país o la región del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="babf5-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="babf5-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="babf5-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="babf5-253">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="babf5-254">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="babf5-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="babf5-256">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-256">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-257">Puerto en el servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="babf5-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="babf5-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="babf5-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="babf5-260">Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="babf5-261">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="babf5-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="babf5-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="babf5-263">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-263">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-264">Puerto en el servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="babf5-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="babf5-266">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-267">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="babf5-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="babf5-269">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-270">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="babf5-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="babf5-272">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-273">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="babf5-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="babf5-275">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-276">Nombre del controlador dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="babf5-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="babf5-278">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-279">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="babf5-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="babf5-281">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-282">Nombre del dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="babf5-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="babf5-284">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-285">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="babf5-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="babf5-287">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="babf5-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="babf5-288">Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="babf5-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="babf5-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="babf5-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="babf5-291">Tipo de conexión de red del autor de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="babf5-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="babf5-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="babf5-293">bit</span><span class="sxs-lookup"><span data-stu-id="babf5-293">bit</span></span></p></td>
<td><p><span data-ttu-id="babf5-p116">Indica si el autor de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</span><span class="sxs-lookup"><span data-stu-id="babf5-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="babf5-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="babf5-297">decimal (18)</span><span class="sxs-lookup"><span data-stu-id="babf5-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="babf5-298">Velocidad del vínculo de red del extremo del autor de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="babf5-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="babf5-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="babf5-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="babf5-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="babf5-301">Tipo de conexión de red del destinatario de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="babf5-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="babf5-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="babf5-303">bit</span><span class="sxs-lookup"><span data-stu-id="babf5-303">bit</span></span></p></td>
<td><p><span data-ttu-id="babf5-p117">Indica si el destinatario de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</span><span class="sxs-lookup"><span data-stu-id="babf5-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="babf5-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="babf5-307">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="babf5-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="babf5-308">Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="babf5-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="babf5-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="babf5-310">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="babf5-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="babf5-311">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="babf5-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="babf5-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="babf5-313">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-313">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-p118">Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="babf5-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="babf5-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="babf5-318">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-318">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-319">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="babf5-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="babf5-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="babf5-321">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-321">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-322">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-323">Vuelta</span><span class="sxs-lookup"><span data-stu-id="babf5-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="babf5-324">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-324">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-325">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="babf5-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="babf5-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="babf5-327">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-327">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-328">Tiempo de ida y vuelta máximo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="babf5-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="babf5-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="babf5-330">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="babf5-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="babf5-331">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="babf5-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="babf5-333">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="babf5-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="babf5-334">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="babf5-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="babf5-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="babf5-336">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-336">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-337">Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="babf5-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-338">Ancho de banda más</span><span class="sxs-lookup"><span data-stu-id="babf5-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="babf5-339">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-339">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-340">Previsiones de ancho de banda de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="babf5-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="babf5-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="babf5-342">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-342">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-343">Códec de audio usado para la llamada, a la que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="babf5-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-344">Resolución de</span><span class="sxs-lookup"><span data-stu-id="babf5-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="babf5-345">Char (9)</span><span class="sxs-lookup"><span data-stu-id="babf5-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="babf5-p119">Resolución del vídeo en píxeles de ancho multiplicados por píxeles de alto. Se proporciona como cadena.</span><span class="sxs-lookup"><span data-stu-id="babf5-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="babf5-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="babf5-349">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-349">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-350">Tasa de bits media de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="babf5-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="babf5-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="babf5-352">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="babf5-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="babf5-353">Tasa de fotogramas de vídeo recibida.</span><span class="sxs-lookup"><span data-stu-id="babf5-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="babf5-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="babf5-355">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="babf5-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="babf5-356">Tasa de fotogramas de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="babf5-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="babf5-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="babf5-358">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-358">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-359">Tasa de bits de vídeo máxima durante la sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="babf5-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="babf5-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="babf5-361">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="babf5-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="babf5-362">Tasa a la que se perdieron los paquetes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="babf5-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="babf5-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="babf5-364">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="babf5-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="babf5-365">Porcentaje del total de fotogramas de vídeo que se pierde.</span><span class="sxs-lookup"><span data-stu-id="babf5-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="babf5-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="babf5-367">bit</span><span class="sxs-lookup"><span data-stu-id="babf5-367">bit</span></span></p></td>
<td><p><span data-ttu-id="babf5-368">No se usa.</span><span class="sxs-lookup"><span data-stu-id="babf5-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="babf5-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="babf5-370">entero</span><span class="sxs-lookup"><span data-stu-id="babf5-370">int</span></span></p></td>
<td><p><span data-ttu-id="babf5-371">Cantidad máxima del ancho de banda asignada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="babf5-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="babf5-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="babf5-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="babf5-373">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="babf5-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="babf5-374">Porcentaje del total de fotogramas de vídeo que se perdió.</span><span class="sxs-lookup"><span data-stu-id="babf5-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="babf5-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="babf5-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="babf5-376">bit</span><span class="sxs-lookup"><span data-stu-id="babf5-376">bit</span></span></p></td>
<td><p><span data-ttu-id="babf5-p120">Dirección de secuencia de la información de identidad p-asserted. El valor 1 indica que la dirección de la secuencia es del autor de la llamada al destinatario; y 0 significa del destinatario al autor.</span><span class="sxs-lookup"><span data-stu-id="babf5-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


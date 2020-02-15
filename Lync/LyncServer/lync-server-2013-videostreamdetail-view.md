---
title: 'Lync Server 2013: vista de VideoStreamDetail'
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
ms.openlocfilehash: 311fb8fcd750261dbb5ef2e579fb092781526a19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="9f7f0-102">Vista VideoStreamDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f7f0-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f7f0-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9f7f0-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9f7f0-104">La vista VideoStreamDetail almacena información de todas las secuencias de vídeo en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="9f7f0-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f7f0-106">Columna</span><span class="sxs-lookup"><span data-stu-id="9f7f0-106">Column</span></span></th>
<th><span data-ttu-id="9f7f0-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9f7f0-107">Data Type</span></span></th>
<th><span data-ttu-id="9f7f0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f7f0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="9f7f0-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9f7f0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-111">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="9f7f0-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-113">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-113">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="9f7f0-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="9f7f0-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-119">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-119">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-120">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="9f7f0-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-122">datetime</span><span class="sxs-lookup"><span data-stu-id="9f7f0-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-123">Fecha y hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="9f7f0-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-125">datetime</span><span class="sxs-lookup"><span data-stu-id="9f7f0-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-126">Fecha y hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="9f7f0-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-128">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-128">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-129">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="9f7f0-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-132">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="9f7f0-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-135">FQDN del grupo de destinatarios de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-136">Caller</span><span class="sxs-lookup"><span data-stu-id="9f7f0-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-138">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-139">Destinatario</span><span class="sxs-lookup"><span data-stu-id="9f7f0-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-141">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="9f7f0-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-144">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9f7f0-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-146">smallint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-147">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-147">Type of caller’s user agent.</span></span> <span data-ttu-id="9f7f0-148">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9f7f0-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-151">Categoría de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-151">Category of caller’s user agent.</span></span> <span data-ttu-id="9f7f0-152">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="9f7f0-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-155">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9f7f0-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-157">smallint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-158">Tipo de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-158">Type of callee’s user agent.</span></span> <span data-ttu-id="9f7f0-159">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9f7f0-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-162">Categoría de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-162">Category of callee’s user agent.</span></span> <span data-ttu-id="9f7f0-163">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-166">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-169">Nombre del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="9f7f0-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-172">Sistema operativo (SO) del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="9f7f0-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-175">Sistema operativo (SO) del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="9f7f0-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-178">Nombre de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="9f7f0-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-181">Nombre de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="9f7f0-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-183">smallint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-184">Número de núcleos de CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="9f7f0-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-186">smallint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-187">Número de núcleos de CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="9f7f0-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-189">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-189">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-190">Velocidad del procesador de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="9f7f0-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-192">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-192">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-193">Velocidad del procesador de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="9f7f0-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-196">Indica si el sistema del autor de la llamada se está ejecutando en un entorno visualizado.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="9f7f0-197">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="9f7f0-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-200">Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="9f7f0-201">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="9f7f0-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-204">Información sobre la ruta de medios, como directa o retransmitida.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="9f7f0-205">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="9f7f0-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-207">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-207">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p109">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="9f7f0-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-211">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-211">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p110">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-214">Transport</span><span class="sxs-lookup"><span data-stu-id="9f7f0-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-215">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-215">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-216">Tipo de transporte: 0 es UDP y 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f7f0-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-219">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-219">IP address of the caller.</span></span> <span data-ttu-id="9f7f0-220">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="9f7f0-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-222">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-222">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-223">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="9f7f0-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-225">bit</span><span class="sxs-lookup"><span data-stu-id="9f7f0-225">bit</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p112">Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f7f0-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-230">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-230">IP address of the callee.</span></span> <span data-ttu-id="9f7f0-231">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="9f7f0-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-233">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-233">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-234">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="9f7f0-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-236">bit</span><span class="sxs-lookup"><span data-stu-id="9f7f0-236">bit</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-237">Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el destinatario de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="9f7f0-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-240">Nombre del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="9f7f0-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-243">Nombre del país o región del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="9f7f0-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-246">Nombre del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="9f7f0-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f7f0-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-249">Nombre del país o la región del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f7f0-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-252">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="9f7f0-253">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="9f7f0-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-255">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-255">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-256">Puerto en el servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f7f0-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-259">Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="9f7f0-260">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="9f7f0-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-262">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-262">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-263">Puerto en el servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="9f7f0-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-265">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-266">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="9f7f0-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-268">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-269">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f7f0-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-271">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-272">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f7f0-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-274">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-275">Nombre del controlador dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="9f7f0-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-277">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-278">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="9f7f0-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-280">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-281">Nombre del dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f7f0-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-283">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-284">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f7f0-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-286">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-287">Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="9f7f0-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-290">Tipo de conexión de red del autor de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="9f7f0-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-292">bit</span><span class="sxs-lookup"><span data-stu-id="9f7f0-292">bit</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p116">Indica si el autor de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="9f7f0-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-296">decimal (18)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-297">Velocidad del vínculo de red del extremo del autor de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="9f7f0-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f7f0-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-300">Tipo de conexión de red del destinatario de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="9f7f0-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-302">bit</span><span class="sxs-lookup"><span data-stu-id="9f7f0-302">bit</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p117">Indica si el destinatario de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="9f7f0-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-306">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-307">Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="9f7f0-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-309">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-310">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="9f7f0-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="9f7f0-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-312">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-312">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p118">Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="9f7f0-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-317">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-317">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-318">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="9f7f0-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="9f7f0-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-320">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-320">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-321">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-322">Vuelta</span><span class="sxs-lookup"><span data-stu-id="9f7f0-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-323">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-323">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-324">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="9f7f0-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-326">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-326">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-327">Tiempo de ida y vuelta máximo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="9f7f0-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-329">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-330">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="9f7f0-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-332">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-333">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="9f7f0-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-335">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-335">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-336">Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="9f7f0-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-337">Ancho de banda más</span><span class="sxs-lookup"><span data-stu-id="9f7f0-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-338">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-338">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-339">Previsiones de ancho de banda de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="9f7f0-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-341">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-341">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-342">Códec de audio usado para la llamada, a la que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-343">Resolución de</span><span class="sxs-lookup"><span data-stu-id="9f7f0-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-344">Char (9)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p119">Resolución del vídeo en píxeles de ancho multiplicados por píxeles de alto. Se proporciona como cadena.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="9f7f0-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-348">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-348">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-349">Tasa de bits media de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="9f7f0-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-351">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-352">Tasa de fotogramas de vídeo recibida.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="9f7f0-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-354">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-355">Tasa de fotogramas de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="9f7f0-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-357">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-357">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-358">Tasa de bits de vídeo máxima durante la sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="9f7f0-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-360">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-361">Tasa a la que se perdieron los paquetes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="9f7f0-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-363">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-364">Porcentaje del total de fotogramas de vídeo que se pierde.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="9f7f0-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-366">bit</span><span class="sxs-lookup"><span data-stu-id="9f7f0-366">bit</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-367">No se usa.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="9f7f0-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-369">int</span><span class="sxs-lookup"><span data-stu-id="9f7f0-369">int</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-370">Cantidad máxima del ancho de banda asignada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7f0-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="9f7f0-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-372">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="9f7f0-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-373">Porcentaje del total de fotogramas de vídeo que se perdió.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7f0-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="9f7f0-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-375">bit</span><span class="sxs-lookup"><span data-stu-id="9f7f0-375">bit</span></span></p></td>
<td><p><span data-ttu-id="9f7f0-p120">Dirección de secuencia de la información de identidad p-asserted. El valor 1 indica que la dirección de la secuencia es del autor de la llamada al destinatario; y 0 significa del destinatario al autor.</span><span class="sxs-lookup"><span data-stu-id="9f7f0-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


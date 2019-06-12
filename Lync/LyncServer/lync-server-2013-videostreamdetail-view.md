---
title: 'Lync Server 2013: vista VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="b7dca-102">Vista VideoStreamDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7dca-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7dca-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b7dca-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b7dca-104">La vista VideoStreamDetail almacena información acerca de cada secuencia de vídeo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b7dca-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="b7dca-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7dca-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7dca-106">Columna</span><span class="sxs-lookup"><span data-stu-id="b7dca-106">Column</span></span></th>
<th><span data-ttu-id="b7dca-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b7dca-107">Data Type</span></span></th>
<th><span data-ttu-id="b7dca-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7dca-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="b7dca-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="b7dca-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b7dca-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b7dca-111">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b7dca-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="b7dca-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="b7dca-113">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-113">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-114">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b7dca-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="b7dca-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="b7dca-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7dca-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-117">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b7dca-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="b7dca-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="b7dca-119">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-119">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-120">IDENTIFICADOR exclusivo dentro de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="b7dca-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="b7dca-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b7dca-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b7dca-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="b7dca-123">Hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="b7dca-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="b7dca-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b7dca-125">datetime</span><span class="sxs-lookup"><span data-stu-id="b7dca-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="b7dca-126">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="b7dca-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="b7dca-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="b7dca-128">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-128">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-129">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b7dca-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b7dca-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-132">FQDN del grupo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b7dca-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b7dca-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b7dca-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-135">FQDN del grupo de destinatarios de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-136">Autor de llamada</span><span class="sxs-lookup"><span data-stu-id="b7dca-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="b7dca-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b7dca-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-138">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-139">Destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="b7dca-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="b7dca-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b7dca-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-141">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b7dca-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b7dca-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-144">Cadena de agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b7dca-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b7dca-146">smallint</span><span class="sxs-lookup"><span data-stu-id="b7dca-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-147">Tipo de agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-147">Type of caller’s user agent.</span></span> <span data-ttu-id="b7dca-148">Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b7dca-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b7dca-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b7dca-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-151">Categoría del agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-151">Category of caller’s user agent.</span></span> <span data-ttu-id="b7dca-152">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b7dca-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b7dca-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-155">Cadena de agente de usuario de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b7dca-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b7dca-157">smallint</span><span class="sxs-lookup"><span data-stu-id="b7dca-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-158">Tipo de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-158">Type of callee’s user agent.</span></span> <span data-ttu-id="b7dca-159">Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b7dca-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b7dca-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b7dca-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-162">Categoría del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-162">Category of callee’s user agent.</span></span> <span data-ttu-id="b7dca-163">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b7dca-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-166">Nombre del punto de conexión de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b7dca-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-169">Nombre del extremo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="b7dca-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="b7dca-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-172">Sistema operativo (SO) del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="b7dca-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="b7dca-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-175">Sistema operativo (SO) del extremo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="b7dca-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="b7dca-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-178">Nombre de la CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="b7dca-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="b7dca-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-181">Nombre de la CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="b7dca-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="b7dca-183">smallint</span><span class="sxs-lookup"><span data-stu-id="b7dca-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-184">Número de núcleos de CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="b7dca-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="b7dca-186">smallint</span><span class="sxs-lookup"><span data-stu-id="b7dca-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-187">Número de núcleos de CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="b7dca-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="b7dca-189">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-189">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-190">Velocidad del procesador de CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="b7dca-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="b7dca-192">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-192">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-193">Velocidad del procesador de CPU del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="b7dca-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="b7dca-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7dca-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-196">Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="b7dca-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="b7dca-197">Para obtener más información, consulte la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="b7dca-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="b7dca-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7dca-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-200">Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="b7dca-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="b7dca-201">Para obtener más información, consulte la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="b7dca-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="b7dca-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7dca-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-204">Información sobre la ruta multimedia, como Direct o retransmitida.</span><span class="sxs-lookup"><span data-stu-id="b7dca-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="b7dca-205">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="b7dca-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="b7dca-207">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-207">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-208">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="b7dca-209">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="b7dca-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="b7dca-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="b7dca-211">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-211">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-212">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="b7dca-213">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="b7dca-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-214">Transport</span><span class="sxs-lookup"><span data-stu-id="b7dca-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="b7dca-215">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-215">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-216">Tipo de transporte: 0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="b7dca-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="b7dca-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b7dca-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="b7dca-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-219">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-219">IP address of the caller.</span></span> <span data-ttu-id="b7dca-220">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="b7dca-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="b7dca-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="b7dca-222">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-222">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-223">Puerto usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="b7dca-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="b7dca-225">bit</span><span class="sxs-lookup"><span data-stu-id="b7dca-225">bit</span></span></p></td>
<td><p><span data-ttu-id="b7dca-226">Indica si la persona que llama está dentro de la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="b7dca-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="b7dca-227">1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="b7dca-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="b7dca-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b7dca-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="b7dca-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-230">Dirección IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b7dca-230">IP address of the callee.</span></span> <span data-ttu-id="b7dca-231">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="b7dca-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="b7dca-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="b7dca-233">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-233">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-234">Puerto usado por el destinatario.</span><span class="sxs-lookup"><span data-stu-id="b7dca-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="b7dca-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="b7dca-236">bit</span><span class="sxs-lookup"><span data-stu-id="b7dca-236">bit</span></span></p></td>
<td><p><span data-ttu-id="b7dca-237">Indica si la persona que llama está dentro de la red de la organización. 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="b7dca-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="b7dca-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="b7dca-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-240">Nombre del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="b7dca-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="b7dca-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-243">Nombre del país o de la región del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="b7dca-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="b7dca-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-246">Nombre del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="b7dca-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="b7dca-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7dca-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-249">Nombre del país o región del sitio de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="b7dca-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b7dca-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="b7dca-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-252">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="b7dca-253">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="b7dca-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="b7dca-255">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-255">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-256">Puerto en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="b7dca-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b7dca-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="b7dca-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-259">Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="b7dca-260">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b7dca-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="b7dca-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="b7dca-262">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-262">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-263">Puerto del servicio perimetral A/V usado por el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="b7dca-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="b7dca-265">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-266">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="b7dca-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="b7dca-268">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-269">Nombre del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="b7dca-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b7dca-271">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-272">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="b7dca-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b7dca-274">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-275">Nombre del controlador del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="b7dca-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="b7dca-277">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-278">Nombre del dispositivo de captura de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="b7dca-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="b7dca-280">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-281">Nombre del dispositivo de representación de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="b7dca-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b7dca-283">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-284">Nombre del controlador del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="b7dca-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="b7dca-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b7dca-286">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b7dca-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-287">Nombre del controlador del dispositivo de representación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="b7dca-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="b7dca-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7dca-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-290">Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="b7dca-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="b7dca-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="b7dca-292">bit</span><span class="sxs-lookup"><span data-stu-id="b7dca-292">bit</span></span></p></td>
<td><p><span data-ttu-id="b7dca-293">Indica si el autor de la llamada se ha conectado a través de una red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="b7dca-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="b7dca-294">1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="b7dca-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="b7dca-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="b7dca-296">decimal (18;)</span><span class="sxs-lookup"><span data-stu-id="b7dca-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-297">Velocidad de vínculo de red para el punto final de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="b7dca-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="b7dca-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="b7dca-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7dca-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7dca-300">Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="b7dca-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="b7dca-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="b7dca-302">bit</span><span class="sxs-lookup"><span data-stu-id="b7dca-302">bit</span></span></p></td>
<td><p><span data-ttu-id="b7dca-303">Indica si el destinatario de la llamada se conecta a través de una red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="b7dca-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="b7dca-304">1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="b7dca-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="b7dca-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="b7dca-306">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="b7dca-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-307">Velocidad de vínculo de red del extremo de la persona que llama (en bps).</span><span class="sxs-lookup"><span data-stu-id="b7dca-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="b7dca-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="b7dca-309">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b7dca-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-310">OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="b7dca-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="b7dca-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="b7dca-312">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-312">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-313">El ancho de banda real aplicado a la transmisión de la parte de envío dada proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="b7dca-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="b7dca-314">Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="b7dca-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="b7dca-315">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="b7dca-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="b7dca-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="b7dca-317">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-317">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-318">Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="b7dca-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="b7dca-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="b7dca-320">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-320">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-321">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="b7dca-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="b7dca-323">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-323">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-324">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="b7dca-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="b7dca-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="b7dca-326">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-326">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-327">Tiempo máximo de ida y vuelta para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="b7dca-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="b7dca-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="b7dca-329">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="b7dca-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-330">Tasa promedio de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="b7dca-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="b7dca-332">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="b7dca-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-333">Pérdida máxima de paquetes observadas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="b7dca-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="b7dca-335">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-335">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-336">Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="b7dca-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-337">Ancho de banda más</span><span class="sxs-lookup"><span data-stu-id="b7dca-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="b7dca-338">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-338">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-339">Cálculo de ancho de banda para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="b7dca-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="b7dca-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="b7dca-341">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-341">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-342">Códec de audio usado para la llamada, al que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b7dca-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-343">Resolución de la</span><span class="sxs-lookup"><span data-stu-id="b7dca-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="b7dca-344">carácter (9)</span><span class="sxs-lookup"><span data-stu-id="b7dca-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-345">Resolución del vídeo en píxeles ancho multiplicado por píxeles alto.</span><span class="sxs-lookup"><span data-stu-id="b7dca-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="b7dca-346">Se ha notificado como una cadena.</span><span class="sxs-lookup"><span data-stu-id="b7dca-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="b7dca-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="b7dca-348">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-348">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-349">Promedio de velocidad de bits de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b7dca-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="b7dca-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="b7dca-351">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b7dca-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-352">Velocidad de fotogramas de video recibido.</span><span class="sxs-lookup"><span data-stu-id="b7dca-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="b7dca-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="b7dca-354">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b7dca-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-355">Velocidad de fotogramas enviada.</span><span class="sxs-lookup"><span data-stu-id="b7dca-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="b7dca-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="b7dca-357">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-357">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-358">Máxima tasa de bits de vídeo durante la sesión de video.</span><span class="sxs-lookup"><span data-stu-id="b7dca-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-359">Tasa</span><span class="sxs-lookup"><span data-stu-id="b7dca-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="b7dca-360">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b7dca-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-361">Velocidad a la que se han perdido paquetes de video.</span><span class="sxs-lookup"><span data-stu-id="b7dca-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="b7dca-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="b7dca-363">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="b7dca-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-364">Porcentaje de fotogramas de video totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="b7dca-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="b7dca-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="b7dca-366">bit</span><span class="sxs-lookup"><span data-stu-id="b7dca-366">bit</span></span></p></td>
<td><p><span data-ttu-id="b7dca-367">No usado.</span><span class="sxs-lookup"><span data-stu-id="b7dca-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="b7dca-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="b7dca-369">int</span><span class="sxs-lookup"><span data-stu-id="b7dca-369">int</span></span></p></td>
<td><p><span data-ttu-id="b7dca-370">Cantidad promedio de ancho de banda asignado para el vídeo.</span><span class="sxs-lookup"><span data-stu-id="b7dca-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dca-371">Media</span><span class="sxs-lookup"><span data-stu-id="b7dca-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="b7dca-372">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="b7dca-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="b7dca-373">Porcentaje de fotogramas de video totales que se han perdido.</span><span class="sxs-lookup"><span data-stu-id="b7dca-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dca-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="b7dca-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b7dca-375">bit</span><span class="sxs-lookup"><span data-stu-id="b7dca-375">bit</span></span></p></td>
<td><p><span data-ttu-id="b7dca-376">Dirección de la secuencia para la información de identidad declarada en p.</span><span class="sxs-lookup"><span data-stu-id="b7dca-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="b7dca-377">1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada. 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="b7dca-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


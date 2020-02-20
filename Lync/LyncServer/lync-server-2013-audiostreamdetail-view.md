---
title: 'Lync Server 2013: vista de AudioStreamDetail'
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
ms.openlocfilehash: b69cdbbe7a4635e60e5912e6f41d2f089612b30a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="a7dfb-102">Vista AudioStreamDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7dfb-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7dfb-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a7dfb-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a7dfb-104">La vista AudioStreamDetail almacena información sobre cada secuencia de audio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="a7dfb-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7dfb-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a7dfb-106">Column</span></span></th>
<th><span data-ttu-id="a7dfb-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a7dfb-107">Data Type</span></span></th>
<th><span data-ttu-id="a7dfb-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="a7dfb-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="a7dfb-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a7dfb-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-111">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="a7dfb-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-113">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-113">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="a7dfb-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-116">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-116">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-117">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="a7dfb-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-119">datetime</span><span class="sxs-lookup"><span data-stu-id="a7dfb-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-120">Fecha y hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="a7dfb-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a7dfb-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-123">Fecha y hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="a7dfb-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-125">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-125">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-126">Categoría del cuadro de diálogo: 0 es el segmento del servidor de mediación de Lync. 1 es el servidor de mediación a la pierna de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="a7dfb-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-128">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-128">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-129">Marca que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="a7dfb-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-131">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-131">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-132">Si está presente, indica por qué no se omitió una llamada incluso si coinciden los identificadores de omisión.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="a7dfb-133">Solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="a7dfb-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="a7dfb-134">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="a7dfb-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-136">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-136">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-137">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="a7dfb-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-140">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="a7dfb-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-143">FQDN del grupo de destinatarios de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-144">Caller</span><span class="sxs-lookup"><span data-stu-id="a7dfb-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-146">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-147">Destinatario</span><span class="sxs-lookup"><span data-stu-id="a7dfb-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-149">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="a7dfb-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-152">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="a7dfb-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-154">smallint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-155">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="a7dfb-156">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="a7dfb-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-159">Categoría del agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="a7dfb-160">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="a7dfb-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-163">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="a7dfb-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-165">smallint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-166">Tipo de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-166">Type of callee’s user agent.</span></span> <span data-ttu-id="a7dfb-167">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="a7dfb-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-170">Categoría de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-170">Category of callee’s user agent.</span></span> <span data-ttu-id="a7dfb-171">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-174">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-177">Nombre del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-180">Sistema operativo (SO) del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-183">Sistema operativo (SO) del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="a7dfb-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-186">Nombre de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="a7dfb-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-189">Nombre de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="a7dfb-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-191">smallint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-192">Número de núcleos de CPU en el extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="a7dfb-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-194">smallint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-195">Número de núcleos de CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="a7dfb-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-197">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-197">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-198">Velocidad del procesador de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="a7dfb-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-200">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-200">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-201">Velocidad del procesador de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="a7dfb-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-204">Indica si el sistema del autor de la llamada se está ejecutando en un entorno visualizado.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="a7dfb-205">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="a7dfb-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-208">Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="a7dfb-209">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="a7dfb-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a7dfb-211">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-211">Correlation key.</span></span> <span data-ttu-id="a7dfb-212">Referencia de la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="a7dfb-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-215">Información sobre la ruta de medios, como directa o retransmitida.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="a7dfb-216">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="a7dfb-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-218">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-218">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-p111">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="a7dfb-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-222">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-222">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-p112">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-225">Transport</span><span class="sxs-lookup"><span data-stu-id="a7dfb-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-227">Tipo de transporte: 0 es UDP y 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="a7dfb-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-230">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-230">IP address of the caller.</span></span> <span data-ttu-id="a7dfb-231">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="a7dfb-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-233">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-233">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-234">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="a7dfb-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-236">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-236">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-237">Indica si el autor de la llamada está dentro de la red del intervalo: 1 significa que el autor de la llamada está dentro de la red de la empresa, 0 significa que el autor de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="a7dfb-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-240">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-240">IP address of the callee.</span></span> <span data-ttu-id="a7dfb-241">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="a7dfb-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-243">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-243">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-244">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="a7dfb-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-246">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-246">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-247">Indica si el destinatario de la llamada está dentro de la red del intervalo: 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="a7dfb-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-250">Nombre del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="a7dfb-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-253">Nombre del país o región del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="a7dfb-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-256">Nombre del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="a7dfb-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a7dfb-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-259">Nombre del país o la región del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="a7dfb-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-262">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="a7dfb-263">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="a7dfb-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-265">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-265">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-266">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="a7dfb-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-269">Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="a7dfb-270">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="a7dfb-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-272">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-272">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-273">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="a7dfb-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-275">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-276">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="a7dfb-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-278">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-279">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="a7dfb-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-281">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-282">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="a7dfb-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-284">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-285">Nombre del controlador dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="a7dfb-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-287">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-288">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="a7dfb-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-290">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-291">Nombre de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="a7dfb-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-293">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-294">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="a7dfb-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-296">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-297">Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="a7dfb-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-300">Tipo de conexión de red del autor de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="a7dfb-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-302">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-302">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-303">Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="a7dfb-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-305">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-306">Velocidad del vínculo de red del extremo del autor de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="a7dfb-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-309">Tipo de conexión de red del destinatario de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="a7dfb-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-311">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-311">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-312">Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="a7dfb-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-314">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-315">Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-317">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-318">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="a7dfb-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-320">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-320">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-321">Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.).</span><span class="sxs-lookup"><span data-stu-id="a7dfb-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="a7dfb-322">No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="a7dfb-323">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda</span><span class="sxs-lookup"><span data-stu-id="a7dfb-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="a7dfb-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-325">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-325">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-326">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="a7dfb-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="a7dfb-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-328">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-328">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-329">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="a7dfb-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-331">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-332">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="a7dfb-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-334">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-335">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-336">Densidad</span><span class="sxs-lookup"><span data-stu-id="a7dfb-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-337">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-338">Densidad media de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="a7dfb-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-340">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-340">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-341">Duración media de la pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="a7dfb-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-343">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-344">Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="a7dfb-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-346">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-346">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-347">Duración media de brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="a7dfb-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-349">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-349">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-350">Número de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-351">Ancho de banda más</span><span class="sxs-lookup"><span data-stu-id="a7dfb-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-352">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-352">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-353">Previsiones de ancho de banda de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="a7dfb-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-355">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-356">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="a7dfb-357">El intervalo es de 0,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="a7dfb-358">Esta métrica muestra la cantidad de MOS de red que se redujo debido a la vibración y pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="a7dfb-359">Para una calidad aceptable, debe ser inferior a 0,5.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="a7dfb-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-361">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-362">Degradación de MOS de red máxima durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="a7dfb-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-364">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-365">Degradación de MOS de red causada por la vibración.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="a7dfb-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-367">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-368">Degradación de MOS de red causada por la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="a7dfb-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-370">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-370">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-371">El códec de audio usado para la llamada, al que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="a7dfb-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-373">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-373">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-374">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-376">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-376">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-377">Nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="a7dfb-378">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-379">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="a7dfb-380">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-382">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-382">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-383">Nivel de señal de audio para el audio que el autor de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="a7dfb-384">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-385">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="a7dfb-386">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-388">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-388">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-389">El nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="a7dfb-390">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-391">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="a7dfb-392">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-394">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-394">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-395">El nivel de ruido de audio del control de ganancia posterior analógico para el audio que ha recibido la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="a7dfb-396">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-397">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="a7dfb-398">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="a7dfb-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-400">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-400">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-401">Devolución de pérdida eco mejora para el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="a7dfb-402">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-402">The unit for this metric is dB.</span></span> <span data-ttu-id="a7dfb-403">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-403">Lower values represent less echo.</span></span> <span data-ttu-id="a7dfb-404">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="a7dfb-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-406">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-406">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-407">Media de problemas por cinco minutos para la representación del altavoz del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="a7dfb-408">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="a7dfb-409">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="a7dfb-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-411">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-411">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-412">Media de problemas por cinco minutos para la captura del micrófono del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="a7dfb-413">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="a7dfb-414">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="a7dfb-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-416">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-417">Tasa de desplazamiento del reloj del dispositivo de micrófono del autor de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="a7dfb-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-419">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-420">Tasa de desplazamiento del reloj del dispositivo de altavoz del autor de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="a7dfb-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-422">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-423">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="a7dfb-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-425">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-426">Promedio del error de marca de tiempo de la secuencia de representación del altavoz del autor de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="a7dfb-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-428">smallint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-429">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="a7dfb-430">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="a7dfb-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-433">Causas de un evento de Eco para el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="a7dfb-434">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="a7dfb-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-436">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-437">Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="a7dfb-438">Si se usa el casco, el valor debería ser bajo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="a7dfb-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-440">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-441">Porcentaje de tiempo en que se detecta el eco en la secuencia enviada del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="a7dfb-442">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-444">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-444">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-445">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="a7dfb-446">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a7dfb-447">Para obtener una buena calidad, el intervalo aceptable debe ser de-30 a-18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-449">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-449">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-450">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="a7dfb-451">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="a7dfb-452">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a7dfb-453">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="a7dfb-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-455">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-455">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-456">Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-458">float</span><span class="sxs-lookup"><span data-stu-id="a7dfb-458">float</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-459">Cuadrado raíz medio (RMS) de la señal entrante al autor de la llamada durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-461">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-461">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-462">Representa el nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="a7dfb-463">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-464">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="a7dfb-465">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-467">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-467">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-468">Nivel de señal de audio para el audio que el destinatario de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="a7dfb-469">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-470">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="a7dfb-471">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-473">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-473">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-474">Nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="a7dfb-475">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-476">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="a7dfb-477">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-479">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-479">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-480">Nivel de ruido de audio del control de ganancia posterior analógico para el audio que el destinatario de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="a7dfb-481">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a7dfb-482">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="a7dfb-483">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="a7dfb-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-485">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-485">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-486">Devolución de pérdida de Eco para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="a7dfb-487">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-487">The unit for this metric is dB.</span></span> <span data-ttu-id="a7dfb-488">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-488">Lower values represent less echo.</span></span> <span data-ttu-id="a7dfb-489">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="a7dfb-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-491">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-491">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-492">Media de problemas por cinco minutos para la representación del altavoz del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="a7dfb-493">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="a7dfb-494">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="a7dfb-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-496">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-496">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-497">Media de problemas por cinco minutos para la captura del micrófono del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="a7dfb-498">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="a7dfb-499">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="a7dfb-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-501">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-502">Tasa de desplazamiento del reloj del dispositivo de micrófono del destinatario de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="a7dfb-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-504">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-505">Tasa de desplazamiento del reloj del dispositivo de altavoz del destinatario de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="a7dfb-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-507">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-508">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="a7dfb-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-510">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-511">Promedio del error de marca de tiempo de la secuencia de representación del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="a7dfb-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-513">smallint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-514">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="a7dfb-515">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="a7dfb-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7dfb-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-518">Causas de un evento echo para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="a7dfb-519">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="a7dfb-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-521">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-522">Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="a7dfb-523">Si se usa el casco, el valor debería ser bajo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="a7dfb-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-525">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-526">Porcentaje de tiempo en que se detecta eco en la secuencia enviada del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="a7dfb-527">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-529">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-529">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-530">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="a7dfb-531">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a7dfb-532">Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="a7dfb-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-534">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-534">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-535">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="a7dfb-536">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="a7dfb-537">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a7dfb-538">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="a7dfb-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-540">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-540">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-541">Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-543">float</span><span class="sxs-lookup"><span data-stu-id="a7dfb-543">float</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-544">Cuadrado raíz medio (RMS) de la señal entrante al destinatario de la llamada durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="a7dfb-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-546">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-547">Relación media de muestras ocultas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="a7dfb-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-549">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-550">Relación media de muestras extendidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="a7dfb-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-552">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-553">Relación media de muestras comprimidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-554">Vuelta</span><span class="sxs-lookup"><span data-stu-id="a7dfb-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-555">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-555">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-556">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="a7dfb-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-558">int</span><span class="sxs-lookup"><span data-stu-id="a7dfb-558">int</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-559">Tiempo de ida y vuelta máximo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-561">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-562">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="a7dfb-563">Esta métrica depende de la pérdida de paquetes, la vibración y el códec que se usan.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="a7dfb-564">El intervalo es de 1,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-566">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-567">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-569">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-570">Puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="a7dfb-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-572">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-573">SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="a7dfb-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-575">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-576">Puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y la captura de las características del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="a7dfb-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-578">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-579">RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7dfb-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="a7dfb-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-581">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-581">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-582">Indica si se usó el FEC de audio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7dfb-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="a7dfb-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-584">bit</span><span class="sxs-lookup"><span data-stu-id="a7dfb-584">bit</span></span></p></td>
<td><p><span data-ttu-id="a7dfb-585">Indica la dirección de la información de identificación p-asserted; 1 significa que la dirección de la secuencia proviene del autor de la llamada al destinatario de la llamada; 0 significa que la dirección de la secuencia es del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


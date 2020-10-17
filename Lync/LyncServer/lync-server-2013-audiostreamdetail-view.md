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
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515787"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="78946-102">Vista AudioStreamDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78946-102">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78946-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="78946-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="78946-104">La vista AudioStreamDetail almacena información sobre cada secuencia de audio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="78946-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="78946-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78946-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78946-106">Columna</span><span class="sxs-lookup"><span data-stu-id="78946-106">Column</span></span></th>
<th><span data-ttu-id="78946-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="78946-107">Data Type</span></span></th>
<th><span data-ttu-id="78946-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="78946-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78946-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="78946-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="78946-110">datetime</span><span class="sxs-lookup"><span data-stu-id="78946-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="78946-111">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="78946-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="78946-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="78946-113">entero</span><span class="sxs-lookup"><span data-stu-id="78946-113">int</span></span></p></td>
<td><p><span data-ttu-id="78946-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="78946-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="78946-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="78946-116">entero</span><span class="sxs-lookup"><span data-stu-id="78946-116">int</span></span></p></td>
<td><p><span data-ttu-id="78946-117">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="78946-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="78946-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="78946-119">datetime</span><span class="sxs-lookup"><span data-stu-id="78946-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="78946-120">Fecha y hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="78946-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="78946-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="78946-122">datetime</span><span class="sxs-lookup"><span data-stu-id="78946-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="78946-123">Fecha y hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="78946-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="78946-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="78946-125">bit</span><span class="sxs-lookup"><span data-stu-id="78946-125">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-126">Categoría del cuadro de diálogo: 0 es el segmento del servidor de mediación de Lync. 1 es el servidor de mediación a la pierna de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="78946-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="78946-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="78946-128">bit</span><span class="sxs-lookup"><span data-stu-id="78946-128">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-129">Marca que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="78946-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="78946-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="78946-131">entero</span><span class="sxs-lookup"><span data-stu-id="78946-131">int</span></span></p></td>
<td><p><span data-ttu-id="78946-132">Si está presente, indica por qué no se omitió una llamada incluso si coinciden los identificadores de omisión.</span><span class="sxs-lookup"><span data-stu-id="78946-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="78946-133">Solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="78946-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="78946-134">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="78946-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="78946-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="78946-136">entero</span><span class="sxs-lookup"><span data-stu-id="78946-136">int</span></span></p></td>
<td><p><span data-ttu-id="78946-137">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="78946-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="78946-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="78946-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-140">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78946-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="78946-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="78946-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="78946-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-143">FQDN del grupo de destinatarios de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78946-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-144">Caller</span><span class="sxs-lookup"><span data-stu-id="78946-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="78946-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="78946-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="78946-146">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-147">Destinatario</span><span class="sxs-lookup"><span data-stu-id="78946-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="78946-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="78946-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="78946-149">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="78946-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="78946-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="78946-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-152">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="78946-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="78946-154">smallint</span><span class="sxs-lookup"><span data-stu-id="78946-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="78946-155">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="78946-156">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="78946-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="78946-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="78946-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="78946-159">Categoría del agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="78946-160">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="78946-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="78946-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="78946-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-163">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="78946-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="78946-165">smallint</span><span class="sxs-lookup"><span data-stu-id="78946-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="78946-166">Tipo de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-166">Type of callee’s user agent.</span></span> <span data-ttu-id="78946-167">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener información.</span><span class="sxs-lookup"><span data-stu-id="78946-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="78946-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="78946-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="78946-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="78946-170">Categoría de agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-170">Category of callee’s user agent.</span></span> <span data-ttu-id="78946-171">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="78946-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="78946-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="78946-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-174">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="78946-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="78946-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="78946-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-177">Nombre del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="78946-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="78946-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-180">Sistema operativo (SO) del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="78946-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="78946-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-183">Sistema operativo (SO) del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="78946-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="78946-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-186">Nombre de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="78946-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="78946-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-189">Nombre de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="78946-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="78946-191">smallint</span><span class="sxs-lookup"><span data-stu-id="78946-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="78946-192">Número de núcleos de CPU en el extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="78946-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="78946-194">smallint</span><span class="sxs-lookup"><span data-stu-id="78946-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="78946-195">Número de núcleos de CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="78946-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="78946-197">entero</span><span class="sxs-lookup"><span data-stu-id="78946-197">int</span></span></p></td>
<td><p><span data-ttu-id="78946-198">Velocidad del procesador de la CPU del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="78946-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="78946-200">entero</span><span class="sxs-lookup"><span data-stu-id="78946-200">int</span></span></p></td>
<td><p><span data-ttu-id="78946-201">Velocidad del procesador de la CPU del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="78946-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="78946-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-204">Indica si el sistema del autor de la llamada se está ejecutando en un entorno visualizado.</span><span class="sxs-lookup"><span data-stu-id="78946-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="78946-205">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="78946-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="78946-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-208">Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="78946-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="78946-209">Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="78946-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78946-211">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="78946-211">Correlation key.</span></span> <span data-ttu-id="78946-212">Referencia de la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="78946-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="78946-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="78946-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-215">Información sobre la ruta de medios, como directa o retransmitida.</span><span class="sxs-lookup"><span data-stu-id="78946-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="78946-216">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="78946-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="78946-218">entero</span><span class="sxs-lookup"><span data-stu-id="78946-218">int</span></span></p></td>
<td><p><span data-ttu-id="78946-p111">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="78946-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="78946-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="78946-222">entero</span><span class="sxs-lookup"><span data-stu-id="78946-222">int</span></span></p></td>
<td><p><span data-ttu-id="78946-p112">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="78946-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-225">Transport</span><span class="sxs-lookup"><span data-stu-id="78946-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="78946-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-227">Tipo de transporte: 0 es UDP y 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="78946-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="78946-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="78946-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="78946-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="78946-230">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-230">IP address of the caller.</span></span> <span data-ttu-id="78946-231">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="78946-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="78946-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="78946-233">entero</span><span class="sxs-lookup"><span data-stu-id="78946-233">int</span></span></p></td>
<td><p><span data-ttu-id="78946-234">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="78946-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="78946-236">bit</span><span class="sxs-lookup"><span data-stu-id="78946-236">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-237">Indica si el autor de la llamada está dentro de la red del intervalo: 1 significa que el autor de la llamada está dentro de la red de la empresa, 0 significa que el autor de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="78946-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="78946-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="78946-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="78946-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="78946-240">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-240">IP address of the callee.</span></span> <span data-ttu-id="78946-241">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="78946-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="78946-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="78946-243">entero</span><span class="sxs-lookup"><span data-stu-id="78946-243">int</span></span></p></td>
<td><p><span data-ttu-id="78946-244">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="78946-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="78946-246">bit</span><span class="sxs-lookup"><span data-stu-id="78946-246">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-247">Indica si el destinatario de la llamada está dentro de la red del intervalo: 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="78946-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="78946-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="78946-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-250">Nombre del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="78946-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="78946-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-253">Nombre del país o región del centro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="78946-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="78946-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-256">Nombre del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="78946-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="78946-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="78946-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="78946-259">Nombre del país o la región del centro del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="78946-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="78946-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="78946-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="78946-262">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="78946-263">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="78946-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="78946-265">entero</span><span class="sxs-lookup"><span data-stu-id="78946-265">int</span></span></p></td>
<td><p><span data-ttu-id="78946-266">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="78946-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="78946-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="78946-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="78946-269">Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="78946-270">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="78946-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="78946-272">entero</span><span class="sxs-lookup"><span data-stu-id="78946-272">int</span></span></p></td>
<td><p><span data-ttu-id="78946-273">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="78946-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="78946-275">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-276">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="78946-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="78946-278">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-279">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="78946-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="78946-281">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-282">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="78946-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="78946-284">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-285">Nombre del controlador dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="78946-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="78946-287">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-288">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="78946-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="78946-290">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-291">Nombre de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="78946-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="78946-293">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-294">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="78946-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="78946-296">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="78946-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78946-297">Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="78946-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="78946-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-300">Tipo de conexión de red del autor de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="78946-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="78946-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="78946-302">bit</span><span class="sxs-lookup"><span data-stu-id="78946-302">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-303">Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="78946-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="78946-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="78946-305">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="78946-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="78946-306">Velocidad del vínculo de red del extremo del autor de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="78946-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="78946-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="78946-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-309">Tipo de conexión de red del destinatario de la llamada: 0 es con cable y 1, inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="78946-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="78946-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="78946-311">bit</span><span class="sxs-lookup"><span data-stu-id="78946-311">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-312">Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="78946-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="78946-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="78946-314">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="78946-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="78946-315">Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</span><span class="sxs-lookup"><span data-stu-id="78946-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="78946-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="78946-317">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-318">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="78946-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="78946-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="78946-320">entero</span><span class="sxs-lookup"><span data-stu-id="78946-320">int</span></span></p></td>
<td><p><span data-ttu-id="78946-321">Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.).</span><span class="sxs-lookup"><span data-stu-id="78946-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="78946-322">No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="78946-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="78946-323">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda</span><span class="sxs-lookup"><span data-stu-id="78946-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="78946-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="78946-325">entero</span><span class="sxs-lookup"><span data-stu-id="78946-325">int</span></span></p></td>
<td><p><span data-ttu-id="78946-326">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="78946-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="78946-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="78946-328">entero</span><span class="sxs-lookup"><span data-stu-id="78946-328">int</span></span></p></td>
<td><p><span data-ttu-id="78946-329">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="78946-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="78946-331">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="78946-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="78946-332">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="78946-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="78946-334">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="78946-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="78946-335">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-336">Densidad</span><span class="sxs-lookup"><span data-stu-id="78946-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="78946-337">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="78946-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="78946-338">Densidad media de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="78946-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="78946-340">entero</span><span class="sxs-lookup"><span data-stu-id="78946-340">int</span></span></p></td>
<td><p><span data-ttu-id="78946-341">Duración media de la pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="78946-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="78946-343">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="78946-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="78946-344">Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="78946-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="78946-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="78946-346">entero</span><span class="sxs-lookup"><span data-stu-id="78946-346">int</span></span></p></td>
<td><p><span data-ttu-id="78946-347">Duración media de brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="78946-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="78946-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="78946-349">entero</span><span class="sxs-lookup"><span data-stu-id="78946-349">int</span></span></p></td>
<td><p><span data-ttu-id="78946-350">Número de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="78946-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-351">Ancho de banda más</span><span class="sxs-lookup"><span data-stu-id="78946-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="78946-352">entero</span><span class="sxs-lookup"><span data-stu-id="78946-352">int</span></span></p></td>
<td><p><span data-ttu-id="78946-353">Previsiones de ancho de banda de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="78946-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="78946-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="78946-355">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-356">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="78946-357">El intervalo es de 0,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="78946-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="78946-358">Esta métrica muestra la cantidad de MOS de red que se redujo debido a la vibración y pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="78946-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="78946-359">Para una calidad aceptable, debe ser inferior a 0,5.</span><span class="sxs-lookup"><span data-stu-id="78946-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="78946-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="78946-361">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-362">Degradación de MOS de red máxima durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="78946-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="78946-364">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-365">Degradación de MOS de red causada por la vibración.</span><span class="sxs-lookup"><span data-stu-id="78946-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="78946-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="78946-367">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-368">Degradación de MOS de red causada por la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="78946-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="78946-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="78946-370">entero</span><span class="sxs-lookup"><span data-stu-id="78946-370">int</span></span></p></td>
<td><p><span data-ttu-id="78946-371">El códec de audio usado para la llamada, al que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="78946-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="78946-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="78946-373">entero</span><span class="sxs-lookup"><span data-stu-id="78946-373">int</span></span></p></td>
<td><p><span data-ttu-id="78946-374">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="78946-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="78946-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-376">entero</span><span class="sxs-lookup"><span data-stu-id="78946-376">int</span></span></p></td>
<td><p><span data-ttu-id="78946-377">Nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="78946-378">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-379">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="78946-380">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="78946-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-382">entero</span><span class="sxs-lookup"><span data-stu-id="78946-382">int</span></span></p></td>
<td><p><span data-ttu-id="78946-383">Nivel de señal de audio para el audio que el autor de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="78946-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="78946-384">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-385">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="78946-386">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="78946-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-388">entero</span><span class="sxs-lookup"><span data-stu-id="78946-388">int</span></span></p></td>
<td><p><span data-ttu-id="78946-389">El nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="78946-390">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-391">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="78946-392">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="78946-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-394">entero</span><span class="sxs-lookup"><span data-stu-id="78946-394">int</span></span></p></td>
<td><p><span data-ttu-id="78946-395">El nivel de ruido de audio del control de ganancia posterior analógico para el audio que ha recibido la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="78946-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="78946-396">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-397">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="78946-398">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="78946-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="78946-400">entero</span><span class="sxs-lookup"><span data-stu-id="78946-400">int</span></span></p></td>
<td><p><span data-ttu-id="78946-401">Devolución de pérdida eco mejora para el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="78946-402">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="78946-402">The unit for this metric is dB.</span></span> <span data-ttu-id="78946-403">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="78946-403">Lower values represent less echo.</span></span> <span data-ttu-id="78946-404">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="78946-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="78946-406">entero</span><span class="sxs-lookup"><span data-stu-id="78946-406">int</span></span></p></td>
<td><p><span data-ttu-id="78946-407">Media de problemas por cinco minutos para la representación del altavoz del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="78946-408">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="78946-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="78946-409">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="78946-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="78946-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="78946-411">entero</span><span class="sxs-lookup"><span data-stu-id="78946-411">int</span></span></p></td>
<td><p><span data-ttu-id="78946-412">Media de problemas por cinco minutos para la captura del micrófono del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="78946-413">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="78946-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="78946-414">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="78946-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="78946-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="78946-416">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-417">Tasa de desplazamiento del reloj del dispositivo de micrófono del autor de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="78946-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="78946-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="78946-419">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-420">Tasa de desplazamiento del reloj del dispositivo de altavoz del autor de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="78946-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="78946-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="78946-422">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-423">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="78946-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="78946-425">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-426">Promedio del error de marca de tiempo de la secuencia de representación del altavoz del autor de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="78946-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="78946-428">smallint</span><span class="sxs-lookup"><span data-stu-id="78946-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="78946-429">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="78946-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="78946-430">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="78946-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="78946-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-433">Causas de un evento de Eco para el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="78946-434">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="78946-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="78946-436">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-437">Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="78946-438">Si se usa el casco, el valor debería ser bajo.</span><span class="sxs-lookup"><span data-stu-id="78946-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="78946-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="78946-440">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-441">Porcentaje de tiempo en que se detecta el eco en la secuencia enviada del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="78946-442">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="78946-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="78946-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-444">entero</span><span class="sxs-lookup"><span data-stu-id="78946-444">int</span></span></p></td>
<td><p><span data-ttu-id="78946-445">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="78946-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="78946-446">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="78946-447">Para obtener una buena calidad, el intervalo aceptable debe ser de-30 a-18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="78946-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-449">entero</span><span class="sxs-lookup"><span data-stu-id="78946-449">int</span></span></p></td>
<td><p><span data-ttu-id="78946-450">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="78946-451">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="78946-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="78946-452">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="78946-453">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="78946-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="78946-455">entero</span><span class="sxs-lookup"><span data-stu-id="78946-455">int</span></span></p></td>
<td><p><span data-ttu-id="78946-456">Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="78946-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="78946-458">float</span><span class="sxs-lookup"><span data-stu-id="78946-458">float</span></span></p></td>
<td><p><span data-ttu-id="78946-459">Cuadrado raíz medio (RMS) de la señal entrante al autor de la llamada durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="78946-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-461">entero</span><span class="sxs-lookup"><span data-stu-id="78946-461">int</span></span></p></td>
<td><p><span data-ttu-id="78946-462">Representa el nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="78946-463">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-464">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="78946-465">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="78946-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-467">entero</span><span class="sxs-lookup"><span data-stu-id="78946-467">int</span></span></p></td>
<td><p><span data-ttu-id="78946-468">Nivel de señal de audio para el audio que el destinatario de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="78946-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="78946-469">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-470">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="78946-471">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="78946-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-473">entero</span><span class="sxs-lookup"><span data-stu-id="78946-473">int</span></span></p></td>
<td><p><span data-ttu-id="78946-474">Nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="78946-475">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-476">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="78946-477">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="78946-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-479">entero</span><span class="sxs-lookup"><span data-stu-id="78946-479">int</span></span></p></td>
<td><p><span data-ttu-id="78946-480">Nivel de ruido de audio del control de ganancia posterior analógico para el audio que el destinatario de la llamada ha recibido.</span><span class="sxs-lookup"><span data-stu-id="78946-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="78946-481">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="78946-482">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="78946-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="78946-483">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="78946-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="78946-485">entero</span><span class="sxs-lookup"><span data-stu-id="78946-485">int</span></span></p></td>
<td><p><span data-ttu-id="78946-486">Devolución de pérdida de Eco para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="78946-487">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="78946-487">The unit for this metric is dB.</span></span> <span data-ttu-id="78946-488">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="78946-488">Lower values represent less echo.</span></span> <span data-ttu-id="78946-489">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="78946-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="78946-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="78946-491">entero</span><span class="sxs-lookup"><span data-stu-id="78946-491">int</span></span></p></td>
<td><p><span data-ttu-id="78946-492">Media de problemas por cinco minutos para la representación del altavoz del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="78946-493">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="78946-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="78946-494">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="78946-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="78946-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="78946-496">entero</span><span class="sxs-lookup"><span data-stu-id="78946-496">int</span></span></p></td>
<td><p><span data-ttu-id="78946-497">Media de problemas por cinco minutos para la captura del micrófono del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="78946-498">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="78946-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="78946-499">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="78946-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="78946-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="78946-501">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-502">Tasa de desplazamiento del reloj del dispositivo de micrófono del destinatario de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="78946-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="78946-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="78946-504">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-505">Tasa de desplazamiento del reloj del dispositivo de altavoz del destinatario de la llamada en relación con el reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="78946-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="78946-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="78946-507">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-508">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="78946-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="78946-510">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-511">Promedio del error de marca de tiempo de la secuencia de representación del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="78946-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="78946-513">smallint</span><span class="sxs-lookup"><span data-stu-id="78946-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="78946-514">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="78946-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="78946-515">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="78946-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="78946-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="78946-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78946-518">Causas de un evento echo para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="78946-519">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78946-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="78946-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="78946-521">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-522">Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="78946-523">Si se usa el casco, el valor debería ser bajo.</span><span class="sxs-lookup"><span data-stu-id="78946-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="78946-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="78946-525">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-526">Porcentaje de tiempo en que se detecta eco en la secuencia enviada del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="78946-527">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="78946-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="78946-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-529">entero</span><span class="sxs-lookup"><span data-stu-id="78946-529">int</span></span></p></td>
<td><p><span data-ttu-id="78946-530">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="78946-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="78946-531">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="78946-532">Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="78946-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="78946-534">entero</span><span class="sxs-lookup"><span data-stu-id="78946-534">int</span></span></p></td>
<td><p><span data-ttu-id="78946-535">Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="78946-536">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="78946-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="78946-537">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="78946-538">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="78946-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="78946-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="78946-540">entero</span><span class="sxs-lookup"><span data-stu-id="78946-540">int</span></span></p></td>
<td><p><span data-ttu-id="78946-541">Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="78946-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="78946-543">float</span><span class="sxs-lookup"><span data-stu-id="78946-543">float</span></span></p></td>
<td><p><span data-ttu-id="78946-544">Cuadrado raíz medio (RMS) de la señal entrante al destinatario de la llamada durante los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="78946-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="78946-546">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-547">Relación media de muestras ocultas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="78946-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="78946-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="78946-549">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-550">Relación media de muestras extendidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="78946-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="78946-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="78946-552">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-553">Relación media de muestras comprimidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="78946-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-554">Vuelta</span><span class="sxs-lookup"><span data-stu-id="78946-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="78946-555">entero</span><span class="sxs-lookup"><span data-stu-id="78946-555">int</span></span></p></td>
<td><p><span data-ttu-id="78946-556">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="78946-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="78946-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="78946-558">entero</span><span class="sxs-lookup"><span data-stu-id="78946-558">int</span></span></p></td>
<td><p><span data-ttu-id="78946-559">Tiempo de ida y vuelta máximo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="78946-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="78946-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="78946-561">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-562">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="78946-563">Esta métrica depende de la pérdida de paquetes, la vibración y el códec que se usan.</span><span class="sxs-lookup"><span data-stu-id="78946-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="78946-564">El intervalo es de 1,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="78946-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="78946-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="78946-566">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-567">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="78946-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="78946-569">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-570">Puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="78946-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="78946-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="78946-572">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-573">SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="78946-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="78946-575">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-576">Puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y la captura de las características del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="78946-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="78946-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="78946-578">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="78946-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="78946-579">RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78946-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="78946-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="78946-581">bit</span><span class="sxs-lookup"><span data-stu-id="78946-581">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-582">Indica si se usó el FEC de audio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78946-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="78946-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="78946-584">bit</span><span class="sxs-lookup"><span data-stu-id="78946-584">bit</span></span></p></td>
<td><p><span data-ttu-id="78946-585">Indica la dirección de la información de identificación p-asserted; 1 significa que la dirección de la secuencia proviene del autor de la llamada al destinatario de la llamada; 0 significa que la dirección de la secuencia es del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78946-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


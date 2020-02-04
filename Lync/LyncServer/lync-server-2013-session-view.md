---
title: 'Lync Server 2013: vista de sesión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="926f3-102">Vista de sesión de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="926f3-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="926f3-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="926f3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="926f3-104">La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="926f3-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="926f3-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="926f3-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="926f3-106">Columna</span><span class="sxs-lookup"><span data-stu-id="926f3-106">Column</span></span></th>
<th><span data-ttu-id="926f3-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="926f3-107">Data Type</span></span></th>
<th><span data-ttu-id="926f3-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="926f3-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="926f3-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="926f3-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="926f3-110">datetime</span><span class="sxs-lookup"><span data-stu-id="926f3-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="926f3-111">Se hace referencia a ella desde la tabla MediaLine.</span><span class="sxs-lookup"><span data-stu-id="926f3-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="926f3-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="926f3-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="926f3-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="926f3-114">URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="926f3-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-115">Correlación</span><span class="sxs-lookup"><span data-stu-id="926f3-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="926f3-116">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="926f3-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="926f3-117">IDENTIFICADOR de correlación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="926f3-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="926f3-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="926f3-119">bit</span><span class="sxs-lookup"><span data-stu-id="926f3-119">bit</span></span></p></td>
<td><p><span data-ttu-id="926f3-120">Categoría de cuadro de diálogo; 0 ¿se encuentra Lync Server en la pierna del servidor de mediación; 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="926f3-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="926f3-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="926f3-122">bit</span><span class="sxs-lookup"><span data-stu-id="926f3-122">bit</span></span></p></td>
<td><p><span data-ttu-id="926f3-123">Indica si se ha omitido la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="926f3-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="926f3-125">int</span><span class="sxs-lookup"><span data-stu-id="926f3-125">int</span></span></p></td>
<td><p><span data-ttu-id="926f3-126">Este campo, si está presente, indica por qué no se omitió una llamada, incluso si los identificadores de omisión coinciden.</span><span class="sxs-lookup"><span data-stu-id="926f3-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="926f3-127">Para Lync Server, solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="926f3-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="926f3-128">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado</span><span class="sxs-lookup"><span data-stu-id="926f3-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="926f3-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="926f3-130">datetime</span><span class="sxs-lookup"><span data-stu-id="926f3-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="926f3-131">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="926f3-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="926f3-133">datetime</span><span class="sxs-lookup"><span data-stu-id="926f3-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="926f3-134">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="926f3-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="926f3-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="926f3-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="926f3-137">FQDN del grupo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="926f3-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="926f3-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="926f3-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="926f3-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="926f3-140">FQDN del grupo de destinatarios de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="926f3-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="926f3-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="926f3-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="926f3-143">URI de identidad afirmada de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="926f3-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="926f3-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="926f3-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="926f3-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="926f3-146">URI de identidad afirmada de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="926f3-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="926f3-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="926f3-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="926f3-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="926f3-149">Nombre del punto de conexión de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="926f3-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="926f3-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="926f3-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="926f3-152">Nombre del punto de conexión de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="926f3-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="926f3-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="926f3-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="926f3-155">Cadena de agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="926f3-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="926f3-157">smallint</span><span class="sxs-lookup"><span data-stu-id="926f3-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="926f3-158">Tipo de agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-158">Type of caller’s user agent.</span></span> <span data-ttu-id="926f3-159">Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="926f3-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="926f3-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="926f3-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="926f3-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="926f3-162">Categoría del agente de usuario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-162">Category of caller’s user agent.</span></span> <span data-ttu-id="926f3-163">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="926f3-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="926f3-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="926f3-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="926f3-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="926f3-166">Cadena de agente de usuario de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="926f3-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="926f3-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="926f3-168">smallint</span><span class="sxs-lookup"><span data-stu-id="926f3-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="926f3-169">Tipo de agente de usuario para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-169">Type of user agent for the callee.</span></span> <span data-ttu-id="926f3-170">Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="926f3-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="926f3-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="926f3-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="926f3-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="926f3-173">Categoría de agente de usuario para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-173">User agent category for the callee.</span></span> <span data-ttu-id="926f3-174">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="926f3-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="926f3-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="926f3-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="926f3-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="926f3-177">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="926f3-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926f3-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="926f3-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="926f3-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="926f3-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="926f3-180">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="926f3-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="926f3-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="926f3-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="926f3-182">int</span><span class="sxs-lookup"><span data-stu-id="926f3-182">int</span></span></p></td>
<td><p><span data-ttu-id="926f3-183">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="926f3-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: vista de sesión'
description: 'Lync Server 2013: vista de sesión.'
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
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545016"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="d441b-103">Vista de sesión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d441b-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d441b-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d441b-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d441b-105">La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d441b-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="d441b-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d441b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d441b-107">Columna</span><span class="sxs-lookup"><span data-stu-id="d441b-107">Column</span></span></th>
<th><span data-ttu-id="d441b-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d441b-108">Data Type</span></span></th>
<th><span data-ttu-id="d441b-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="d441b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d441b-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="d441b-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="d441b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d441b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d441b-112">Se obtiene de la tabla MediaLine.</span><span class="sxs-lookup"><span data-stu-id="d441b-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-113">Uri</span><span class="sxs-lookup"><span data-stu-id="d441b-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="d441b-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d441b-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d441b-115">ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="d441b-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="d441b-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="d441b-117">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="d441b-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d441b-118">Id. de correlación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="d441b-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="d441b-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="d441b-120">bit</span><span class="sxs-lookup"><span data-stu-id="d441b-120">bit</span></span></p></td>
<td><p><span data-ttu-id="d441b-121">Categoría del cuadro de diálogo; 0 es Lync Server a la pierna del servidor de mediación; 1 es el servidor de mediación a la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="d441b-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="d441b-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="d441b-123">bit</span><span class="sxs-lookup"><span data-stu-id="d441b-123">bit</span></span></p></td>
<td><p><span data-ttu-id="d441b-124">Indica si la llamada se pasó o no.</span><span class="sxs-lookup"><span data-stu-id="d441b-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="d441b-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="d441b-126">entero</span><span class="sxs-lookup"><span data-stu-id="d441b-126">int</span></span></p></td>
<td><p><span data-ttu-id="d441b-127">Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían.</span><span class="sxs-lookup"><span data-stu-id="d441b-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="d441b-128">Para Lync Server, solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="d441b-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="d441b-129">0x0001: identificador de omisión desconocido del adaptador de red predeterminado</span><span class="sxs-lookup"><span data-stu-id="d441b-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="d441b-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="d441b-131">datetime</span><span class="sxs-lookup"><span data-stu-id="d441b-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="d441b-132">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="d441b-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="d441b-134">datetime</span><span class="sxs-lookup"><span data-stu-id="d441b-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="d441b-135">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="d441b-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="d441b-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d441b-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d441b-138">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d441b-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="d441b-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="d441b-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d441b-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d441b-141">FQDN del grupo de destinatarios de la llamada</span><span class="sxs-lookup"><span data-stu-id="d441b-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="d441b-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="d441b-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d441b-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d441b-144">URI de la identidad afirmada del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="d441b-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="d441b-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d441b-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d441b-147">URI de la identidad afirmada del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d441b-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d441b-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d441b-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d441b-150">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="d441b-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d441b-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d441b-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d441b-153">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="d441b-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d441b-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d441b-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d441b-156">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d441b-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d441b-158">smallint</span><span class="sxs-lookup"><span data-stu-id="d441b-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="d441b-159">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-159">Type of caller’s user agent.</span></span> <span data-ttu-id="d441b-160">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d441b-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d441b-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d441b-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d441b-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="d441b-163">Categoría del agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-163">Category of caller’s user agent.</span></span> <span data-ttu-id="d441b-164">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d441b-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="d441b-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d441b-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d441b-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d441b-167">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d441b-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d441b-169">smallint</span><span class="sxs-lookup"><span data-stu-id="d441b-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="d441b-170">Tipo del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-170">Type of user agent for the callee.</span></span> <span data-ttu-id="d441b-171">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d441b-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d441b-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d441b-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d441b-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="d441b-174">Categoría del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-174">User agent category for the callee.</span></span> <span data-ttu-id="d441b-175">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d441b-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="d441b-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="d441b-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d441b-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d441b-178">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d441b-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="d441b-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="d441b-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d441b-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d441b-181">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d441b-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="d441b-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="d441b-183">entero</span><span class="sxs-lookup"><span data-stu-id="d441b-183">int</span></span></p></td>
<td><p><span data-ttu-id="d441b-184">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d441b-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


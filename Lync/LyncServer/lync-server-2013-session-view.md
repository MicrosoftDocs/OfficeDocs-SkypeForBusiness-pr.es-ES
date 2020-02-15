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
ms.openlocfilehash: 7d20d748f9c9754efab768a702f1272bc70d889e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="2b885-102">Vista de sesión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b885-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b885-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2b885-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2b885-104">La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2b885-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="2b885-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b885-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b885-106">Columna</span><span class="sxs-lookup"><span data-stu-id="2b885-106">Column</span></span></th>
<th><span data-ttu-id="2b885-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2b885-107">Data Type</span></span></th>
<th><span data-ttu-id="2b885-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="2b885-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b885-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="2b885-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="2b885-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2b885-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b885-111">Se obtiene de la tabla MediaLine.</span><span class="sxs-lookup"><span data-stu-id="2b885-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-112">Uri</span><span class="sxs-lookup"><span data-stu-id="2b885-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="2b885-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b885-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b885-114">ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="2b885-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="2b885-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="2b885-116">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="2b885-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="2b885-117">Id. de correlación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2b885-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="2b885-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="2b885-119">bit</span><span class="sxs-lookup"><span data-stu-id="2b885-119">bit</span></span></p></td>
<td><p><span data-ttu-id="2b885-120">Categoría del cuadro de diálogo; 0 es Lync Server a la pierna del servidor de mediación; 1 es el servidor de mediación a la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="2b885-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="2b885-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="2b885-122">bit</span><span class="sxs-lookup"><span data-stu-id="2b885-122">bit</span></span></p></td>
<td><p><span data-ttu-id="2b885-123">Indica si la llamada se pasó o no.</span><span class="sxs-lookup"><span data-stu-id="2b885-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="2b885-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="2b885-125">int</span><span class="sxs-lookup"><span data-stu-id="2b885-125">int</span></span></p></td>
<td><p><span data-ttu-id="2b885-126">Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían.</span><span class="sxs-lookup"><span data-stu-id="2b885-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="2b885-127">Para Lync Server, solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="2b885-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="2b885-128">0x0001: identificador de omisión desconocido del adaptador de red predeterminado</span><span class="sxs-lookup"><span data-stu-id="2b885-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="2b885-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="2b885-130">datetime</span><span class="sxs-lookup"><span data-stu-id="2b885-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b885-131">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="2b885-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="2b885-133">datetime</span><span class="sxs-lookup"><span data-stu-id="2b885-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b885-134">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="2b885-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="2b885-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b885-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b885-137">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2b885-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="2b885-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="2b885-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b885-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b885-140">FQDN del grupo de destinatarios de la llamada</span><span class="sxs-lookup"><span data-stu-id="2b885-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="2b885-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="2b885-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b885-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b885-143">URI de la identidad afirmada del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="2b885-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="2b885-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b885-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b885-146">URI de la identidad afirmada del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="2b885-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="2b885-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b885-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b885-149">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="2b885-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="2b885-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b885-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b885-152">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="2b885-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="2b885-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b885-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b885-155">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="2b885-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="2b885-157">smallint</span><span class="sxs-lookup"><span data-stu-id="2b885-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b885-158">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-158">Type of caller’s user agent.</span></span> <span data-ttu-id="2b885-159">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b885-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="2b885-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="2b885-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b885-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="2b885-162">Categoría del agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-162">Category of caller’s user agent.</span></span> <span data-ttu-id="2b885-163">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b885-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="2b885-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="2b885-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b885-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b885-166">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="2b885-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="2b885-168">smallint</span><span class="sxs-lookup"><span data-stu-id="2b885-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b885-169">Tipo del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-169">Type of user agent for the callee.</span></span> <span data-ttu-id="2b885-170">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b885-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="2b885-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="2b885-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b885-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="2b885-173">Categoría del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-173">User agent category for the callee.</span></span> <span data-ttu-id="2b885-174">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b885-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="2b885-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="2b885-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b885-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b885-177">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b885-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="2b885-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="2b885-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b885-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b885-180">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b885-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="2b885-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="2b885-182">int</span><span class="sxs-lookup"><span data-stu-id="2b885-182">int</span></span></p></td>
<td><p><span data-ttu-id="2b885-183">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b885-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 30183ffde7380b5029ac458f102eaf81ecee914b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510097"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="380d1-102">Vista de sesión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="380d1-102">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="380d1-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="380d1-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="380d1-104">La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="380d1-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="380d1-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="380d1-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="380d1-106">Columna</span><span class="sxs-lookup"><span data-stu-id="380d1-106">Column</span></span></th>
<th><span data-ttu-id="380d1-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="380d1-107">Data Type</span></span></th>
<th><span data-ttu-id="380d1-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="380d1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="380d1-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="380d1-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="380d1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="380d1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="380d1-111">Se obtiene de la tabla MediaLine.</span><span class="sxs-lookup"><span data-stu-id="380d1-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-112">Uri</span><span class="sxs-lookup"><span data-stu-id="380d1-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="380d1-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="380d1-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="380d1-114">ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="380d1-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="380d1-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="380d1-116">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="380d1-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="380d1-117">Id. de correlación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="380d1-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="380d1-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="380d1-119">bit</span><span class="sxs-lookup"><span data-stu-id="380d1-119">bit</span></span></p></td>
<td><p><span data-ttu-id="380d1-120">Categoría del cuadro de diálogo; 0 es Lync Server a la pierna del servidor de mediación; 1 es el servidor de mediación a la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="380d1-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="380d1-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="380d1-122">bit</span><span class="sxs-lookup"><span data-stu-id="380d1-122">bit</span></span></p></td>
<td><p><span data-ttu-id="380d1-123">Indica si la llamada se pasó o no.</span><span class="sxs-lookup"><span data-stu-id="380d1-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="380d1-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="380d1-125">entero</span><span class="sxs-lookup"><span data-stu-id="380d1-125">int</span></span></p></td>
<td><p><span data-ttu-id="380d1-126">Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían.</span><span class="sxs-lookup"><span data-stu-id="380d1-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="380d1-127">Para Lync Server, solo se define un valor:</span><span class="sxs-lookup"><span data-stu-id="380d1-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="380d1-128">0x0001: identificador de omisión desconocido del adaptador de red predeterminado</span><span class="sxs-lookup"><span data-stu-id="380d1-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="380d1-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="380d1-130">datetime</span><span class="sxs-lookup"><span data-stu-id="380d1-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="380d1-131">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="380d1-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="380d1-133">datetime</span><span class="sxs-lookup"><span data-stu-id="380d1-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="380d1-134">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="380d1-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="380d1-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="380d1-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="380d1-137">FQDN del grupo de autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="380d1-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="380d1-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="380d1-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="380d1-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="380d1-140">FQDN del grupo de destinatarios de la llamada</span><span class="sxs-lookup"><span data-stu-id="380d1-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="380d1-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="380d1-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="380d1-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="380d1-143">URI de la identidad afirmada del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="380d1-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="380d1-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="380d1-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="380d1-146">URI de la identidad afirmada del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="380d1-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="380d1-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="380d1-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="380d1-149">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="380d1-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="380d1-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="380d1-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="380d1-152">Nombre del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="380d1-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="380d1-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="380d1-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="380d1-155">Cadena de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="380d1-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="380d1-157">smallint</span><span class="sxs-lookup"><span data-stu-id="380d1-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="380d1-158">Tipo de agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-158">Type of caller’s user agent.</span></span> <span data-ttu-id="380d1-159">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="380d1-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="380d1-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="380d1-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="380d1-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="380d1-162">Categoría del agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-162">Category of caller’s user agent.</span></span> <span data-ttu-id="380d1-163">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="380d1-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="380d1-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="380d1-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="380d1-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="380d1-166">Cadena del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="380d1-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="380d1-168">smallint</span><span class="sxs-lookup"><span data-stu-id="380d1-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="380d1-169">Tipo del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-169">Type of user agent for the callee.</span></span> <span data-ttu-id="380d1-170">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="380d1-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="380d1-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="380d1-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="380d1-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="380d1-173">Categoría del agente de usuario del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-173">User agent category for the callee.</span></span> <span data-ttu-id="380d1-174">Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="380d1-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="380d1-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="380d1-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="380d1-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="380d1-177">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="380d1-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="380d1-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="380d1-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="380d1-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="380d1-180">URI del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="380d1-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="380d1-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="380d1-182">entero</span><span class="sxs-lookup"><span data-stu-id="380d1-182">int</span></span></p></td>
<td><p><span data-ttu-id="380d1-183">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="380d1-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


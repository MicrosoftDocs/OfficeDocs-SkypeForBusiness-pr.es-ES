---
title: 'Lync Server 2013: tabla de sesiones'
description: 'Lync Server 2013: tabla de sesiones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576456"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="bdc6f-103">Tabla Session en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc6f-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdc6f-104">_**Última modificación del tema:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="bdc6f-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="bdc6f-105">Cada registro representa una sesión que implica audio o audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="bdc6f-106">Contiene información general sobre la sesión.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-106">It contains overall information about the session.</span></span> <span data-ttu-id="bdc6f-107">Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdc6f-108"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bdc6f-109"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bdc6f-110"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bdc6f-111"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="bdc6f-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-114">Principal</span><span class="sxs-lookup"><span data-stu-id="bdc6f-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-115">Se hace referencia a ella desde la <a href="lync-server-2013-dialog-table.md">tabla de cuadro de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-117">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-117">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-118">Principal</span><span class="sxs-lookup"><span data-stu-id="bdc6f-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-119">Se hace referencia a ella desde la <a href="lync-server-2013-dialog-table.md">tabla de cuadro de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-121">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-121">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-122">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-123">Clave de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-123">Conference key.</span></span> <span data-ttu-id="bdc6f-124">Se hace referencia a ella desde la <a href="lync-server-2013-conference-table.md">tabla de conferencia en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-126">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-126">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-127">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-128">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-128">Correlation key.</span></span> <span data-ttu-id="bdc6f-129">Referencia de la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-131">bit</span><span class="sxs-lookup"><span data-stu-id="bdc6f-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bdc6f-132">Categoría del cuadro de diálogo; 0 es Lync Server a la pierna del servidor de mediación; 1 es el servidor de mediación a la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-134">bit</span><span class="sxs-lookup"><span data-stu-id="bdc6f-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc6f-135">Marca que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-137">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc6f-138">Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="bdc6f-139">Para Lync Server, solo se define un valor.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="bdc6f-140">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-142">datetime</span><span class="sxs-lookup"><span data-stu-id="bdc6f-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bdc6f-143">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-145">datetime</span><span class="sxs-lookup"><span data-stu-id="bdc6f-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bdc6f-146">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-148">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-148">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-149">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-150">El grupo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-150">The pool of the caller.</span></span> <span data-ttu-id="bdc6f-151">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla Pool en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-153">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-153">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-154">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-155">Grupo del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-155">The pool of the call receiver.</span></span> <span data-ttu-id="bdc6f-156">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla Pool en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-158">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-158">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-159">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-160">URI de SIP en la identidad de SIP declarada (PAI) del extremo de recepción.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="bdc6f-161">Se hace referencia a ella desde la <a href="lync-server-2013-user-table.md">tabla user en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-163">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-163">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-164">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-165">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-165">Caller’s URI.</span></span> <span data-ttu-id="bdc6f-166">Se hace referencia a ella desde la <a href="lync-server-2013-user-table.md">tabla user en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-168">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-168">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-169">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-170">Extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-170">Caller’s endpoint.</span></span> <span data-ttu-id="bdc6f-171">Se hace referencia a ella desde la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-173">bit</span><span class="sxs-lookup"><span data-stu-id="bdc6f-173">bit</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-174">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-175">Agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-175">Caller’s user agent.</span></span> <span data-ttu-id="bdc6f-176">Referencia de la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-178">smallint</span><span class="sxs-lookup"><span data-stu-id="bdc6f-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc6f-179">Prioridad de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-181">bit</span><span class="sxs-lookup"><span data-stu-id="bdc6f-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc6f-182">Esta columna se ha dejado de usar y no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="bdc6f-183">En su lugar, esta información se indica en una base de líneas por medios.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="bdc6f-184">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-186">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-186">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-187">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-188">P-asserted-Identity del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="bdc6f-189">La identidad de aserción de P (PAI) se usa para transmitir la verdadera identidad del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-191">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-191">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-192">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-193">Extremo que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc6f-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-195">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-195">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-196">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-197">Agente de usuario empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="bdc6f-198">Los agentes de usuario representan el dispositivo de extremo de cliente.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc6f-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="bdc6f-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc6f-200">entero</span><span class="sxs-lookup"><span data-stu-id="bdc6f-200">int</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-201">Externa</span><span class="sxs-lookup"><span data-stu-id="bdc6f-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc6f-202">URI de SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="bdc6f-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


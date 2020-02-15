---
title: 'Lync Server 2013: tabla de sesiones'
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
ms.openlocfilehash: c252ef5cd96511875fa299f44ca2a707f766f59a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="09379-102">Tabla Session en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09379-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09379-103">_**Última modificación del tema:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="09379-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="09379-104">Cada registro representa una sesión que implica audio o audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="09379-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="09379-105">Contiene información general sobre la sesión.</span><span class="sxs-lookup"><span data-stu-id="09379-105">It contains overall information about the session.</span></span> <span data-ttu-id="09379-106">Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.</span><span class="sxs-lookup"><span data-stu-id="09379-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09379-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="09379-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="09379-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="09379-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="09379-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="09379-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="09379-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="09379-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09379-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="09379-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-112">datetime</span><span class="sxs-lookup"><span data-stu-id="09379-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="09379-113">Principal</span><span class="sxs-lookup"><span data-stu-id="09379-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="09379-114">Se hace referencia a ella desde la <a href="lync-server-2013-dialog-table.md">tabla de cuadro de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="09379-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-116">int</span><span class="sxs-lookup"><span data-stu-id="09379-116">int</span></span></p></td>
<td><p><span data-ttu-id="09379-117">Principal</span><span class="sxs-lookup"><span data-stu-id="09379-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="09379-118">Se hace referencia a ella desde la <a href="lync-server-2013-dialog-table.md">tabla de cuadro de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="09379-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-120">int</span><span class="sxs-lookup"><span data-stu-id="09379-120">int</span></span></p></td>
<td><p><span data-ttu-id="09379-121">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-122">Clave de conferencia.</span><span class="sxs-lookup"><span data-stu-id="09379-122">Conference key.</span></span> <span data-ttu-id="09379-123">Se hace referencia a ella desde la <a href="lync-server-2013-conference-table.md">tabla de conferencia en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="09379-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-125">int</span><span class="sxs-lookup"><span data-stu-id="09379-125">int</span></span></p></td>
<td><p><span data-ttu-id="09379-126">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-127">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="09379-127">Correlation key.</span></span> <span data-ttu-id="09379-128">Referencia de la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="09379-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-130">bit</span><span class="sxs-lookup"><span data-stu-id="09379-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="09379-131">Categoría del cuadro de diálogo; 0 es Lync Server a la pierna del servidor de mediación; 1 es el servidor de mediación a la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="09379-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="09379-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-133">bit</span><span class="sxs-lookup"><span data-stu-id="09379-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09379-134">Marca que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="09379-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="09379-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-136">int</span><span class="sxs-lookup"><span data-stu-id="09379-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09379-137">Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían.</span><span class="sxs-lookup"><span data-stu-id="09379-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="09379-138">Para Lync Server, solo se define un valor.</span><span class="sxs-lookup"><span data-stu-id="09379-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="09379-139">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="09379-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="09379-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-141">datetime</span><span class="sxs-lookup"><span data-stu-id="09379-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="09379-142">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="09379-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-144">datetime</span><span class="sxs-lookup"><span data-stu-id="09379-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="09379-145">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="09379-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-147">int</span><span class="sxs-lookup"><span data-stu-id="09379-147">int</span></span></p></td>
<td><p><span data-ttu-id="09379-148">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-149">El grupo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="09379-149">The pool of the caller.</span></span> <span data-ttu-id="09379-150">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla Pool en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="09379-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-152">int</span><span class="sxs-lookup"><span data-stu-id="09379-152">int</span></span></p></td>
<td><p><span data-ttu-id="09379-153">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-154">Grupo del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="09379-154">The pool of the call receiver.</span></span> <span data-ttu-id="09379-155">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla Pool en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="09379-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-157">int</span><span class="sxs-lookup"><span data-stu-id="09379-157">int</span></span></p></td>
<td><p><span data-ttu-id="09379-158">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-159">URI de SIP en la identidad de SIP declarada (PAI) del extremo de recepción.</span><span class="sxs-lookup"><span data-stu-id="09379-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="09379-160">Se hace referencia a ella desde la <a href="lync-server-2013-user-table.md">tabla user en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="09379-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-162">int</span><span class="sxs-lookup"><span data-stu-id="09379-162">int</span></span></p></td>
<td><p><span data-ttu-id="09379-163">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-164">URI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-164">Caller’s URI.</span></span> <span data-ttu-id="09379-165">Se hace referencia a ella desde la <a href="lync-server-2013-user-table.md">tabla user en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="09379-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-167">int</span><span class="sxs-lookup"><span data-stu-id="09379-167">int</span></span></p></td>
<td><p><span data-ttu-id="09379-168">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-169">Extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-169">Caller’s endpoint.</span></span> <span data-ttu-id="09379-170">Se hace referencia a ella desde la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="09379-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-172">bit</span><span class="sxs-lookup"><span data-stu-id="09379-172">bit</span></span></p></td>
<td><p><span data-ttu-id="09379-173">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-174">Agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-174">Caller’s user agent.</span></span> <span data-ttu-id="09379-175">Referencia de la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="09379-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="09379-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-177">smallint</span><span class="sxs-lookup"><span data-stu-id="09379-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09379-178">Prioridad de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="09379-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-180">bit</span><span class="sxs-lookup"><span data-stu-id="09379-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09379-181">Esta columna se ha dejado de usar y no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09379-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="09379-182">En su lugar, esta información se indica en una base de líneas por medios.</span><span class="sxs-lookup"><span data-stu-id="09379-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="09379-183">Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="09379-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="09379-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-185">int</span><span class="sxs-lookup"><span data-stu-id="09379-185">int</span></span></p></td>
<td><p><span data-ttu-id="09379-186">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-187">P-asserted-Identity del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="09379-188">La identidad de aserción de P (PAI) se usa para transmitir la verdadera identidad del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="09379-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-190">int</span><span class="sxs-lookup"><span data-stu-id="09379-190">int</span></span></p></td>
<td><p><span data-ttu-id="09379-191">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-192">Extremo que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09379-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="09379-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-194">int</span><span class="sxs-lookup"><span data-stu-id="09379-194">int</span></span></p></td>
<td><p><span data-ttu-id="09379-195">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-196">Agente de usuario empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="09379-197">Los agentes de usuario representan el dispositivo de extremo de cliente.</span><span class="sxs-lookup"><span data-stu-id="09379-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09379-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="09379-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="09379-199">int</span><span class="sxs-lookup"><span data-stu-id="09379-199">int</span></span></p></td>
<td><p><span data-ttu-id="09379-200">Externa</span><span class="sxs-lookup"><span data-stu-id="09379-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09379-201">URI de SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="09379-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


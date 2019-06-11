---
title: 'Lync Server 2013: Tabla Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="6f266-102">Tabla Session en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f266-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f266-103">_**Última modificación del tema:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="6f266-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="6f266-104">Cada registro representa una sesión que incluye audio, audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="6f266-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="6f266-105">Contiene información general sobre la sesión.</span><span class="sxs-lookup"><span data-stu-id="6f266-105">It contains overall information about the session.</span></span> <span data-ttu-id="6f266-106">Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="6f266-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f266-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6f266-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6f266-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6f266-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f266-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6f266-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="6f266-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6f266-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6f266-114">Se hace referencia a ellos desde la <a href="lync-server-2013-dialog-table.md">tabla de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-116">int</span><span class="sxs-lookup"><span data-stu-id="6f266-116">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-117">Primary</span><span class="sxs-lookup"><span data-stu-id="6f266-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="6f266-118">Se hace referencia a ellos desde la <a href="lync-server-2013-dialog-table.md">tabla de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-120">int</span><span class="sxs-lookup"><span data-stu-id="6f266-120">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-122">Tecla de conferencia.</span><span class="sxs-lookup"><span data-stu-id="6f266-122">Conference key.</span></span> <span data-ttu-id="6f266-123">Se hace referencia a ellos desde la <a href="lync-server-2013-conference-table.md">tabla de conferencia en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-125">int</span><span class="sxs-lookup"><span data-stu-id="6f266-125">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-126">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-127">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="6f266-127">Correlation key.</span></span> <span data-ttu-id="6f266-128">Se hace referencia a ellos desde la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-130">bit</span><span class="sxs-lookup"><span data-stu-id="6f266-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f266-131">Categoría de cuadro de diálogo; 0 ¿se encuentra Lync Server en la pierna del servidor de mediación; 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="6f266-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-133">bit</span><span class="sxs-lookup"><span data-stu-id="6f266-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f266-134">Marcador que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="6f266-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-136">int</span><span class="sxs-lookup"><span data-stu-id="6f266-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f266-137">Este campo, si está presente, indica por qué no se omitió una llamada, incluso si los identificadores de omisión coinciden.</span><span class="sxs-lookup"><span data-stu-id="6f266-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="6f266-138">Para Lync Server, solo se define un valor.</span><span class="sxs-lookup"><span data-stu-id="6f266-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="6f266-139">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6f266-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-141">datetime</span><span class="sxs-lookup"><span data-stu-id="6f266-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f266-142">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-144">datetime</span><span class="sxs-lookup"><span data-stu-id="6f266-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f266-145">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-147">int</span><span class="sxs-lookup"><span data-stu-id="6f266-147">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-148">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-149">El grupo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="6f266-149">The pool of the caller.</span></span> <span data-ttu-id="6f266-150">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla de grupos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-152">int</span><span class="sxs-lookup"><span data-stu-id="6f266-152">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-153">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-154">La piscina del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-154">The pool of the call receiver.</span></span> <span data-ttu-id="6f266-155">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla de grupos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-157">int</span><span class="sxs-lookup"><span data-stu-id="6f266-157">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-158">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-159">URI de SIP en la identidad declarada por SIP (PAI) del punto final de recepción.</span><span class="sxs-lookup"><span data-stu-id="6f266-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="6f266-160">Se hace referencia a ellos desde la <a href="lync-server-2013-user-table.md">tabla de usuario en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-162">int</span><span class="sxs-lookup"><span data-stu-id="6f266-162">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-163">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-164">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="6f266-164">Caller’s URI.</span></span> <span data-ttu-id="6f266-165">Se hace referencia a ellos desde la <a href="lync-server-2013-user-table.md">tabla de usuario en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-167">int</span><span class="sxs-lookup"><span data-stu-id="6f266-167">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-168">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-169">Extremo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="6f266-169">Caller’s endpoint.</span></span> <span data-ttu-id="6f266-170">Se hace referencia a ellos desde la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-172">bit</span><span class="sxs-lookup"><span data-stu-id="6f266-172">bit</span></span></p></td>
<td><p><span data-ttu-id="6f266-173">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-174">Agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-174">Caller’s user agent.</span></span> <span data-ttu-id="6f266-175">Se hace referencia a ella desde la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f266-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-177">smallint</span><span class="sxs-lookup"><span data-stu-id="6f266-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f266-178">La prioridad de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-180">bit</span><span class="sxs-lookup"><span data-stu-id="6f266-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f266-181">Esta columna ha quedado obsoleta y no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f266-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6f266-182">En su lugar, esta información se notifica en una base de líneas por medios.</span><span class="sxs-lookup"><span data-stu-id="6f266-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="6f266-183">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6f266-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-185">int</span><span class="sxs-lookup"><span data-stu-id="6f266-185">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-186">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-187">P-asserted-identidad del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="6f266-188">La identidad de aserción de P (PAI) se usa para transmitir la verdadera identidad del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-190">int</span><span class="sxs-lookup"><span data-stu-id="6f266-190">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-191">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-192">Extremo que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f266-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-194">int</span><span class="sxs-lookup"><span data-stu-id="6f266-194">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-195">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-196">Agente de usuario empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="6f266-197">Los agentes de usuario representan el dispositivo de extremo cliente.</span><span class="sxs-lookup"><span data-stu-id="6f266-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f266-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="6f266-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6f266-199">int</span><span class="sxs-lookup"><span data-stu-id="6f266-199">int</span></span></p></td>
<td><p><span data-ttu-id="6f266-200">Extranjero</span><span class="sxs-lookup"><span data-stu-id="6f266-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f266-201">URI SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="6f266-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


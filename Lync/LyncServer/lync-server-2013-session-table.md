---
title: 'Lync Server 2013: Tabla Session'
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
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="a0967-102">Tabla Session en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0967-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0967-103">_**Última modificación del tema:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="a0967-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="a0967-104">Cada registro representa una sesión que incluye audio, audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0967-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="a0967-105">Contiene información general sobre la sesión.</span><span class="sxs-lookup"><span data-stu-id="a0967-105">It contains overall information about the session.</span></span> <span data-ttu-id="a0967-106">Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a0967-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0967-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a0967-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a0967-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a0967-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0967-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a0967-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a0967-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a0967-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0967-114">Se hace referencia a ellos desde la <a href="lync-server-2013-dialog-table.md">tabla de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-116">int</span><span class="sxs-lookup"><span data-stu-id="a0967-116">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a0967-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0967-118">Se hace referencia a ellos desde la <a href="lync-server-2013-dialog-table.md">tabla de diálogo en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-120">int</span><span class="sxs-lookup"><span data-stu-id="a0967-120">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-122">Tecla de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a0967-122">Conference key.</span></span> <span data-ttu-id="a0967-123">Se hace referencia a ellos desde la <a href="lync-server-2013-conference-table.md">tabla de conferencia en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-125">int</span><span class="sxs-lookup"><span data-stu-id="a0967-125">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-126">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-127">Clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="a0967-127">Correlation key.</span></span> <span data-ttu-id="a0967-128">Se hace referencia a ellos desde la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-130">bit</span><span class="sxs-lookup"><span data-stu-id="a0967-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0967-131">Categoría de cuadro de diálogo; 0 ¿se encuentra Lync Server en la pierna del servidor de mediación; 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="a0967-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-133">bit</span><span class="sxs-lookup"><span data-stu-id="a0967-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0967-134">Marcador que indica si la llamada se ha omitido o no.</span><span class="sxs-lookup"><span data-stu-id="a0967-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-136">int</span><span class="sxs-lookup"><span data-stu-id="a0967-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0967-137">Este campo, si está presente, indica por qué no se omitió una llamada, incluso si los identificadores de omisión coinciden.</span><span class="sxs-lookup"><span data-stu-id="a0967-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="a0967-138">Para Lync Server, solo se define un valor.</span><span class="sxs-lookup"><span data-stu-id="a0967-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="a0967-139">0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a0967-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-141">datetime</span><span class="sxs-lookup"><span data-stu-id="a0967-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0967-142">Hora de inicio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-144">datetime</span><span class="sxs-lookup"><span data-stu-id="a0967-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0967-145">Hora de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-147">int</span><span class="sxs-lookup"><span data-stu-id="a0967-147">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-148">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-149">El grupo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="a0967-149">The pool of the caller.</span></span> <span data-ttu-id="a0967-150">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla de grupos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-152">int</span><span class="sxs-lookup"><span data-stu-id="a0967-152">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-153">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-154">La piscina del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-154">The pool of the call receiver.</span></span> <span data-ttu-id="a0967-155">Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla de grupos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-157">int</span><span class="sxs-lookup"><span data-stu-id="a0967-157">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-158">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-159">URI de SIP en la identidad declarada por SIP (PAI) del punto final de recepción.</span><span class="sxs-lookup"><span data-stu-id="a0967-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="a0967-160">Se hace referencia a ellos desde la <a href="lync-server-2013-user-table.md">tabla de usuario en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-162">int</span><span class="sxs-lookup"><span data-stu-id="a0967-162">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-163">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-164">URI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="a0967-164">Caller’s URI.</span></span> <span data-ttu-id="a0967-165">Se hace referencia a ellos desde la <a href="lync-server-2013-user-table.md">tabla de usuario en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-167">int</span><span class="sxs-lookup"><span data-stu-id="a0967-167">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-168">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-169">Extremo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="a0967-169">Caller’s endpoint.</span></span> <span data-ttu-id="a0967-170">Se hace referencia a ellos desde la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-172">bit</span><span class="sxs-lookup"><span data-stu-id="a0967-172">bit</span></span></p></td>
<td><p><span data-ttu-id="a0967-173">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-174">Agente de usuario del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-174">Caller’s user agent.</span></span> <span data-ttu-id="a0967-175">Se hace referencia a ella desde la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0967-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-177">smallint</span><span class="sxs-lookup"><span data-stu-id="a0967-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0967-178">La prioridad de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-180">bit</span><span class="sxs-lookup"><span data-stu-id="a0967-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0967-181">Esta columna ha quedado obsoleta y no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0967-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a0967-182">En su lugar, esta información se notifica en una base de líneas por medios.</span><span class="sxs-lookup"><span data-stu-id="a0967-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="a0967-183">Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a0967-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-185">int</span><span class="sxs-lookup"><span data-stu-id="a0967-185">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-186">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-187">P-asserted-identidad del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="a0967-188">La identidad de aserción de P (PAI) se usa para transmitir la verdadera identidad del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-190">int</span><span class="sxs-lookup"><span data-stu-id="a0967-190">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-191">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-192">Extremo que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0967-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-194">int</span><span class="sxs-lookup"><span data-stu-id="a0967-194">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-195">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-196">Agente de usuario empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="a0967-197">Los agentes de usuario representan el dispositivo de extremo cliente.</span><span class="sxs-lookup"><span data-stu-id="a0967-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0967-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="a0967-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a0967-199">int</span><span class="sxs-lookup"><span data-stu-id="a0967-199">int</span></span></p></td>
<td><p><span data-ttu-id="a0967-200">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a0967-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0967-201">URI SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0967-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


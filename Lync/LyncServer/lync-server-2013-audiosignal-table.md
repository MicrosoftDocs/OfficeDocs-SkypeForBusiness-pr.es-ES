---
title: 'Lync Server 2013: Tabla AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="1d3a9-102">Tabla AudioSignal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d3a9-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d3a9-103">_**Última modificación del tema:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="1d3a9-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="1d3a9-104">Cada registro representa las métricas de señal de audio de un extremo.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="1d3a9-105">Normalmente, cada llamada tiene dos registros, uno para la persona que llama y el otro es para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d3a9-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1d3a9-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1d3a9-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1d3a9-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1d3a9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1d3a9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-115">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-115">int</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1d3a9-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-117">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="1d3a9-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-120">Primary</span><span class="sxs-lookup"><span data-stu-id="1d3a9-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-121">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-123">bit</span><span class="sxs-lookup"><span data-stu-id="1d3a9-123">bit</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-124">Primary</span><span class="sxs-lookup"><span data-stu-id="1d3a9-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="1d3a9-125">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="1d3a9-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="1d3a9-126">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="1d3a9-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-128">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-129">Representa el nivel de señal de audio de control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="1d3a9-130">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="1d3a9-131">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="1d3a9-132">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-134">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-135">Consulta SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-137">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-138">Representa el nivel de ruido de audio del control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="1d3a9-139">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="1d3a9-140">Para obtener una calidad aceptable, debe ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="1d3a9-141">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-143">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-144">Consulta SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-146">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-147">Métrica de mejora de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="1d3a9-148">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-148">The unit for this metric is dB.</span></span> <span data-ttu-id="1d3a9-149">Los valores más bajos representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-149">Lower values represent less echo.</span></span> <span data-ttu-id="1d3a9-150">El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-152">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-153">Promedio de problemas por cinco minutos para el procesamiento de altavoz.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="1d3a9-154">Para obtener una buena calidad, debe ser inferior a un período de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="1d3a9-155">No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-157">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-158">Promedio de problemas por cinco minutos para la captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="1d3a9-159">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="1d3a9-160">No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-162">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="1d3a9-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-163">Velocidad de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-165">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="1d3a9-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-166">Velocidad de desplazamiento del reloj del dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-168">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="1d3a9-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-169">Velocidad de desplazamiento del reloj del dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="1d3a9-170">Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-172">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="1d3a9-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-173">El altavoz promedio representa el error de marca de tiempo de la secuencia, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-175">smallint</span><span class="sxs-lookup"><span data-stu-id="1d3a9-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-176">El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="1d3a9-177">Causas de la entrada de conmutación de voz:</span><span class="sxs-lookup"><span data-stu-id="1d3a9-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="1d3a9-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="1d3a9-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="1d3a9-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="1d3a9-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="1d3a9-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="1d3a9-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="1d3a9-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="1d3a9-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="1d3a9-182">La causa puede ser una combinación de estas causas individuales.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="1d3a9-183">RegKey solo puede habilitar ENTER_VS_FORCEORCONVERGENCE para fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="1d3a9-184">El tipo de datos de esta columna se modificó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="1d3a9-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-187">Causas de un evento de eco:</span><span class="sxs-lookup"><span data-stu-id="1d3a9-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="1d3a9-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="1d3a9-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="1d3a9-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="1d3a9-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="1d3a9-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="1d3a9-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="1d3a9-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="1d3a9-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="1d3a9-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="1d3a9-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="1d3a9-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="1d3a9-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="1d3a9-194">La causa puede ser una combinación de estas causas individuales.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-196">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="1d3a9-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-p109">Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-202">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="1d3a9-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-203">Porcentaje de tiempo durante el que se detecta eco en el flujo enviado.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="1d3a9-204">Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-206">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-207">Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="1d3a9-208">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="1d3a9-209">Para obtener una buena calidad, el rango aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-211">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-212">Nivel de señal recibido en el servidor de mediación de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="1d3a9-213">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="1d3a9-214">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="1d3a9-215">Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-217">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-218">Control automático de ganancia (AGC) en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-220">float</span><span class="sxs-lookup"><span data-stu-id="1d3a9-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d3a9-221">El cuadrado de la media raíz (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-223">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-224">Nivel de señal como recibido en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="1d3a9-225">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-227">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-228">Nivel de señal como recibido en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="1d3a9-229">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-231">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-232">Nivel de ruido recibido en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="1d3a9-233">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-235">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-236">Nivel de ruido recibido en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="1d3a9-237">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-239">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-240">Nivel de señal enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="1d3a9-241">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-243">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-244">Nivel de señal enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="1d3a9-245">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3a9-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-247">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-248">Nivel de ruido enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="1d3a9-249">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d3a9-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1d3a9-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1d3a9-251">int</span><span class="sxs-lookup"><span data-stu-id="1d3a9-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d3a9-252">Nivel de ruido enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="1d3a9-253">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: tabla AudioSignal'
description: 'Lync Server 2013: tabla AudioSignal.'
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
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568766"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="ce428-103">Tabla AudioSignal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce428-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce428-104">_**Última modificación del tema:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="ce428-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="ce428-105">Cada registro representa métricas de señal de audio para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ce428-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="ce428-106">Normalmente, cada llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce428-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce428-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ce428-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ce428-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ce428-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce428-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ce428-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce428-113">Principal</span><span class="sxs-lookup"><span data-stu-id="ce428-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce428-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ce428-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-116">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-116">int</span></span></p></td>
<td><p><span data-ttu-id="ce428-117">Principal</span><span class="sxs-lookup"><span data-stu-id="ce428-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce428-118">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ce428-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="ce428-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ce428-121">Principal</span><span class="sxs-lookup"><span data-stu-id="ce428-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce428-122">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ce428-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-124">bit</span><span class="sxs-lookup"><span data-stu-id="ce428-124">bit</span></span></p></td>
<td><p><span data-ttu-id="ce428-125">Principal</span><span class="sxs-lookup"><span data-stu-id="ce428-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce428-126">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="ce428-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="ce428-127">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="ce428-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-129">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-130">Representa el nivel de señal de audio de control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="ce428-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="ce428-131">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="ce428-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ce428-132">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ce428-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="ce428-133">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="ce428-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-135">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-136">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="ce428-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-138">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-139">Representa el nivel de ruido de audio del control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="ce428-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="ce428-140">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="ce428-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ce428-141">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ce428-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="ce428-142">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="ce428-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-144">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-145">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="ce428-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-147">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-148">Métrica de mejora de pérdida de devolución de eco.</span><span class="sxs-lookup"><span data-stu-id="ce428-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="ce428-149">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="ce428-149">The unit for this metric is dB.</span></span> <span data-ttu-id="ce428-150">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="ce428-150">Lower values represent less echo.</span></span> <span data-ttu-id="ce428-151">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="ce428-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-153">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-154">Media de problemas por cinco minutos para la representación del altavoz.</span><span class="sxs-lookup"><span data-stu-id="ce428-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="ce428-155">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ce428-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="ce428-156">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="ce428-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-158">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-159">Media de problemas por cinco minutos para la captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="ce428-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="ce428-160">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ce428-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="ce428-161">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="ce428-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-163">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ce428-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-164">Tasa de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="ce428-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-166">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ce428-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-167">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="ce428-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-169">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ce428-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-170">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="ce428-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="ce428-171">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce428-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-173">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ce428-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-174">Error medio de marca de tiempo de la secuencia de representación del altavoz, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce428-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-176">smallint</span><span class="sxs-lookup"><span data-stu-id="ce428-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-177">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="ce428-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ce428-178">Causas de la entrada de conmutación de voz:</span><span class="sxs-lookup"><span data-stu-id="ce428-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="ce428-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="ce428-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="ce428-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="ce428-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="ce428-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="ce428-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="ce428-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="ce428-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="ce428-183">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="ce428-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="ce428-184">RegKey solo puede habilitar ENTER_VS_FORCEORCONVERGENCE mediante RegKey con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="ce428-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="ce428-185">El tipo de datos para esta columna se modificó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="ce428-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-188">Causas de un evento ECHO:</span><span class="sxs-lookup"><span data-stu-id="ce428-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="ce428-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="ce428-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="ce428-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="ce428-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="ce428-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="ce428-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="ce428-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="ce428-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="ce428-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="ce428-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="ce428-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="ce428-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="ce428-195">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="ce428-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-197">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ce428-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-198">Porcentaje de tiempo durante el que se detectó el eco en la secuencia de captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="ce428-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="ce428-199">Normalmente, los valores son bajos para auriculares o auriculares, y más arriba para los teléfonos de altavoces o los altavoces autónomos.</span><span class="sxs-lookup"><span data-stu-id="ce428-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="ce428-200">Para los dispositivos que admiten la cancelación del eco acústico en la tarjeta, los valores altos indican la pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="ce428-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="ce428-201">Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce428-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-203">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ce428-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-204">Porcentaje de tiempo en que se detecta eco en la secuencia enviada.</span><span class="sxs-lookup"><span data-stu-id="ce428-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="ce428-205">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="ce428-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-207">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-208">Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ce428-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="ce428-209">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="ce428-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ce428-210">Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="ce428-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-212">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-213">Nivel de señal recibido en el servidor de mediación de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce428-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="ce428-214">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ce428-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="ce428-215">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="ce428-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ce428-216">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ce428-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-218">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-219">Control de ganancia automático (AGC) en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ce428-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-221">float</span><span class="sxs-lookup"><span data-stu-id="ce428-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce428-222">El cuadrado raíz medio (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce428-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-224">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-225">Nivel de señal tal y como se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="ce428-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="ce428-226">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-228">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-229">Nivel de señal como recibido en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="ce428-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="ce428-230">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-232">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-233">Nivel de ruido según se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="ce428-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="ce428-234">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-236">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-237">Nivel de ruido que se recibe en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="ce428-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="ce428-238">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-240">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-241">Nivel de señal como enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="ce428-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="ce428-242">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-244">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-245">Nivel de señal como enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="ce428-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="ce428-246">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce428-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-248">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-249">Nivel de ruido enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="ce428-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="ce428-250">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce428-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ce428-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ce428-252">entero</span><span class="sxs-lookup"><span data-stu-id="ce428-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce428-253">Nivel de ruido enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="ce428-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="ce428-254">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce428-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


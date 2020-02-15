---
title: 'Lync Server 2013: tabla AudioSignal'
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
ms.openlocfilehash: 9d7dcf9337dceded96679411e575abc888164618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="d26ec-102">Tabla AudioSignal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d26ec-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d26ec-103">_**Última modificación del tema:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="d26ec-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="d26ec-104">Cada registro representa métricas de señal de audio para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d26ec-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="d26ec-105">Normalmente, cada llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d26ec-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d26ec-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d26ec-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d26ec-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d26ec-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d26ec-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d26ec-112">Principal</span><span class="sxs-lookup"><span data-stu-id="d26ec-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d26ec-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d26ec-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-115">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-115">int</span></span></p></td>
<td><p><span data-ttu-id="d26ec-116">Principal</span><span class="sxs-lookup"><span data-stu-id="d26ec-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="d26ec-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d26ec-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="d26ec-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d26ec-120">Principal</span><span class="sxs-lookup"><span data-stu-id="d26ec-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="d26ec-121">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d26ec-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-123">bit</span><span class="sxs-lookup"><span data-stu-id="d26ec-123">bit</span></span></p></td>
<td><p><span data-ttu-id="d26ec-124">Principal</span><span class="sxs-lookup"><span data-stu-id="d26ec-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="d26ec-125">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="d26ec-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="d26ec-126">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="d26ec-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-128">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-129">Representa el nivel de señal de audio de control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="d26ec-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="d26ec-130">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="d26ec-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d26ec-131">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="d26ec-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="d26ec-132">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="d26ec-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-134">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-135">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="d26ec-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-137">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-138">Representa el nivel de ruido de audio del control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="d26ec-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="d26ec-139">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="d26ec-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d26ec-140">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="d26ec-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="d26ec-141">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="d26ec-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-143">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-144">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="d26ec-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-146">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-147">Métrica de mejora de pérdida de devolución de eco.</span><span class="sxs-lookup"><span data-stu-id="d26ec-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="d26ec-148">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="d26ec-148">The unit for this metric is dB.</span></span> <span data-ttu-id="d26ec-149">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="d26ec-149">Lower values represent less echo.</span></span> <span data-ttu-id="d26ec-150">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="d26ec-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-152">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-153">Media de problemas por cinco minutos para la representación del altavoz.</span><span class="sxs-lookup"><span data-stu-id="d26ec-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="d26ec-154">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="d26ec-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="d26ec-155">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="d26ec-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-157">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-158">Media de problemas por cinco minutos para la captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="d26ec-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="d26ec-159">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="d26ec-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="d26ec-160">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="d26ec-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-162">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d26ec-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-163">Tasa de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="d26ec-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-165">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d26ec-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-166">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="d26ec-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-168">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d26ec-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-169">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="d26ec-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="d26ec-170">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d26ec-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-172">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d26ec-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-173">Error medio de marca de tiempo de la secuencia de representación del altavoz, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d26ec-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-175">smallint</span><span class="sxs-lookup"><span data-stu-id="d26ec-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-176">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="d26ec-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="d26ec-177">Causas de la entrada de conmutación de voz:</span><span class="sxs-lookup"><span data-stu-id="d26ec-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="d26ec-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="d26ec-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="d26ec-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d26ec-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d26ec-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="d26ec-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="d26ec-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d26ec-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d26ec-182">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="d26ec-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="d26ec-183">RegKey solo puede habilitar ENTER_VS_FORCEORCONVERGENCE mediante RegKey con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="d26ec-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="d26ec-184">El tipo de datos para esta columna se modificó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="d26ec-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-187">Causas de un evento ECHO:</span><span class="sxs-lookup"><span data-stu-id="d26ec-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="d26ec-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="d26ec-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="d26ec-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d26ec-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d26ec-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="d26ec-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="d26ec-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d26ec-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d26ec-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="d26ec-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="d26ec-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="d26ec-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="d26ec-194">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="d26ec-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-196">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d26ec-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-197">Porcentaje de tiempo durante el que se detectó el eco en la secuencia de captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="d26ec-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="d26ec-198">Normalmente, los valores son bajos para auriculares o auriculares, y más arriba para los teléfonos de altavoces o los altavoces autónomos.</span><span class="sxs-lookup"><span data-stu-id="d26ec-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="d26ec-199">Para los dispositivos que admiten la cancelación del eco acústico en la tarjeta, los valores altos indican la pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="d26ec-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="d26ec-200">Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d26ec-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-202">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d26ec-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-203">Porcentaje de tiempo en que se detecta eco en la secuencia enviada.</span><span class="sxs-lookup"><span data-stu-id="d26ec-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="d26ec-204">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="d26ec-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-206">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-207">Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d26ec-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="d26ec-208">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="d26ec-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d26ec-209">Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="d26ec-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-211">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-212">Nivel de señal recibido en el servidor de mediación de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d26ec-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="d26ec-213">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d26ec-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="d26ec-214">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="d26ec-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d26ec-215">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="d26ec-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-217">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-218">Control de ganancia automático (AGC) en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d26ec-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-220">float</span><span class="sxs-lookup"><span data-stu-id="d26ec-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d26ec-221">El cuadrado raíz medio (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d26ec-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-223">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-224">Nivel de señal tal y como se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="d26ec-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d26ec-225">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-227">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-228">Nivel de señal como recibido en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="d26ec-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d26ec-229">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-231">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-232">Nivel de ruido según se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="d26ec-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d26ec-233">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-235">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-236">Nivel de ruido que se recibe en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="d26ec-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d26ec-237">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-239">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-240">Nivel de señal como enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="d26ec-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d26ec-241">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-243">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-244">Nivel de señal como enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="d26ec-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d26ec-245">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26ec-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-247">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-248">Nivel de ruido enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="d26ec-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d26ec-249">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26ec-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d26ec-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d26ec-251">int</span><span class="sxs-lookup"><span data-stu-id="d26ec-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d26ec-252">Nivel de ruido enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="d26ec-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d26ec-253">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ec-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 2d09842cb8b905798855cef7e015e4d9b32e72dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="9900d-102">Tabla AudioSignal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9900d-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9900d-103">_**Última modificación del tema:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="9900d-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="9900d-104">Cada registro representa métricas de señal de audio para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9900d-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="9900d-105">Normalmente, cada llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9900d-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9900d-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9900d-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9900d-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9900d-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9900d-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9900d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9900d-112">Principal</span><span class="sxs-lookup"><span data-stu-id="9900d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9900d-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9900d-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-115">int</span><span class="sxs-lookup"><span data-stu-id="9900d-115">int</span></span></p></td>
<td><p><span data-ttu-id="9900d-116">Principal</span><span class="sxs-lookup"><span data-stu-id="9900d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9900d-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9900d-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="9900d-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9900d-120">Principal</span><span class="sxs-lookup"><span data-stu-id="9900d-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="9900d-121">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9900d-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-123">bit</span><span class="sxs-lookup"><span data-stu-id="9900d-123">bit</span></span></p></td>
<td><p><span data-ttu-id="9900d-124">Principal</span><span class="sxs-lookup"><span data-stu-id="9900d-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="9900d-125">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="9900d-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="9900d-126">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="9900d-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-128">int</span><span class="sxs-lookup"><span data-stu-id="9900d-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-129">Representa el nivel de señal de audio de control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="9900d-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="9900d-130">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="9900d-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9900d-131">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9900d-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="9900d-132">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="9900d-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-134">int</span><span class="sxs-lookup"><span data-stu-id="9900d-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-135">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="9900d-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-137">int</span><span class="sxs-lookup"><span data-stu-id="9900d-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-138">Representa el nivel de ruido de audio del control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="9900d-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="9900d-139">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="9900d-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9900d-140">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9900d-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="9900d-141">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="9900d-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-143">int</span><span class="sxs-lookup"><span data-stu-id="9900d-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-144">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="9900d-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-146">int</span><span class="sxs-lookup"><span data-stu-id="9900d-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-147">Métrica de mejora de pérdida de devolución de eco.</span><span class="sxs-lookup"><span data-stu-id="9900d-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="9900d-148">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="9900d-148">The unit for this metric is dB.</span></span> <span data-ttu-id="9900d-149">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="9900d-149">Lower values represent less echo.</span></span> <span data-ttu-id="9900d-150">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="9900d-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-152">int</span><span class="sxs-lookup"><span data-stu-id="9900d-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-153">Media de problemas por cinco minutos para la representación del altavoz.</span><span class="sxs-lookup"><span data-stu-id="9900d-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="9900d-154">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="9900d-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="9900d-155">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="9900d-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-157">int</span><span class="sxs-lookup"><span data-stu-id="9900d-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-158">Media de problemas por cinco minutos para la captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="9900d-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="9900d-159">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="9900d-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="9900d-160">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="9900d-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-162">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="9900d-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-163">Tasa de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="9900d-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-165">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="9900d-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-166">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="9900d-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-168">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="9900d-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-169">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="9900d-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="9900d-170">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9900d-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-172">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="9900d-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-173">Error medio de marca de tiempo de la secuencia de representación del altavoz, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9900d-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-175">smallint</span><span class="sxs-lookup"><span data-stu-id="9900d-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-176">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="9900d-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="9900d-177">Causas de la entrada de conmutación de voz:</span><span class="sxs-lookup"><span data-stu-id="9900d-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="9900d-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="9900d-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="9900d-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="9900d-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="9900d-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="9900d-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="9900d-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="9900d-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="9900d-182">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="9900d-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="9900d-183">RegKey solo puede habilitar ENTER_VS_FORCEORCONVERGENCE mediante RegKey con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="9900d-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="9900d-184">El tipo de datos para esta columna se modificó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="9900d-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-187">Causas de un evento ECHO:</span><span class="sxs-lookup"><span data-stu-id="9900d-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="9900d-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="9900d-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="9900d-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="9900d-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="9900d-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="9900d-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="9900d-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="9900d-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="9900d-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="9900d-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="9900d-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="9900d-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="9900d-194">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="9900d-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-196">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="9900d-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-197">Porcentaje de tiempo durante el que se detectó el eco en la secuencia de captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="9900d-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="9900d-198">Normalmente, los valores son bajos para auriculares o auriculares, y más arriba para los teléfonos de altavoces o los altavoces autónomos.</span><span class="sxs-lookup"><span data-stu-id="9900d-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="9900d-199">Para los dispositivos que admiten la cancelación del eco acústico en la tarjeta, los valores altos indican la pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="9900d-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="9900d-200">Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9900d-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-202">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="9900d-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-203">Porcentaje de tiempo en que se detecta eco en la secuencia enviada.</span><span class="sxs-lookup"><span data-stu-id="9900d-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="9900d-204">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="9900d-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-206">int</span><span class="sxs-lookup"><span data-stu-id="9900d-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-207">Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="9900d-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="9900d-208">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="9900d-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="9900d-209">Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="9900d-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-211">int</span><span class="sxs-lookup"><span data-stu-id="9900d-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-212">Nivel de señal recibido en el servidor de mediación de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="9900d-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="9900d-213">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="9900d-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="9900d-214">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="9900d-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="9900d-215">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="9900d-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-217">int</span><span class="sxs-lookup"><span data-stu-id="9900d-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-218">Control de ganancia automático (AGC) en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="9900d-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-220">float</span><span class="sxs-lookup"><span data-stu-id="9900d-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9900d-221">El cuadrado raíz medio (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9900d-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-223">int</span><span class="sxs-lookup"><span data-stu-id="9900d-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-224">Nivel de señal tal y como se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="9900d-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="9900d-225">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-227">int</span><span class="sxs-lookup"><span data-stu-id="9900d-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-228">Nivel de señal como recibido en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="9900d-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="9900d-229">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-231">int</span><span class="sxs-lookup"><span data-stu-id="9900d-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-232">Nivel de ruido según se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="9900d-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="9900d-233">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-235">int</span><span class="sxs-lookup"><span data-stu-id="9900d-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-236">Nivel de ruido que se recibe en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="9900d-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="9900d-237">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-239">int</span><span class="sxs-lookup"><span data-stu-id="9900d-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-240">Nivel de señal como enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="9900d-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="9900d-241">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-243">int</span><span class="sxs-lookup"><span data-stu-id="9900d-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-244">Nivel de señal como enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="9900d-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="9900d-245">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9900d-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-247">int</span><span class="sxs-lookup"><span data-stu-id="9900d-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-248">Nivel de ruido enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="9900d-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="9900d-249">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9900d-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="9900d-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="9900d-251">int</span><span class="sxs-lookup"><span data-stu-id="9900d-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9900d-252">Nivel de ruido enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="9900d-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="9900d-253">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9900d-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


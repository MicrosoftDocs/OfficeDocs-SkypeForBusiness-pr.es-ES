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
ms.openlocfilehash: de07393ef9f43346d0c1b4c96dcfdcf33f00513a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="3ae5f-102">Tabla AudioSignal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ae5f-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ae5f-103">_**Última modificación del tema:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="3ae5f-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="3ae5f-104">Cada registro representa métricas de señal de audio para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="3ae5f-105">Normalmente, cada llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ae5f-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3ae5f-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3ae5f-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3ae5f-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="3ae5f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-112">Principal</span><span class="sxs-lookup"><span data-stu-id="3ae5f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-115">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-115">int</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-116">Principal</span><span class="sxs-lookup"><span data-stu-id="3ae5f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="3ae5f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-120">Principal</span><span class="sxs-lookup"><span data-stu-id="3ae5f-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-121">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-123">bit</span><span class="sxs-lookup"><span data-stu-id="3ae5f-123">bit</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-124">Principal</span><span class="sxs-lookup"><span data-stu-id="3ae5f-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="3ae5f-125">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="3ae5f-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="3ae5f-126">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="3ae5f-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-128">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-129">Representa el nivel de señal de audio de control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="3ae5f-130">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="3ae5f-131">Para obtener una calidad aceptable, debe tener al menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="3ae5f-132">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-134">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-135">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-137">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-138">Representa el nivel de ruido de audio del control de ganancia posterior analógico.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="3ae5f-139">La unidad para esta métrica es dBmo.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="3ae5f-140">Para obtener una calidad aceptable, debe ser inferior a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="3ae5f-141">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-143">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-144">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-146">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-147">Métrica de mejora de pérdida de devolución de eco.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="3ae5f-148">La unidad para esta métrica es dB.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-148">The unit for this metric is dB.</span></span> <span data-ttu-id="3ae5f-149">Los valores inferiores representan menos eco.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-149">Lower values represent less echo.</span></span> <span data-ttu-id="3ae5f-150">El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-152">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-153">Media de problemas por cinco minutos para la representación del altavoz.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="3ae5f-154">Para obtener una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="3ae5f-155">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-157">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-158">Media de problemas por cinco minutos para la captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="3ae5f-159">Para una buena calidad, debe ser inferior a uno por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="3ae5f-160">No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-162">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3ae5f-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-163">Tasa de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-165">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3ae5f-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-166">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-168">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3ae5f-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-169">Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="3ae5f-170">Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-172">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3ae5f-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-173">Error medio de marca de tiempo de la secuencia de representación del altavoz, en milisegundos, en los últimos 20 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-175">smallint</span><span class="sxs-lookup"><span data-stu-id="3ae5f-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-176">El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="3ae5f-177">Causas de la entrada de conmutación de voz:</span><span class="sxs-lookup"><span data-stu-id="3ae5f-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="3ae5f-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="3ae5f-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="3ae5f-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="3ae5f-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="3ae5f-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="3ae5f-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="3ae5f-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="3ae5f-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="3ae5f-182">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="3ae5f-183">RegKey solo puede habilitar ENTER_VS_FORCEORCONVERGENCE mediante RegKey con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="3ae5f-184">El tipo de datos para esta columna se modificó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="3ae5f-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-187">Causas de un evento ECHO:</span><span class="sxs-lookup"><span data-stu-id="3ae5f-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="3ae5f-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="3ae5f-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="3ae5f-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="3ae5f-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="3ae5f-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="3ae5f-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="3ae5f-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="3ae5f-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="3ae5f-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="3ae5f-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="3ae5f-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="3ae5f-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="3ae5f-194">La causa puede ser una combinación de causas individuales.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-196">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3ae5f-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-197">Porcentaje de tiempo durante el que se detectó el eco en la secuencia de captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="3ae5f-198">Normalmente, los valores son bajos para auriculares o auriculares, y más arriba para los teléfonos de altavoces o los altavoces autónomos.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="3ae5f-199">Para los dispositivos que admiten la cancelación del eco acústico en la tarjeta, los valores altos indican la pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="3ae5f-200">Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-202">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3ae5f-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-203">Porcentaje de tiempo en que se detecta eco en la secuencia enviada.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="3ae5f-204">Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-206">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-207">Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="3ae5f-208">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="3ae5f-209">Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-211">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-212">Nivel de señal recibido en el servidor de mediación de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="3ae5f-213">Esto solo se aplica al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="3ae5f-214">La unidad de esta métrica es dBoV.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="3ae5f-215">Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-217">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-218">Control de ganancia automático (AGC) en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-220">float</span><span class="sxs-lookup"><span data-stu-id="3ae5f-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae5f-221">El cuadrado raíz medio (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-223">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-224">Nivel de señal tal y como se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="3ae5f-225">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-227">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-228">Nivel de señal como recibido en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="3ae5f-229">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-231">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-232">Nivel de ruido según se recibe en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="3ae5f-233">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-235">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-236">Nivel de ruido que se recibe en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="3ae5f-237">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-239">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-240">Nivel de señal como enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="3ae5f-241">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-243">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-244">Nivel de señal como enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="3ae5f-245">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae5f-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-247">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-248">Nivel de ruido enviado en el canal 1.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="3ae5f-249">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae5f-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3ae5f-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae5f-251">int</span><span class="sxs-lookup"><span data-stu-id="3ae5f-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae5f-252">Nivel de ruido enviado en el canal 2.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="3ae5f-253">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae5f-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


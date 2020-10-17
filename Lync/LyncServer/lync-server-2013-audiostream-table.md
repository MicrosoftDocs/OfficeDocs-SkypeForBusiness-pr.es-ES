---
title: 'Lync Server 2013: tabla AudioStream'
description: 'Lync Server 2013: tabla AudioStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552346"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="d0ab4-103">Tabla AudioStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0ab4-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0ab4-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d0ab4-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d0ab4-105">Cada registro representa una secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-105">Each record represents one audio stream.</span></span> <span data-ttu-id="d0ab4-106">Una línea de medios de audio suele contener dos secuencias de audio.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0ab4-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d0ab4-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d0ab4-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d0ab4-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d0ab4-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-113">Principal</span><span class="sxs-lookup"><span data-stu-id="d0ab4-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-116">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-116">int</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-117">Principal</span><span class="sxs-lookup"><span data-stu-id="d0ab4-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-118">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0ab4-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-121">Principal</span><span class="sxs-lookup"><span data-stu-id="d0ab4-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-122">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-124">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-124">int</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-125">Principal</span><span class="sxs-lookup"><span data-stu-id="d0ab4-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-126">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-128">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-129">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="d0ab4-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-131">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-132">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-134">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-135">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-137">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-138">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-139"><strong>Densidad</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-140">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-141">Densidad media de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-143">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-144">Duración media de la pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-146">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-147">Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-149">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-150">Duración media de brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-152">Int</span><span class="sxs-lookup"><span data-stu-id="d0ab4-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-153">Número de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-154"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-155">Int</span><span class="sxs-lookup"><span data-stu-id="d0ab4-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-156">Previsiones de ancho de banda de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-158">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-159">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-159">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="d0ab4-160">El intervalo es de 0,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-160">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="d0ab4-161">Esta métrica muestra la cantidad de MOS de red que se redujo debido a la vibración y pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-161">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="d0ab4-162">Para una calidad aceptable, debe ser inferior a 0,5.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-162">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-164">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-165">Degradación de MOS de red máxima durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-167">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-168">Degradación de MOS de red causada por la vibración.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-170">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-171">Degradación de MOS de red causada por la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-173">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-173">int</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-174">Externa</span><span class="sxs-lookup"><span data-stu-id="d0ab4-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0ab4-175">El códec de audio usado para la llamada, a la que se hace referencia desde la tabla PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-177">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-178">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-179"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-180">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-181">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="d0ab4-182">Para obtener una calidad aceptable, debe ser inferior a 100 ms.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-184">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-185">Tiempo de ida y vuelta máximo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-187">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-188">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="d0ab4-189">Esta métrica depende de la pérdida de paquetes, la vibración y el códec que se usan.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="d0ab4-190">El intervalo es de [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="d0ab4-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-192">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-193">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-195">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-196">La puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-198">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-199">El SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-201">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-202">La puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y la captura de las características del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-204">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-205">El RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-207">bit</span><span class="sxs-lookup"><span data-stu-id="d0ab4-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-208">Marca que indica si se usó FEC de audio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-210">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-211">Relación media de muestras ocultas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-213">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-214">Relación media de muestras extendidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-216">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d0ab4-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-217">Relación media de muestras comprimidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-218"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-219">bit</span><span class="sxs-lookup"><span data-stu-id="d0ab4-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-220">Se reciben datos de secuencia en el lado del receptor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-221"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-222">bit</span><span class="sxs-lookup"><span data-stu-id="d0ab4-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-223">Se reciben datos de secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-225">bit</span><span class="sxs-lookup"><span data-stu-id="d0ab4-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0ab4-226">1 significa que la dirección de la secuencia va desde el autor de la llamada al destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="d0ab4-227">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-229">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-230">Desviación estándar para las horas de llegada de vibración.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="d0ab4-231">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-233">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-234">Relación máxima de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="d0ab4-235">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-237">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-238">Desviación estándar de la proporción de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="d0ab4-239">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-241">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-242">Proporción de paquetes descartados por la restauración en comparación con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="d0ab4-243">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-245">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-246">Relación de los paquetes de corrección de errores de reenvío utilizados en comparación con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="d0ab4-247">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-249">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-250">Número máximo de paquetes de audio comprimidos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="d0ab4-251">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-253">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-254">Indica el porcentaje de tiempo que la llamada estuvo en estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="d0ab4-255">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-257">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-258">Indica el porcentaje de la llamada durante el cual la congestión se debió a la llegada retrasada de paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="d0ab4-259">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-261">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-262">Indica el porcentaje de tiempo que la llamada estaba compitiendo por los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="d0ab4-263">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-265">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-266">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d0ab4-267">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-269">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-270">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d0ab4-271">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-273">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-274">Desviación estándar de la estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d0ab4-275">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-277">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-278">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d0ab4-279">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-281">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p105">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-284">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-286">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p106">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-289">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-291">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p107">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-294">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-296">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p108">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-300">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-302">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p109">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-306">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-308">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p110">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-312">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-314">entero</span><span class="sxs-lookup"><span data-stu-id="d0ab4-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p111">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-318">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-320">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p112">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-324">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-326">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-p113">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d0ab4-330">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-332">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-333">Porcentaje de la llamada descodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="d0ab4-334">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-336">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-337">Porcentaje de la llamada representada como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="d0ab4-338">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-340">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-341">Tasa de pérdida de paquetes tras aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="d0ab4-342">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0ab4-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-344">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-345">Porcentaje de la llamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="d0ab4-346">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0ab4-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d0ab4-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0ab4-348">float</span><span class="sxs-lookup"><span data-stu-id="d0ab4-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0ab4-349">Porcentaje de la llamada capturado como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="d0ab4-350">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0ab4-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Tabla AudioStream'
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="4cf68-102">Tabla AudioStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cf68-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cf68-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4cf68-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4cf68-104">Cada registro representa una secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="4cf68-104">Each record represents one audio stream.</span></span> <span data-ttu-id="4cf68-105">Una línea de medios de audio normalmente contiene dos secuencias de audio.</span><span class="sxs-lookup"><span data-stu-id="4cf68-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cf68-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4cf68-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4cf68-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4cf68-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-111">datetime</span><span class="sxs-lookup"><span data-stu-id="4cf68-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4cf68-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4cf68-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4cf68-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4cf68-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-115">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-115">int</span></span></p></td>
<td><p><span data-ttu-id="4cf68-116">Primary</span><span class="sxs-lookup"><span data-stu-id="4cf68-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="4cf68-117">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4cf68-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="4cf68-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4cf68-120">Primary</span><span class="sxs-lookup"><span data-stu-id="4cf68-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="4cf68-121">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4cf68-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-123">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-123">int</span></span></p></td>
<td><p><span data-ttu-id="4cf68-124">Primary</span><span class="sxs-lookup"><span data-stu-id="4cf68-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="4cf68-125">IDENTIFICADOR exclusivo dentro de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="4cf68-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-127">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-128">Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="4cf68-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-130">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-131">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-133">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="4cf68-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-134">Tasa promedio de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-136">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="4cf68-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-137">Pérdida máxima de paquetes observadas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-139">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4cf68-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-140">Densidad promedio de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-142">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-143">Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-145">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4cf68-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-146">Densidad media de pérdida de paquetes entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="4cf68-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-148">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-149">Duración media de los huecos entre las ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="4cf68-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-151">ENT</span><span class="sxs-lookup"><span data-stu-id="4cf68-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-152">Recuento de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="4cf68-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-153"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-154">ENT</span><span class="sxs-lookup"><span data-stu-id="4cf68-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-155">Cálculo de ancho de banda para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="4cf68-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-157">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-158">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="4cf68-159">El intervalo está comprendido entre 0,0 y 5,0.</span><span class="sxs-lookup"><span data-stu-id="4cf68-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="4cf68-160">Esta métrica muestra el monto que se redujo en el MOS de red debido a la vibración y a la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="4cf68-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="4cf68-161">Para una calidad aceptable, debe ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="4cf68-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-163">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-164">La degradación de OP máxima de red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-166">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-167">Degradación de MOS de red causada por vibración.</span><span class="sxs-lookup"><span data-stu-id="4cf68-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-169">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-170">Degradación de MOS de red causada por pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="4cf68-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-172">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-172">int</span></span></p></td>
<td><p><span data-ttu-id="4cf68-173">Extranjero</span><span class="sxs-lookup"><span data-stu-id="4cf68-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4cf68-174">El códec de audio usado para la llamada, al que se hace referencia desde la tabla PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="4cf68-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-176">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-177">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="4cf68-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-179">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-180">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="4cf68-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="4cf68-181">Para obtener una calidad aceptable, debe ser inferior a 100 $.</span><span class="sxs-lookup"><span data-stu-id="4cf68-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-183">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-184">Tiempo máximo de ida y vuelta para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="4cf68-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-186">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-187">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="4cf68-188">Esta métrica depende de la pérdida del paquete, de la vibración y del códec usado.</span><span class="sxs-lookup"><span data-stu-id="4cf68-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="4cf68-189">El rango es de [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="4cf68-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-191">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-192">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-194">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-195">La puntuación media de escucha de banda ancha prevista para el audio enviado, incluyendo el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="4cf68-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-197">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-198">El SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-200">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-201">La puntuación media de escucha de banda ancha prevista para el audio recibido de la red, incluido el nivel de voz, el nivel de ruido, el códec, las condiciones de la red y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="4cf68-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-203">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4cf68-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-204">El RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-206">bit</span><span class="sxs-lookup"><span data-stu-id="4cf68-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-207">Marca que indica si se usó el audio FEC para la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-209">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="4cf68-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-210">Relación media entre las muestras ocultas generadas por la corrección de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="4cf68-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-212">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="4cf68-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-213">Relación media de muestras extendidas generadas por la recuperación de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="4cf68-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-215">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="4cf68-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-216">Relación media de muestras comprimidas generadas por la corrección de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="4cf68-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-217"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-218">bit</span><span class="sxs-lookup"><span data-stu-id="4cf68-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-219">Se reciben los datos de la secuencia del lado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="4cf68-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-220"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-221">bit</span><span class="sxs-lookup"><span data-stu-id="4cf68-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-222">Se reciben los datos de la secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="4cf68-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-224">bit</span><span class="sxs-lookup"><span data-stu-id="4cf68-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4cf68-225">1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="4cf68-226">0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="4cf68-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-228">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-229">Desviación estándar para las horas de llegada de la vibración.</span><span class="sxs-lookup"><span data-stu-id="4cf68-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="4cf68-230">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-232">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-233">Relación máxima de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="4cf68-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="4cf68-234">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-236">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-237">Desviación estándar para la proporción de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="4cf68-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="4cf68-238">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-240">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-241">Proporción de paquetes descartados por el healro comparado con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="4cf68-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="4cf68-242">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-244">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-245">Relación entre los paquetes de corrección de errores de reenvío en comparación con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="4cf68-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="4cf68-246">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-248">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-249">Número máximo de paquetes de audio que el Healer ha comprimido.</span><span class="sxs-lookup"><span data-stu-id="4cf68-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="4cf68-250">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-252">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-253">Indica el porcentaje de la hora en que la llamada se encontraba en un estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="4cf68-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="4cf68-254">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-256">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-257">Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada demorada de los paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="4cf68-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="4cf68-258">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-260">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-261">Indica el porcentaje de la hora en que la llamada compite en los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="4cf68-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="4cf68-262">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-264">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-265">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4cf68-266">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-268">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-269">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4cf68-270">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-272">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-273">Desviación estándar de la estimación del ancho de banda medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4cf68-274">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-276">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-277">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="4cf68-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4cf68-278">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-280">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-281">Cantidad total de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="4cf68-281">Total amount of one-way latency.</span></span> <span data-ttu-id="4cf68-282">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-283">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-285">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-286">Cantidad promedio de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="4cf68-286">Average amount of one-way latency.</span></span> <span data-ttu-id="4cf68-287">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-288">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-290">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-291">Cantidad máxima de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="4cf68-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="4cf68-292">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-293">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-295">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-296">Total de repeticiones de ráfagas unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="4cf68-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="4cf68-297">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="4cf68-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="4cf68-298">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-299">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-301">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-302">Densidad de ráfaga unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="4cf68-302">Total one-way burst density.</span></span> <span data-ttu-id="4cf68-303">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="4cf68-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="4cf68-304">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-305">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-307">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-308">Total de duración de ráfaga unidireccional.</span><span class="sxs-lookup"><span data-stu-id="4cf68-308">Total one-way burst duration.</span></span> <span data-ttu-id="4cf68-309">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="4cf68-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="4cf68-310">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-311">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-313">int</span><span class="sxs-lookup"><span data-stu-id="4cf68-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-314">Total de repeticiones de intervalos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="4cf68-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="4cf68-315">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="4cf68-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="4cf68-316">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-317">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-319">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-320">Densidad de brechas en un camino total.</span><span class="sxs-lookup"><span data-stu-id="4cf68-320">Total one-way gap density.</span></span> <span data-ttu-id="4cf68-321">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="4cf68-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="4cf68-322">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-323">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-325">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-326">Duración del intervalo unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="4cf68-326">Total one-way gap duration.</span></span> <span data-ttu-id="4cf68-327">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="4cf68-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="4cf68-328">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf68-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4cf68-329">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-331">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-332">Porcentaje de la llamada descodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="4cf68-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="4cf68-333">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-335">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-336">Porcentaje de la llamada representada como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="4cf68-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="4cf68-337">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-339">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-340">Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="4cf68-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="4cf68-341">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cf68-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-343">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-344">Porcentaje de la llamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="4cf68-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="4cf68-345">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cf68-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="4cf68-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4cf68-347">float</span><span class="sxs-lookup"><span data-stu-id="4cf68-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4cf68-348">Porcentaje de la llamada capturada como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="4cf68-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="4cf68-349">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cf68-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: tabla AudioStream'
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
ms.openlocfilehash: 0f169a00a9eff262d0229daf6e52110d64cf7a34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="52852-102">Tabla AudioStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52852-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52852-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="52852-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="52852-104">Cada registro representa una secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="52852-104">Each record represents one audio stream.</span></span> <span data-ttu-id="52852-105">Una línea de medios de audio suele contener dos secuencias de audio.</span><span class="sxs-lookup"><span data-stu-id="52852-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52852-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="52852-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="52852-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="52852-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="52852-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="52852-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="52852-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="52852-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52852-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="52852-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-111">datetime</span><span class="sxs-lookup"><span data-stu-id="52852-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="52852-112">Principal</span><span class="sxs-lookup"><span data-stu-id="52852-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="52852-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="52852-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="52852-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-115">int</span><span class="sxs-lookup"><span data-stu-id="52852-115">int</span></span></p></td>
<td><p><span data-ttu-id="52852-116">Principal</span><span class="sxs-lookup"><span data-stu-id="52852-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="52852-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="52852-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="52852-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="52852-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="52852-120">Principal</span><span class="sxs-lookup"><span data-stu-id="52852-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="52852-121">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="52852-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="52852-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-123">int</span><span class="sxs-lookup"><span data-stu-id="52852-123">int</span></span></p></td>
<td><p><span data-ttu-id="52852-124">Principal</span><span class="sxs-lookup"><span data-stu-id="52852-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="52852-125">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="52852-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="52852-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-127">int</span><span class="sxs-lookup"><span data-stu-id="52852-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-128">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="52852-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="52852-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-130">int</span><span class="sxs-lookup"><span data-stu-id="52852-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-131">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="52852-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-133">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="52852-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-134">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="52852-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-136">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="52852-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-137">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-138"><strong>Densidad</strong></span><span class="sxs-lookup"><span data-stu-id="52852-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-139">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="52852-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-140">Densidad media de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="52852-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-142">int</span><span class="sxs-lookup"><span data-stu-id="52852-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-143">Duración media de la pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="52852-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-145">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="52852-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-146">Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="52852-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="52852-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-148">int</span><span class="sxs-lookup"><span data-stu-id="52852-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-149">Duración media de brechas entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="52852-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="52852-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-151">Int</span><span class="sxs-lookup"><span data-stu-id="52852-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-152">Número de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="52852-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-153"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="52852-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-154">Int</span><span class="sxs-lookup"><span data-stu-id="52852-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-155">Previsiones de ancho de banda de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="52852-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="52852-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-157">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-158">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="52852-159">El intervalo es de 0,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="52852-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="52852-160">Esta métrica muestra la cantidad de MOS de red que se redujo debido a la vibración y pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="52852-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="52852-161">Para una calidad aceptable, debe ser inferior a 0,5.</span><span class="sxs-lookup"><span data-stu-id="52852-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="52852-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-163">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-164">Degradación de MOS de red máxima durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="52852-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-166">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-167">Degradación de MOS de red causada por la vibración.</span><span class="sxs-lookup"><span data-stu-id="52852-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="52852-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-169">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-170">Degradación de MOS de red causada por la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="52852-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="52852-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-172">int</span><span class="sxs-lookup"><span data-stu-id="52852-172">int</span></span></p></td>
<td><p><span data-ttu-id="52852-173">Externa</span><span class="sxs-lookup"><span data-stu-id="52852-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52852-174">El códec de audio usado para la llamada, a la que se hace referencia desde la tabla PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="52852-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="52852-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-176">int</span><span class="sxs-lookup"><span data-stu-id="52852-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-177">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="52852-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-178"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="52852-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-179">int</span><span class="sxs-lookup"><span data-stu-id="52852-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-180">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="52852-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="52852-181">Para obtener una calidad aceptable, debe ser inferior a 100 ms.</span><span class="sxs-lookup"><span data-stu-id="52852-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="52852-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-183">int</span><span class="sxs-lookup"><span data-stu-id="52852-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-184">Tiempo de ida y vuelta máximo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="52852-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="52852-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-186">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-187">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="52852-188">Esta métrica depende de la pérdida de paquetes, la vibración y el códec que se usan.</span><span class="sxs-lookup"><span data-stu-id="52852-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="52852-189">El intervalo es de [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="52852-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="52852-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-191">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-192">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="52852-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-194">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-195">La puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="52852-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="52852-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-197">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-198">El SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="52852-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-200">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-201">La puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y la captura de las características del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52852-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="52852-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-203">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-204">El RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="52852-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-206">bit</span><span class="sxs-lookup"><span data-stu-id="52852-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-207">Marca que indica si se usó FEC de audio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="52852-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-209">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-210">Relación media de muestras ocultas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="52852-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="52852-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-212">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-213">Relación media de muestras extendidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="52852-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="52852-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-215">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="52852-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-216">Relación media de muestras comprimidas generadas por la recuperación de audio en muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="52852-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-217"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="52852-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-218">bit</span><span class="sxs-lookup"><span data-stu-id="52852-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-219">Se reciben datos de secuencia en el lado del receptor.</span><span class="sxs-lookup"><span data-stu-id="52852-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-220"><strong>Salida</strong></span><span class="sxs-lookup"><span data-stu-id="52852-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-221">bit</span><span class="sxs-lookup"><span data-stu-id="52852-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-222">Se reciben datos de secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="52852-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="52852-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-224">bit</span><span class="sxs-lookup"><span data-stu-id="52852-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52852-225">1 significa que la dirección de la secuencia va desde el autor de la llamada al destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="52852-226">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="52852-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-228">float</span><span class="sxs-lookup"><span data-stu-id="52852-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-229">Desviación estándar para las horas de llegada de vibración.</span><span class="sxs-lookup"><span data-stu-id="52852-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="52852-230">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="52852-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-232">float</span><span class="sxs-lookup"><span data-stu-id="52852-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-233">Relación máxima de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="52852-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="52852-234">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="52852-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-236">float</span><span class="sxs-lookup"><span data-stu-id="52852-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-237">Desviación estándar de la proporción de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="52852-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="52852-238">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52852-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-240">float</span><span class="sxs-lookup"><span data-stu-id="52852-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-241">Proporción de paquetes descartados por la restauración en comparación con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="52852-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="52852-242">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52852-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-244">float</span><span class="sxs-lookup"><span data-stu-id="52852-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-245">Relación de los paquetes de corrección de errores de reenvío utilizados en comparación con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="52852-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="52852-246">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="52852-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-248">float</span><span class="sxs-lookup"><span data-stu-id="52852-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-249">Número máximo de paquetes de audio comprimidos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="52852-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="52852-250">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="52852-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-252">float</span><span class="sxs-lookup"><span data-stu-id="52852-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-253">Indica el porcentaje de tiempo que la llamada estuvo en estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="52852-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="52852-254">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="52852-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-256">float</span><span class="sxs-lookup"><span data-stu-id="52852-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-257">Indica el porcentaje de la llamada durante el cual la congestión se debió a la llegada retrasada de paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="52852-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="52852-258">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="52852-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-260">float</span><span class="sxs-lookup"><span data-stu-id="52852-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-261">Indica el porcentaje de tiempo que la llamada estaba compitiendo por los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="52852-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="52852-262">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="52852-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-264">int</span><span class="sxs-lookup"><span data-stu-id="52852-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-265">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="52852-266">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="52852-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-268">int</span><span class="sxs-lookup"><span data-stu-id="52852-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-269">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="52852-270">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="52852-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-272">int</span><span class="sxs-lookup"><span data-stu-id="52852-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-273">Desviación estándar de la estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="52852-274">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="52852-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-276">int</span><span class="sxs-lookup"><span data-stu-id="52852-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-277">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="52852-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="52852-278">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="52852-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-280">float</span><span class="sxs-lookup"><span data-stu-id="52852-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p105">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-283">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="52852-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-285">float</span><span class="sxs-lookup"><span data-stu-id="52852-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p106">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-288">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="52852-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-290">float</span><span class="sxs-lookup"><span data-stu-id="52852-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p107">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-293">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="52852-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-295">int</span><span class="sxs-lookup"><span data-stu-id="52852-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p108">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-299">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="52852-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-301">float</span><span class="sxs-lookup"><span data-stu-id="52852-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p109">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-305">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="52852-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-307">float</span><span class="sxs-lookup"><span data-stu-id="52852-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p110">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-311">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="52852-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-313">int</span><span class="sxs-lookup"><span data-stu-id="52852-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p111">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-317">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="52852-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-319">float</span><span class="sxs-lookup"><span data-stu-id="52852-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p112">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-323">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="52852-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-325">float</span><span class="sxs-lookup"><span data-stu-id="52852-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-p113">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="52852-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="52852-329">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="52852-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-331">float</span><span class="sxs-lookup"><span data-stu-id="52852-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-332">Porcentaje de la llamada descodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="52852-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="52852-333">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="52852-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-335">float</span><span class="sxs-lookup"><span data-stu-id="52852-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-336">Porcentaje de la llamada representada como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="52852-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="52852-337">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="52852-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-339">float</span><span class="sxs-lookup"><span data-stu-id="52852-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-340">Tasa de pérdida de paquetes tras aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="52852-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="52852-341">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52852-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="52852-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-343">float</span><span class="sxs-lookup"><span data-stu-id="52852-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-344">Porcentaje de la llamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="52852-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="52852-345">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52852-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="52852-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="52852-347">float</span><span class="sxs-lookup"><span data-stu-id="52852-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52852-348">Porcentaje de la llamada capturado como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="52852-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="52852-349">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52852-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Tabla AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="e3d6b-102">Tabla AudioStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3d6b-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3d6b-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e3d6b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e3d6b-104">Cada registro representa una secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-104">Each record represents one audio stream.</span></span> <span data-ttu-id="e3d6b-105">Una línea de medios de audio normalmente contiene dos secuencias de audio.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3d6b-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e3d6b-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e3d6b-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e3d6b-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e3d6b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e3d6b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-115">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-115">int</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e3d6b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-117">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e3d6b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-120">Primary</span><span class="sxs-lookup"><span data-stu-id="e3d6b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-121">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-123">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-123">int</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-124">Primary</span><span class="sxs-lookup"><span data-stu-id="e3d6b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-125">IDENTIFICADOR exclusivo dentro de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-127">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-128">Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="e3d6b-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-130">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-131">Vibración máxima de la red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-133">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-134">Tasa promedio de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-136">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-137">Pérdida máxima de paquetes observadas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-139">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-140">Densidad promedio de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-142">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-143">Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-145">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-146">Densidad media de pérdida de paquetes entre ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-148">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-149">Duración media de los huecos entre las ráfagas de pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-151">ENT</span><span class="sxs-lookup"><span data-stu-id="e3d6b-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-152">Recuento de paquetes de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-153"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-154">ENT</span><span class="sxs-lookup"><span data-stu-id="e3d6b-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-155">Cálculo de ancho de banda para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-157">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-158">Degradación de MOS de red para toda la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="e3d6b-159">El intervalo está comprendido entre 0,0 y 5,0.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="e3d6b-160">Esta métrica muestra el monto que se redujo en el MOS de red debido a la vibración y a la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="e3d6b-161">Para una calidad aceptable, debe ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-163">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-164">La degradación de OP máxima de red durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-166">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-167">Degradación de MOS de red causada por vibración.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-169">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-170">Degradación de MOS de red causada por pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-172">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-172">int</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-173">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e3d6b-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3d6b-174">El códec de audio usado para la llamada, al que se hace referencia desde la tabla PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-176">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-177">Frecuencia de muestreo de la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-179">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-180">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="e3d6b-181">Para obtener una calidad aceptable, debe ser inferior a 100 $.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-183">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-184">Tiempo máximo de ida y vuelta para la secuencia de audio.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-186">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-187">MOS de red de banda ancha promedio para la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="e3d6b-188">Esta métrica depende de la pérdida del paquete, de la vibración y del códec usado.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="e3d6b-189">El rango es de [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="e3d6b-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-191">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-192">MOS de red de banda ancha mínima para la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-194">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-195">La puntuación media de escucha de banda ancha prevista para el audio enviado, incluyendo el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-197">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-198">El SendListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-200">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-201">La puntuación media de escucha de banda ancha prevista para el audio recibido de la red, incluido el nivel de voz, el nivel de ruido, el códec, las condiciones de la red y las características del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-203">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-204">El RecvListenMOS mínimo para la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-206">bit</span><span class="sxs-lookup"><span data-stu-id="e3d6b-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-207">Marca que indica si se usó el audio FEC para la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-209">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-210">Relación media entre las muestras ocultas generadas por la corrección de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-212">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-213">Relación media de muestras extendidas generadas por la recuperación de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-215">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="e3d6b-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-216">Relación media de muestras comprimidas generadas por la corrección de audio a muestras típicas.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-217"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-218">bit</span><span class="sxs-lookup"><span data-stu-id="e3d6b-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-219">Se reciben los datos de la secuencia del lado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-220"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-221">bit</span><span class="sxs-lookup"><span data-stu-id="e3d6b-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-222">Se reciben los datos de la secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-224">bit</span><span class="sxs-lookup"><span data-stu-id="e3d6b-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3d6b-225">1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="e3d6b-226">0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-228">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-229">Desviación estándar para las horas de llegada de la vibración.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="e3d6b-230">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-232">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-233">Relación máxima de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="e3d6b-234">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-236">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-237">Desviación estándar para la proporción de paquetes ocultos por el Healer.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="e3d6b-238">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-240">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-241">Proporción de paquetes descartados por el healro comparado con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="e3d6b-242">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-244">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-245">Relación entre los paquetes de corrección de errores de reenvío en comparación con el número total de paquetes recibidos.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="e3d6b-246">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-248">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-249">Número máximo de paquetes de audio que el Healer ha comprimido.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="e3d6b-250">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-252">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-253">Indica el porcentaje de la hora en que la llamada se encontraba en un estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="e3d6b-254">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-256">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-257">Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada demorada de los paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="e3d6b-258">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-260">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-261">Indica el porcentaje de la hora en que la llamada compite en los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="e3d6b-262">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-264">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-265">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e3d6b-266">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-268">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-269">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e3d6b-270">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-272">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-273">Desviación estándar de la estimación del ancho de banda medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e3d6b-274">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-276">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-277">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e3d6b-278">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-280">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-281">Cantidad total de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-281">Total amount of one-way latency.</span></span> <span data-ttu-id="e3d6b-282">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-283">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-285">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-286">Cantidad promedio de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-286">Average amount of one-way latency.</span></span> <span data-ttu-id="e3d6b-287">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-288">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-290">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-291">Cantidad máxima de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="e3d6b-292">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-293">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-295">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-296">Total de repeticiones de ráfagas unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="e3d6b-297">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="e3d6b-298">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-299">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-301">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-302">Densidad de ráfaga unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-302">Total one-way burst density.</span></span> <span data-ttu-id="e3d6b-303">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="e3d6b-304">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-305">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-307">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-308">Total de duración de ráfaga unidireccional.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-308">Total one-way burst duration.</span></span> <span data-ttu-id="e3d6b-309">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="e3d6b-310">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-311">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-313">int</span><span class="sxs-lookup"><span data-stu-id="e3d6b-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-314">Total de repeticiones de intervalos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="e3d6b-315">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="e3d6b-316">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-317">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-319">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-320">Densidad de brechas en un camino total.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-320">Total one-way gap density.</span></span> <span data-ttu-id="e3d6b-321">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="e3d6b-322">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-323">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-325">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-326">Duración del intervalo unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-326">Total one-way gap duration.</span></span> <span data-ttu-id="e3d6b-327">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="e3d6b-328">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e3d6b-329">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-331">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-332">Porcentaje de la llamada descodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="e3d6b-333">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-335">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-336">Porcentaje de la llamada representada como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="e3d6b-337">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-339">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-340">Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="e3d6b-341">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d6b-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-343">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-344">Porcentaje de la llamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="e3d6b-345">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d6b-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e3d6b-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3d6b-347">float</span><span class="sxs-lookup"><span data-stu-id="e3d6b-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d6b-348">Porcentaje de la llamada capturada como estéreo por el cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="e3d6b-349">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


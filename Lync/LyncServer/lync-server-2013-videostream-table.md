---
title: 'Lync Server 2013: Tabla VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="9120b-102">Tabla VideoStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9120b-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9120b-103">_**Última modificación del tema:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="9120b-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="9120b-104">Cada registro representa una secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9120b-104">Each record represents one video stream.</span></span> <span data-ttu-id="9120b-105">Una línea de medios de vídeo suele contener dos secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9120b-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9120b-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9120b-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9120b-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9120b-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9120b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9120b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9120b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9120b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9120b-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9120b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-115">int</span><span class="sxs-lookup"><span data-stu-id="9120b-115">int</span></span></p></td>
<td><p><span data-ttu-id="9120b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="9120b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9120b-117">R al que se hace referencia en la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9120b-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9120b-120">Primary</span><span class="sxs-lookup"><span data-stu-id="9120b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="9120b-121">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9120b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-123">int</span><span class="sxs-lookup"><span data-stu-id="9120b-123">int</span></span></p></td>
<td><p><span data-ttu-id="9120b-124">Primary</span><span class="sxs-lookup"><span data-stu-id="9120b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="9120b-125">IDENTIFICADOR exclusivo dentro de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="9120b-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-127">smallint</span><span class="sxs-lookup"><span data-stu-id="9120b-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="9120b-128">Externo, principal</span><span class="sxs-lookup"><span data-stu-id="9120b-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="9120b-129">Descripción de la carga.</span><span class="sxs-lookup"><span data-stu-id="9120b-129">Payload description.</span></span> <span data-ttu-id="9120b-130">Para obtener más información, consulte la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9120b-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-132">int</span><span class="sxs-lookup"><span data-stu-id="9120b-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-133">Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="9120b-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-135">int</span><span class="sxs-lookup"><span data-stu-id="9120b-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-136">Vibración máxima de red durante la sesión de video.</span><span class="sxs-lookup"><span data-stu-id="9120b-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-138">int</span><span class="sxs-lookup"><span data-stu-id="9120b-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-139">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="9120b-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-141">int</span><span class="sxs-lookup"><span data-stu-id="9120b-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-142">Tiempo máximo de ida y vuelta para la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9120b-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-144">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="9120b-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-145">Tasa promedio de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9120b-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-147">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="9120b-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-148">Pérdida máxima de paquetes observadas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9120b-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-150">int</span><span class="sxs-lookup"><span data-stu-id="9120b-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-151">Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="9120b-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-152"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-153">int</span><span class="sxs-lookup"><span data-stu-id="9120b-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-154">Cálculo de ancho de banda para la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9120b-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-155"><strong>Resolución de la</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-156">carácter (9)</span><span class="sxs-lookup"><span data-stu-id="9120b-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-157">Resolución del vídeo en píxeles ancho multiplicado por píxeles alto.</span><span class="sxs-lookup"><span data-stu-id="9120b-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="9120b-158">Se ha notificado como una cadena.</span><span class="sxs-lookup"><span data-stu-id="9120b-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-160">int</span><span class="sxs-lookup"><span data-stu-id="9120b-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-161">Promedio de velocidad de bits de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9120b-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-163">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9120b-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-164">La velocidad de fotogramas de vídeo recibida.</span><span class="sxs-lookup"><span data-stu-id="9120b-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-166">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9120b-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-167">La velocidad de fotogramas de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="9120b-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-169">int</span><span class="sxs-lookup"><span data-stu-id="9120b-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-170">La máxima tasa de bits de vídeo durante la sesión de video.</span><span class="sxs-lookup"><span data-stu-id="9120b-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-172">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9120b-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-173">El porcentaje de fotogramas de video totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="9120b-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-175">bit</span><span class="sxs-lookup"><span data-stu-id="9120b-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-176">No disponible.</span><span class="sxs-lookup"><span data-stu-id="9120b-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-177"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-178">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9120b-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-179">El porcentaje de fotogramas de video totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="9120b-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-182">El porcentaje de la llamada que se encontraba en la resolución de formato de intercambio común (CIF).</span><span class="sxs-lookup"><span data-stu-id="9120b-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-185">El porcentaje de la llamada que se mostraba en la resolución VGA.</span><span class="sxs-lookup"><span data-stu-id="9120b-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-188">El porcentaje de la llamada que se encontraba en la resolución de HD720.</span><span class="sxs-lookup"><span data-stu-id="9120b-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-191">Porcentaje de la duración de la llamada sin colocación de fotogramas.</span><span class="sxs-lookup"><span data-stu-id="9120b-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-194">Porcentaje de la duración de la llamada con la caída de fotograma B.</span><span class="sxs-lookup"><span data-stu-id="9120b-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-197">Porcentaje de la duración de la llamada con fotograma de fotograma BP.</span><span class="sxs-lookup"><span data-stu-id="9120b-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-200">Porcentaje de la duración de la llamada con el fotograma BPSP.</span><span class="sxs-lookup"><span data-stu-id="9120b-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="9120b-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-203">Porcentaje de la duración de la llamada con el fotograma BPSPI.</span><span class="sxs-lookup"><span data-stu-id="9120b-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-204"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-205">bit</span><span class="sxs-lookup"><span data-stu-id="9120b-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-206">Se reciben los datos de la secuencia del lado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9120b-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-207"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-208">bit</span><span class="sxs-lookup"><span data-stu-id="9120b-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-209">Se reciben los datos de la secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-211">bit</span><span class="sxs-lookup"><span data-stu-id="9120b-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9120b-212">1 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="9120b-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="9120b-213">0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="9120b-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-215">float</span><span class="sxs-lookup"><span data-stu-id="9120b-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-216">Indica el porcentaje de la hora en que la llamada se encontraba en un estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="9120b-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="9120b-217">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-219">float</span><span class="sxs-lookup"><span data-stu-id="9120b-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-220">Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada demorada de los paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="9120b-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="9120b-221">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-223">float</span><span class="sxs-lookup"><span data-stu-id="9120b-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-224">Indica el porcentaje de la hora en que la llamada compite en los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="9120b-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="9120b-225">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-227">int</span><span class="sxs-lookup"><span data-stu-id="9120b-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-228">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9120b-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9120b-229">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-231">int</span><span class="sxs-lookup"><span data-stu-id="9120b-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-232">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9120b-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9120b-233">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-235">int</span><span class="sxs-lookup"><span data-stu-id="9120b-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-236">Desviación estándar de la estimación del ancho de banda medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9120b-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9120b-237">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-239">int</span><span class="sxs-lookup"><span data-stu-id="9120b-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-240">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9120b-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9120b-241">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-243">float</span><span class="sxs-lookup"><span data-stu-id="9120b-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-244">Porcentaje de la llamada en la que el punto de conexión determinó que la conexión de red no pudo admitir el vídeo de vista.</span><span class="sxs-lookup"><span data-stu-id="9120b-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="9120b-245">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-247">float</span><span class="sxs-lookup"><span data-stu-id="9120b-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-248">Cantidad total de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="9120b-248">Total amount of one-way latency.</span></span> <span data-ttu-id="9120b-249">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-250">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-252">float</span><span class="sxs-lookup"><span data-stu-id="9120b-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-253">Cantidad promedio de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="9120b-253">Average amount of one-way latency.</span></span> <span data-ttu-id="9120b-254">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-255">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-257">float</span><span class="sxs-lookup"><span data-stu-id="9120b-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-258">Cantidad máxima de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="9120b-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="9120b-259">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-260">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-262">int</span><span class="sxs-lookup"><span data-stu-id="9120b-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-263">Total de repeticiones de ráfagas unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="9120b-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="9120b-264">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="9120b-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9120b-265">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-266">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-268">int</span><span class="sxs-lookup"><span data-stu-id="9120b-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-269">Densidad de ráfaga unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="9120b-269">Total one-way burst density.</span></span> <span data-ttu-id="9120b-270">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="9120b-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9120b-271">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-272">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-274">float</span><span class="sxs-lookup"><span data-stu-id="9120b-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-275">Total de duración de ráfaga unidireccional.</span><span class="sxs-lookup"><span data-stu-id="9120b-275">Total one-way burst duration.</span></span> <span data-ttu-id="9120b-276">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="9120b-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9120b-277">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-278">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-280">int</span><span class="sxs-lookup"><span data-stu-id="9120b-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-281">Total de repeticiones de intervalos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="9120b-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="9120b-282">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="9120b-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9120b-283">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-284">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-286">float</span><span class="sxs-lookup"><span data-stu-id="9120b-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-287">Densidad de brechas en un camino total.</span><span class="sxs-lookup"><span data-stu-id="9120b-287">Total one-way gap density.</span></span> <span data-ttu-id="9120b-288">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="9120b-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9120b-289">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-290">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-292">float</span><span class="sxs-lookup"><span data-stu-id="9120b-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-293">Duración del intervalo unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="9120b-293">Total one-way gap duration.</span></span> <span data-ttu-id="9120b-294">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="9120b-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9120b-295">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="9120b-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9120b-296">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-297"><strong>Tasa</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-298">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9120b-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-299">Velocidad a la que se han perdido paquetes de video.</span><span class="sxs-lookup"><span data-stu-id="9120b-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="9120b-300">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-302">int</span><span class="sxs-lookup"><span data-stu-id="9120b-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-303">Cantidad promedio de ancho de banda asignado para el vídeo.</span><span class="sxs-lookup"><span data-stu-id="9120b-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="9120b-304">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-306">smallint</span><span class="sxs-lookup"><span data-stu-id="9120b-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="9120b-307">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9120b-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9120b-308">Tipo de códecs de vídeo usados por el remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="9120b-309">Para obtener más información, consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9120b-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9120b-310">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-312">int</span><span class="sxs-lookup"><span data-stu-id="9120b-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-313">Ancho de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="9120b-314">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-316">int</span><span class="sxs-lookup"><span data-stu-id="9120b-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-317">Alto de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="9120b-318">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-320">float</span><span class="sxs-lookup"><span data-stu-id="9120b-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-321">Promedio de transmisión de velocidad de fotogramas de vídeo utilizada por el remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="9120b-322">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-324">int</span><span class="sxs-lookup"><span data-stu-id="9120b-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-325">La tasa de bits máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="9120b-326">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-328">int</span><span class="sxs-lookup"><span data-stu-id="9120b-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-329">Promedio de velocidad de bits del remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-331">int</span><span class="sxs-lookup"><span data-stu-id="9120b-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-332">Número máximo de transmisiones de vídeo usadas por el remitente.</span><span class="sxs-lookup"><span data-stu-id="9120b-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="9120b-333">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-335">smallint</span><span class="sxs-lookup"><span data-stu-id="9120b-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="9120b-336">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9120b-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9120b-337">Códigos de vídeo usados por el destinatario.</span><span class="sxs-lookup"><span data-stu-id="9120b-337">Video codes used by the receiver.</span></span> <span data-ttu-id="9120b-338">Para obtener más información, consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9120b-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9120b-339">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-341">int</span><span class="sxs-lookup"><span data-stu-id="9120b-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-342">Ancho de resolución usado por el receptor.</span><span class="sxs-lookup"><span data-stu-id="9120b-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="9120b-343">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-345">int</span><span class="sxs-lookup"><span data-stu-id="9120b-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-346">Alto de resolución usado por el receptor.</span><span class="sxs-lookup"><span data-stu-id="9120b-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="9120b-347">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-348"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-349">float</span><span class="sxs-lookup"><span data-stu-id="9120b-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-350">Promedio de velocidad de fotogramas de video usada por el receptor.</span><span class="sxs-lookup"><span data-stu-id="9120b-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="9120b-351">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-353">int</span><span class="sxs-lookup"><span data-stu-id="9120b-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-354">La velocidad de bits máxima para el receptor.</span><span class="sxs-lookup"><span data-stu-id="9120b-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="9120b-355">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-357">int</span><span class="sxs-lookup"><span data-stu-id="9120b-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-358">Promedio de velocidad de bits para el receptor.</span><span class="sxs-lookup"><span data-stu-id="9120b-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="9120b-359">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-361">int</span><span class="sxs-lookup"><span data-stu-id="9120b-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-362">Máximo de transmisiones de vídeo para el destinatario.</span><span class="sxs-lookup"><span data-stu-id="9120b-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="9120b-363">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-365">int</span><span class="sxs-lookup"><span data-stu-id="9120b-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-366">Las transmisiones de video mínimas para el destinatario.</span><span class="sxs-lookup"><span data-stu-id="9120b-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="9120b-367">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-369">int</span><span class="sxs-lookup"><span data-stu-id="9120b-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-370">Modo de vídeo (por ejemplo, Galería o un único flujo) para el receptor.</span><span class="sxs-lookup"><span data-stu-id="9120b-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="9120b-371">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-372"><strong>Tasa</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-373">float</span><span class="sxs-lookup"><span data-stu-id="9120b-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-374">Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="9120b-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="9120b-375">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-376"><strong>Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-377">float</span><span class="sxs-lookup"><span data-stu-id="9120b-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-378">Porcentaje de tiempo que el indicador de capacidad dinámica estaba activo.</span><span class="sxs-lookup"><span data-stu-id="9120b-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="9120b-379">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-381">carácter (9)</span><span class="sxs-lookup"><span data-stu-id="9120b-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-382">Resolución mínima medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9120b-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="9120b-383">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-385">float</span><span class="sxs-lookup"><span data-stu-id="9120b-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-386">Porcentaje de la llamada por debajo del umbral de baja velocidad de bits (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="9120b-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="9120b-387">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-388"><strong>Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-389">float</span><span class="sxs-lookup"><span data-stu-id="9120b-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-390">Porcentaje de la llamada por debajo del umbral de baja velocidad de fotogramas (7,5 fotogramas por segundo, entrada).</span><span class="sxs-lookup"><span data-stu-id="9120b-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="9120b-391">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-392"><strong>Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-393">float</span><span class="sxs-lookup"><span data-stu-id="9120b-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-394">Porcentaje de la llamada que se produjo en la resolución más baja.</span><span class="sxs-lookup"><span data-stu-id="9120b-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="9120b-395">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="9120b-396">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9120b-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-398">float</span><span class="sxs-lookup"><span data-stu-id="9120b-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-399">Duración de la llamada en segundos.</span><span class="sxs-lookup"><span data-stu-id="9120b-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="9120b-400">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9120b-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="9120b-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="9120b-402">bit</span><span class="sxs-lookup"><span data-stu-id="9120b-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9120b-403">Indica si los datos se han agregado desde varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="9120b-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="9120b-404">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9120b-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


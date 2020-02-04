---
title: 'Lync Server 2013: Tabla VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="f26b3-102">Tabla VideoStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f26b3-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f26b3-103">_**Última modificación del tema:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="f26b3-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="f26b3-104">Cada registro representa una secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f26b3-104">Each record represents one video stream.</span></span> <span data-ttu-id="f26b3-105">Una línea de medios de vídeo suele contener dos secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f26b3-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f26b3-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f26b3-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f26b3-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f26b3-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f26b3-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f26b3-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f26b3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f26b3-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f26b3-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-115">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-115">int</span></span></p></td>
<td><p><span data-ttu-id="f26b3-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f26b3-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f26b3-117">R al que se hace referencia en la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f26b3-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f26b3-120">Primary</span><span class="sxs-lookup"><span data-stu-id="f26b3-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f26b3-121">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f26b3-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-123">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-123">int</span></span></p></td>
<td><p><span data-ttu-id="f26b3-124">Primary</span><span class="sxs-lookup"><span data-stu-id="f26b3-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f26b3-125">IDENTIFICADOR exclusivo dentro de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="f26b3-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-127">smallint</span><span class="sxs-lookup"><span data-stu-id="f26b3-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="f26b3-128">Externo, principal</span><span class="sxs-lookup"><span data-stu-id="f26b3-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="f26b3-129">Descripción de la carga.</span><span class="sxs-lookup"><span data-stu-id="f26b3-129">Payload description.</span></span> <span data-ttu-id="f26b3-130">Para obtener más información, consulte la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f26b3-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-132">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-133">Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="f26b3-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-135">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-136">Vibración máxima de red durante la sesión de video.</span><span class="sxs-lookup"><span data-stu-id="f26b3-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-138">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-139">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="f26b3-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-141">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-142">Tiempo máximo de ida y vuelta para la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f26b3-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-144">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="f26b3-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-145">Tasa promedio de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-147">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="f26b3-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-148">Pérdida máxima de paquetes observadas durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-150">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-151">Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="f26b3-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-152"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-153">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-154">Cálculo de ancho de banda para la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f26b3-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-155"><strong>Resolución de la</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-156">carácter (9)</span><span class="sxs-lookup"><span data-stu-id="f26b3-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-157">Resolución del vídeo en píxeles ancho multiplicado por píxeles alto.</span><span class="sxs-lookup"><span data-stu-id="f26b3-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="f26b3-158">Se ha notificado como una cadena.</span><span class="sxs-lookup"><span data-stu-id="f26b3-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-160">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-161">Promedio de velocidad de bits de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f26b3-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-163">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f26b3-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-164">La velocidad de fotogramas de vídeo recibida.</span><span class="sxs-lookup"><span data-stu-id="f26b3-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-166">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f26b3-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-167">La velocidad de fotogramas de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-169">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-170">La máxima tasa de bits de vídeo durante la sesión de video.</span><span class="sxs-lookup"><span data-stu-id="f26b3-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-172">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f26b3-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-173">El porcentaje de fotogramas de video totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="f26b3-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-175">bit</span><span class="sxs-lookup"><span data-stu-id="f26b3-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-176">No disponible.</span><span class="sxs-lookup"><span data-stu-id="f26b3-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-177"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-178">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f26b3-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-179">El porcentaje de fotogramas de video totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="f26b3-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-182">El porcentaje de la llamada que se encontraba en la resolución de formato de intercambio común (CIF).</span><span class="sxs-lookup"><span data-stu-id="f26b3-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-185">El porcentaje de la llamada que se mostraba en la resolución VGA.</span><span class="sxs-lookup"><span data-stu-id="f26b3-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-188">El porcentaje de la llamada que se encontraba en la resolución de HD720.</span><span class="sxs-lookup"><span data-stu-id="f26b3-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-191">Porcentaje de la duración de la llamada sin colocación de fotogramas.</span><span class="sxs-lookup"><span data-stu-id="f26b3-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-194">Porcentaje de la duración de la llamada con la caída de fotograma B.</span><span class="sxs-lookup"><span data-stu-id="f26b3-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-197">Porcentaje de la duración de la llamada con fotograma de fotograma BP.</span><span class="sxs-lookup"><span data-stu-id="f26b3-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-200">Porcentaje de la duración de la llamada con el fotograma BPSP.</span><span class="sxs-lookup"><span data-stu-id="f26b3-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="f26b3-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-203">Porcentaje de la duración de la llamada con el fotograma BPSPI.</span><span class="sxs-lookup"><span data-stu-id="f26b3-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-204"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-205">bit</span><span class="sxs-lookup"><span data-stu-id="f26b3-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-206">Se reciben los datos de la secuencia del lado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f26b3-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-207"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-208">bit</span><span class="sxs-lookup"><span data-stu-id="f26b3-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-209">Se reciben los datos de la secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-211">bit</span><span class="sxs-lookup"><span data-stu-id="f26b3-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f26b3-212">1 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f26b3-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f26b3-213">0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f26b3-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-215">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-216">Indica el porcentaje de la hora en que la llamada se encontraba en un estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="f26b3-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f26b3-217">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-219">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-220">Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada demorada de los paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="f26b3-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f26b3-221">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-223">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-224">Indica el porcentaje de la hora en que la llamada compite en los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="f26b3-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f26b3-225">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-227">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-228">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f26b3-229">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-231">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-232">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f26b3-233">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-235">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-236">Desviación estándar de la estimación del ancho de banda medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f26b3-237">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-239">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-240">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f26b3-241">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-243">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-244">Porcentaje de la llamada en la que el punto de conexión determinó que la conexión de red no pudo admitir el vídeo de vista.</span><span class="sxs-lookup"><span data-stu-id="f26b3-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="f26b3-245">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-247">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-248">Cantidad total de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f26b3-248">Total amount of one-way latency.</span></span> <span data-ttu-id="f26b3-249">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-250">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-252">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-253">Cantidad promedio de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f26b3-253">Average amount of one-way latency.</span></span> <span data-ttu-id="f26b3-254">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-255">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-257">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-258">Cantidad máxima de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f26b3-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="f26b3-259">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-260">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-262">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-263">Total de repeticiones de ráfagas unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f26b3-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="f26b3-264">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f26b3-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f26b3-265">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-266">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-268">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-269">Densidad de ráfaga unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="f26b3-269">Total one-way burst density.</span></span> <span data-ttu-id="f26b3-270">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f26b3-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f26b3-271">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-272">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-274">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-275">Total de duración de ráfaga unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f26b3-275">Total one-way burst duration.</span></span> <span data-ttu-id="f26b3-276">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f26b3-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f26b3-277">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-278">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-280">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-281">Total de repeticiones de intervalos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f26b3-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="f26b3-282">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="f26b3-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f26b3-283">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-284">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-286">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-287">Densidad de brechas en un camino total.</span><span class="sxs-lookup"><span data-stu-id="f26b3-287">Total one-way gap density.</span></span> <span data-ttu-id="f26b3-288">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="f26b3-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f26b3-289">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-290">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-292">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-293">Duración del intervalo unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="f26b3-293">Total one-way gap duration.</span></span> <span data-ttu-id="f26b3-294">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="f26b3-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f26b3-295">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f26b3-296">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-297"><strong>Tasa</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-298">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f26b3-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-299">Velocidad a la que se han perdido paquetes de video.</span><span class="sxs-lookup"><span data-stu-id="f26b3-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="f26b3-300">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-302">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-303">Cantidad promedio de ancho de banda asignado para el vídeo.</span><span class="sxs-lookup"><span data-stu-id="f26b3-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="f26b3-304">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-306">smallint</span><span class="sxs-lookup"><span data-stu-id="f26b3-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="f26b3-307">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f26b3-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f26b3-308">Tipo de códecs de vídeo usados por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="f26b3-309">Para obtener más información, consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f26b3-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f26b3-310">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-312">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-313">Ancho de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="f26b3-314">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-316">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-317">Alto de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="f26b3-318">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-320">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-321">Promedio de transmisión de velocidad de fotogramas de vídeo utilizada por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="f26b3-322">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-324">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-325">La tasa de bits máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="f26b3-326">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-328">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-329">Promedio de velocidad de bits del remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-331">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-332">Número máximo de transmisiones de vídeo usadas por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f26b3-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="f26b3-333">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-335">smallint</span><span class="sxs-lookup"><span data-stu-id="f26b3-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="f26b3-336">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f26b3-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f26b3-337">Códigos de vídeo usados por el destinatario.</span><span class="sxs-lookup"><span data-stu-id="f26b3-337">Video codes used by the receiver.</span></span> <span data-ttu-id="f26b3-338">Para obtener más información, consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f26b3-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f26b3-339">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-341">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-342">Ancho de resolución usado por el receptor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-343">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-345">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-346">Alto de resolución usado por el receptor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-347">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-348"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-349">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-350">Promedio de velocidad de fotogramas de video usada por el receptor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-351">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-353">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-354">La velocidad de bits máxima para el receptor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-355">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-357">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-358">Promedio de velocidad de bits para el receptor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-359">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-361">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-362">Máximo de transmisiones de vídeo para el destinatario.</span><span class="sxs-lookup"><span data-stu-id="f26b3-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-363">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-365">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-366">Las transmisiones de video mínimas para el destinatario.</span><span class="sxs-lookup"><span data-stu-id="f26b3-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-367">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-369">int</span><span class="sxs-lookup"><span data-stu-id="f26b3-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-370">Modo de vídeo (por ejemplo, Galería o un único flujo) para el receptor.</span><span class="sxs-lookup"><span data-stu-id="f26b3-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="f26b3-371">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-372"><strong>Tasa</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-373">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-374">Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="f26b3-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f26b3-375">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-376"><strong>Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-377">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-378">Porcentaje de tiempo que el indicador de capacidad dinámica estaba activo.</span><span class="sxs-lookup"><span data-stu-id="f26b3-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="f26b3-379">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-381">carácter (9)</span><span class="sxs-lookup"><span data-stu-id="f26b3-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-382">Resolución mínima medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f26b3-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="f26b3-383">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-385">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-386">Porcentaje de la llamada por debajo del umbral de baja velocidad de bits (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="f26b3-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="f26b3-387">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-388"><strong>Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-389">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-390">Porcentaje de la llamada por debajo del umbral de baja velocidad de fotogramas (7,5 fotogramas por segundo, entrada).</span><span class="sxs-lookup"><span data-stu-id="f26b3-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="f26b3-391">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-392"><strong>Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-393">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-394">Porcentaje de la llamada que se produjo en la resolución más baja.</span><span class="sxs-lookup"><span data-stu-id="f26b3-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="f26b3-395">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="f26b3-396">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f26b3-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-398">float</span><span class="sxs-lookup"><span data-stu-id="f26b3-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-399">Duración de la llamada en segundos.</span><span class="sxs-lookup"><span data-stu-id="f26b3-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="f26b3-400">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f26b3-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="f26b3-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="f26b3-402">bit</span><span class="sxs-lookup"><span data-stu-id="f26b3-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f26b3-403">Indica si los datos se han agregado desde varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="f26b3-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="f26b3-404">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f26b3-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


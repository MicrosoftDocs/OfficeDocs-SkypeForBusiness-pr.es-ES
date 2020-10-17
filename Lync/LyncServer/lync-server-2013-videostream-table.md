---
title: 'Lync Server 2013: tabla Videostream'
description: 'Lync Server 2013: tabla Videostream.'
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567996"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="f5b12-103">Tabla Videostream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b12-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5b12-104">_**Última modificación del tema:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="f5b12-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="f5b12-105">Cada registro representa una secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-105">Each record represents one video stream.</span></span> <span data-ttu-id="f5b12-106">Una línea de medios de vídeo suele contener dos secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5b12-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f5b12-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f5b12-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f5b12-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f5b12-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f5b12-113">Principal</span><span class="sxs-lookup"><span data-stu-id="f5b12-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5b12-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5b12-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-116">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-116">int</span></span></p></td>
<td><p><span data-ttu-id="f5b12-117">Principal</span><span class="sxs-lookup"><span data-stu-id="f5b12-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5b12-118">R al que se hace referencia desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5b12-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5b12-121">Principal</span><span class="sxs-lookup"><span data-stu-id="f5b12-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5b12-122">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5b12-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-124">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-124">int</span></span></p></td>
<td><p><span data-ttu-id="f5b12-125">Principal</span><span class="sxs-lookup"><span data-stu-id="f5b12-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5b12-126">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="f5b12-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-128">smallint</span><span class="sxs-lookup"><span data-stu-id="f5b12-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="f5b12-129">Externo, principal</span><span class="sxs-lookup"><span data-stu-id="f5b12-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="f5b12-130">Descripción de la carga.</span><span class="sxs-lookup"><span data-stu-id="f5b12-130">Payload description.</span></span> <span data-ttu-id="f5b12-131">Consulte la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f5b12-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-133">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-134">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="f5b12-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-136">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-137">Vibración máxima de la red durante la sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-138"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-139">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-140">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="f5b12-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-142">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-143">Tiempo de ida y vuelta máximo de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-145">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f5b12-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-146">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-148">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f5b12-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-149">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-151">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-152">Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="f5b12-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-153"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-154">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-155">Estimaciones de ancho de banda para la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-156"><strong>Resolución de</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-157">Char (9)</span><span class="sxs-lookup"><span data-stu-id="f5b12-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-p103">Resolución del vídeo en píxeles de ancho multiplicados por píxeles de alto. Se proporciona como cadena.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-161">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-162">Tasa de bits media de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-164">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5b12-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-165">La velocidad de fotogramas de vídeo recibida.</span><span class="sxs-lookup"><span data-stu-id="f5b12-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-167">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5b12-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-168">La velocidad de fotogramas de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-170">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-171">La velocidad de bits de vídeo máxima durante la sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-173">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5b12-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-174">Porcentaje de fotogramas de vídeo totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="f5b12-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-176">bit</span><span class="sxs-lookup"><span data-stu-id="f5b12-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-177">No disponible.</span><span class="sxs-lookup"><span data-stu-id="f5b12-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-179">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5b12-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-180">Porcentaje de fotogramas de vídeo totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="f5b12-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-183">Porcentaje de la llamada que estaba en la resolución CIF (formato de intercambio común).</span><span class="sxs-lookup"><span data-stu-id="f5b12-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-186">Porcentaje de la llamada que estaba en resolución VGA.</span><span class="sxs-lookup"><span data-stu-id="f5b12-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-189">Porcentaje de la llamada que se realizó en la resolución HD720.</span><span class="sxs-lookup"><span data-stu-id="f5b12-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-192">Porcentaje de duración de la llamada sin colocación de fotogramas.</span><span class="sxs-lookup"><span data-stu-id="f5b12-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-195">Porcentaje de duración de la llamada con caída de fotograma B.</span><span class="sxs-lookup"><span data-stu-id="f5b12-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-198">Porcentaje de duración de la llamada con colocada fotograma BP.</span><span class="sxs-lookup"><span data-stu-id="f5b12-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-201">Porcentaje de duración de la llamada con colocación de fotogramas BPSP.</span><span class="sxs-lookup"><span data-stu-id="f5b12-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5b12-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-204">Porcentaje de duración de la llamada con colocación de fotogramas BPSPI.</span><span class="sxs-lookup"><span data-stu-id="f5b12-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-205"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-206">bit</span><span class="sxs-lookup"><span data-stu-id="f5b12-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-207">Se reciben datos de secuencia en el lado del receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-208"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-209">bit</span><span class="sxs-lookup"><span data-stu-id="f5b12-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-210">Se reciben datos de secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-212">bit</span><span class="sxs-lookup"><span data-stu-id="f5b12-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5b12-213">1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.</span><span class="sxs-lookup"><span data-stu-id="f5b12-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f5b12-214">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-216">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-217">Indica el porcentaje de tiempo que la llamada estuvo en estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="f5b12-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f5b12-218">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-220">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-221">Indica el porcentaje de la llamada durante el cual la congestión se debió a la llegada retrasada de paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="f5b12-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f5b12-222">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-224">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-225">Indica el porcentaje de tiempo que la llamada estaba compitiendo por los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="f5b12-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f5b12-226">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-228">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-229">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f5b12-230">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-232">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-233">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f5b12-234">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-236">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-237">Desviación estándar de la estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f5b12-238">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-240">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-241">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f5b12-242">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-244">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-245">Porcentaje de la llamada en la que el extremo determinó que la conexión de red no pudo admitir el vídeo MultiView.</span><span class="sxs-lookup"><span data-stu-id="f5b12-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="f5b12-246">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-248">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p104">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-251">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-253">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p105">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-256">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-258">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p106">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-261">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-263">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p107">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-267">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-269">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p108">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-273">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-275">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p109">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-279">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-281">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p110">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-285">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-287">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p111">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-291">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-293">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-p112">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f5b12-297">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-299">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5b12-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-300">Tasa a la que se perdieron los paquetes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="f5b12-301">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-303">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-304">Cantidad máxima del ancho de banda asignada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="f5b12-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="f5b12-305">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-307">smallint</span><span class="sxs-lookup"><span data-stu-id="f5b12-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="f5b12-308">Externa</span><span class="sxs-lookup"><span data-stu-id="f5b12-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5b12-309">Tipo de códecs de vídeo que ha usado el remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="f5b12-310">Consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f5b12-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f5b12-311">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-313">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-314">Ancho de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="f5b12-315">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-317">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-318">Alto de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="f5b12-319">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-321">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-322">Promedio de transmisión de velocidad de fotogramas de vídeo usada por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="f5b12-323">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-325">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-326">Velocidad de bits máxima del remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="f5b12-327">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-329">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-330">Velocidad de bits media del remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-332">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-333">Número máximo de transmisiones de vídeo usadas por el remitente.</span><span class="sxs-lookup"><span data-stu-id="f5b12-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="f5b12-334">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-336">smallint</span><span class="sxs-lookup"><span data-stu-id="f5b12-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="f5b12-337">Externa</span><span class="sxs-lookup"><span data-stu-id="f5b12-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5b12-338">Códigos de vídeo usados por el receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-338">Video codes used by the receiver.</span></span> <span data-ttu-id="f5b12-339">Consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f5b12-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f5b12-340">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-342">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-343">Ancho de resolución usado por el receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-344">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-346">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-347">Altura de resolución usada por el receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-348">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-350">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-351">Velocidad media de fotogramas de vídeo usada por el receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-352">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-354">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-355">Velocidad de bits máxima del receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-356">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-358">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-359">Velocidad de bits media del receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-360">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-362">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-363">Secuencias de vídeo máximas para el receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-364">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-366">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-367">Secuencias de vídeo mínimas para el receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-368">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-370">entero</span><span class="sxs-lookup"><span data-stu-id="f5b12-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-371">Modo de vídeo (por ejemplo, Galería o secuencia única) para el receptor.</span><span class="sxs-lookup"><span data-stu-id="f5b12-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="f5b12-372">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-374">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-375">Tasa de pérdida de paquetes tras aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="f5b12-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f5b12-376">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-378">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-379">Porcentaje de tiempo que la marca de capacidad dinámica estuvo activa.</span><span class="sxs-lookup"><span data-stu-id="f5b12-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="f5b12-380">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-382">Char (9)</span><span class="sxs-lookup"><span data-stu-id="f5b12-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-383">Resolución mínima medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5b12-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="f5b12-384">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-386">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-387">Porcentaje de la llamada por debajo del umbral de velocidad de bits baja (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="f5b12-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="f5b12-388">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-390">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-391">Porcentaje de la llamada por debajo del umbral de velocidad de fotogramas baja (7,5 fotogramas por segundo, entrante).</span><span class="sxs-lookup"><span data-stu-id="f5b12-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="f5b12-392">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-394">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-395">Porcentaje de la llamada que se produjo con la resolución más baja.</span><span class="sxs-lookup"><span data-stu-id="f5b12-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="f5b12-396">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="f5b12-397">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5b12-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-399">float</span><span class="sxs-lookup"><span data-stu-id="f5b12-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-400">Duración de la llamada en segundos.</span><span class="sxs-lookup"><span data-stu-id="f5b12-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="f5b12-401">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5b12-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="f5b12-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="f5b12-403">bit</span><span class="sxs-lookup"><span data-stu-id="f5b12-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5b12-404">Indica si los datos se han agregado desde varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="f5b12-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="f5b12-405">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b12-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


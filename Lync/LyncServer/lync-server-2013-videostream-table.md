---
title: 'Lync Server 2013: tabla Videostream'
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
ms.openlocfilehash: 59799e9b6feb076575d8187936a42a408d0dba2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="66abc-102">Tabla Videostream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66abc-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66abc-103">_**Última modificación del tema:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="66abc-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="66abc-104">Cada registro representa una secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-104">Each record represents one video stream.</span></span> <span data-ttu-id="66abc-105">Una línea de medios de vídeo suele contener dos secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66abc-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="66abc-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="66abc-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="66abc-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66abc-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-111">datetime</span><span class="sxs-lookup"><span data-stu-id="66abc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="66abc-112">Principal</span><span class="sxs-lookup"><span data-stu-id="66abc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="66abc-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="66abc-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-115">int</span><span class="sxs-lookup"><span data-stu-id="66abc-115">int</span></span></p></td>
<td><p><span data-ttu-id="66abc-116">Principal</span><span class="sxs-lookup"><span data-stu-id="66abc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="66abc-117">R al que se hace referencia desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="66abc-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="66abc-120">Principal</span><span class="sxs-lookup"><span data-stu-id="66abc-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="66abc-121">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="66abc-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-123">int</span><span class="sxs-lookup"><span data-stu-id="66abc-123">int</span></span></p></td>
<td><p><span data-ttu-id="66abc-124">Principal</span><span class="sxs-lookup"><span data-stu-id="66abc-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="66abc-125">Identificador único de una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="66abc-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-127">smallint</span><span class="sxs-lookup"><span data-stu-id="66abc-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="66abc-128">Externo, principal</span><span class="sxs-lookup"><span data-stu-id="66abc-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="66abc-129">Descripción de la carga.</span><span class="sxs-lookup"><span data-stu-id="66abc-129">Payload description.</span></span> <span data-ttu-id="66abc-130">Consulte la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="66abc-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-132">int</span><span class="sxs-lookup"><span data-stu-id="66abc-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-133">Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="66abc-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-135">int</span><span class="sxs-lookup"><span data-stu-id="66abc-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-136">Vibración máxima de la red durante la sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-137"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-138">int</span><span class="sxs-lookup"><span data-stu-id="66abc-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-139">Tiempo de ida y vuelta de las estadísticas de RTCP.</span><span class="sxs-lookup"><span data-stu-id="66abc-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-141">int</span><span class="sxs-lookup"><span data-stu-id="66abc-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-142">Tiempo de ida y vuelta máximo de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-144">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="66abc-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-145">Promedio de frecuencia de pérdida de paquetes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-147">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="66abc-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-148">Pérdida máxima de paquetes observada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-150">int</span><span class="sxs-lookup"><span data-stu-id="66abc-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-151">Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="66abc-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-152"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-153">int</span><span class="sxs-lookup"><span data-stu-id="66abc-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-154">Estimaciones de ancho de banda para la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-155"><strong>Resolución de</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-156">Char (9)</span><span class="sxs-lookup"><span data-stu-id="66abc-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-p103">Resolución del vídeo en píxeles de ancho multiplicados por píxeles de alto. Se proporciona como cadena.</span><span class="sxs-lookup"><span data-stu-id="66abc-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-160">int</span><span class="sxs-lookup"><span data-stu-id="66abc-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-161">Tasa de bits media de la secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-163">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66abc-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-164">La velocidad de fotogramas de vídeo recibida.</span><span class="sxs-lookup"><span data-stu-id="66abc-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-166">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66abc-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-167">La velocidad de fotogramas de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="66abc-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-169">int</span><span class="sxs-lookup"><span data-stu-id="66abc-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-170">La velocidad de bits de vídeo máxima durante la sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-172">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66abc-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-173">Porcentaje de fotogramas de vídeo totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="66abc-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-175">bit</span><span class="sxs-lookup"><span data-stu-id="66abc-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-176">No disponible.</span><span class="sxs-lookup"><span data-stu-id="66abc-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-178">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66abc-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-179">Porcentaje de fotogramas de vídeo totales que se pierden.</span><span class="sxs-lookup"><span data-stu-id="66abc-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-182">Porcentaje de la llamada que estaba en la resolución CIF (formato de intercambio común).</span><span class="sxs-lookup"><span data-stu-id="66abc-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-185">Porcentaje de la llamada que estaba en resolución VGA.</span><span class="sxs-lookup"><span data-stu-id="66abc-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-188">Porcentaje de la llamada que se realizó en la resolución HD720.</span><span class="sxs-lookup"><span data-stu-id="66abc-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-191">Porcentaje de duración de la llamada sin colocación de fotogramas.</span><span class="sxs-lookup"><span data-stu-id="66abc-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-194">Porcentaje de duración de la llamada con caída de fotograma B.</span><span class="sxs-lookup"><span data-stu-id="66abc-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-197">Porcentaje de duración de la llamada con colocada fotograma BP.</span><span class="sxs-lookup"><span data-stu-id="66abc-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-200">Porcentaje de duración de la llamada con colocación de fotogramas BPSP.</span><span class="sxs-lookup"><span data-stu-id="66abc-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="66abc-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-203">Porcentaje de duración de la llamada con colocación de fotogramas BPSPI.</span><span class="sxs-lookup"><span data-stu-id="66abc-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-204"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-205">bit</span><span class="sxs-lookup"><span data-stu-id="66abc-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-206">Se reciben datos de secuencia en el lado del receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-207"><strong>Salida</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-208">bit</span><span class="sxs-lookup"><span data-stu-id="66abc-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-209">Se reciben datos de secuencia en el lado del remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-211">bit</span><span class="sxs-lookup"><span data-stu-id="66abc-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66abc-212">1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.</span><span class="sxs-lookup"><span data-stu-id="66abc-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="66abc-213">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-215">float</span><span class="sxs-lookup"><span data-stu-id="66abc-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-216">Indica el porcentaje de tiempo que la llamada estuvo en estado de congestión de pérdida.</span><span class="sxs-lookup"><span data-stu-id="66abc-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="66abc-217">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-219">float</span><span class="sxs-lookup"><span data-stu-id="66abc-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-220">Indica el porcentaje de la llamada durante el cual la congestión se debió a la llegada retrasada de paquetes de red.</span><span class="sxs-lookup"><span data-stu-id="66abc-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="66abc-221">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-223">float</span><span class="sxs-lookup"><span data-stu-id="66abc-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-224">Indica el porcentaje de tiempo que la llamada estaba compitiendo por los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="66abc-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="66abc-225">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-227">int</span><span class="sxs-lookup"><span data-stu-id="66abc-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-228">Cantidad mínima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66abc-229">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-231">int</span><span class="sxs-lookup"><span data-stu-id="66abc-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-232">Cantidad máxima de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66abc-233">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-235">int</span><span class="sxs-lookup"><span data-stu-id="66abc-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-236">Desviación estándar de la estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66abc-237">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-239">int</span><span class="sxs-lookup"><span data-stu-id="66abc-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-240">Cantidad promedio de estimación del ancho de banda medido durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66abc-241">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-243">float</span><span class="sxs-lookup"><span data-stu-id="66abc-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-244">Porcentaje de la llamada en la que el extremo determinó que la conexión de red no pudo admitir el vídeo MultiView.</span><span class="sxs-lookup"><span data-stu-id="66abc-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="66abc-245">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-247">float</span><span class="sxs-lookup"><span data-stu-id="66abc-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p104">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-250">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-252">float</span><span class="sxs-lookup"><span data-stu-id="66abc-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p105">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-255">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-257">float</span><span class="sxs-lookup"><span data-stu-id="66abc-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p106">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-260">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-262">int</span><span class="sxs-lookup"><span data-stu-id="66abc-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p107">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-266">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-268">int</span><span class="sxs-lookup"><span data-stu-id="66abc-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p108">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-272">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-274">float</span><span class="sxs-lookup"><span data-stu-id="66abc-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p109">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-278">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-280">int</span><span class="sxs-lookup"><span data-stu-id="66abc-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p110">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-284">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-286">float</span><span class="sxs-lookup"><span data-stu-id="66abc-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p111">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-290">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-292">float</span><span class="sxs-lookup"><span data-stu-id="66abc-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-p112">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="66abc-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66abc-296">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-298">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66abc-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-299">Tasa a la que se perdieron los paquetes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="66abc-300">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-302">int</span><span class="sxs-lookup"><span data-stu-id="66abc-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-303">Cantidad máxima del ancho de banda asignada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="66abc-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="66abc-304">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-306">smallint</span><span class="sxs-lookup"><span data-stu-id="66abc-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="66abc-307">Externa</span><span class="sxs-lookup"><span data-stu-id="66abc-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66abc-308">Tipo de códecs de vídeo que ha usado el remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="66abc-309">Consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="66abc-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="66abc-310">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-312">int</span><span class="sxs-lookup"><span data-stu-id="66abc-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-313">Ancho de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="66abc-314">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-316">int</span><span class="sxs-lookup"><span data-stu-id="66abc-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-317">Alto de resolución usado por el remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="66abc-318">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-320">float</span><span class="sxs-lookup"><span data-stu-id="66abc-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-321">Promedio de transmisión de velocidad de fotogramas de vídeo usada por el remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="66abc-322">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-324">int</span><span class="sxs-lookup"><span data-stu-id="66abc-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-325">Velocidad de bits máxima del remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="66abc-326">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-328">int</span><span class="sxs-lookup"><span data-stu-id="66abc-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-329">Velocidad de bits media del remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-331">int</span><span class="sxs-lookup"><span data-stu-id="66abc-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-332">Número máximo de transmisiones de vídeo usadas por el remitente.</span><span class="sxs-lookup"><span data-stu-id="66abc-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="66abc-333">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-335">smallint</span><span class="sxs-lookup"><span data-stu-id="66abc-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="66abc-336">Externa</span><span class="sxs-lookup"><span data-stu-id="66abc-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66abc-337">Códigos de vídeo usados por el receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-337">Video codes used by the receiver.</span></span> <span data-ttu-id="66abc-338">Consulte la <a href="lync-server-2013-codecdescription-table.md">tabla CodecDescription en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="66abc-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="66abc-339">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-341">int</span><span class="sxs-lookup"><span data-stu-id="66abc-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-342">Ancho de resolución usado por el receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="66abc-343">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-345">int</span><span class="sxs-lookup"><span data-stu-id="66abc-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-346">Altura de resolución usada por el receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="66abc-347">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-349">float</span><span class="sxs-lookup"><span data-stu-id="66abc-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-350">Velocidad media de fotogramas de vídeo usada por el receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="66abc-351">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-353">int</span><span class="sxs-lookup"><span data-stu-id="66abc-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-354">Velocidad de bits máxima del receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="66abc-355">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-357">int</span><span class="sxs-lookup"><span data-stu-id="66abc-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-358">Velocidad de bits media del receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="66abc-359">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-361">int</span><span class="sxs-lookup"><span data-stu-id="66abc-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-362">Secuencias de vídeo máximas para el receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="66abc-363">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-365">int</span><span class="sxs-lookup"><span data-stu-id="66abc-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-366">Secuencias de vídeo mínimas para el receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="66abc-367">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-369">int</span><span class="sxs-lookup"><span data-stu-id="66abc-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-370">Modo de vídeo (por ejemplo, Galería o secuencia única) para el receptor.</span><span class="sxs-lookup"><span data-stu-id="66abc-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="66abc-371">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-373">float</span><span class="sxs-lookup"><span data-stu-id="66abc-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-374">Tasa de pérdida de paquetes tras aplicar la corrección de errores de reenvío.</span><span class="sxs-lookup"><span data-stu-id="66abc-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="66abc-375">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-377">float</span><span class="sxs-lookup"><span data-stu-id="66abc-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-378">Porcentaje de tiempo que la marca de capacidad dinámica estuvo activa.</span><span class="sxs-lookup"><span data-stu-id="66abc-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="66abc-379">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-381">Char (9)</span><span class="sxs-lookup"><span data-stu-id="66abc-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-382">Resolución mínima medida durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66abc-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="66abc-383">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-385">float</span><span class="sxs-lookup"><span data-stu-id="66abc-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-386">Porcentaje de la llamada por debajo del umbral de velocidad de bits baja (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="66abc-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="66abc-387">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-389">float</span><span class="sxs-lookup"><span data-stu-id="66abc-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-390">Porcentaje de la llamada por debajo del umbral de velocidad de fotogramas baja (7,5 fotogramas por segundo, entrante).</span><span class="sxs-lookup"><span data-stu-id="66abc-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="66abc-391">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-393">float</span><span class="sxs-lookup"><span data-stu-id="66abc-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-394">Porcentaje de la llamada que se produjo con la resolución más baja.</span><span class="sxs-lookup"><span data-stu-id="66abc-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="66abc-395">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="66abc-396">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66abc-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-398">float</span><span class="sxs-lookup"><span data-stu-id="66abc-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-399">Duración de la llamada en segundos.</span><span class="sxs-lookup"><span data-stu-id="66abc-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="66abc-400">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66abc-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="66abc-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="66abc-402">bit</span><span class="sxs-lookup"><span data-stu-id="66abc-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66abc-403">Indica si los datos se han agregado desde varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="66abc-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="66abc-404">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66abc-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


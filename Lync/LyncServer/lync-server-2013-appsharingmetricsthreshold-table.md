---
title: 'Lync Server 2013: tabla AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="6b1aa-102">Tabla AppSharingMetricsThreshold en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b1aa-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b1aa-103">_**Última modificación del tema:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="6b1aa-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="6b1aa-104">La tabla AppSharingMetricsThreshold contiene valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="6b1aa-105">Estos umbrales se usan para determinar si la experiencia de uso compartido de aplicaciones se debe clasificar como mala.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="6b1aa-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b1aa-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6b1aa-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6b1aa-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6b1aa-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-112">int</span><span class="sxs-lookup"><span data-stu-id="6b1aa-112">int</span></span></p></td>
<td><p><span data-ttu-id="6b1aa-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6b1aa-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6b1aa-114">Tipo de llamada que se realizó.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b1aa-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-116">int</span><span class="sxs-lookup"><span data-stu-id="6b1aa-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-117">Límite de ancho de banda óptimo para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="6b1aa-118">El valor predeterminado es 1 millón.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-120">int</span><span class="sxs-lookup"><span data-stu-id="6b1aa-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-121">Limitación de ancho de banda aceptable para el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="6b1aa-122">El valor predeterminado es 500000.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b1aa-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-124">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="6b1aa-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-125">Tasa de porcentaje óptima para los mosaicos "estropeados" para clasificar la calidad de uso compartido de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="6b1aa-126">Este valor es el porcentaje del contenido del que el que comparte no ha podido comunicarse con el visor.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="6b1aa-127">El contenido puede ser descartado (o estropeado) cuando el compartidor descarta los mosaicos del origen de los gráficos o los mosaicos de ASMCU descarta los mosaicos del compartidor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="6b1aa-128">El valor predeterminado es 11 por ciento.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-130">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="6b1aa-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-131">tasa porcentual de cceptable para los cuadros "estropeados" para clasificar la calidad de uso compartido de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="6b1aa-132">Este valor es el porcentaje del contenido del que el que comparte no ha podido comunicarse con el visor.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="6b1aa-133">El contenido puede ser descartado (o estropeado) cuando el compartidor descarta los mosaicos del origen de los gráficos o los mosaicos de ASMCU descarta los mosaicos del compartidor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="6b1aa-134">El valor predeterminado es 36 por ciento.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b1aa-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-136">int</span><span class="sxs-lookup"><span data-stu-id="6b1aa-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-137">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-139">int</span><span class="sxs-lookup"><span data-stu-id="6b1aa-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-140">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b1aa-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-142">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-143">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-145">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-146">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b1aa-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-148">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-149">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-151">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-152">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b1aa-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-154">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-155">Valor óptimo para el retraso relativo relativo entre los dos extremos multimedia implicados en el uso compartido de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="6b1aa-156">Es una medición de la latencia de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="6b1aa-157">El valor predeterminado es 1,0 segundos.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="6b1aa-158">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-160">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-161">Valor óptimo para el retraso relativo relativo entre los dos extremos multimedia implicados en el uso compartido de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="6b1aa-162">Es una medición de la latencia de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="6b1aa-163">El valor predeterminado es 1,75 segundos.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="6b1aa-164">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b1aa-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-166">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-167">Valor óptimo de la latencia media de procesamiento de mosaicos RDP en el servidor de conferencia como durante la duración de la sesión de visualización.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="6b1aa-168">Latencia es la diferencia horaria entre cuando el fotograma inicial está codificado en el servidor (compartidor o MCU, según el escenario) y se descodifica el mismo fotograma de inicio en el visor.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="6b1aa-169">Una media alta refleja un retraso mayor en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="6b1aa-170">Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="6b1aa-171">El valor predeterminado es 200ms.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="6b1aa-172">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b1aa-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6b1aa-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6b1aa-174">float</span><span class="sxs-lookup"><span data-stu-id="6b1aa-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b1aa-175">Valor aceptable de la latencia media de procesamiento de mosaicos RDP en el servidor de conferencia como durante la duración de la sesión de visualización.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="6b1aa-176">Latencia es la diferencia horaria entre cuando el fotograma inicial está codificado en el servidor (compartidor o MCU, según el escenario) y se descodifica el mismo fotograma de inicio en el visor.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="6b1aa-177">Una media alta refleja un retraso mayor en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="6b1aa-178">Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="6b1aa-179">El valor predeterminado es 200ms.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="6b1aa-180">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


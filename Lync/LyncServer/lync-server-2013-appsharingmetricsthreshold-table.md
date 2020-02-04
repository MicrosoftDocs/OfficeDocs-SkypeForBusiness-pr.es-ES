---
title: 'Lync Server 2013: tabla AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="7279e-102">Tabla AppSharingMetricsThreshold en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7279e-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7279e-103">_**Última modificación del tema:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="7279e-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="7279e-104">La tabla AppSharingMetricsThreshold contiene valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7279e-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="7279e-105">Estos umbrales se usan para determinar si la experiencia de uso compartido de aplicaciones se debe clasificar como mala.</span><span class="sxs-lookup"><span data-stu-id="7279e-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="7279e-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7279e-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7279e-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7279e-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7279e-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7279e-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-112">int</span><span class="sxs-lookup"><span data-stu-id="7279e-112">int</span></span></p></td>
<td><p><span data-ttu-id="7279e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7279e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7279e-114">Tipo de llamada que se realizó.</span><span class="sxs-lookup"><span data-stu-id="7279e-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7279e-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-116">int</span><span class="sxs-lookup"><span data-stu-id="7279e-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-117">Límite de ancho de banda óptimo para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7279e-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="7279e-118">El valor predeterminado es 1 millón.</span><span class="sxs-lookup"><span data-stu-id="7279e-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7279e-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-120">int</span><span class="sxs-lookup"><span data-stu-id="7279e-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-121">Limitación de ancho de banda aceptable para el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7279e-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="7279e-122">El valor predeterminado es 500000.</span><span class="sxs-lookup"><span data-stu-id="7279e-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7279e-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-124">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="7279e-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-125">Tasa de porcentaje óptima para los mosaicos "estropeados" para clasificar la calidad de uso compartido de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7279e-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="7279e-126">Este valor es el porcentaje del contenido del que el que comparte no ha podido comunicarse con el visor.</span><span class="sxs-lookup"><span data-stu-id="7279e-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="7279e-127">El contenido puede ser descartado (o estropeado) cuando el compartidor descarta los mosaicos del origen de los gráficos o los mosaicos de ASMCU descarta los mosaicos del compartidor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7279e-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="7279e-128">El valor predeterminado es 11 por ciento.</span><span class="sxs-lookup"><span data-stu-id="7279e-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7279e-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-130">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="7279e-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-131">tasa porcentual de cceptable para los cuadros "estropeados" para clasificar la calidad de uso compartido de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7279e-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="7279e-132">Este valor es el porcentaje del contenido del que el que comparte no ha podido comunicarse con el visor.</span><span class="sxs-lookup"><span data-stu-id="7279e-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="7279e-133">El contenido puede ser descartado (o estropeado) cuando el compartidor descarta los mosaicos del origen de los gráficos o los mosaicos de ASMCU descarta los mosaicos del compartidor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7279e-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="7279e-134">El valor predeterminado es 36 por ciento.</span><span class="sxs-lookup"><span data-stu-id="7279e-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7279e-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-136">int</span><span class="sxs-lookup"><span data-stu-id="7279e-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-137">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7279e-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-139">int</span><span class="sxs-lookup"><span data-stu-id="7279e-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-140">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7279e-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-142">float</span><span class="sxs-lookup"><span data-stu-id="7279e-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-143">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7279e-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-145">float</span><span class="sxs-lookup"><span data-stu-id="7279e-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-146">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7279e-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-148">float</span><span class="sxs-lookup"><span data-stu-id="7279e-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-149">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7279e-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-151">float</span><span class="sxs-lookup"><span data-stu-id="7279e-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-152">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7279e-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-154">float</span><span class="sxs-lookup"><span data-stu-id="7279e-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-155">Valor óptimo para el retraso relativo relativo entre los dos extremos multimedia implicados en el uso compartido de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7279e-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="7279e-156">Es una medición de la latencia de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="7279e-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="7279e-157">El valor predeterminado es 1,0 segundos.</span><span class="sxs-lookup"><span data-stu-id="7279e-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="7279e-158">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7279e-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-160">float</span><span class="sxs-lookup"><span data-stu-id="7279e-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-161">Valor óptimo para el retraso relativo relativo entre los dos extremos multimedia implicados en el uso compartido de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7279e-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="7279e-162">Es una medición de la latencia de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="7279e-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="7279e-163">El valor predeterminado es 1,75 segundos.</span><span class="sxs-lookup"><span data-stu-id="7279e-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="7279e-164">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7279e-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-166">float</span><span class="sxs-lookup"><span data-stu-id="7279e-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-167">Valor óptimo de la latencia media de procesamiento de mosaicos RDP en el servidor de conferencia como durante la duración de la sesión de visualización.</span><span class="sxs-lookup"><span data-stu-id="7279e-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="7279e-168">Latencia es la diferencia horaria entre cuando el fotograma inicial está codificado en el servidor (compartidor o MCU, según el escenario) y se descodifica el mismo fotograma de inicio en el visor.</span><span class="sxs-lookup"><span data-stu-id="7279e-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="7279e-169">Una media alta refleja un retraso mayor en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="7279e-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="7279e-170">Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.</span><span class="sxs-lookup"><span data-stu-id="7279e-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="7279e-171">El valor predeterminado es 200ms.</span><span class="sxs-lookup"><span data-stu-id="7279e-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="7279e-172">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7279e-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7279e-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7279e-174">float</span><span class="sxs-lookup"><span data-stu-id="7279e-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7279e-175">Valor aceptable de la latencia media de procesamiento de mosaicos RDP en el servidor de conferencia como durante la duración de la sesión de visualización.</span><span class="sxs-lookup"><span data-stu-id="7279e-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="7279e-176">Latencia es la diferencia horaria entre cuando el fotograma inicial está codificado en el servidor (compartidor o MCU, según el escenario) y se descodifica el mismo fotograma de inicio en el visor.</span><span class="sxs-lookup"><span data-stu-id="7279e-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="7279e-177">Una media alta refleja un retraso mayor en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="7279e-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="7279e-178">Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.</span><span class="sxs-lookup"><span data-stu-id="7279e-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="7279e-179">El valor predeterminado es 200ms.</span><span class="sxs-lookup"><span data-stu-id="7279e-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="7279e-180">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7279e-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


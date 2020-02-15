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
ms.openlocfilehash: 89260bb2e854087ec1167ff0fd8039c58ac99300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="ee8c3-102">Tabla AppSharingMetricsThreshold en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee8c3-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee8c3-103">_**Última modificación del tema:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="ee8c3-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="ee8c3-p101">La tabla AppSharingMetricsThreshold contiene los valores óptimos y aceptables de la métrica de la calidad de la experiencia usada con el uso compartido de aplicaciones. Estos umbrales se utilizan para determinar si la experiencia de uso compartido de aplicaciones debe calificarse como pobre.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="ee8c3-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee8c3-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ee8c3-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ee8c3-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ee8c3-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-112">int</span><span class="sxs-lookup"><span data-stu-id="ee8c3-112">int</span></span></p></td>
<td><p><span data-ttu-id="ee8c3-113">Principal</span><span class="sxs-lookup"><span data-stu-id="ee8c3-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ee8c3-114">Tipo de llamada realizada.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee8c3-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-116">int</span><span class="sxs-lookup"><span data-stu-id="ee8c3-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-p102">Limitación del ancho de banda óptima para el uso compartido de aplicaciones. El valor predeterminado es 1000000.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-120">int</span><span class="sxs-lookup"><span data-stu-id="ee8c3-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-p103">Limitación del ancho de banda aceptable para el uso compartido de aplicaciones. El valor predeterminado es 500000.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee8c3-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-124">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ee8c3-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-p104">Porcentaje óptimo para los mosaicos "desechados" para clasificar la calidad de un uso compartido de aplicaciones. Este valor es el porcentaje del contenido del iniciador de la sesión que no llegó al visualizador. Puede que el contenido se descarte (o se deseche) cuando el iniciador de la sesión descarta mosaicos del origen de gráficos o cuando ASMCU descarta mosaicos del iniciador de la sesión, respectivamente. El valor predeterminado es 11%.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-130">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ee8c3-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-p105">Porcentaje aceptable para los mosaicos "desechados" para clasificar la calidad de un uso compartido de aplicaciones. Este valor es el porcentaje del contenido del iniciador de la sesión que no llegó al visualizador. Puede que el contenido se descarte (o se deseche) cuando el iniciador de la sesión descarta mosaicos del origen de gráficos o cuando ASMCU descarta mosaicos del iniciador de la sesión, respectivamente. El valor predeterminado es 36%.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee8c3-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-136">int</span><span class="sxs-lookup"><span data-stu-id="ee8c3-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-137">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-139">int</span><span class="sxs-lookup"><span data-stu-id="ee8c3-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-140">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee8c3-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-142">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-143">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-145">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-146">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee8c3-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-148">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-149">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-151">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-152">Esta columna no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee8c3-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-154">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-p106">Valor óptimo para el retraso unidireccional relativo entre los dos extremos multimedia implicados en el uso compartido de aplicaciones. Se trata de una medida de latencia de un solo salto. El valor predeterminado es 1,0 segundos.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="ee8c3-158">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-160">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-p107">Valor óptimo para el retraso unidireccional relativo entre los dos extremos multimedia implicados en el uso compartido de aplicaciones. Se trata de una medida de latencia de un solo salto. El valor predeterminado es 1,75 segundos.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="ee8c3-164">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee8c3-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-166">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-167">Valor óptimo para la latencia media de procesamiento de mosaicos de RDP en el servidor de conferencia AS en la duración de la sesión de visualización.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="ee8c3-168">La latencia es la diferencia de tiempo entre el momento en que el marco de inicio se codifica en el servidor (Sharer o MCU, según el escenario) y el mismo marco de inicio se descodifica en el visor.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="ee8c3-p109">Una media elevada refleja un retraso mayor en la experiencia de visualización. Es posible que los servidores de conferencia sobrecargados experimenten, de media, retrasos mayores. El valor predeterminado es 200 ms.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="ee8c3-172">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee8c3-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ee8c3-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee8c3-174">float</span><span class="sxs-lookup"><span data-stu-id="ee8c3-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee8c3-175">Valor aceptable para la latencia media de procesamiento de mosaicos de RDP en el servidor de conferencia AS en la duración de la sesión de visualización.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="ee8c3-176">La latencia es la diferencia de tiempo entre el momento en que el marco de inicio se codifica en el servidor (Sharer o MCU, según el escenario) y el mismo marco de inicio se descodifica en el visor.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="ee8c3-p111">Una media elevada refleja un retraso mayor en la experiencia de visualización. Es posible que los servidores de conferencia sobrecargados experimenten, de media, retrasos mayores. El valor predeterminado es 200 ms.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="ee8c3-180">La columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee8c3-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


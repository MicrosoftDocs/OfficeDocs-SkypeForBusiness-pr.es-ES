---
title: 'Lync Server 2013: tabla VideoMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="c0627-102">Tabla VideoMetricsThreshold en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0627-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0627-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c0627-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c0627-104">La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para la medición de la calidad de la medición que se usa con las videollamadas.</span><span class="sxs-lookup"><span data-stu-id="c0627-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0627-105"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c0627-106"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c0627-107"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c0627-108"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0627-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-110">int</span><span class="sxs-lookup"><span data-stu-id="c0627-110">int</span></span></p></td>
<td><p><span data-ttu-id="c0627-111">Primary</span><span class="sxs-lookup"><span data-stu-id="c0627-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0627-112">Tipo de llamada que se realizó.</span><span class="sxs-lookup"><span data-stu-id="c0627-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-114">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-115">El valor predeterminado es 0,05.</span><span class="sxs-lookup"><span data-stu-id="c0627-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-117">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-118">El valor predeterminado es 0,10.</span><span class="sxs-lookup"><span data-stu-id="c0627-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-120">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-121">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="c0627-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-123">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-124">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="c0627-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-126">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="c0627-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-127">El valor predeterminado es 12,0000.</span><span class="sxs-lookup"><span data-stu-id="c0627-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-129">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="c0627-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-130">El valor predeterminado es 7,0000.</span><span class="sxs-lookup"><span data-stu-id="c0627-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-132">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-133">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="c0627-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-135">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-136">El valor predeterminado es 10,0/</span><span class="sxs-lookup"><span data-stu-id="c0627-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-138">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-139">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="c0627-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-141">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-142">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="c0627-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-144">foat</span><span class="sxs-lookup"><span data-stu-id="c0627-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-145">El valor predeterminado es 0,05.</span><span class="sxs-lookup"><span data-stu-id="c0627-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-147">float</span><span class="sxs-lookup"><span data-stu-id="c0627-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-148">El valor predeterminado es 0,10.</span><span class="sxs-lookup"><span data-stu-id="c0627-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-150">float</span><span class="sxs-lookup"><span data-stu-id="c0627-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-151">El valor predeterminado es 12.</span><span class="sxs-lookup"><span data-stu-id="c0627-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-153">float</span><span class="sxs-lookup"><span data-stu-id="c0627-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-154">El valor predeterminado es 7.</span><span class="sxs-lookup"><span data-stu-id="c0627-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0627-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-156">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-157">El valor predeterminado es 5,00.</span><span class="sxs-lookup"><span data-stu-id="c0627-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0627-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c0627-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c0627-159">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="c0627-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0627-160">El valor predeterminado es 10,00.</span><span class="sxs-lookup"><span data-stu-id="c0627-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


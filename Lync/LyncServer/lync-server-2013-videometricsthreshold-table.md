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
ms.openlocfilehash: 2f1f1fc7ca86c10fa9c409c73c2f4b54ee2777a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508517"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="60092-102">Tabla VideoMetricsThreshold en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60092-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60092-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="60092-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="60092-104">La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para las métricas de Calidad de experiencia utilizadas con videollamadas.</span><span class="sxs-lookup"><span data-stu-id="60092-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60092-105"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="60092-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="60092-106"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="60092-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="60092-107"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="60092-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="60092-108"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="60092-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60092-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="60092-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-110">entero</span><span class="sxs-lookup"><span data-stu-id="60092-110">int</span></span></p></td>
<td><p><span data-ttu-id="60092-111">Principal</span><span class="sxs-lookup"><span data-stu-id="60092-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="60092-112">Tipo de llamada realizada.</span><span class="sxs-lookup"><span data-stu-id="60092-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-114">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-115">El valor predeterminado es 0,05.</span><span class="sxs-lookup"><span data-stu-id="60092-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-117">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-118">El valor predeterminado es 0,10.</span><span class="sxs-lookup"><span data-stu-id="60092-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-120">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-121">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="60092-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-123">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-124">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="60092-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-126">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="60092-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-127">El valor predeterminado es 12,0000.</span><span class="sxs-lookup"><span data-stu-id="60092-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-129">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="60092-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-130">El valor predeterminado es 7,0000.</span><span class="sxs-lookup"><span data-stu-id="60092-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-132">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-133">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="60092-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-135">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-136">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="60092-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-138">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-139">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="60092-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-141">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-142">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="60092-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-144">foat</span><span class="sxs-lookup"><span data-stu-id="60092-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-145">El valor predeterminado es 0,05.</span><span class="sxs-lookup"><span data-stu-id="60092-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-147">float</span><span class="sxs-lookup"><span data-stu-id="60092-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-148">El valor predeterminado es 0,10.</span><span class="sxs-lookup"><span data-stu-id="60092-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-150">float</span><span class="sxs-lookup"><span data-stu-id="60092-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-151">El valor predeterminado es 12.</span><span class="sxs-lookup"><span data-stu-id="60092-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-153">float</span><span class="sxs-lookup"><span data-stu-id="60092-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-154">El valor predeterminado es 7.</span><span class="sxs-lookup"><span data-stu-id="60092-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60092-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="60092-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-156">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-157">El valor predeterminado es 5,00.</span><span class="sxs-lookup"><span data-stu-id="60092-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60092-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="60092-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="60092-159">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="60092-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="60092-160">El valor predeterminado es 10,00.</span><span class="sxs-lookup"><span data-stu-id="60092-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


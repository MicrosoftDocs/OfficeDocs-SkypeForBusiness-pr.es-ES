---
title: 'Lync Server 2013: tabla VideoMetricsThreshold'
description: 'Lync Server 2013: tabla VideoMetricsThreshold.'
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
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568006"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="d7a85-103">Tabla VideoMetricsThreshold en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7a85-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7a85-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d7a85-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d7a85-105">La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para las métricas de Calidad de experiencia utilizadas con videollamadas.</span><span class="sxs-lookup"><span data-stu-id="d7a85-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a85-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d7a85-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d7a85-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d7a85-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-111">entero</span><span class="sxs-lookup"><span data-stu-id="d7a85-111">int</span></span></p></td>
<td><p><span data-ttu-id="d7a85-112">Principal</span><span class="sxs-lookup"><span data-stu-id="d7a85-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d7a85-113">Tipo de llamada realizada.</span><span class="sxs-lookup"><span data-stu-id="d7a85-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-115">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-116">El valor predeterminado es 0,05.</span><span class="sxs-lookup"><span data-stu-id="d7a85-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-118">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-119">El valor predeterminado es 0,10.</span><span class="sxs-lookup"><span data-stu-id="d7a85-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-121">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-122">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="d7a85-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-124">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-125">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="d7a85-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-127">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d7a85-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-128">El valor predeterminado es 12,0000.</span><span class="sxs-lookup"><span data-stu-id="d7a85-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-130">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d7a85-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-131">El valor predeterminado es 7,0000.</span><span class="sxs-lookup"><span data-stu-id="d7a85-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-133">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-134">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="d7a85-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-136">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-137">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="d7a85-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-139">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-140">El valor predeterminado es 5,0.</span><span class="sxs-lookup"><span data-stu-id="d7a85-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-142">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-143">El valor predeterminado es 10,0.</span><span class="sxs-lookup"><span data-stu-id="d7a85-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-145">foat</span><span class="sxs-lookup"><span data-stu-id="d7a85-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-146">El valor predeterminado es 0,05.</span><span class="sxs-lookup"><span data-stu-id="d7a85-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-148">float</span><span class="sxs-lookup"><span data-stu-id="d7a85-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-149">El valor predeterminado es 0,10.</span><span class="sxs-lookup"><span data-stu-id="d7a85-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-151">float</span><span class="sxs-lookup"><span data-stu-id="d7a85-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-152">El valor predeterminado es 12.</span><span class="sxs-lookup"><span data-stu-id="d7a85-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-154">float</span><span class="sxs-lookup"><span data-stu-id="d7a85-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-155">El valor predeterminado es 7.</span><span class="sxs-lookup"><span data-stu-id="d7a85-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a85-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-157">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-158">El valor predeterminado es 5,00.</span><span class="sxs-lookup"><span data-stu-id="d7a85-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a85-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d7a85-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a85-160">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a85-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7a85-161">El valor predeterminado es 10,00.</span><span class="sxs-lookup"><span data-stu-id="d7a85-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


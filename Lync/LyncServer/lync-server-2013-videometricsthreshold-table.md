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
# <a name="videometricsthreshold-table-in-lync-server-2013"></a>Tabla VideoMetricsThreshold en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para las métricas de Calidad de experiencia utilizadas con videollamadas.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Tipo de llamada realizada.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLROptimal</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 0,05.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPostFECPLRAcceptable</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverageOptimal</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td></td>
<td><p>El valor predeterminado es 12,0000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvFramerateAverageAcceptable</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td></td>
<td><p>El valor predeterminado es 7,0000.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercentOptimal</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowFrameRateCallPercentAcceptable</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowResolutionCallPercentOptimal</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercentAcceptable</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRateOptimal</strong></p></td>
<td><p>foat</p></td>
<td></td>
<td><p>El valor predeterminado es 0,05.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPacketLossRateAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>El valor predeterminado es 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFrameRateAvgOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>El valor predeterminado es 12.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameRateAvgAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>El valor predeterminado es 7.</p></td>
</tr>
<tr class="even">
<td><p><strong>DynamicCapabilityPercentOptimal</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 5,00.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercentAcceptable</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>El valor predeterminado es 10,00.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


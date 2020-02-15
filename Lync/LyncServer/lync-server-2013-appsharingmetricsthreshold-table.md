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

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Tabla AppSharingMetricsThreshold en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-12-08_

La tabla AppSharingMetricsThreshold contiene los valores óptimos y aceptables de la métrica de la calidad de la experiencia usada con el uso compartido de aplicaciones. Estos umbrales se utilizan para determinar si la experiencia de uso compartido de aplicaciones debe calificarse como pobre.

Esta tabla se introdujo en Microsoft Lync Server 2013.


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
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Tipo de llamada realizada.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitación del ancho de banda óptima para el uso compartido de aplicaciones. El valor predeterminado es 1000000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitación del ancho de banda aceptable para el uso compartido de aplicaciones. El valor predeterminado es 500000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>Porcentaje óptimo para los mosaicos "desechados" para clasificar la calidad de un uso compartido de aplicaciones. Este valor es el porcentaje del contenido del iniciador de la sesión que no llegó al visualizador. Puede que el contenido se descarte (o se deseche) cuando el iniciador de la sesión descarta mosaicos del origen de gráficos o cuando ASMCU descarta mosaicos del iniciador de la sesión, respectivamente. El valor predeterminado es 11%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>Porcentaje aceptable para los mosaicos "desechados" para clasificar la calidad de un uso compartido de aplicaciones. Este valor es el porcentaje del contenido del iniciador de la sesión que no llegó al visualizador. Puede que el contenido se descarte (o se deseche) cuando el iniciador de la sesión descarta mosaicos del origen de gráficos o cuando ASMCU descarta mosaicos del iniciador de la sesión, respectivamente. El valor predeterminado es 36%.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Esta columna no se usa en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Esta columna no se usa en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta columna no se usa en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta columna no se usa en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta columna no se usa en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta columna no se usa en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor óptimo para el retraso unidireccional relativo entre los dos extremos multimedia implicados en el uso compartido de aplicaciones. Se trata de una medida de latencia de un solo salto. El valor predeterminado es 1,0 segundos.</p>
<p>La columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor óptimo para el retraso unidireccional relativo entre los dos extremos multimedia implicados en el uso compartido de aplicaciones. Se trata de una medida de latencia de un solo salto. El valor predeterminado es 1,75 segundos.</p>
<p>La columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor óptimo para la latencia media de procesamiento de mosaicos de RDP en el servidor de conferencia AS en la duración de la sesión de visualización. La latencia es la diferencia de tiempo entre el momento en que el marco de inicio se codifica en el servidor (Sharer o MCU, según el escenario) y el mismo marco de inicio se descodifica en el visor.</p>
<p>Una media elevada refleja un retraso mayor en la experiencia de visualización. Es posible que los servidores de conferencia sobrecargados experimenten, de media, retrasos mayores. El valor predeterminado es 200 ms.</p>
<p>La columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor aceptable para la latencia media de procesamiento de mosaicos de RDP en el servidor de conferencia AS en la duración de la sesión de visualización. La latencia es la diferencia de tiempo entre el momento en que el marco de inicio se codifica en el servidor (Sharer o MCU, según el escenario) y el mismo marco de inicio se descodifica en el visor.</p>
<p>Una media elevada refleja un retraso mayor en la experiencia de visualización. Es posible que los servidores de conferencia sobrecargados experimenten, de media, retrasos mayores. El valor predeterminado es 200 ms.</p>
<p>La columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


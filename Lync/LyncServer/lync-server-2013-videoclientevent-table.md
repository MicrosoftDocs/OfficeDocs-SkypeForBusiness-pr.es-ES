---
title: 'Lync Server 2013: Tabla VideoClientEvent'
TOCTitle: Tabla VideoClientEvent
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48277036
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla VideoClientEvent en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro contiene un evento de cliente para un extremo en una videollamada. Generalmente una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Principal</p></td>
<td><p>0: Datos del destinatario de la llamada</p>
<p>1: Datos del autor de la llamada</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento LowBandwidth para un estado no válido. No hay suficiente ancho de banda para tener una experiencia de voz aceptable.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento ReceiveSendQuality para un estado no válido.</p>
<p>La calidad de la red en términos de vibración o pérdida de paquetes es severa e impacta en la calidad del audio que se recibe.</p></td>
</tr>
</tbody>
</table>


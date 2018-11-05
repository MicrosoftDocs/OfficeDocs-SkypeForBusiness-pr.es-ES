---
title: Tabla TraceRoute en Lync Server 2013
TOCTitle: Tabla TraceRoute en Lync Server 2013
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48276469
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla TraceRoute en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.


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
<td><p>Principal, Externa</p></td>
<td><p>Fecha y hora en que empezó la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Identificador único que se usa para diferenciar varias llamadas que pueden haber empezado el mismo día a la misma hora.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Representa el tipo de línea de vídeo que se usa en la llamada. Los valores admitidos son:</p>
<ul>
<li><p>0: audio</p></li>
<li><p>1: vídeo</p></li>
<li><p>2: vídeo panorámico</p></li>
<li><p>3: uso compartido de aplicaciones/escritorio</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Principal</p></td>
<td><p>Extremo que ha realizado la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Salto de red.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador único de la dirección IP. La información de la dirección IP se almacena en <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Tiempo de ida y vuelta. El tiempo de ida y vuelta mide el tiempo que tarda el paquete de voz en llegar a su destino y devolver una notificación que informe de que se ha recibido.</p></td>
</tr>
</tbody>
</table>


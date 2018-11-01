---
title: 'Lync Server 2013: Tabla Server'
TOCTitle: Tabla Server
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48276127
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Server en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.


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
<td><p><strong>ServerKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica el servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>índice</p></td>
<td><p>Cadena de dirección MAC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>1: Servidor de mediación</p>
<p>2: Servidor de conferencia A/V16394: Servicio perimetral A/V32769: Puerta de enlace</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar(512)</p></td>
<td><p></p></td>
<td><p>Grupo al que pertenece el servidor. Solo aplicable para el servidor de conferencia A/V.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
</tbody>
</table>


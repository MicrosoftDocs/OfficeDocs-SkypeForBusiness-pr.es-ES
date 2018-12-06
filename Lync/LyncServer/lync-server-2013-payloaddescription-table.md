---
title: 'Lync Server 2013: Tabla PayloadDescription'
TOCTitle: Tabla PayloadDescription
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48276603
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla PayloadDescription en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla PayloadDescription es una tabla auxiliar. Cada registro representa un códec que se usa en una sesión de audio o vídeo.


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
<td><p><strong>PayloadDescriptionKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único de identificación del códec.</p></td>
</tr>
<tr class="even">
<td><p><strong>PayloadDescription</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Única</p></td>
<td><p>Nombre del códec.</p></td>
</tr>
</tbody>
</table>


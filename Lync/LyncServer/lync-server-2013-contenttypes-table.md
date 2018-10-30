---
title: 'Lync Server 2013: Tabla ContentTypes'
TOCTitle: Tabla ContentTypes
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48276953
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ContentTypes en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla ContentTypes es una tabla auxiliar que almacena una lista de los tipos de contenido utilizados en sesiones punto a punto y sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número único de identificación del tipo de contenido.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td> </td>
<td><p>Nombre del tipo de contenido.</p></td>
</tr>
</tbody>
</table>


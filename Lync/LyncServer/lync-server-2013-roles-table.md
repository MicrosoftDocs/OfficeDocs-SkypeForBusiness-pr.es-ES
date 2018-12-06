---
title: 'Lync Server 2013: Tabla Roles'
TOCTitle: Tabla Roles
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48277028
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Roles en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.


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
<td><p><strong>RoleId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0 - Desconocido</p></li>
<li><p>1 - Moderador</p></li>
<li><p>2 - Asistente</p></li>
</ul></td>
</tr>
</tbody>
</table>


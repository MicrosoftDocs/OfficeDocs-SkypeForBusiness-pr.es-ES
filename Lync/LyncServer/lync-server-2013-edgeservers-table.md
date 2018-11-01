---
title: 'Lync Server 2013: Tabla EdgeServers'
TOCTitle: Tabla EdgeServers
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48276351
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla EdgeServers en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla EdgeServers es una tabla auxiliar. En cada registro se almacena información sobre un servidor perimetral que participa en llamadas con registros en esta base de datos.


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
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este servidor perimetral.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Nombre del servidor perimetral.</p></td>
</tr>
</tbody>
</table>


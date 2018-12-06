---
title: 'Lync Server 2013: Tabla Region'
TOCTitle: Tabla Region
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398235(v=OCS.15)
ms:contentKeyID: 48274552
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Region en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Region es una tabla auxiliar. Cada registro representa un país/región definido en la configuración de red.


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
<td><p><strong>RegionKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica el país/región.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegionName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Única</p></td>
<td><p>Nombre del país/región.</p></td>
</tr>
</tbody>
</table>


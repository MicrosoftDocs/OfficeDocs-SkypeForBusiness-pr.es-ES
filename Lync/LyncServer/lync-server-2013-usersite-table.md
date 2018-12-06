---
title: 'Lync Server 2013: Tabla UserSite'
TOCTitle: Tabla UserSite
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48274596
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla UserSite en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla UserSite es una tabla auxiliar. Cada registro representa un sitio de usuario definido en la configuración de red.


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
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica el sitio de usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Única</p></td>
<td><p>Nombre del sitio de usuario.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Se obtiene de la <a href="lync-server-2013-region-table.md">Tabla Region en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


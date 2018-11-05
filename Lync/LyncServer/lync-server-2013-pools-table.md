---
title: 'Lync Server 2013: Tabla Pools'
TOCTitle: Tabla Pools
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398991(v=OCS.15)
ms:contentKeyID: 48276913
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Pools en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Grupos es una tabla auxiliar que almacena información sobre los diversos grupos. Cada registro de la tabla representa un grupo.


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
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica a este grupo.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>FQDN del grupo.</p></td>
</tr>
</tbody>
</table>


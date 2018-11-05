---
title: 'Lync Server 2013: Tabla Tenants'
TOCTitle: Tabla Tenants
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48276561
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Tenants en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.


> [!NOTE]
> En una instalación local, el CDR usa el identificador de inquilino integrado para indicar distintos tipos de autenticación, como la de conectividad de mensajería instantánea pública, federada y anónima.




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
<td><p><strong>TenantId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este identificador de inquilino.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000: de empresa</p></li>
<li><p>00000000-0000-0000-0000-000000000001: federada</p></li>
<li><p>00000000-0000-0000-0000-000000000002: anónima</p></li>
<li><p>00000000-0000-0000-0000-000000000003: conectividad de mensajería instantánea pública</p></li>
</ul></td>
</tr>
</tbody>
</table>


---
title: 'Lync Server 2013: Tabla Users'
TOCTitle: Tabla Users
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48276245
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Users en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Users es una tabla auxiliar. En cada registro se almacena información sobre un usuario que participa en llamadas o sesiones con registros en la base de datos.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Marca de tiempo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica a este usuario.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p>URI del usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Id. de inquilino de este usuario. Consulte <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de URI de este usuario. Consulte <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


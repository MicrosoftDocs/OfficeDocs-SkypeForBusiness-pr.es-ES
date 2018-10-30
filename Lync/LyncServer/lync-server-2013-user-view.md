---
title: Vista de usuario
TOCTitle: Vista de usuario
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49889238
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista de usuario

 

_**Última modificación del tema:** 2015-03-09_

La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserId</p></td>
<td><p>Int</p></td>
<td><p>Número único que identifica a este usuario.</p></td>
</tr>
<tr class="even">
<td><p>UserUri</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario.</p></td>
</tr>
<tr class="odd">
<td><p>TenantKey</p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Inquilino del usuario. Para más información, vea <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>UriType</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI de usuario. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


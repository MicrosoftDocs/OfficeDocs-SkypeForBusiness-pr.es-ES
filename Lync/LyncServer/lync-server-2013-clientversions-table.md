---
title: 'Lync Server 2013: Tabla ClientVersions'
TOCTitle: Tabla ClientVersions
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48275284
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ClientVersions en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos versiones y tipos de clientes que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.


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
<td><p><strong>VersionId</strong></p></td>
<td><p><strong>int</strong></p></td>
<td><p>Principal</p></td>
<td><p>Número único de identificación de esta versión y este tipo de cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versión</strong></p></td>
<td><p><strong>nvarchar(256)</strong></p></td>
<td><p></p></td>
<td><p>Nombre de la versión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Especifica el tipo de cliente usado en la sesión. Para más información, vea <a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a>.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


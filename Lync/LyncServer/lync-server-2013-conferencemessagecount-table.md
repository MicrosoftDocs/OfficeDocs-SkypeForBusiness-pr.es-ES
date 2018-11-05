---
title: 'Lync Server 2013: Tabla ConferenceMessageCount'
TOCTitle: Tabla ConferenceMessageCount
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48275742
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ConferenceMessageCount en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea y va acompañado del número de mensajes que dicho usuario ha enviado. Cada conferencia viene representada por varios registros en esta tabla, un registro por usuario.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Hora de la instancia de conferencia. Se usa junto con <strong>SessionIdSeq</strong> para identificar una instancia de conferencia de forma única. Vea la <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número que identifica la instancia de conferencia. Se usa junto con <strong>SessionIdTime</strong> para identificar una instancia de conferencia de forma única. Vea <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número único que identifica a este usuario, referido de la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Número de mensajes que este usuario ha enviado durante la conferencia.</p></td>
</tr>
</tbody>
</table>


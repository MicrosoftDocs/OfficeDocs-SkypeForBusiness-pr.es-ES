---
title: 'Lync Server 2013: Tabla FocusJoinsAndLeaves'
TOCTitle: Tabla FocusJoinsAndLeaves
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48276992
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla FocusJoinsAndLeaves en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro de esta tabla contiene datos de CDR con información sobre cuándo los usuarios se unen o abandonan una conferencia. En esta tabla, cada conferencia se representa con un registro para cada vez que un usuario se une y abandona la conferencia.


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
<td><p>datetime</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Hora de la instancia de conferencia. Se usa junto con <strong>SessionIdSeq</strong> para identificar una instancia de conferencia de forma única. Vea la <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número que identifica la instancia de conferencia. Se usa junto con <strong>SessionIdTime</strong> para identificar una instancia de conferencia de forma única. Vea <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en combinación con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número del identificador para identificar la sesión. Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión. Vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Número único que identifica a este usuario, referido de la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Si un usuario inicia sesión en varios equipos o dispositivos a la vez, <strong>UserInstance</strong> se usa para identificar de forma única la combinación usuario/dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Si el usuario inició sesión de manera interna o no.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Rol del usuario en la conferencia, por ejemplo moderador o asistente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora en que el usuario se une a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora en que el usuario abandona la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Versión del software cliente del usuario, referido a <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificador único global (GUID) del extremo usado en la conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


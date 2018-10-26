---
title: 'Lync Server 2013: Tabla McuJoinsAndLeaves'
TOCTitle: Tabla McuJoinsAndLeaves
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48275233
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla McuJoinsAndLeaves en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada uno de los registros de esta tabla contiene detalles de llamada relativos a una combinación de entrada o salida de un usuario y del servidor de conferencias. Por ejemplo, si un usuario se une a una conferencia que incluye conferencias web y elementos de audio/vídeo, se crearía un registro para la unión a la conferencia web de ese usuario, y se crearía otro registro para la unión a la conferencia de audio/vídeo por parte del usuario.


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
<td><p>Principal, Externa</p></td>
<td><p>Número único que identifica este usuario. Vea <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Si un usuario se encuentra conectado a varios equipos de forma simultánea, McuUserInstance identifica de forma única la combinación de usuario/dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica si el usuario se está uniendo desde una RTC o no.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número único que identifica este servidor de conferencias. Vea <a href="lync-server-2013-mcus-table.md">Tabla Mcus en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Externa</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en combinación con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> como identificación única de una sesión. Para más información, vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p> </p></td>
<td><p>Hora a la que este usuario se une a este servidor de conferencias.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p> </p></td>
<td><p>Hora a la que este usuario sale de este servidor de conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador que especifica el número de versión de software de cliente que se usa en la conferencia. Para más información, vea <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


---
title: Vista FocusJoinsAndLeaves
TOCTitle: Vista FocusJoinsAndLeaves
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49888918
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista FocusJoinsAndLeaves

 

_**Última modificación del tema:** 2015-03-09_

La vista FocusJoinsAndLeaves almacena la información sobre las incorporaciones y los abandonos de una conferencia. Cada conferencia se representa en esta vista con un registro que se escribe cada vez que un usuario se incorpora o abandona la conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la instancia de conferencia. Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única. Vea <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación de la instancia de la conferencia. Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única. Vea <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del usuario del que se ha capturado la información de incorporación/abandono.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Escriba la URI del usuario del que se ha capturado la información de incorporación/abandono. Vea la <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario del que se ha capturado la información de incorporación/abandono. Vea la <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificador único del usuario del que se ha capturado la información de incorporación/abandono.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versión del cliente usada por el usuario del que se ha capturado la información de incorporación/abandono.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente que ha usado el usuario del que se ha capturado la información de incorporación/abandono. Vea la <a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a> para obtener más detalles.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Nombre de la categoría del cliente usado por el usuario del que se ha capturado la información de incorporación/abandono.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Bit que indica si el usuario es interno o externo.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la solicitud de la sesión. Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única. Vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Si un usuario inicia sesión en varios equipos o dispositivos a la vez, UserInstance se usa para identificar de forma única la combinación usuario/dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>ID del cuadro de diálogo SIP de la sesión. El formato es: dialog;from-tag;to-tag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que el usuario se incorporó a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que el usuario abandonó la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Rol del usuario en la conferencia, por ejemplo moderador o asistente.</p></td>
</tr>
</tbody>
</table>


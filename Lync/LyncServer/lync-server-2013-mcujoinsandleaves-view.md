---
title: Vista McuJoinsAndLeaves
TOCTitle: Vista McuJoinsAndLeaves
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49889223
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista McuJoinsAndLeaves

 

_**Última modificación del tema:** 2015-03-09_

La vista McuJoinsAndLeaves almacena información sobre el momento en que los usuarios se unen a un servidor de conferencia o lo abandonan. Cada uno de los registros de esta vista contiene detalles de llamada sobre una combinación del servidor de conferencia y de la información sobre la entrada o la salida del mismo. La vista se introdujo en Microsoft Lync Server 2013.


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
<td><p>Hora de la instancia de conferencia. Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única. Para más información, vea <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación de la instancia de conferencia. Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única. Para más información, vea <a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URI del servidor de conferencia al que se conectó el usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URI del servidor de conferencia al que se conectó el usuario. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario del que se capturó la información de entrada/salida del servidor de conferencia. Para más información, vea <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versión del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia. Para más información, vea <a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Nombre de la categoría del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Identificación única de la combinación usuario/dispositivo para los usuarios con una sesión iniciada en varios dispositivos.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p>Bit que representa si el usuario es interno o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la solicitud de sesión. Se usa junto con SessionIdSeq para identificar una sesión de forma única. Para más información, vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación de la sesión. Se usa junto con SessionIdTime para identificar una sesión de forma única. Para más información, vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que el usuario se unió al servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que el usuario abandonó el servidor de conferencia.</p></td>
</tr>
</tbody>
</table>


﻿---
title: Vista ConferenceSessionDetails
TOCTitle: Vista ConferenceSessionDetails
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49889193
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista ConferenceSessionDetails

 

_**Última modificación del tema:** 2015-03-09_

La vista ConferenceSessionDetails almacena información sobre sesiones con varios participantes. Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<td><p>Hora de la solicitud de sesión. Se usa junto a SessionIdSeq para identificar una sesión. Para más información, vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificador que identifica la sesión. Se usa junto a SessionIdTime para identificar únicamente una sesión. Para más información, vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la primera solicitud de invitación. Este campo se rellena normalmente con datos generados por el mensaje INVITE inicial en la sesión. Si no aparece ningún mensaje INVITE, el campo se rellena con la fecha y hora del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI de la conferencia. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del servidor de conferencias.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del servidor de conferencias. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del usuario que participó en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que participó en la sesión. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario que participó en la sesión. Para más información, vea <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificador único del usuario que participó en la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versión del servidor de conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Tipo del servidor de conferencias. Para más información, vea <a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Categoría del servidor de conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versión del cliente usado por el usuario que participó en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente usado por el usuario que participó en la sesión. Para más información, vea <a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Nombre de categoría del cliente usado por el usuario que participó en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del usuario en cuyo nombre se inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario en cuyo nombre se inició la sesión. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario en cuyo nombre se inició la sesión. Para más información, vea <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del usuario a quien se hizo referencia en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario a quien se hizo referencia en la sesión. Para más información, vea <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario a quien se hizo referencia en la sesión. Para más información, vea <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>Id. del diálogo SIP. El formato es</p>
<p>:diálogo;etiqueta-origen;etiqueta-destino</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Número de identificador que identifica el cuadro de diálogo que se reemplazó por la sesión actual. Para más información, vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificador que identifica la sesión. Se usa junto a ReplaceDialogIdTime para identificar únicamente una sesión que se reemplaza por esta sesión. Para más información, vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>Id. del diálogo SIP que reemplaza esta sesión. El formato es:</p>
<p>diálogo;etiqueta-origen;etiqueta-destino</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el servidor de conferencias inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el servidor de conferencias finalizó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el usuario ha iniciado sesión desde la red interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de respuesta del primer mensaje INVITE. Este campo se rellena normalmente con datos generados por el mensaje INVITE inicial en la sesión. Si no aparece ningún mensaje INVITE, el campo se rellena con la fecha y hora del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Código de respuesta SIP a la invitación de la sesión. Este campo se rellena normalmente con datos generados por el mensaje INVITE inicial en la sesión. Si no aparece ningún mensaje INVITE, el campo se rellena con la fecha y hora del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>Identificador de diagnóstico capturado de los encabezados SIP de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de contenido para la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del servidor front-end que captura los datos de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo que captura los datos de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediación usado por el usuario que participó en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Puerta de enlace usada por el usuario que participó en la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del servidor perimetral usado por el usuario que participó en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica los atributos del usuario que participó en la sesión. Se permiten las siguientes definiciones de atributos:</p>
<p>0x01 - Integrado con el teléfono de escritorio</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributos:</p>
<p>0x01 - Reintento de sesión0</p>
<p>x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas</p></td>
</tr>
</tbody>
</table>


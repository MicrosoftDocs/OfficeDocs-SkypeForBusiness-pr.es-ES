﻿---
title: 'Lync Server 2013: Tabla SessionDetails'
TOCTitle: Tabla SessionDetails
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48275723
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla SessionDetails en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa una sesión punto a punto, que puede ser una llamada de teléfono de VoIP a VoIP, una sesión de mensajería instantánea entre dos partes o cualquier otro tipo de sesión. Puede combinar esta tabla con la [Tabla Media en Lync Server 2013](lync-server-2013-media-table.md) para conocer los detalles de cada medio que toma parte en la sesión.

Tenga en cuenta que los campos IsUser1IntegratedWithDeskPhone y IsUser2IntegratedWithDeskPhone se han suprimido de la tabla SessionDetails utilizada en Microsoft Lync Server 2013.


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
<td><p>Hora de la solicitud de sesión. Se usa en combinación con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número con el que se identifica la sesión. Se usa junto con <strong>SessionIdTime</strong> para identificar una sesión de manera exclusiva*. Referencia a la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID con el que se correlacionan varias sesiones.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Externa</p></td>
<td><p>Número de identificador que identifica el cuadro de diálogo que se reemplazó por la sesión actual. Para más información, vea <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número con el que se identifica la sesión. Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de manera exclusiva una sesión que se reemplazó por esta sesión. Referencia a la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1Id</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador de un usuario de la sesión. Referencia a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador de otro usuario de la sesión. Referencia a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID que identifica el extremo que utilizó el primer usuario en la sesión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID que identifica el extremo que utilizó el segundo usuario en la sesión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI de destinatario original en la solicitud SIP. Referencia a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del usuario que inició la sesión. Referencia a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Señala el identificador de usuario en cuyo nombre llama el autor de la llamada. Referencia a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del usuario por el que se hace referencia a la sesión. Referencia a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del servidor front-end usado en esta sesión. Referencia a la <a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del grupo en el que se capturó la sesión. Referencia a la <a href="lync-server-2013-pools-table.md">Tabla Pools en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de contenido empleado en la sesión. Referencia a la <a href="lync-server-2013-contenttypes-table.md">Tabla ContentTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Versión de cliente usada por el usuario 1. Referencia a la <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Versión de cliente usada por el usuario 2. Referencia a la <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor perimetral usado por el usuario 1. Referencia a la <a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor perimetral usado por el usuario 2. Referencia a la <a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si el usuario 1 ha iniciado sesión de manera interna o no.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si el usuario 2 ha iniciado sesión de manera interna o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora de la primera solicitud INVITE. Este campo normalmente se rellena con los datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la fecha y la hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora de respuesta al primer mensaje INVITE. Este campo normalmente se rellena con los datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la fecha y la hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Identificador de diagnóstico capturado del encabezado SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Prioridad de la llamada. Consulte la <a href="lync-server-2013-callpriorities-table.md">Tabla CallPriorities en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Número de mensajes que envió el usuario 1 durante la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Número de mensajes que envió el usuario 2 durante la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora al final de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Conjunto de bits que indica el tipo de medio de esta sesión. A continuación se enumeran las definiciones de los tipos:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>IM</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>AUDIO</p></td>
<td><p>16</p></td>
</tr>
<tr class="even">
<td><p>VIDEO</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Conjunto de bits que señala los atributos del usuario 1. Se enumeran las siguientes definiciones de atributo:</p>
<ul>
<li><p>0x01 - Integrado en teléfono de escritorio</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Conjunto de bits que señala los atributos del usuario 2. Se enumeran las siguientes definiciones de atributo:</p>
<ul>
<li><p>0x01 - Integrado en teléfono de escritorio</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</p>
<ul>
<li><p>0x01 - Reintento de sesión</p></li>
<li><p>0x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Procesado</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Para uso interno del servicio de supervisión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\* En la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.


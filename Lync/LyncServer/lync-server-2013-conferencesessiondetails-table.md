---
title: 'Lync Server 2013: Tabla ConferenceSessionDetails '
TOCTitle: Tabla ConferenceSessionDetails
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48276154
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ConferenceSessionDetails en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.


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
<td><p>Hora de solicitud de la sesión. Se utiliza en combinación con <strong>SessionIdSeq</strong> como identificación única de una sesión de conferencia. Consulte la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número de id. para identificar la sesión. Se utiliza en combinación con <strong>SessionIdTime</strong> como identificación única de una sesión de conferencia. Consulte la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI de conferencia basada en Foco relacionada con esta sesión. Consulte la <a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a>. Esta URI es una URI de conferencia basada en Foco.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI de conferencia para servidor de conferencia relacionada con esta sesión. Consulte la <a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a>. Esta URI es la URI de conferencia basada en servidor de conferencia. En las sesiones de conferencia basadas en Foco, esta columna será nula.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Id. de un usuario en la sesión de conferencia. Consulte la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID para identificar la instancia del extremo. Por ejemplo, si un usuarios inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un id. de extremo diferente.</p></td>
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
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Versión del cliente utilizada por el usuario de conferencia. Consulte la <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Versión del cliente utilizada por el usuario de servidor. Consulte la <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p></td>
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
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si la sesión la inició el servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si la sesión la finalizó el servidor de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Tanto si el usuario ha iniciado sesión desde un equipo interno como si no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Código de respuesta de protocolo de inicio de sesión (SIP) a la invitación de sesión. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Identificador de diagnóstico capturado del encabezado SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del servidor front-end usado en esta sesión. Referencia a la <a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del grupo en el que se capturó la sesión. Referencia a la <a href="lync-server-2013-pools-table.md">Tabla Pools en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>El servidor de mediación que está utilizando la llamada. Consulte la <a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>La puerta de enlace que está utilizando la llamada. Consulte la <a href="lync-server-2013-gateways-table.md">Tabla Gateways en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>El servidor perimetral que está utilizando la llamada. Consulte la <a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de contenido empleado en la sesión. Referencia a la <a href="lync-server-2013-contenttypes-table.md">Tabla ContentTypes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora de la primera solicitud INVITE. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora de la primera respuesta SIP. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora en que finalizó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externa</p></td>
<td><p>Contiene el valor de tipo URI de MCU procedente de la <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>. Este campo se utiliza para mejorar el rendimiento de las consultas.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Conjunto de bits que indica los atributos del usuario. Se detallan las siguientes definiciones de atributos:</p>
<ul>
<li><p>Integrado con el teléfono de escritorio: 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</p>
<ul>
<li><p>Reintento de sesión: 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* En la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.


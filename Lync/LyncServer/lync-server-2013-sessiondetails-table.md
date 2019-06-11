---
title: 'Lync Server 2013: Tabla SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a>Tabla SessionDetails en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cada registro representa una sesión de punto a punto, que puede ser una llamada de teléfono VoIP-VoIP, una sesión de mi de dos partes u otro tipo de sesión. Puede realizar una combinación de tabla con la [tabla multimedia en Lync Server 2013](lync-server-2013-media-table.md) para buscar los detalles de cada elemento multimedia implicado en esta sesión.

Observe que los campos IsUser1IntegratedWithDeskPhone y IsUser2IntegratedWithDeskPhone se han quitado de la tabla SessionDetails que se usa en Microsoft Lync Server 2013.


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
<td><p>Principal, extranjero</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión. * para obtener más información, consulta la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Un GUID para correlacionar varias sesiones.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Extranjero</p></td>
<td><p>Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de forma única una sesión que se reemplaza por esta sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1Id</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR de un usuario de la sesión. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del otro usuario de la sesión. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>GUID que identifica el extremo utilizado por el primer usuario de la sesión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>GUID que identifica el extremo usado por el segundo usuario de la sesión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>El URI del usuario original para la solicitud SIP. para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del usuario que inició la sesión. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Indica el identificador del usuario de la persona que llama en nombre. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del usuario al que hace referencia la llamada. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del servidor front-end usado para esta sesión. Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del grupo en el que se capturó la sesión. Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Tipo de contenido usado en la sesión. Para obtener más información, consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Versión de cliente usada por el usuario1. Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Versión de cliente usada por usuario2. Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Servidor perimetral usado por el usuario1. Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Servidor perimetral usado por usuario2. Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si user1 está conectado desde interno o no.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si usuario2 está conectado desde interno o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>La hora de la primera solicitud de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información). Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>La hora de la respuesta al primer mensaje de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Código de respuesta SIP a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Prioridad de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-callpriorities-table.md">tabla CallPriorities en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de mensajes enviados por el usuario1 durante la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de mensajes enviados por usuario2 durante la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora de finalización de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Un conjunto de bits que indica el tipo de medio de esta sesión. En la lista se muestran las definiciones de los tipos:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>MI</p></td>
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
<td><p>4,8</p></td>
</tr>
<tr class="odd">
<td><p>AUDIO</p></td>
<td><p>apartado</p></td>
</tr>
<tr class="even">
<td><p>CÁMARA</p></td>
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
<td></td>
<td><p>Un conjunto de bits que indica los atributos del Usuario1. Se muestran las siguientes definiciones de atributos:</p>
<ul>
<li><p>0x01: integrado con un teléfono de escritorio</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Un conjunto de bits que indica los atributos de usuario2. Se muestran las siguientes definiciones de atributos:</p>
<ul>
<li><p>0x01: integrado con un teléfono de escritorio</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Un conjunto de bits que indica los atributos de la llamada. Se muestran las siguientes definiciones de atributos:</p>
<ul>
<li><p>0x01-reintento de sesión</p></li>
<li><p>0x02: una llamada realizada por el agente en nombre de un grupo de respuesta</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Procesar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Para uso interno del servicio de supervisión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si varias sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para una será 1, la otra será 2, y así sucesivamente.

</div>

<span> </span>

</div>

</div>

</div>


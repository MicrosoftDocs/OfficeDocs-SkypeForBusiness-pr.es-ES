---
title: 'Lync Server 2013: vista de SessionDetails'
description: 'Lync Server 2013: vista de SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573246"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a>Vista SessionDetails en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista SessionDetails almacena información sobre sesiones punto a punto, que podrían ser una llamada telefónica VoIP-VoIP, una sesión de mensajería instantánea (MI) entre dos partes o cualquier otro tipo de sesión. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<td><p>Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Consulte la tabla de <a href="lync-server-2013-dialogs-table.md">cuadros de diálogo en la tabla de Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Número de identificador para identificar la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora de la primera solicitud INVITE. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO). Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario que se unió a la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario que inició la sesión. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario que se unió a la sesión. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Inquilino del usuario que inició la sesión. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Inquilino del usuario que se unió a la sesión. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único del extremo del usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único del extremo del usuario que se unió a la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora de finalización de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>entero</p></td>
<td><p>Número de mensajes que envió el usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>entero</p></td>
<td><p>Número de mensajes que envió el usuario que se unió a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versión de cliente que usa el usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>entero</p></td>
<td><p>Cliente que usa el usuario que inició la sesión. Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nombre de la categoría del cliente que usa el usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versión de cliente que usa el usuario que se unió a la sesión</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToClientType</strong></p></td>
<td><p>entero</p></td>
<td><p>Cliente que usa el usuario que se unió a la sesión. Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nombre de la categoría del cliente que usa el usuario que se unió a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario destinatario de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Tipo de URI del usuario destinatario de la sesión. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario en cuyo nombre se inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario en cuyo nombre se inició la sesión. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Inquilino del usuario en cuyo nombre se inició la sesión. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario que hizo referencia a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario que hizo referencia a la sesión. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Inquilino del usuario que hizo referencia a la sesión. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Identificador</strong></p></td>
<td><p>VARCHAR (775)</p></td>
<td><p>Identificador del diálogo SIP. El formato es:</p>
<p>Dialog; from-Tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único global usado para correlacionar varias sesiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora del diálogo que se sustituyó por la sesión. Se usa en combinación con ReplaceDialogIdSeq para identificar de forma exclusiva un diálogo que se sustituye con la sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Número de identificador de la sesión. Se usa en combinación con ReplaceDialogIdTime para identificar de forma exclusiva un diálogo que se sustituye con la sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>VARCHAR (775)</p></td>
<td><p>El identificador de diálogo SIP que sustituye la sesión. El formato es:</p>
<p>Dialog; from-Tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora de la respuesta al primer mensaje INVITE. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>entero</p></td>
<td><p>Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>entero</p></td>
<td><p>Identificador de diagnóstico capturado de los encabezados SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de contenido de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del servidor front-end que capturó los datos de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del grupo que capturó los datos de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del servidor perimetral que usa el usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del servidor perimetral que usa el usuario que inició la sesión</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el usuario que inició la sesión se conectó desde la red interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el usuario que se unió a la sesión se conectó desde la red interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Prioridad de llamada de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:</p>
<p>0x01 - Integrado en teléfono de escritorio</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:</p>
<p>0x01 - Integrado en teléfono de escritorio</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica los atributos de llamada. Se permiten las siguientes definiciones de atributo:</p>
<p>0x01 - Reintento de sesión</p>
<p>0x02 - Una llamada realizada por un agente en nombre de un Grupo de respuesta</p></td>
</tr>
<tr class="even">
<td><p><strong>Location</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Ubicación de una llamada de emergencia.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


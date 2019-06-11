---
title: 'Lync Server 2013: vista ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a>Vista ConferenceSessionDetails en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

La vista ConferenceSessionDetails almacena información sobre las sesiones de varias partes. Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico. Esta vista se presentó en Microsoft Lync Server 2013.


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
<td><p>Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la primera solicitud de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la Conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URI de tipo de conferencia. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del servidor de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del servidor de conferencia. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario implicado en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que formaba parte de la sesión. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Espacio empresarial del usuario que formaba parte de la sesión. Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único del usuario que forma parte de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versión del servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Tipo de servidor de conferencia. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versión del cliente utilizada por el usuario que participó en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente usado por el usuario que participó en la sesión. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nombre de la categoría del cliente que ha usado el usuario que forma parte de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario en cuyo nombre se inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario en cuyo nombre se inició la sesión. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario cuyo en nombre se ha iniciado la sesión. Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Identificador URI del usuario que remitió la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que ha remitido la sesión. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Espacio empresarial del usuario que remitió la sesión. Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>IDENTIFICACIÓN del cuadro de diálogo SIP. El formato es</p>
<p>:d ialog; de-etiqueta; to-Tag</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa junto con ReplaceDialogIdTime para identificar de forma única una sesión que se reemplaza por esta sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>VARCHAR (775)</p></td>
<td><p>IDENTIFICACIÓN del cuadro de diálogo SIP que reemplaza la sesión. El formato de es:</p>
<p>cuadro de diálogo; desde: etiqueta; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si la sesión ha sido iniciada por el servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el servidor de conferencia finalizó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el usuario ha iniciado sesión en la red interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la respuesta al primer mensaje de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Código de respuesta SIP a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR de diagnóstico capturado de los encabezados de SIP de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de contenido de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del servidor front-end que capturó los datos para la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de servidores que ha capturado los datos de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediación usado por el usuario que participó en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Puerta</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Puerta de enlace usada por el usuario que participó la sesión.</p></td>
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
<p>0x01: integrado con un teléfono de escritorio</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributo:</p>
<p>0x01-reintento Session0</p>
<p>x02: una llamada realizada por el agente en nombre de un grupo de respuesta</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Tabla ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Tabla ConferenceSessionDetails en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico.


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
<td><p>Fechas</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Hora de la solicitud de sesión; se usa junto con <strong>SessionIdSeq</strong> para identificar de forma exclusiva una sesión de conferencia. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> para identificar de forma exclusiva una sesión de conferencia. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> . *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Centrar el URI de conferencia relacionado con esta sesión. Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> . Este URI es un URI de conferencia basado en el foco.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>URI de conferencia del servidor de conferencia relacionado con esta sesión. Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> . Este URI es el URI de conferencia basado en el servidor de conferencia. Para sesiones de conferencia focalizadas, esta columna será nula.</p></td>
</tr>
<tr class="even">
<td><p><strong>Iddeusuario</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR de un usuario en la sesión de conferencia. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Un GUID para identificar la instancia de Endpoint. Por ejemplo, si un usuario inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un identificador de extremo diferente.</p></td>
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
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Versión del cliente usada por el usuario de la Conferencia. Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Versión de cliente usada por el servidor de conferencia. Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</p></td>
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
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica si la sesión ha sido iniciada por el servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica si la sesión finalizó por el servidor de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si el usuario ha iniciado sesión en un interno o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Código de respuesta del Protocolo de inicio de sesión (SIP) a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del servidor front-end usado para esta sesión. Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del grupo en el que se capturó la sesión. Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>El servidor de mediación que usa la llamada. Para obtener más información, consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>La puerta de enlace que usa la llamada. Para obtener más información, consulte la <a href="lync-server-2013-gateways-table.md">tabla de puertas de enlace en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>El servidor perimetral que usa la llamada. Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Tipo de contenido usado en la sesión. Para obtener más información, consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>La hora de la primera solicitud de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora de la primera respuesta del SIP. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>La hora de finalización de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Extranjero</p></td>
<td><p>Contiene el valor de tipo URI de MCU de la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a>. Este campo se usa para mejorar el rendimiento de las consultas.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Un conjunto de bits que indica los atributos de usuario. Se muestran las siguientes definiciones de atributos:</p>
<ul>
<li><p>Integrado con un teléfono de escritorio: 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Un conjunto de bits que indica los atributos de la llamada. Se muestran las siguientes definiciones de atributos:</p>
<ul>
<li><p>Reintento de sesión: 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si varias sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para una será 1, la otra será 2, y así sucesivamente.

</div>

<span> </span>

</div>

</div>

</div>


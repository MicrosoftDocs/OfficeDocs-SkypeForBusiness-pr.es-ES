---
title: 'Lync Server 2013: tabla ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57d8e3cb0a79c8ce6a6c1c51891fbad265f045de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529207"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Tabla ConferenceSessionDetails en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

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
<td><p>DateTime</p></td>
<td><p>Principal, Exterior</p></td>
<td><p>Hora de la solicitud de sesión; se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una sesión de conferencia. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal, Exterior</p></td>
<td><p>Número del identificador para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión de conferencia. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>URI de conferencia basada en Foco relacionada con esta sesión. Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información. Esta URI es una URI de conferencia basada en Foco.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador que distingue entre instancias de conferencias recurrentes. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>URI de conferencia para servidor de conferencia relacionada con esta sesión. Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información. Esta URI es la URI de conferencia basada en servidor de conferencia. En las sesiones de conferencia basadas en Foco, esta columna será nula.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>IDENTIFICADOR de un usuario en la sesión de conferencia. Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>GUID para identificar la instancia del extremo. Por ejemplo, si un usuarios inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un id. de extremo diferente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Señala el identificador de usuario en cuyo nombre llama el autor de la llamada. Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del usuario por el que se hace referencia a la sesión. Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Versión del cliente utilizada por el usuario de conferencia. Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Versión del cliente utilizada por el usuario de servidor. Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Externa</p></td>
<td><p>Número con el que se identifica el diálogo que se reemplazó por la sesión actual. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Número con el que se identifica la sesión. Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de manera exclusiva una sesión que se reemplazó por esta sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica si la sesión la inició el servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica si la sesión la finalizó el servidor de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Tanto si el usuario ha iniciado sesión desde un equipo interno como si no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>entero</p></td>
<td></td>
<td><p>Código de respuesta de protocolo de inicio de sesión (SIP) a la invitación de sesión. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>entero</p></td>
<td></td>
<td><p>Identificador de diagnóstico capturado del encabezado SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del servidor front-end usado en esta sesión. Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del grupo en el que se capturó la sesión. Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>El servidor de mediación que está utilizando la llamada. Consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>La puerta de enlace que está utilizando la llamada. Consulte la <a href="lync-server-2013-gateways-table.md">tabla puertas de enlace en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>El servidor perimetral que está utilizando la llamada. Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de contenido empleado en la sesión. Consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora de la primera solicitud INVITE. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora de la primera respuesta SIP. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora en que finalizó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externa</p></td>
<td><p>Contiene el valor tipo de URI de MCU de la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a>. Este campo se utiliza para mejorar el rendimiento de las consultas.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Conjunto de bits que indica los atributos del usuario. Se detallan las siguientes definiciones de atributos:</p>
<ul>
<li><p>Integrado con el teléfono de escritorio: 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</p>
<ul>
<li><p>Reintento de sesión: 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1. Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.

</div>

<span> </span>

</div>

</div>

</div>


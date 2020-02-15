---
title: 'Lync Server 2013: vista de ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1fe360726c94062391a4559f73a375d68b5f384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Vista ErrorReport en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-22_

La vista ErrorReport almacena información sobre los errores que se notifican. Cada registro representa la aparición de un error. Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<td><p><strong>Campos errortime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número para identificar el error. Se usa en combinación con ErrorTime para identificar el error de forma exclusiva.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Identificador de diagnóstico del informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario que ha originado el error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario que ha originado el error. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Inquilino del usuario que ha originado el error. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario destinatario del informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario destinatario del informe de errores. Para más información, consulte la tabla UriTypes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Inquilino del usuario destinatario del informe de errores. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>Uri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la conferencia destinataria del informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI de la conferencia destinataria del informe de errores. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la solicitud de la sesión que originó el informe de errores. Se usa de forma conjunta con SessionIdseq para identificar de forma exclusiva una sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número para identificar la solicitud de sesión que originó el informe de errores. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>Identificador</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>Identificador de diálogo SIP que originó el error. El formato es:</p>
<p>Dialog; from-Tag; to-Tag</p>
<p>Estos datos pueden convertirse en formato de texto con esta sintaxis:</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versión del cliente que usa el usuario que originó el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente que usa el usuario que originó el error. Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nombre de categoría del cliente que usa el usuario que originó el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre de la aplicación que originó el error (si el informe se envió desde un componente de servidor).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Código de respuesta SIP a la sesión del mensaje SIP que contiene el informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Tipo de solicitud que ha generado errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Tipo de contenido de la solicitud que ha generado errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de sesión. Consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el informe de errores fue capturado por el agente del CDR que se ejecuta en el servidor front-end o si lo envió el cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Reservado para uso futuro.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Más información sobre el error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nombre de dominio completo del servidor front-end que ha enviado el informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nombre de dominio completo del grupo de servidores que contiene el servidor front-end que ha enviado el informe.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


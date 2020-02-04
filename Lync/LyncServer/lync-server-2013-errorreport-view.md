---
title: 'Lync Server 2013: vista ErrorReport'
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
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Vista ErrorReport en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-22_

La vista ErrorReport almacena información sobre los errores notificados. Cada registro es una aparición de error. Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente. Esta vista se presentó en Microsoft Lync Server 2013.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de error. Se usa junto con ErrorReportSeq para identificar de forma única un error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación para identificar el error. Se usa junto con ErrorTime para identificar de forma única un error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR de diagnóstico del informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Identificador URI del usuario que originó el error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que originó el error. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Espacio empresarial del usuario que originó el error. Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUr</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Identificador URI del usuario que era el destino del informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que se dirige al informe de errores. Para obtener más información, consulte la tabla UriTypes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Espacio empresarial del usuario que se dirige al informe de errores. Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la Conferencia que era el destino del informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI de la Conferencia que era el destino del informe de errores. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la solicitud de sesión que originó el informe de errores. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación para identificar la solicitud de sesión que originó el informe de errores. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>IDENTIFICADOR del cuadro de diálogo SIP de la sesión que originó el error. El formato es:</p>
<p>cuadro de diálogo; desde: etiqueta; to-Tag</p>
<p>Estos datos se pueden convertir a formato de texto con esta sintaxis:</p>
<p>CAST (Cast) (ExternalId as varbinary (Max)) as VARCHAR (Max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versión del cliente utilizada por el usuario que originó el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipocliente</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente usado por el usuario que originó el error. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nombre de la categoría del cliente que ha usado el usuario que originó el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>Origen</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del servidor que originó el error (si el informe fue enviado desde un componente de servidor).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aplicación</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre de la aplicación que originó el error (si el informe fue enviado desde un componente de servidor).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Código de respuesta SIP a la sesión del mensaje SIP que contiene el informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Tipo de solicitud en la que se produjo un error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Tipo de contenido de la solicitud en la que se produjo un error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de sesión. Para obtener más información, consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el informe de errores fue capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fdisableautoindexingonschemaupdate</strong></p></td>
<td><p>smallint</p></td>
<td><p>Reservado para uso futuro.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Información adicional sobre el error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nombre de dominio completo del servidor front-end que ha enviado el informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nombre de dominio completo del grupo que contiene el servidor front-end que ha enviado el informe.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


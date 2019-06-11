---
title: 'Lync Server 2013: Tabla ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>Tabla ErrorReport en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

La tabla ErrorReport almacena información sobre los errores que se han producido. Cada registro es una aparición de error. Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Fecha y hora en que se produjo el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Número de identificación para identificar el informe de errores. Se usa en conjunción con <strong>ErrorTime</strong> para identificar de manera exclusiva un informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR único del tipo de error. Para obtener más información, consulte la <a href="lync-server-2013-errordef-table.md">tabla ErrorDef en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Usuario que originó la solicitud que causó el error. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Usuario de destino de la solicitud que causó el error. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>URI de conferencia relacionado con el error. Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> . Normalmente, si ConferenceUriId no es null, FromUserId o ToUserId será null.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Extranjero</p></td>
<td><p>Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor). Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor). Para obtener más información, consulte la <a href="lync-server-2013-application-table.md">tabla de aplicaciones en Lync Server 2013</a> .</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>imagen</p></td>
<td><p> </p></td>
<td><p>Más información sobre el error.</p>
<p>Estos datos se pueden convertir a formato de texto con esta sintaxis:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>La versión de cliente del extremo que envía el informe de errores. Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Es el informe de errores capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fdisableautoindexingonschemaupdate</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Reservado para uso futuro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Representa el nombre de dominio completo del servidor que ha generado el informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Representa el nombre de dominio completo del grupo en el que se generó el informe de errores.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


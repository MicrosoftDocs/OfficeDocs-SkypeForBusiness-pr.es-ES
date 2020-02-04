---
title: 'Lync Server 2013: Tabla ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Tabla ProgressReport en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Los informes de progreso se basan en los datos cargados por el cliente en la base de datos después de completarse una llamada o sesión. Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico.

Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia a errores sino a mensajes que indican el estado de las llamadas o los mensajes.


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
<td><p>Principal, extranjero</p></td>
<td><p>Fecha y hora del informe de errores de progreso que contiene este informe de progreso. Para obtener más información, consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación usado en conjunción con ErrorTime, ProgressReportSeq para identificar de manera exclusiva un informe de progreso. Para obtener más información, consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación que identifica el informe de errores. ErrorReporSeq se usa junto con ErrorTime para identificar de forma exclusiva un informe de errores. Para obtener más información, consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a></p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Número de identificación para identificar el informe de progreso. Se usa junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>IDENTIFICADOR de diagnóstico del informe de progreso.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Servidor que ha enviado el informe de errores (si el informe se envió desde un componente de servidor). Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> . Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>El proceso de Lync Server sobre el que se encuentra el informe. Para obtener más información, consulte la tabla de la aplicación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Detalle</strong></p></td>
<td><p>imagen</p></td>
<td></td>
<td><p>Detalles del informe de progreso, almacenado en formato binario, para ahorrar espacio. Estos datos se pueden convertir a formato de texto con esta sintaxis:</p>
<p>CAST (detallar como varbinary (Max)) como varchar (Max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador único que correlaciona la información de tiempo de Unión para los distintos componentes implicados en una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Tiempo (en milisegundos) para que un componente específico se una a una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


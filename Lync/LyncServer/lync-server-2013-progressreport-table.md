---
title: 'Lync Server 2013: Tabla ProgressReport'
TOCTitle: Tabla ProgressReport
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48274938
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ProgressReport en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión. Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos.

Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no se hacen necesariamente referencia a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.


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
<td><p>Datetime</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Fecha y hora del informe de errores de progreso que contiene este informe de progreso. Vea <a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número de identificación usado junto con ErrorTime, ProgressReportSeq para identificar de manera única un informe de progreso. Consulte <a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número de id. que identifica el informe de errores. ErrorReporSeq se usa junto con ErrorTime para identificar de manera única un informe de errores. Vea la <a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a> para obtener más información</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número de identificación usado para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Id. de diagnóstico del informe de progreso.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor que envió el informe de errores (si el informe se envió desde un componente de servidor). Vea la <a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a> para obtener más información. Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>El proceso de Lync Server al que se refiere el informe. Vea la tabla de aplicaciones para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>Detail</strong></p></td>
<td><p>imagen</p></td>
<td><p></p></td>
<td><p>Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos pueden convertirse en formato de texto usando esta sintaxis:</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificador único que correlaciona información de hora de conexión para los diferentes componentes que participan en una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Tiempo (en milisegundos) para que un componente específico se una a una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


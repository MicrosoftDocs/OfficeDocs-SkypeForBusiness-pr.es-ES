---
title: Vista ProgressReport
TOCTitle: Vista ProgressReport
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49889543
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista ProgressReport

 

_**Última modificación del tema:** 2015-03-09_

La vista ProgressReport almacena información sobre las sesiones finalizadas. Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos. Esta vista se introdujo en Microsoft Lync Server 2013.


> [!NOTE]
> Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no se hacen necesariamente referencia a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.




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
<td><p>Fecha y hora en que se produjo el error. Se usa junto con ErrorReportSeq como identificación única de un error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número para identificar el error. Se usa junto con ErrorTime como identificación única de un error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Identificador del informe de progreso. Se usa para diferenciar informes de progreso del mismo informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Identificador de diagnóstico del informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del servidor que generó el error (si el informe se envió desde un componente de servidor).</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre de la aplicación que generó el error (si el informe se envió desde un componente de servidor).</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificador único que correlaciona la información de hora de conexión para los diferentes componentes de una conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Tiempo (en milisegundos) necesario para que un componente específico se una a las conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Información adicional del error.</p></td>
</tr>
</tbody>
</table>


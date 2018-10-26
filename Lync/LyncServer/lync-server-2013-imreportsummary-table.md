---
title: Tabla IMReportSummary en Lync Server 2013
TOCTitle: Tabla IMReportSummary en Lync Server 2013
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48274738
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla IMReportSummary en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.


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
<td><p><strong>StartTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal</p></td>
<td><p>Fecha y hora en que comenzó la sesión de mensajería instantánea.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimePeriod</strong></p></td>
<td><p>char(1)</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (257)</p></td>
<td><p>Principal</p></td>
<td><p>Nombre de dominio completo del grupo de servidores que hospeda la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Prioridad (por ejemplo, urgente o no urgente) de la llamada. La información de prioridad se almacena en la <a href="lync-server-2013-callpriorities-table.md">Tabla CallPriorities en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>Número total de mensajes instantáneos intercambiados durante la sesión.</p></td>
</tr>
</tbody>
</table>


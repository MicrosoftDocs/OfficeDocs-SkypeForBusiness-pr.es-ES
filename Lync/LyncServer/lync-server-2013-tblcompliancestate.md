---
title: 'Lync Server 2013: tblComplianceState'
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48277054
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceState en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.

### Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>lastProcessedEntryID</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>ID del último evento de cumplimiento procesado.</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador del servidor de cumplimiento que contiene el bloqueo exclusivo en la base de datos o, si no lo hay, -1.</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>datetime2, not null</p></td>
<td><p>Fecha y hora de expiración del bloqueo (si activeServerID no es -1).</p></td>
</tr>
</tbody>
</table>


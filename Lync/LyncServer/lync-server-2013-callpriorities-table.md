---
title: 'Lync Server 2013: Tabla CallPriorities'
TOCTitle: Tabla CallPriorities
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48274281
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla CallPriorities en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamada, como "emergencia", "urgente" o "normal".


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
<td><p><strong>PriorityId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Prioridad</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0 - Desconocido</p></li>
<li><p>1 - No urgente</p></li>
<li><p>2 - Normal</p></li>
<li><p>3 - Urgente</p></li>
<li><p>4 - Emergencia</p></li>
</ul></td>
</tr>
</tbody>
</table>


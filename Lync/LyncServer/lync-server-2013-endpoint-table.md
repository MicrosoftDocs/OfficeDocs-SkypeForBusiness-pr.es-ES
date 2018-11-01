---
title: 'Lync Server 2013: Tabla Endpoint'
TOCTitle: Tabla Endpoint
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48275254
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Endpoint en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Extremo es una tabla de apoyo que almacena información acerca de los extremos que han participado en las sesiones registradas en la base de datos. Cada uno de los registros de la tabla representa un extremo.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este extremo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Única</p></td>
<td><p>Nombre del extremo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sistema operativo</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p> </p></td>
<td><p>Sistema operativo (SO) del extremo.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p></p></td>
<td><p>Nombre de la CPU del extremo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Número de núcleos de CPU del extremo.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Velocidad del procesador de la CPU del extremo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Marca de bits que señala si el sistema se está ejecutando en un entorno virtualizado:</p>
<ul>
<li><p>0x0000 – Ninguno</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMWare</p></li>
<li><p>0x0004 – Virtual PC</p></li>
<li><p>0x0008 – Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>


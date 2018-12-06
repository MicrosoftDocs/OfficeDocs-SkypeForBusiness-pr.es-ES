---
title: 'Lync Server 2013: Tabla DeviceDriver'
TOCTitle: Tabla DeviceDriver
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48276667
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla DeviceDriver en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla DeviceDriver es una tabla auxiliar. Cada registro representa un controlador que usa un dispositivo de captura o un dispositivo de representación.


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
<td><p><strong>DeviceDriverKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único de identificación de este registro de controlador de dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Único</p></td>
<td><p>Nombre de controlador de dispositivo.</p></td>
</tr>
</tbody>
</table>


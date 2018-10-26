---
title: 'Lync Server 2013: Tabla Devices'
TOCTitle: Tabla Devices
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48275273
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Devices en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).


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
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número único de identificación de esta versión de hardware.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Fabricante de este dispositivo. Consulte <a href="lync-server-2013-manufacturers-table.md">Tabla Manufacturers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Versión de hardware de este dispositivo. Consulte <a href="lync-server-2013-hardwareversions-table.md">Tabla HardwareVersions en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>Dirección MAC</p></td>
</tr>
</tbody>
</table>


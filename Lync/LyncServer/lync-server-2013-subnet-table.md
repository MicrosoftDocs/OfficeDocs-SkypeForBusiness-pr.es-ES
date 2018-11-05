---
title: 'Lync Server 2013: Tabla Subnet'
TOCTitle: Tabla Subnet
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48275710
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Subnet en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Representación en número entero de la IP de la subred.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetMask</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Máscara de la subred.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-usersite-table.md">Tabla UserSite en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>nvarchar(512)</p></td>
<td><p></p></td>
<td><p>Descripción de la subred.</p></td>
</tr>
</tbody>
</table>


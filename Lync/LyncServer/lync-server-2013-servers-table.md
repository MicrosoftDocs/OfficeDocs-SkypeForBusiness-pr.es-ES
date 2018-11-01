---
title: 'Lync Server 2013: Tabla Servers'
TOCTitle: Tabla Servers
ms:assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398223(v=OCS.15)
ms:contentKeyID: 48274524
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Servers en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Servers es una tabla auxiliar que almacena información acerca de los distintos servidores. Cada registro de la tabla representa un servidor.


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
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerFQDN</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>FQDN del servidor.</p></td>
</tr>
</tbody>
</table>


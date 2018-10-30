---
title: 'Lync Server 2013: Tabla Gateways'
TOCTitle: Tabla Gateways
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48276300
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Gateways en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Gateways es una tabla auxiliar. En cada registro se almacena información sobre una puerta de enlace que participa en llamadas de red telefónica conmutada (RTC) con registros en esta base de datos.


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
<td><p><strong>GatewayId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica esta puerta de enlace.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Nombre de la puerta de enlace.</p></td>
</tr>
</tbody>
</table>


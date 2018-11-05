---
title: 'Lync Server 2013: Tabla MediationServers'
TOCTitle: Tabla MediationServers
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48276158
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla MediationServers en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla MediationServers es una tabla auxiliar. En cada registro se almacena información sobre un servidor de mediación que participa en llamadas con registros en esta base de datos.


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
<td><p><strong>MediationServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Nombre del servidor de mediación.</p></td>
</tr>
</tbody>
</table>


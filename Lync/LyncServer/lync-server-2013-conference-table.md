---
title: 'Lync Server 2013: Tabla Conference'
TOCTitle: Tabla Conference
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48274751
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Conference en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.


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
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este registro de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Único</p></td>
<td><p>ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>Int</p></td>
<td><p>índice</p></td>
<td><p>Suma de comprobación del URI de conferencia. Para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
</tbody>
</table>


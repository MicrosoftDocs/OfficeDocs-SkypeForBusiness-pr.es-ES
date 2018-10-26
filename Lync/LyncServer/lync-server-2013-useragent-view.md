---
title: Vista UserAgent
TOCTitle: Vista UserAgent
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49889638
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista UserAgent

 

_**Última modificación del tema:** 2015-03-09_

La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que cuentan con registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>Número único que identifica al agente de usuario.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario.</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario. Consulte <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a UACategory CAA.</p></td>
</tr>
</tbody>
</table>


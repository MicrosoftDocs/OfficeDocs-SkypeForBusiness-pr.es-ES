---
title: 'Lync Server 2013: Tabla MediaList'
TOCTitle: Tabla MediaList
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48274626
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla MediaList en Lync Server 2013

 

_**Última modificación del tema:** 2016-07-12_

La lista MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>1 – MI</p></li>
<li><p>2 – Transferencia de archivos</p></li>
<li><p>3 – Asistencia remota</p></li>
<li><p>4 – Uso compartido de aplicaciones</p></li>
<li><p>5 – audio</p></li>
<li><p>6 – vídeo</p></li>
<li><p>7 – Invitación a la aplicación</p></li>
</ul></td>
</tr>
</tbody>
</table>


---
title: 'Lync Server 2013: Tabla CallType'
TOCTitle: Tabla CallType
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48276248
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla CallType en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla CallType es una tabla estática donde se almacena la lista de posibles tipos de llamada.


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td><p></p></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0 – Desconocido</p></li>
<li><p>1 – Mensajería instantánea</p></li>
<li><p>2 – Uso compartido de aplicaciones</p></li>
<li><p>3 – audio</p></li>
<li><p>4 – Audio y vídeo</p></li>
<li><p>5 – Transferencia de archivos</p></li>
</ul></td>
</tr>
</tbody>
</table>


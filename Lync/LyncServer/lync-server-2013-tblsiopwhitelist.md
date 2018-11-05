---
title: 'Lync Server 2013: tblSiopWhiteList'
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48274310
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblSiopWhiteList en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblSiopWhiteList es la lista de complementos registrados que es posible asociar con nodos.

### Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>GUID, no NULL</p></td>
<td><p>GUID del complemento.</p></td>
</tr>
<tr class="even">
<td><p>siopName</p></td>
<td><p>nvarchar (50), no NULL</p></td>
<td><p>Nombre para mostrar del complemento.</p></td>
</tr>
<tr class="odd">
<td><p>siopUrl</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>URL del complemento.</p></td>
</tr>
</tbody>
</table>


### Tecla

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


---
title: 'Lync Server 2013: tblEnumValue'
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48276181
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblEnumValue en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblEnumValue es una tabla dentro del código que limita los valores de visibilidad y comportamiento de los atributos utilizados en la tabla Node.

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
<td><p>valueID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Id. del valorvalue.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Identificador del atributo.</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Nombre del valor.</p></td>
</tr>
</tbody>
</table>


### Teclas

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
<td><p>valueID</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblEnumAttribute.attributeID.</p></td>
</tr>
</tbody>
</table>


### Valores de tabla

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>private</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>scope</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2</p></td>
<td><p>normal</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2</p></td>
<td><p>auditorium</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>1</p></td>
<td><p>open</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[tblNode en Lync Server 2013](lync-server-2013-tblnode.md)


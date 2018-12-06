---
title: 'Lync Server 2013: tblEnumAttribute'
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48274558
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblEnumAttribute en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.

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
<td><p>attributeID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Identificador del atributo.</p></td>
</tr>
<tr class="even">
<td><p>attributeName</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Nombre del atributo.</p></td>
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
<td><p>attributeID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


### Valores de tabla

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>attributeID</th>
<th>attributeName</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Visibilidad.</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Comportamiento.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[tblNode en Lync Server 2013](lync-server-2013-tblnode.md)


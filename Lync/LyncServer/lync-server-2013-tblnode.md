---
title: 'Lync Server 2013: tblNode'
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48276179
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblNode en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblNode contiene el árbol de objetos (con nodos de categorías o salones de chat) según se haya administrado en el Panel de control de Lync Server 2013 y en los cmdlets administrativos.

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
<td><p>nodeID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. de nodo (número único).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, no NULL</p></td>
<td><p>GUID de nodo.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>Int</p></td>
<td><p>Id. de nodo de elemento primario. El nodo raíz (con id. 1) se incluye también a sí mismo como elemento principal.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, no NULL</p></td>
<td><p>Verdadero si el nodo es una categoría.</p>
<p>Falso si el nodo es un salón de chat.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Nombre de nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Descripción de nodo.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>bit</p></td>
<td><p>Para categorías:</p>
<ul>
<li><p>Verdadero si se activan las invitaciones.</p></li>
<li><p>Falso si se desactivan las invitaciones.</p></li>
</ul>
<p>Para salones:</p>
<ul>
<li><p>Falso si se desactivan las invitaciones (invalida la categoría principal).</p></li>
<li><p>NULL si la configuración de invitaciones se ha heredado de la categoría principal.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>logged</p></td>
<td><p>bit</p></td>
<td><p>Para categorías:</p>
<ul>
<li><p>Verdadero si el historial de chat está activado.</p></li>
<li><p>Falso si el historial de chat está desactivado.</p></li>
</ul>
<p>Para salones:</p>
<ul>
<li><p>NULL.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>Para categorías:</p>
<ul>
<li><p>Verdadero si se permite cargar archivos.</p></li>
<li><p>Falso si no se permite cargar archivos.</p></li>
</ul>
<p>Para salones:</p>
<ul>
<li><p>NULL.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>disabled</p></td>
<td><p>bit, no NULL</p></td>
<td><p>Verdadero si el salón de chat está desactivado. Se aplica solo a los salones de chat. (Falso para categorías.)</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Comportamiento (consultado en la tabla EnumValue):</p>
<ul>
<li><p>4: Normal (salones de chat normales)</p></li>
<li><p>5: Auditorium (salones de chat de tipo auditorio, solo pueden contribuir los moderadores).</p></li>
</ul>
<p>Solo se aplica a salones de chat.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Visibilidad (consultado en la tabla EnumValue):</p>
<ul>
<li><p>2: Privado</p></li>
<li><p>3: Con ámbito</p></li>
<li><p>6: Open</p></li>
</ul>
<p>Solo se aplica a salones de chat.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>Identificador único global</p></td>
<td><p>GUID complemento si hay un complemento asociado a este salón de chat. (Las categorías no tienen complementos.)</p>
<p>La información de complemento se consulta en la tabla SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. del principal que creó este nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo de creación del nodo.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. del principal que actualizó por última vez este nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo de la última actualización de este nodo.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>Datetime</p></td>
<td><p>Hora de la última operación de purga (retirada de ámbitos de la tabla tblScopedPrincipal y roles de la tabla tblPrincipalRole) que afectó a este nodo. La utiliza el mecanismo interno de actualización de caché del servicio de chat.</p></td>
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
<td><p>nodeID</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>Clave externa con búsqueda en la tabla tblEnumValue.valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Clave externa con búsqueda en la tabla tblEnumValue.valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Clave externa con búsqueda en la tabla RoleType.rtypeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblSiopWhiteList.siopId.</p></td>
</tr>
</tbody>
</table>


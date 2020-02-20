---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cee7c67421ae12d08e52bee1b013dfa6280472f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>tblNode en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) tal como se administra en el panel de control de Lync Server 2013 y en los cmdlets administrativos.

### <a name="columns"></a>Columns

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
<td><p>IDENTIFICADOR de nodo (número único).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>GUID de nodo.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR de nodo de primario. El nodo raíz (con identificador 1) también se incluye como primario.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, not null</p></td>
<td><p>True si el nodo es una categoría.</p>
<p>False si el nodo es un salón de chat.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Nombre del nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Descripción del nodo.</p></td>
</tr>
<tr class="odd">
<td><p>invitar</p></td>
<td><p>bit</p></td>
<td><p>Para categorías:</p>
<ul>
<li><p>True si se activan las invitaciones.</p></li>
<li><p>False si los invitados están desactivados.</p></li>
</ul>
<p>Para los salones:</p>
<ul>
<li><p>False si los invitados están desactivados (invalida la categoría principal).</p></li>
<li><p>NULL si la configuración de invitaciones se ha heredado de la categoría principal.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>iniciado sesión</p></td>
<td><p>bit</p></td>
<td><p>Para categorías:</p>
<ul>
<li><p>True si el historial de chat está activado.</p></li>
<li><p>False si el historial de chat está desactivado.</p></li>
</ul>
<p>Para los salones:</p>
<ul>
<li><p>Que.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>Para categorías:</p>
<ul>
<li><p>True si se permiten las cargas de archivos.</p></li>
<li><p>False si no se permiten las cargas de archivos.</p></li>
</ul>
<p>Para los salones:</p>
<ul>
<li><p>Que.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>capacidad</p></td>
<td><p>bit, not null</p></td>
<td><p>True si el salón de chat está deshabilitado. Solo se aplica a salones de chat. (False para las categorías.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>comportamiento</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Comportamiento (buscar en la tabla EnumValue):</p>
<ul>
<li><p>4: normal (salones de chat normales).</p></li>
<li><p>5: auditorio (los salones de chat de auditorio, solo los moderadores pueden contribuir).</p></li>
</ul>
<p>Solo se aplica a salones de chat.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Visibilidad (buscar en la tabla EnumValue):</p>
<ul>
<li><p>2: privado</p></li>
<li><p>3: con ámbito</p></li>
<li><p>6: abrir</p></li>
</ul>
<p>Solo se aplica a salones de chat.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>GUID de complemento si un complemento está asociado con este salón de chat. (Las categorías no tienen complementos).</p>
<p>La información del complemento se busca en la tabla SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>IDENTIFICADOR de la entidad de identidad que creó este nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo de la creación del nodo.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>IDENTIFICADOR de la entidad de identidad que realizó la última actualización de este nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo de la última actualización de este nodo.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>Hora de la última operación de purga (la eliminación de ámbitos de la tabla tblScopedPrincipal y los roles de la tabla tblPrincipalRole) que afectaban a este nodo. Se usa en el mecanismo de actualización de caché interna del servicio de chat.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

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
<td><p>comportamiento</p></td>
<td><p>Clave externa con búsqueda en la tabla tblEnumValue. valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Clave externa con búsqueda en la tabla tblEnumValue. valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblSiopWhiteList. siopId.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


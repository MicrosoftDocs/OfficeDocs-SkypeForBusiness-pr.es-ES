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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>tblNode en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) tal como se administra en el panel de control y los cmdlets administrativos de Lync Server 2013.

### <a name="columns"></a>Columnas

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
<td><p>int, not null</p></td>
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
<td><p>IDENTIFICADOR de nodo del elemento primario. El nodo raíz (con identificador 1) también se incluye como principal.</p></td>
</tr>
<tr class="even">
<td><p>Nodo</p></td>
<td><p>bit, not null</p></td>
<td><p>True si el nodo es una categoría.</p>
<p>Falso si el nodo es un salón de chat.</p></td>
</tr>
<tr class="odd">
<td><p>nombreDeNodo</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Nombre del nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Descripción del nodo.</p></td>
</tr>
<tr class="odd">
<td><p>recibir</p></td>
<td><p>bit</p></td>
<td><p>Para las categorías:</p>
<ul>
<li><p>True si los invitados están activados.</p></li>
<li><p>False si los invitados están deshabilitados.</p></li>
</ul>
<p>Para salas:</p>
<ul>
<li><p>False si los invitados están deshabilitados (reemplaza la categoría principal).</p></li>
<li><p>NULL si la configuración de invitados se hereda de la categoría principal.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>conectarse</p></td>
<td><p>bit</p></td>
<td><p>Para las categorías:</p>
<ul>
<li><p>True si el historial de chat está activado.</p></li>
<li><p>Falso si el historial de conversaciones está deshabilitado.</p></li>
</ul>
<p>Para salas:</p>
<ul>
<li><p>Valor.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>Para las categorías:</p>
<ul>
<li><p>True si se permiten las cargas de archivos.</p></li>
<li><p>False si no se permiten las cargas de archivos.</p></li>
</ul>
<p>Para salas:</p>
<ul>
<li><p>Valor.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>habilitar</p></td>
<td><p>bit, not null</p></td>
<td><p>True si el salón de chat está deshabilitado. Solo se aplica a salones de chat. (Falso para categorías).</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>problema</p></td>
<td><p>smallint, not null</p></td>
<td><p>Comportamiento (que se busca en la tabla EnumValue):</p>
<ul>
<li><p>4: normal (salones de chat normales).</p></li>
<li><p>5: auditorio (salones de chat de Auditorio; solo los moderadores pueden contribuir).</p></li>
</ul>
<p>Solo se aplica a salones de chat.</p></td>
</tr>
<tr class="odd">
<td><p>visión</p></td>
<td><p>smallint, not null</p></td>
<td><p>Visibilidad (en la tabla EnumValue):</p>
<ul>
<li><p>2: privado</p></li>
<li><p>3: ámbito</p></li>
<li><p>6: abrir</p></li>
</ul>
<p>Solo se aplica a salones de chat.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>Identificador único global</p></td>
<td><p>GUID de complemento si un complemento está asociado con este salón de chat. (Las categorías no tienen complementos).</p>
<p>La información del complemento se busca en la tabla SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de la entidad de identidad que creó este nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Marca de tiempo de la creación del nodo.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de la entidad de identidad que realizó la última actualización de este nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Marca de tiempo de la última actualización de este nodo.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>Hora de la última operación de purga (eliminación de ámbitos de la tabla tblScopedPrincipal y roles de la tabla tblPrincipalRole) que afectó a este nodo. Lo usa el mecanismo de actualización de la caché interna del servicio de chat.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Sus

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
<td><p>problema</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblEnumValue. valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visión</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblEnumValue. valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblNode. nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblSiopWhiteList. siopId.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


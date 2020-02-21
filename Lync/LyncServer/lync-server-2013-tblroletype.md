---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 721932aa2929930b3da742355a46c5e2066c5c83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-25_

tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.

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
<td><p>Prinid</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador del tipo de rol.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Descripción del tipo de rol. Existen cuatro roles disponibles:</p>
<ul>
<li><p>Miembro: miembro de salón de chat</p></li>
<li><p>Administrador: administrador de salón de chat</p></li>
<li><p>Miembro con voz: moderador de un salón de chat de tipo auditorio</p></li>
<li><p>Creador: puede crear salones de chat</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Conjunto de permisos del rol. Los valores usados son:</p>
<ul>
<li><p>2: True si el rol puede administrar nodos.</p></li>
<li><p>4: True si el rol puede crear nodos secundarios.</p></li>
<li><p>7: True si el rol puede unirse a un salón de chat (o salones de chat secundarios de una categoría).</p></li>
<li><p>8: True si el rol puede hablar en un salón de chat (o salones de chat secundarios de una categoría).</p></li>
<li><p>10: True si el rol puede leer el historial de chat incluso cuando no se unió a un salón de chat.</p></li>
<li><p>11: True si el rol puede ver el salón de chat. (Restricción adicional según factores, como ámbito y visibilidad).</p></li>
<li><p>12: True si el rol puede hablar en un salón de chat de tipo auditorio.</p></li>
<li><p>13: True si el rol puede omitir las reglas de visibilidad al ver nodos.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key 

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
<td><p>Prinid</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


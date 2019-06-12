---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-25_

tblRoleType es una tabla de búsqueda estática con tipos de roles y sus conjuntos de permisos asociados.

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
<td><p>rtypeID</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de tipo de rol.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Descripción de tipo de rol. Hay cuatro roles disponibles:</p>
<ul>
<li><p>Miembro: miembro del salón de chat</p></li>
<li><p>Administrador: administrador del salón de chat</p></li>
<li><p>Voz: moderador de un salón de chat de Auditorio</p></li>
<li><p>Creador: puede crear salones de chat</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Conjunto de permisos para el rol. Los bits utilizados son:</p>
<ul>
<li><p>2: verdadero si el rol puede administrar nodos.</p></li>
<li><p>4: true si el rol puede crear nodos secundarios.</p></li>
<li><p>7: verdadero si el rol puede unirse a un salón de chat (o a salones de chat de niños de una categoría).</p></li>
<li><p>8: verdadero si el rol puede chatear en un salón de chat (o en los salones de chat de los niños de una categoría).</p></li>
<li><p>10: verdadero si el rol puede leer el historial de chats incluso cuando no está unido a un salón de chat.</p></li>
<li><p>11: verdadero si el rol puede ver el salón de chat. (Esto se ha refinado con factores como el alcance y la visibilidad).</p></li>
<li><p>12: verdadero si el rol puede chatear en un salón de chat de Auditorio.</p></li>
<li><p>13: verdadero si el rol puede omitir las reglas de visibilidad al ver los nodos.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Clave

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
<td><p>rtypeID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


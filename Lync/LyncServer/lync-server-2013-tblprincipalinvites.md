---
title: 'Lync Server 2013: tblPrincipalInvites'
description: 'Lync Server 2013: tblPrincipalInvites.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564676"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a>tblPrincipalInvites en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-25_

La tabla tblPrincipalInvites contiene invitaciones para todos los usuarios y para todos los nodos con la opción de invitación automática activada.

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
<td><p>prinID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. de la entidad de seguridad</p></td>
</tr>
<tr class="even">
<td><p>invID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Número secuencial único (por identificador de la entidad de seguridad) generado desde la tabla tblLastInviteId.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de nodo (solo salón de chat).</p></td>
</tr>
<tr class="even">
<td><p>created</p></td>
<td><p>datetime, no NULL</p></td>
<td><p>Momento de la creación.</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


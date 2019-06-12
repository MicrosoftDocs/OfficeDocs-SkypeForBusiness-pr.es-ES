---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a>tblScopePrincipal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblScopePrincipal contiene ámbitos asignados a los nodos.

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
<td><p>scopeNodeID</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de nodo al que se aplica el ámbito.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR principal.</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, not null</p></td>
<td><p>Verdadero si el tipo de ámbito es denegar; False si la opción permitir.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblNode. nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a>tblPrincipalInvites en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-25_

tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.

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
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR principal.</p></td>
</tr>
<tr class="even">
<td><p>invID</p></td>
<td><p>int, not null</p></td>
<td><p>Número secuencial único (por identificador de entidad de identidad) generado desde la tabla tblLastInviteId.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de nodo (solo salón de chat).</p></td>
</tr>
<tr class="even">
<td><p>creado</p></td>
<td><p>DateTime, not null</p></td>
<td><p>Momento de la creación.</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblNode. nodeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: tabla de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ccf7fad4b7b84746c70384269c2a903b840b6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a>Tabla user en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica a este usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Única</p></td>
<td><p>Cadena del URI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1 es un tipo de URI desconocido.</p>
<p>2 es un URI de usuario.</p>
<p>4 es un URI de conferencia.</p>
<p>8 es un URI de teléfono.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Inquilino del usuario, con referencia a la tabla Tenant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Última marca de tiempo en la que el usuario tuvo una llamada de audio de mala calidad.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


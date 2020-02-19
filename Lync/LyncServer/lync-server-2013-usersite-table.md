---
title: 'Lync Server 2013: tabla UserSite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ae68f3c5512c3f7828fe197712637e4a60e9ea5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a>Tabla UserSite en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-11-09_

La tabla UserSite es una tabla de apoyo. Cada registro representa un sitio de usuario definido en la configuración de red.


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
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica el sitio del usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Única</p></td>
<td><p>Nombre del sitio del usuario.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Referencia de la <a href="lync-server-2013-region-table.md">tabla region en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Tabla UriTypes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 916f4e6b06bc8fab484d29f7fe88170025de01d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a>Tabla UriTypes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-06-16_

La tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) supervisados en Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Identificador único asignado a un tipo de URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Descripciones de los distintos tipos de URI. Los valores permitidos son:</p>
<ul>
<li><p>1: URI del teléfono</p></li>
<li><p>0: URI de usuario</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Tabla CallType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1fa6f96d215de9ed39311e5afc84def7d71725
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="calltype-table-in-lync-server-2013"></a>Tabla CallType en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

La tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamadas.


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0--desconocido</p></li>
<li><p>1: mensajería instantánea</p></li>
<li><p>2: uso compartido de aplicaciones</p></li>
<li><p>3: audio</p></li>
<li><p>4: audio y vídeo</p></li>
<li><p>5: transferencia de archivos</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


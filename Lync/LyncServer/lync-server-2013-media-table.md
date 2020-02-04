---
title: 'Lync Server 2013: Tabla Media'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a>Tabla Media en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cada registro representa un tipo de medio usado en una sesión de punto a punto. Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio.

<div>


> [!NOTE]  
> La tabla de medios no se debe usar para calcular la duración multimedia de una sesión. Esta tabla contiene los detalles de señalización de intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los elementos multimedia solo se inician después de que la sesión acepte la sesión. La EndTime normalmente significa la hora de finalización de esta sesión.



</div>


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número único que identifica este tipo de medio. Para obtener más información, consulte la <a href="lync-server-2013-medialist-table.md">tabla medial en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Este es el tiempo que se envió una solicitud de medios, no la hora real de inicio de medios. <strong>StartTime</strong> incluye la hora de configuración de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Esta es la hora de finalización de la sesión.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


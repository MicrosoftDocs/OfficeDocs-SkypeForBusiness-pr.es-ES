---
title: 'Lync Server 2013: Tabla MediaList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92c8a0a6957eed00cf4e25f60ce2e0ff24d1fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Tabla MediaList en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-12_

La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Valores: 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Asignación estática de los valores de MediaID y Media:</p>
<ul>
<li><p>1: MENSAJERÍA INSTANTÁNEA</p></li>
<li><p>2 – Transferencia de archivos</p></li>
<li><p>3 – Asistencia remota</p></li>
<li><p>4 – Uso compartido de aplicaciones</p></li>
<li><p>5: audio</p></li>
<li><p>6-vídeo</p></li>
<li><p>7 – Invitación a la aplicación</p></li>
</ul></td>
</tr>
</tbody>
</table>


Si está intentando determinar el tipo de modalidad para los valores en LcsCDR.SessionDetailsView.MediaTypes, deberá usar el siguiente fragmento de código de JOIN. 

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>


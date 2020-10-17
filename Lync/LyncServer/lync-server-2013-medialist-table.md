---
title: 'Lync Server 2013: tabla de la MediaL'
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
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505727"
---
# <a name="medialist-table-in-lync-server-2013"></a>Tabla de MediaL en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-12_

La lista MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.


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
<td><p>Principal</p></td>
<td><p>Valores: 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Asignación estática de MediaID y valores de medios:</p>
<ul>
<li><p>1 – MI</p></li>
<li><p>2 – Transferencia de archivos</p></li>
<li><p>3 – Asistencia remota</p></li>
<li><p>4 – Uso compartido de aplicaciones</p></li>
<li><p>5: audio</p></li>
<li><p>6 – vídeo</p></li>
<li><p>7 – Invitación a la aplicación</p></li>
</ul></td>
</tr>
</tbody>
</table>


Si está intentando determinar el tipo de modalidad para los valores en LcsCDR. SessionDetailsView. MediaTypes, debe usar el siguiente fragmento de código join:

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>


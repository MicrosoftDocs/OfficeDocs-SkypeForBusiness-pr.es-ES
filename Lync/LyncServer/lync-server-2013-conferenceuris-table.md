---
title: 'Lync Server 2013: Tabla ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>Tabla ConferenceUris en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-25_

La tabla ConfereneUris es una tabla de soporte que almacena una lista de los distintos URI de conferencia que participaron en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa un URI de conferencia.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Marca de tiempo, usada internamente.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Número único que identifica este URI de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>URI de la Conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Comprobación</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Suma de comprobación de ConferenceUri. Se usa para aumentar la velocidad de las búsquedas de bases de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Tipo de URI, como conf: chat para conferencias de mensajería instantánea o conf: audio-video para conferencias de audio y vídeo. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en la tabla de 2013 de Lync Server</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: tabla ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9142be1b2d46a7d7634394970d07dfa450a22e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529177"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a>Tabla ConferenceUris en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-25_

La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.


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
<td><p>Principal</p></td>
<td><p>Marca de tiempo, interna utilizada.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica esta URI de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Uri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>URI de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Suma de comprobación</strong></p></td>
<td><p>entero</p></td>
<td></td>
<td><p>Suma de comprobación de ConferenceUri. Se utiliza para acelerar las búsquedas en bases de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de URI, como por ejemplo conf:chat para conferencia de mensajería instantánea, o conf:audio-video para conferencia A/V. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en la tabla de Lync Server 2013</a> para obtener más información.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


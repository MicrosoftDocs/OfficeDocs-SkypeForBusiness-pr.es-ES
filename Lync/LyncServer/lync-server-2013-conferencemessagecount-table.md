---
title: 'Lync Server 2013: tabla ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae806fc50fb0d4c4936fb6fbf6f879f4d4fc2ce4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529337"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a>Tabla ConferenceMessageCount en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cada registro de esta tabla representa un usuario en una conferencia de mi y incluye el número de mensajes enviados por el usuario. Cada conferencia se representa mediante varios registros en esta tabla; un registro para cada usuario.


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
<td><p>Principal, Externa</p></td>
<td><p>Hora de la instancia de conferencia. Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una instancia de conferencia. Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número de identificación de la instancia de conferencia. Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia. Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Número único que identifica a este usuario, al que se hace referencia en la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>El número de mensajes enviados por este usuario durante esta conferencia.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Tabla ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a>Tabla ConferenceMessageCount en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por el usuario. Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.


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
<td><p>Hora de la instancia de conferencia. Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación para identificar la instancia de la Conferencia. Se usa junto con <strong>SessionIdTime</strong> para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Iddeusuario</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Número único que identifica a este usuario, al que se hace referencia en la <a href="lync-server-2013-users-table.md">tabla usuarios de Lync Server 2013</a>.</p></td>
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


---
title: 'Lync Server 2013: vista de ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5708da08376a4a2bd2564bb3c6809bcfc71aeabe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529307"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a>Vista ConferenceMessageCount en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La vista ConferenceMessageCount contiene todas las columnas de la <A href="lync-server-2013-conferencesessiondetails-view.md">vista ConferenceSessionDetails en Lync Server 2013</A> , además de las columnas que se enumeran a continuación.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario que envió el mensaje.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario que envió los mensajes. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>identificador</p></td>
<td><p>Inquilino del usuario que envió los mensajes. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>Número de mensajes que envió el usuario durante la sesión de conferencia.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


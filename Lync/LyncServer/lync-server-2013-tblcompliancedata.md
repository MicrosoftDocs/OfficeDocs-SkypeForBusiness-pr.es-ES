---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 162676768c3cb358db436dc2ba40ce378a31ba6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509457"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a>tblComplianceData en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.

### <a name="columns"></a>Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Id. del evento.</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, no NULL</p></td>
<td><p>Hora de inserción (puede estar lejos en el futuro para cmplType=9 porque la entrada solo es un marcador de posición en ese caso).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, no NULL</p></td>
<td><p>Tipo de evento de cumplimiento:</p>
<ul>
<li><p>1: Chat</p></li>
<li><p>2: Backchat</p></li>
<li><p>3: Descarga de archivos</p></li>
<li><p>4: Carga de archivos</p></li>
<li><p>9: Transferencia de archivo provisional</p></li>
<li><p>10: Eliminación de chats (con reemplazo)</p></li>
<li><p>11: Depuración de chats</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo del evento.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>Identificador uniforme de recursos (URI) del canal.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>BIGINT</p></td>
<td><p>Identificador de chat (correspondiente a la tabla tblChat.chatId).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de entidad de seguridad del póster (correspondiente a la tabla tblPrincipal.prinID).</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>URI del usuario.</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (máx.)</p></td>
<td><p>Mensaje (la codificación depende de cmplType).</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key 

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


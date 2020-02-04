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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>tblComplianceData en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.

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
<td><p>BIGINT, not null</p></td>
<td><p>IDENTIFICADOR de evento.</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, not null</p></td>
<td><p>Hora de inserción (puede ser muy próxima para cmplType = 9 porque la entrada es solo un marcador de posición en ese caso).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, not null</p></td>
<td><p>Tipo de evento de conformidad:</p>
<ul>
<li><p>1: chatear</p></li>
<li><p>2: chatear</p></li>
<li><p>3: descarga de archivos</p></li>
<li><p>4: carga de archivos</p></li>
<li><p>9: transferencia provisional de archivos</p></li>
<li><p>10: eliminación de chat (con Replace)</p></li>
<li><p>11: purgado de chat</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Marca de tiempo del evento.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255), not null</p></td>
<td><p>Identificador uniforme de recursos (URI) del canal.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>BIGINT</p></td>
<td><p>IDENTIFICADOR de chat (corresponde a la tabla tblChat. chatId).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR principal del póster (correspondiente a la tabla tblPrincipal. prinID).</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255), not null</p></td>
<td><p>URI de usuario.</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (Max)</p></td>
<td><p>Mensaje (la codificación depende de cmplType).</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Clave

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


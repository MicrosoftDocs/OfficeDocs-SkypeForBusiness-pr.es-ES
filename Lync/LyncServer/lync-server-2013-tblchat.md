---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f3879924b37fa535973116af599f4713c58a207
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblChat contiene todos los mensajes instantáneos.

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
<td><p>channelId</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de nodo.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Número secuencial único (por identificador de nodo) que define el pedido del salón de chat, generado por la tabla tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Marca de tiempo del mensaje de la conversación.</p></td>
</tr>
<tr class="even">
<td><p>Iddeusuario</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR principal del póster.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, not null</p></td>
<td><p>True si el mensaje es un mensaje de alerta. Falso si no lo es.</p></td>
</tr>
<tr class="even">
<td><p>objetos</p></td>
<td><p>nvarchar (Max), not null</p></td>
<td><p>Contenido de la conversación (versión de texto sin formato). El contenido suele estar en texto sin formato, con las siguientes excepciones:</p>
<ul>
<li><p>Los archivos se representan como ma-FileLink: links.</p></li>
<li><p>Los vínculos se representan como un elemento HTML (aunque el tipo de contenido no se puede considerar HTML).</p></li>
<li><p>Los casos se codifican como un formato "[artículo]....".</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>enriquecido</p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Contenido de la conversación (la versión RTF). Puede ser null si el cliente no lo proporciona.</p></td>
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
<td><p>&lt;channelID, conversado&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


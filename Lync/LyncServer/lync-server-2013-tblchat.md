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
ms.openlocfilehash: 0a3f0672fc3cf41113c0cfa206890848f8ccbde0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblChat contiene todos los mensajes de chat.

### <a name="columns"></a>Columns

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
<td><p>int, no NULL</p></td>
<td><p>Identificador del nodo.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Número secuencial único (por identificador de nodo) que define el orden de los salones de chat, generado por la tabla tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo del mensaje de chat.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador principal de la persona que publicó el mensaje.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si el mensaje es de alerta. False si no lo es.</p></td>
</tr>
<tr class="even">
<td><p>contenido</p></td>
<td><p>nvarchar (max), no NULL</p></td>
<td><p>Contenido del chat (versión de texto sin formato). El contenido suele ser texto sin formato con las siguientes excepciones:</p>
<ul>
<li><p>Los archivos se representan como vínculos ma-filelink:.</p></li>
<li><p>Los vínculos se representan como un elemento HTML (aunque el tipo de contenido no puede considerarse como HTML).</p></li>
<li><p>Las historias se codifican como un formato tipo "[STORY]...".</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>txt</p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Contenido del chat (versión RTF). Puede ser un valor NULL si el cliente no lo proporciona.</p></td>
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
<td><p>&lt;channelID, chat&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


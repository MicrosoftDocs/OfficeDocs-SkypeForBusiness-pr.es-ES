---
title: 'Lync Server 2013: tblChat'
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48276443
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblChat en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblChat contiene todos los mensajes de chat.

### Columnas

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
<td><p>content</p></td>
<td><p>nvarchar (max), no NULL</p></td>
<td><p>Contenido del chat (versión de texto sin formato). El contenido suele ser texto sin formato con las siguientes excepciones:</p>
<ul>
<li><p>Los archivos se representan como vínculos ma-filelink:.</p></li>
<li><p>Los vínculos se representan como un elemento HTML (aunque el tipo de contenido no puede considerarse como HTML).</p></li>
<li><p>Las historias se codifican como un formato tipo &quot;[STORY]...&quot;.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar(max)</p></td>
<td><p>Contenido del chat (versión RTF). Puede ser un valor NULL si el cliente no lo proporciona.</p></td>
</tr>
</tbody>
</table>


### Tecla

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
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


---
title: 'Lync Server 2013: tblComplianceData'
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48274308
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceData en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.

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
<td><p>cmplEventID</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Id. del evento</p></td>
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
<td><p>bigint</p></td>
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
<td><p>nvarchar(max)</p></td>
<td><p>Mensaje (la codificación depende de cmplType).</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


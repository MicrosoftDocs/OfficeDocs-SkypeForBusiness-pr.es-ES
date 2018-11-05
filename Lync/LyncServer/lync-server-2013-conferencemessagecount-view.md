---
title: Vista ConferenceMessageCount
TOCTitle: Vista ConferenceMessageCount
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49889373
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista ConferenceMessageCount

 

_**Última modificación del tema:** 2015-03-09_

La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia. Esta vista se presentó por primera vez en Microsoft Lync Server 2013.


> [!NOTE]
> La vista ConferenceMessageCount contiene todas las columnas de la <A href="lync-server-2013-conferencesessiondetails-view.md">Vista ConferenceSessionDetails</A> además de las siguientes columnas.




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
<td><p>nvarchar(450)</p></td>
<td><p>URI del usuario que envió el mensaje.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que envió los mensajes. Consulte la <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Inquilino del usuario que envió los mensajes. Consulte la <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>Número de mensajes que envió el usuario durante la sesión de conferencia.</p></td>
</tr>
</tbody>
</table>


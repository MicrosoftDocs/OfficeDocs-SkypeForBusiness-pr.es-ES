---
title: Vista de conferencias
TOCTitle: Vista de conferencias
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49889661
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista de conferencias

 

_**Última modificación del tema:** 2015-03-09_

La vista Conferencias almacena información sobre las conferencias. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la solicitud de sesión. Se usa junto con SessionIdSeq para identificar una sesión de forma exclusiva. Consulte <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificador de la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Consulte <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo del URI de la conferencia. Consulte <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Se usa en conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri, pero un ConfInstance distinto.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de inicio de la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del usuario que organizó la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OrganizerType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que organizó la conferencia. Consulte <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario que organizó la conferencia. Consulte <a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre de dominio completo del grupo que hospedó la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Máscara de bits que contiene atributos de la conferencia. Los valores posibles son:</p>
<p>0X01: transacción sintética</p></td>
</tr>
</tbody>
</table>


---
title: 'Lync Server 2013: tblComplianceParticipant'
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48275412
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceParticipant en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>Identificador uniforme de recursos (URI) del canal.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad del participante (correspondiente a la tabla tblPrincipal.prinID).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo del evento participante.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>Nulo si el participante aún está participando. La marca de tiempo del canal que abandona el evento si no es nulo.</p>
<p>Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>URI del usuario.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>Identidad del servidor (como en la tabla tblServerIdentity.serverID).</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>Sesión del servidor. Es un número aleatorio que se genera cada vez que se inicia un servicio de chat. Sirve para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</p></td>
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
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


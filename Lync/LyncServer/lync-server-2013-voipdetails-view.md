---
title: Vista VoIPDetails
TOCTitle: Vista VoIPDetails
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49888896
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista VoIPDetails

 

_**Última modificación del tema:** 2015-03-09_

La vista VoIPDetails almacena información acerca de sesiones de punto a punto, donde al menos un usuario es un usuario VoIP. Esta vista se introdujo en Microsoft Lync Server 2013.


> [!NOTE]
> La vista VoIPDetails contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">Vista SessionDetails</A> además de las columnas mostradas a continuación.




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
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de teléfono del usuario que ha iniciado la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de teléfono del usuario que se ha unido a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de teléfono del usuario que ha desconectado la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que ha desconectado la sesión. Vea la <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Inquilino del usuario que ha desconectado la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de teléfono del usuario que ha desconectado la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediación usado por el usuario que ha iniciado la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediación usado por el usuario que se ha unido a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Puerta de enlace usada por el usuario que ha iniciado la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Puerta de enlace usada por el usuario que ha iniciado la sesión.</p></td>
</tr>
</tbody>
</table>


---
title: 'Lync Server 2013: Tabla VoipDetails'
TOCTitle: Tabla VoipDetails
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48275702
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla VoipDetails en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa una llamada entre dos partes en la que al menos una de ellas es un usuario de VoIP.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en combinación con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> como identificación única de una sesión. Para más información, vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p><strong>PhoneId</strong> del autor de la llamada. Referencia a la <a href="lync-server-2013-phones-table.md">Tabla Phones en Lync Server 2013</a>. Si no es NULL y <strong>FromGatewayId</strong> tampoco es NULL, el autor de la llamada era un usuario de RTC.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p><strong>PhoneId</strong> del destinatario de la llamada. Vea <a href="lync-server-2013-phones-table.md">Tabla Phones en Lync Server 2013</a> para obtener más información. Si no es NULL y <strong>ToGatewayId</strong> tampoco es NULL, el destinatario de la llamada era un usuario de RTC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor de mediación del que procede la llamada. Referencia a la <a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor de mediación al que se dirige la llamada. Referencia a la <a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Puerta de enlace de la que procede la llamada. Vea <a href="lync-server-2013-gateways-table.md">Tabla Gateways en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Puerta de enlace a la que se dirige la llamada. Vea <a href="lync-server-2013-gateways-table.md">Tabla Gateways en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI del usuario que desconectó la llamada, si es que dicho usuario posee un URI. Referencia a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del teléfono del que se desconectó la llamada. Referencia a la <a href="lync-server-2013-phones-table.md">Tabla Phones en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


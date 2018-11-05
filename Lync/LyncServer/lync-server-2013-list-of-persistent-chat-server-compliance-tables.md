---
title: "Lync Server 2013: Lista de tablas de cumplimiento del servidor de chat persistente"
TOCTitle: Lista de tablas de cumplimiento del servidor de chat persistente
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48275898
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El esquema de la base de datos de cumplimiento de Chat persistente consiste en las siguientes tablas.

## Lista de tablas de cumplimiento de Servidor de chat persistente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabla</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData en Lync Server 2013</a></p></td>
<td><p>Contiene los eventos de cumplimiento que aún no fueron procesados por el adaptador configurado.</p>
<p>Esta tabla incluye los eventos relacionados con Chat persistente, como los mensajes de chat y las descargas de archivos. (Los eventos participantes son seguidos por la tabla tblComplianceParticipant).</p>
<p>(Los servidores que procesaron los eventos en esta tabla se enumeran en la tabla tblComplianceFanout).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout en Lync Server 2013</a></p></td>
<td><p>Contiene los servidores que procesaron un evento de cumplimiento. Esta tabla está fuertemente vinculada con la tabla tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant en Lync Server 2013</a></p></td>
<td><p>Contiene los participantes actuales por servicio de chat y por servidor. Se mantiene basado en eventos de cumplimiento de unión y participación recibidos por el servicio de Chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState en Lync Server 2013</a></p></td>
<td><p>Contiene información de estado de cumplimiento de todo el grupo.</p></td>
</tr>
</tbody>
</table>


---
title: Tabla MonitoredUserSiteLink
TOCTitle: Tabla MonitoredUserSiteLink
ms:assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398233(v=OCS.15)
ms:contentKeyID: 48274550
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla MonitoredUserSiteLink

 

_**Última modificación del tema:** 2015-03-09_

La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserSite1Key</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-usersite-table.md">Tabla UserSite en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSite2Key</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Referencia de la <a href="lync-server-2013-usersite-table.md">Tabla UserSite en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


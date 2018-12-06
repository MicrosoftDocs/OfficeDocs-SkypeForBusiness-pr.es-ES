---
title: 'Lync Server 2013: tblActivePeers'
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48276416
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblActivePeers en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.

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
<td><p>aplServerID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador del servidor que publicó la entrada.</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador del punto al que está conectado el servidor que realizó la publicación.</p></td>
</tr>
</tbody>
</table>


### Teclas

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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</p></td>
</tr>
</tbody>
</table>


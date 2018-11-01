---
title: 'Lync Server 2013: tblScopePrincipal'
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48275044
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblScopePrincipal en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblScopePrincipal contiene ámbitos asignados a nodos.

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
<td><p>scopeNodeID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. de nodo al que se aplica el ámbito.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si el tipo de ámbito es Denegar; False si es Permitir.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad que actualizó esta entrada por última vez.</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>Clave externa con búsqueda en la tabla RoleType.rtypeID.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>Clave externa con búsqueda en la tabla Node.nodeID.</p></td>
</tr>
</tbody>
</table>


---
title: 'Lync Server 2013: tblLastInviteId'
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48274669
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblLastInviteId en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.

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
<td><p>prinID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad</p></td>
</tr>
<tr class="even">
<td><p>lastInviteID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de invitación usado por última vez.</p></td>
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
<td><p>prinID</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clave externa con búsqueda en la tabla Node.nodeID.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[tblPrincipalInvites en Lync Server 2013](lync-server-2013-tblprincipalinvites.md)


---
title: 'Lync Server 2013: tblPrincipalInvites'
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48275278
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalInvites en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblPrincipalInvites contiene invitaciones para todos los usuarios y para todos los nodos con la opción de invitación automática activada.

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
<td><p>invID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Número secuencial único (por identificador de la entidad de seguridad) generado desde la tabla tblLastInviteId.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de nodo (solo salón de chat).</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>datetime, no NULL</p></td>
<td><p>Momento de la creación.</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>


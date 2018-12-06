---
title: 'Lync Server 2013: tblLastChatId'
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48274559
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblLastChatId en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblLastChatId contiene el último id. de chat generado (y usado en la tabla tblChat) para cada usuario.

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
<td><p>nodeID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de nodo (tipo de salón de chat únicamente).</p></td>
</tr>
<tr class="even">
<td><p>lastChatID</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Identificador de chat usado por última vez.</p></td>
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
<td><p>&lt;nodeID, lastChatID&gt;</p></td>
<td><p>Clave principal (nodeID es suficiente para el procesamiento).</p></td>
</tr>
<tr class="even">
<td><p>nodeID</p></td>
<td><p>Clave externa con búsqueda en la tabla RoleType.rtypeID.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[tblChat en Lync Server 2013](lync-server-2013-tblchat.md)


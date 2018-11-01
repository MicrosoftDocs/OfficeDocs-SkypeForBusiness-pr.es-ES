---
title: 'Lync Server 2013: tblComplianceFanout'
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48277204
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceFanout en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.

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
<td><p>fanoutEventID</p></td>
<td><p>int</p></td>
<td><p>Id. del evento</p></td>
</tr>
<tr class="even">
<td><p>fanoutServerID</p></td>
<td><p>int</p></td>
<td><p>Identidad del servidor (correspondiente a la tabla ServerIdentity.serverID).</p></td>
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
<td><p>fanoutEventID</p></td>
<td><p>Clave externa con búsqueda en la tabla ComplianceData.cmplEventID.</p></td>
</tr>
</tbody>
</table>


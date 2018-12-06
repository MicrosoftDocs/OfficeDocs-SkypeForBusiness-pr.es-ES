---
title: 'Lync Server 2013: tblConfig'
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48275693
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblConfig en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblConfig contiene algunos valores de configuración no admitidos en el Servidor de chat persistente, todo en una fila.

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
<td><p>configLabel</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>Contiene &quot;grupo&quot;.</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar(max)</p></td>
<td><p>Contenido de la configuración.</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID, no NULL</p></td>
<td><p>Identificador único de la instancia de base de datos.</p></td>
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
<td><p>configLabel</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


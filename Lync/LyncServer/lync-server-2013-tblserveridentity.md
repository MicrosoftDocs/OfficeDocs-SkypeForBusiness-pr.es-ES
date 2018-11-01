---
title: 'Lync Server 2013: tblServerIdentity'
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48275275
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblServerIdentity en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblServerIdentity contiene los servidores de chat activos del Grupo de servidores de chat persistente.

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
<td><p>serverID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. de servidor. Corresponde al id. de instancia de Almacén de administración central.</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Dirección de servidor con la dirección de Windows Communication Foundation.</p></td>
</tr>
<tr class="odd">
<td><p>serverLastPingTime</p></td>
<td><p>datetime</p></td>
<td><p>La última hora en la que el servidor de canal actualizó esta fila para probar que está ejecutándose.</p></td>
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
<td><p>serverID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


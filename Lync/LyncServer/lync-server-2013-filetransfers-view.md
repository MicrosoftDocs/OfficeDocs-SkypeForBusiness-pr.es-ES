---
title: Vista FileTransfers
TOCTitle: Vista FileTransfers
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49889772
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista FileTransfers

 

_**Última modificación del tema:** 2015-03-09_

La vista FileTranfer almacena información sobre sesiones de transferencia de archivos punto a punto. Esta vista se introdujo en Microsoft Lync Server 2013.


> [!NOTE]
> La vista FileTransfers contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">Vista SessionDetails</A> además de las columnas enumeradas a continuación.




<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del archivo transferido.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificador único para distinguir entre las transferencias de archivos en las que participa el mismo nombre de archivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aceptar</strong></p></td>
<td><p>bit</p></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rechazar</strong></p></td>
<td><p>bit</p></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancelar</strong></p></td>
<td><p>bit</p></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</p></td>
</tr>
</tbody>
</table>


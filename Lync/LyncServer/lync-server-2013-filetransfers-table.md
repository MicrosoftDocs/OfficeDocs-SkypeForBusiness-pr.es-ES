---
title: 'Lync Server 2013: Tabla FileTransfers'
TOCTitle: Tabla FileTransfers
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48275246
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla FileTransfers en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa una sesión de transferencia de archivos.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en combinación con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> como identificación única de una sesión. Para más información, vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre de archivo</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Nombre del archivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>Identificador único para distinguir entre las transferencias de archivos en las que participa el mismo nombre de archivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Principal</p></td>
<td><p>Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aceptar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rechazar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancelar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</p></td>
</tr>
</tbody>
</table>


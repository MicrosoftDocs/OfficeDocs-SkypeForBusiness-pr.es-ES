---
title: 'Lync Server 2013: tabla FileTransfers'
description: 'Lync Server 2013: tabla FileTransfers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573366"
---
# <a name="filetransfers-table-in-lync-server-2013"></a>Tabla FileTransfers en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

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
<td><p>Principal, Exterior</p></td>
<td><p>Hora de la solicitud de sesión. Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal, Exterior</p></td>
<td><p>Número del identificador para identificar la sesión. Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre de archivo</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Nombre del archivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Identificador único para distinguir entre las transferencias de archivos con el mismo nombre de archivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Principal</p></td>
<td><p>Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


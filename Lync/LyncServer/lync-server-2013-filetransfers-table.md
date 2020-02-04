---
title: 'Lync Server 2013: Tabla FileTransfers'
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
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Tabla FileTransfers en Lync Server 2013

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
<td><p>Principal, extranjero</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre de archivo</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Nombre del archivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Identificador único para distinguir entre transferencias de archivos que impliquen el mismo nombre de archivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ésta</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Primary</p></td>
<td><p>Se usa para identificar cada mensaje de seguimiento como asociado con este.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aceptable</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puede ser TRUE o NULL. Si es verdadero, rechazar y cancelar será nulo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rechace</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puede ser TRUE o NULL. Si es verdadero, aceptar y cancelar será nulo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancelar.</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puede ser TRUE o NULL. Si es verdadero, aceptar y rechazar serán NULOs.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


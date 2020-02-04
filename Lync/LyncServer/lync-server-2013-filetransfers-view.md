---
title: 'Lync Server 2013: vista FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Vista FileTransfers en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos de punto a punto. Esta vista se presentó en Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La vista FileTransfers contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">vista SessionDetails de Lync Server 2013</A> , además de las columnas que figuran a continuación.



</div>


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
<td><p><strong>Ésta</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Se usa para identificar cada mensaje de seguimiento como asociado con este.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único para distinguir entre transferencias de archivos que impliquen el mismo nombre de archivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aceptable</strong></p></td>
<td><p>bit</p></td>
<td><p>Puede ser TRUE o NULL. Si es verdadero, rechazar y cancelar será nulo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rechace</strong></p></td>
<td><p>bit</p></td>
<td><p>Puede ser TRUE o NULL. Si es verdadero, aceptar y cancelar será nulo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancelar.</strong></p></td>
<td><p>bit</p></td>
<td><p>Puede ser TRUE o NULL. Si es verdadero, aceptar y rechazar serán NULOs.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


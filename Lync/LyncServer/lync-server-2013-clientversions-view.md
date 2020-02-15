---
title: 'Lync Server 2013: vista de ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a7e62fbf56d270c6d2d0c65415dc28dd30e4449
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a>Vista ClientVersions en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Puede haber varios registros para determinadas columnas.



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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Número único de identificación de esta versión y este tipo de cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Representa el agente de usuario.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Tipo de cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría a la que pertenece el cliente. Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a ClientCategory CAA.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


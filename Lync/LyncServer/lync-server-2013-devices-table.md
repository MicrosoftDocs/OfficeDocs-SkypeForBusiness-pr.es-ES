---
title: 'Lync Server 2013: Tabla Devices'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381b03fc5680276a64fc327f423f74c6773c2ed3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a>Tabla Devices en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-25_

La tabla dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).


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
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Número único que identifica esta versión de hardware.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Fabricante de este dispositivo. Para obtener más información, consulte la <a href="lync-server-2013-manufacturers-table.md">tabla de fabricantes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Versión de hardware de este dispositivo. Para obtener más información, consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>BIGINT</p></td>
<td></td>
<td><p>Dirección MAC</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


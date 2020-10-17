---
title: 'Lync Server 2013: tabla de extremos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a71e59b6cf9b4143a5b984cc7b169279aa2cb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533327"
---
# <a name="endpoint-table-in-lync-server-2013"></a>Tabla Endpoint en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

La tabla de extremos es una tabla de apoyo que almacena información sobre los puntos de conexión que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un punto de conexión.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EndpointKey</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este extremo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Única</p></td>
<td><p>Nombre del extremo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MacOS</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p> </p></td>
<td><p>Sistema operativo (SO) del extremo.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar(128</p></td>
<td></td>
<td><p>Nombre de la CPU del extremo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Número de núcleos de CPU del extremo.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>entero</p></td>
<td></td>
<td><p>Velocidad del procesador de la CPU del extremo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Marca de bits que indica si el sistema se está ejecutando en un entorno virtualizado:</p>
<ul>
<li><p>0x0000 – ninguno</p></li>
<li><p>0x0001: HyperV</p></li>
<li><p>0x0002: VMWare</p></li>
<li><p>0x0004: Virtual PC</p></li>
<li><p>0x0008 – equipo de Xen</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


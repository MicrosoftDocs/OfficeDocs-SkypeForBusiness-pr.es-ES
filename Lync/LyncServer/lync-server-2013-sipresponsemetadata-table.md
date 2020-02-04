---
title: 'Lync Server 2013: tabla SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Tabla SIPResponseMetaData en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP, así como la clasificación y la definición de cada uno de esos códigos. Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta la solicitud.

Esta tabla se introdujo en Microsoft Lync Server 2013.


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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Valor numérico que representa el código de respuesta SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Las</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Clasificación general para el código de respuesta. Las clasificaciones incluyen:</p>
<ul>
<li><p>1: respuestas informativas</p></li>
<li><p>2: respuestas correctas</p></li>
<li><p>3: respuestas de redireccionamiento</p></li>
<li><p>4-respuestas de error del cliente</p></li>
<li><p>5--respuestas de error de servidor</p></li>
<li><p>6: respuesta de error global</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Descripción</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</p>
<p>La llamada se está reenviando</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


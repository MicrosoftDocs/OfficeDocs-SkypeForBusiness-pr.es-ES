---
title: 'Lync Server 2013: tabla SIPResponseMetaData'
description: 'Lync Server 2013: tabla SIPResponseMetaData.'
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
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558986"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Tabla SIPResponseMetaData en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y definición de cada uno de estos códigos. Estos códigos se generan como respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza responderla.

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
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Valor numérico que representa el código de respuesta SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>entero</p></td>
<td></td>
<td><p>Clasificación general para el código de respuesta. Las clasificaciones incluyen:</p>
<ul>
<li><p>1 – Respuestas de tipo informativo</p></li>
<li><p>2 – Respuestas correctas</p></li>
<li><p>3 – Respuestas de redirección</p></li>
<li><p>4 – Respuestas de error de cliente</p></li>
<li><p>5--respuestas de error de servidor</p></li>
<li><p>6 – Respuesta de error global</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Descripción</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</p>
<p>Se está desviando la llamada</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


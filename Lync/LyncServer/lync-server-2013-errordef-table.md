---
title: 'Lync Server 2013: tabla ErrorDef'
description: 'Lync Server 2013: tabla ErrorDef.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542756"
---
# <a name="errordef-table-in-lync-server-2013"></a>Tabla ErrorDef en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-25_

La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Número de identificador único que identifica este tipo de error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>entero</p></td>
<td><p> </p></td>
<td><p>Código de respuesta SIP estándar asociado a este error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>entero</p></td>
<td><p> </p></td>
<td><p>IDENTIFICADOR de diagnóstico de Microsoft.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de la llamada. Consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary (33)</p></td>
<td><p> </p></td>
<td><p>Tipo de solicitud que ha generado errores.</p>
<p>Estos datos pueden convertirse en formato de texto con esta sintaxis:</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary (257)</p></td>
<td><p> </p></td>
<td><p>Tipo de contenido de la solicitud que ha generado errores.</p>
<p>Estos datos pueden convertirse a formato de texto mediante el uso de esta sintaxis:</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


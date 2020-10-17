---
title: 'Lync Server 2013: tabla UserAgent'
description: 'Lync Server 2013: tabla UserAgent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b701d8384313d0267dd566e0c32242f6cc077472
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558896"
---
# <a name="useragent-table-in-lync-server-2013"></a>Tabla UserAgent en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-25_

La tabla UserAgent es una tabla de apoyo que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario


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
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica a este agente de usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Única</p></td>
<td><p>Cadena de agente de usuario.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 es el servidor de mediación.</p>
<p>2 es un servidor de conferencia A/V.</p>
<p>4 es Lync.</p>
<p>8 es teléfono IP.</p>
<p>16 es consola de Live Meeting.</p>
<p>32 es la herramienta de validación de implementación (DVT).</p>
<p>64 es Lync en equipos Macintosh.</p>
<p>128 es el operador de Office Communications Server 2007 R2.</p>
<p>256 es el servicio de anuncio de conferencia.</p>
<p>512 es operador automático de conferencia.</p>
<p>1024 es una aplicación de grupo de respuesta.</p>
<p>2048 está fuera del control de voz.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


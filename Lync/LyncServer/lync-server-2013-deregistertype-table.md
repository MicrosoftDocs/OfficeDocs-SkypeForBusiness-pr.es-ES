---
title: 'Lync Server 2013: tabla DeRegisterType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 915a5d0a2c5c4a5f38063b56dc133d2558aa65ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a>Tabla DeRegisterType en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de anulación del registro de usuario, como ‘iniciado por cliente’, ‘registro expirado’ o ‘respuesta de cliente interrumpida’.


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0 -- Desconocido</p></li>
<li><p>1 -- Anulación del registro iniciada por el cliente</p></li>
<li><p>2 -- Registro expirado</p></li>
<li><p>3 – Cliente bloqueado</p></li>
<li><p>4 -- Atributos de usuario modificados</p></li>
<li><p>5 – Registrador preferido modificado</p></li>
<li><p>6 -- Cliente heredado en modo de supervivencia</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: tabla categoría'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a80ab2b570a067a1157e999d056c47d514ec4ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a>Tabla categoría en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-20_

La tabla categoría contiene el nombre descriptivo para cada clasificación de diagnóstico de Microsoft Lync Server 2013. De forma predeterminada, Lync Server 2013 usa las siguientes clasificaciones:

  - 0 -- Éxito

  - 1--error esperado

  - 2 – Error inesperado

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
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único de la clasificación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Valor y nombre descriptivo asignados a la clasificación. Los valores permitidos son:</p>
<ul>
<li><p>0 -- Éxito</p></li>
<li><p>1--error esperado</p></li>
<li><p>2 – Error inesperado</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


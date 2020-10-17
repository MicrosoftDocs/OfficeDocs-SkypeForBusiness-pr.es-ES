---
title: 'Lync Server 2013: tblEnumAttribute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b015d1148c3c820c27cdbe48e191bd09d2f55e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509357"
---
# <a name="tblenumattribute-in-lync-server-2013"></a>tblEnumAttribute en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.

### <a name="columns"></a>Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>attributeID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Identificador del atributo.</p></td>
</tr>
<tr class="even">
<td><p>attributeName</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Nombre del atributo.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key 

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>attributeID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>Valores de tabla

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>attributeID</th>
<th>attributeName</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Notoriedad.</p></td>
</tr>
<tr class="even">
<td><p>segundo</p></td>
<td><p>Comportamiento.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Consulte también


[tblNode en Lync Server 2013](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


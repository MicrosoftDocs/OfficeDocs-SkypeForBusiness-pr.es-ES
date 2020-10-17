---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509327"
---
# <a name="tblenumvalue-in-lync-server-2013"></a>tblEnumValue en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla node.

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
<td><p>valueID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>IDENTIFICADOR del valor.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Identificador del atributo.</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Nombre del valor.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

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
<td><p>valueID</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblEnumAttribute. attributeID.</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>Valores de tabla

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>segundo</p></td>
<td><p>1</p></td>
<td><p>empresa</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>ámbito</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>segundo</p></td>
<td><p>normalmente</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>segundo</p></td>
<td><p>Auditorio</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>1</p></td>
<td><p>pendiente</p></td>
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


---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef0ee11cd780037410ea1d7e0d94c83e139d8418
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523777"
---
# <a name="tblpreference-in-lync-server-2013"></a>tblPreference en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

tblPreference contiene las preferencias de cliente de los usuarios. Esto suele ser usado por los clientes anteriores a Lync 2013.

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
<td><p>prefLabel</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>Etiqueta con un formato como: &lt; URI del SIP del usuario &gt; | nombre de usuario. &lt; conjunto de preferencias &gt; .</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Número secuencial (por etiqueta) para el control de versiones.</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (máx.)</p></td>
<td><p>Contenido codificado.</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad que ha actualizado la preferencia.</p></td>
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
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


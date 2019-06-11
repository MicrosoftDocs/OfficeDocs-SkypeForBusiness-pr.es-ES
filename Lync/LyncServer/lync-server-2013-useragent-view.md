---
title: 'Lync Server 2013: vista UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a>Vista UserAgent en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La vista UserAgent almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>Número único que identifica a este agente de usuario.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario.</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario. Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_ 1.0 pertenece a la UACategory CAA.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


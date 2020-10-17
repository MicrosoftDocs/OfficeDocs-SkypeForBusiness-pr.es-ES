---
title: 'Lync Server 2013: vista de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0e6cd8658278a8d7798153698355f5a73f2952b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516157"
---
# <a name="media-view-in-lync-server-2013"></a>Vista de elementos multimedia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios. Esta vista se introdujo en Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La vista Medios no debería utilizarse para calcular la duración de medios de una sesión. Esta vista contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que se acepta la sesión.



</div>

La vista de elementos multimedia contiene todas las columnas de la [vista SessionDetails en Lync Server 2013](lync-server-2013-sessiondetails-view.md) , además de las que se enumeran a continuación.


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
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de medio. Consulte la <a href="lync-server-2013-medialist-table.md">tabla de medial en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que se envió la solicitud de medios.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la sesión.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: vista multimedia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a>Vista de elementos multimedia de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista multimedia almacena información sobre un tipo de medio usado en una sesión de punto a punto. Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio. Esta vista se presentó en Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La vista de elementos multimedia no debe usarse para calcular la duración multimedia de una sesión. Esta vista contiene los detalles de señalización de intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los medios solo se inician una vez que se acepta la sesión.



</div>

La vista contenido multimedia contiene todas las columnas de la [vista SessionDetails de Lync Server 2013](lync-server-2013-sessiondetails-view.md) , además de las que se muestran a continuación.


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
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de medio. Para obtener más información, consulte la <a href="lync-server-2013-medialist-table.md">tabla medial en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora en que se envió una solicitud de medios.</p></td>
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


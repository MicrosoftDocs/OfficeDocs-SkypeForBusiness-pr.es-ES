---
title: 'Lync Server 2013: llamadas salientes'
description: 'Lync Server 2013: llamadas salientes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14f19dec35a6da47a2ddd62657d5d087a854f16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546856"
---
# <a name="outgoing-calls-in-lync-server-2013"></a>Llamadas salientes en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento de llamadas salientes de usuarios habilitados para el enrutamiento Location-Based se ve afectado por la ubicación de red del extremo del usuario. En la tabla siguiente se muestra cómo el enrutamiento de Location-Based afecta al enrutamiento de las llamadas salientes en función de la ubicación del extremo del autor de la llamada.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>Autor de la llamada que realiza una llamada saliente a la RTC

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Extremo de usuario ubicado en un sitio de red habilitado para el enrutamiento Location-Based</th>
<th>Extremo de usuario ubicado en un sitio de red desconocido o no habilitado para el enrutamiento Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorización de llamadas salientes</p></td>
<td><p>La llamada se autoriza en función de la Directiva de voz del usuario</p></td>
<td><p>La llamada se autoriza en función de la Directiva de voz del usuario</p></td>
</tr>
<tr class="even">
<td><p>Enrutamiento de llamadas salientes</p></td>
<td><p>La llamada se enruta según la Directiva de enrutamiento de voz del sitio de red</p></td>
<td><p>La llamada se redirige según la Directiva de voz del usuario y solo a través de troncos no habilitados para Location-Based enrutamiento (si está disponible)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Consulte también


[Escenarios para Location-Based el enrutamiento en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


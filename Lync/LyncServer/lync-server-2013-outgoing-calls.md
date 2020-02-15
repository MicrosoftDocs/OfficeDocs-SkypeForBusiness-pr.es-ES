---
title: 'Lync Server 2013: llamadas salientes'
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
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Llamadas salientes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento de llamadas salientes de usuarios habilitados para el enrutamiento basado en ubicación se ve afectado por la ubicación de red del extremo del usuario. En la tabla siguiente se muestra cómo el enrutamiento basado en ubicación afecta al enrutamiento de las llamadas salientes en función de la ubicación del extremo del autor de la llamada.

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
<th>Extremo de usuario ubicado en un sitio de red habilitado para el enrutamiento basado en ubicación</th>
<th>Extremo de usuario ubicado en un sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación</th>
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
<td><p>La llamada se enruta según la Directiva de voz del usuario y solo a través de troncos no habilitados para el enrutamiento basado en ubicación (si está disponible).</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Vea también


[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


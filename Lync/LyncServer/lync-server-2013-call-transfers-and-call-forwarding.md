---
title: 'Lync Server 2013: transferencias de llamadas y desvío de llamadas'
description: 'Lync Server 2013: transferencias de llamadas y desvío de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565256"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Transferencias de llamadas y desvío de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Cuando se trata de un punto final de RTC, el enrutamiento de Location-Based analiza la ubicación del punto de conexión de calle y el extremo al que se transferirá o reenviará la llamada (es decir, el destino de transferencia o reenvío). El enrutamiento de Location-Based determina si la llamada se debe transferir o reenviar en función de la ubicación de ambos puntos de conexión.

En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con un punto de conexión RTC y el usuario de Lync transfiere la llamada a otro usuario de Lync. En función de la ubicación del sitio de red del extremo del cesionario, el Location-Based el enrutamiento afecta a la ruta de la transferencia o el desvío de la llamada.

### <a name="initiating-call-transfer-or-forward"></a>Inicio de transferencia o reenvío de llamadas

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuario que inicia la transferencia o el desvío de la llamada</th>
<th>El extremo de destino está en el mismo sitio de red que el usuario que inicia la transferencia de llamadas o el reenvío</th>
<th>El extremo de destino está en un sitio de red diferente a medida que el usuario inicia la transferencia de llamadas o reenvía</th>
<th>El extremo de destino está en un sitio de red desconocido o un sitio de red no habilitado para el enrutamiento Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync</p></td>
<td><p>Se permite la transferencia o el desvío de llamadas</p></td>
<td><p>No se permite el desvío o la transferencia de llamadas</p></td>
<td><p>No se permite el desvío o la transferencia de llamadas</p></td>
</tr>
</tbody>
</table>

  

Por ejemplo: un usuario de Lync en una llamada con un punto de conexión RTC transfiere la llamada a otro usuario de Lync que se encuentra en el mismo sitio de red. En este caso, se permite la transferencia de llamadas.

En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con otro usuario de Lync y uno de los usuarios transfiere la llamada a un extremo de RTC. En función de la ubicación del usuario al que se transfiere la llamada, la tabla detalla cómo el enrutamiento de Location-Based afecta a la llamada.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Transferencia de llamadas o reenviar a extremo de RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de extremo de transferencia/reenvío de llamadas</th>
<th>Usuarios de Lync en el mismo sitio de red</th>
<th>Usuarios de Lync en sitios de red diferentes</th>
<th>Uno o ambos usuarios de Lync en un sitio de red o sitio de red desconocido no están habilitados para el enrutamiento Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>La Directiva de enrutamiento de voz del sitio del usuario transferido permite desviar o transferir las llamadas permitidas.</p></td>
<td><p>La Directiva de enrutamiento de voz del sitio del usuario transferido permite desviar o transferir las llamadas permitidas.</p></td>
<td><p>La Directiva de voz del usuario transferido permite desviar o transferir las llamadas solo a través de troncos no habilitados para Location-Based enrutamiento</p></td>
</tr>
</tbody>
</table>

  
Por ejemplo: un usuario de Lync en una llamada con otro usuario de Lync que se encuentra en el mismo sitio de red transfiere la llamada a un punto de conexión de RTC y se permite la transferencia de llamadas.

<div>

## <a name="see-also"></a>Consulte también


[Escenarios para Location-Based el enrutamiento en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


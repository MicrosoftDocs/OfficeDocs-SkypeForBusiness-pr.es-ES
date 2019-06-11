---
title: 'Lync Server 2013: Transferencia y desvío de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Transferencia y desvío de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Cuando se trata de un punto final de RTC, el enrutamiento basado en la ubicación analiza la ubicación del extremo de la calle y el punto final al que se transferirá o desviará la llamada (es decir, el destino de transferencia/reenvío). El enrutamiento basado en la ubicación determina si la llamada se debe transferir o desviar dependiendo de la ubicación de ambos puntos de conexión.

En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con un punto final de RTC, y el usuario de Lync transfiere la llamada a otro usuario de Lync. En función de la ubicación del sitio de red del extremo del cesionario, el enrutamiento basado en la ubicación afecta al enrutamiento de la transferencia de la llamada o hacia adelante.

### <a name="initiating-call-transfer-or-forward"></a>Inicio de la transferencia o el desvío de la llamada

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
<th>El extremo de destino está en el mismo sitio de red que el usuario que inicia la transferencia o el desvío de la llamada</th>
<th>El extremo de destino está en un sitio de red diferente del sitio del usuario que inicia la transferencia o el desvío de la llamada</th>
<th>El extremo de destino está en un sitio de red desconocido o el sitio de red no está habilitado para el enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync</p></td>
<td><p>Se permite el desvío o la transferencia de la llamada</p></td>
<td><p>No se permite el desvío ni la transferencia de la llamada</p></td>
<td><p>No se permite el desvío ni la transferencia de la llamada</p></td>
</tr>
</tbody>
</table>

  

Por ejemplo: un usuario de Lync en una llamada con un punto final de la RTC transfiere la llamada a otro usuario de Lync que se encuentra en el mismo sitio de red. En este caso, se permite la transferencia de la llamada.

En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con otro usuario de Lync, y uno de los usuarios transfiere la llamada a un punto final de la RTC. La tabla recoge los detalles de cómo el enrutamiento basado en ubicación afecta a la llamada en función de la ubicación del usuario al que se transfiere la llamada.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Transferencia o desvío de la llamada al extremo de RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino del extremo de la transferencia o el desvío de la llamada</th>
<th>Usuarios de Lync en el mismo sitio de red</th>
<th>Usuarios de Lync en diferentes sitios de red</th>
<th>Uno o ambos usuarios de Lync en un sitio de red o sitio de red desconocidos no están habilitados para el enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Desvío o transferencia de llamada permitido por la directiva de enrutamiento de voz del sitio del usuario al que se transfiere la llamada</p></td>
<td><p>Desvío o transferencia de llamada permitido por la directiva de enrutamiento de voz del sitio del usuario al que se transfiere la llamada</p></td>
<td><p>Desvío o transferencia de llamada permitido por la directiva de voz del usuario al que se transfiere la llamada únicamente a través de troncos no habilitados para el enrutamiento basado en ubicación</p></td>
</tr>
</tbody>
</table>

  
Por ejemplo: un usuario de Lync en una llamada con otro usuario de Lync que se encuentra en el mismo sitio de red transfiere la llamada a un punto final de RTC y se permite la transferencia de llamadas.

<div>

## <a name="see-also"></a>Vea también


[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


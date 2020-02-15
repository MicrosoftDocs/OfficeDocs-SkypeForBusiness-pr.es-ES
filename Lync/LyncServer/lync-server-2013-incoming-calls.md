---
title: 'Lync Server 2013: llamadas entrantes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c153af6e14c291189f714f7054f72301d6859a88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Llamadas entrantes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento de llamadas entrantes a los usuarios habilitados para el enrutamiento basado en ubicación depende de la ubicación del extremo del usuario. El enrutamiento de las llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un punto de conexión que se encuentra en un sitio de red habilitado para enrutamiento basado en ubicación y el extremo se encuentra en el mismo sitio de red que la puerta de enlace RTC, la llamada se redirigirá. Si un usuario tiene una llamada entrante a un punto de conexión que se encuentra en un sitio de red habilitado para enrutamiento basado en ubicación y el extremo se encuentra en un sitio de red diferente de la puerta de enlace RTC, la llamada no se enrutará. Cuando un usuario no tiene extremos ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se redirigirá directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la persona que ha recibido la llamada.

La configuración del desvío de llamadas de un usuario que está habilitado para el enrutamiento basado en ubicación seguirá aplicándose, pero las llamadas reenviadas estarán sujetas a las restricciones de enrutamiento del usuario en función de la ubicación.

En la tabla siguiente se muestra cómo el enrutamiento basado en ubicación afecta al enrutamiento de las llamadas entrantes en función de la ubicación del extremo del destinatario de la llamada. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento basado en ubicación y el enrutamiento basado en ubicación solo permite el enrutamiento de llamadas RTC a extremos dentro del mismo sitio de red.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Destinatario de la llamada que recibe una llamada entrante de la RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Extremo del destinatario de la llamada que se encuentra en el mismo sitio de red que la puerta de enlace RTC</th>
<th>Extremo del destinatario de la llamada no ubicado en el mismo sitio de red que la puerta de enlace RTC</th>
<th>Extremo del destinatario de la llamada ubicado en un sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Enrutamiento de llamadas RTC entrantes</p></td>
<td><p>La llamada entrante se redirige a los extremos del destinatario de la llamada</p></td>
<td><p>La llamada entrante no se enruta a los extremos del destinatario de la llamada</p></td>
<td><p>La llamada entrante no se enruta a los extremos del destinatario de la llamada</p></td>
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


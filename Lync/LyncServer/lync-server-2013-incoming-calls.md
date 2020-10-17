---
title: 'Lync Server 2013: llamadas entrantes'
description: 'Lync Server 2013: llamadas entrantes.'
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
ms.openlocfilehash: 3a72c7fc378240f9751eae8e6c24e9cc601b08d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547736"
---
# <a name="incoming-calls-in-lync-server-2013"></a>Llamadas entrantes en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento de llamadas entrantes a los usuarios habilitados para Location-Based el enrutamiento depende de la ubicación del extremo del usuario. El enrutamiento de las llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un punto de conexión que se encuentra en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en el mismo sitio de red que la puerta de enlace RTC, la llamada se redirigirá. Si un usuario tiene una llamada entrante a un punto de conexión que se encuentra en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en un sitio de red diferente de la puerta de enlace RTC, no se enrutará la llamada. Cuando un usuario no tiene extremos ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se redirigirá directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la persona que ha recibido la llamada.

La configuración de desvío de llamadas de un usuario que está habilitada para Location-Based el enrutamiento seguirá aplicándose, pero las llamadas reenviadas estarán sujetas a Location-Based restricciones de enrutamiento del usuario.

En la tabla siguiente se muestra cómo el enrutamiento de Location-Based afecta al enrutamiento de las llamadas entrantes en función de la ubicación del extremo del destinatario de la llamada. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento Location-Based y Location-Based enrutamiento solo permite el enrutamiento de llamadas RTC a extremos dentro del mismo sitio de red.

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
<th>Extremo del destinatario de la llamada ubicado en un sitio de red desconocido o no habilitado para el enrutamiento de Location-Based</th>
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

## <a name="see-also"></a>Consulte también


[Escenarios para Location-Based el enrutamiento en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


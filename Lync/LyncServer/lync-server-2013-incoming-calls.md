---
title: 'Lync Server 2013: Llamadas entrantes'
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
ms.openlocfilehash: e70e5a489cbfa581c666374e6535b898727e1fdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Llamadas entrantes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento de llamadas entrantes a los usuarios habilitados para el enrutamiento basado en la ubicación depende de la ubicación del extremo del usuario. El enrutamiento de llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento basado en ubicación y el punto final se encuentra en el mismo sitio de red que la puerta de enlace PSTN, la llamada se redirigirá. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento basado en ubicación y el punto final se encuentra en un sitio de red diferente de la puerta de enlace PSTN, la llamada no se redirigirá. Cuando un usuario no tenga extremos ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se redirigirá directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la persona a la que se está llamando.

La configuración del desvío de llamadas de un usuario habilitado para el enrutamiento basado en la ubicación se seguirá aplicando; sin embargo, las llamadas desviadas estarán sujetas a las restricciones de enrutamiento basadas en la ubicación del usuario.

En la tabla siguiente se muestra cómo afecta el enrutamiento basado en la ubicación al enrutamiento de las llamadas entrantes en función de la ubicación del punto final de la llamada. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento basado en la ubicación y el enrutamiento basado en la ubicación solo permite el enrutamiento de llamadas RTC a puntos de conexión dentro del mismo sitio de red.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>El destinatario recibe una llamada entrante desde la RTC

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
<th>El extremo del destinatario se encuentra en el mismo sitio de red que la puerta de enlace RTC</th>
<th>El extremo del destinatario no se encuentra en el mismo sitio de red que la puerta de enlace RTC</th>
<th>El extremo del destinatario se encuentra en un sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Enrutamiento de una llamada RTC entrante</p></td>
<td><p>La llamada entrante se redirige a los extremos del destinatario</p></td>
<td><p>La llamada entrante no se redirige a los extremos del destinatario</p></td>
<td><p>La llamada entrante no se redirige a los extremos del destinatario</p></td>
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


---
title: 'Lync Server 2013: Tono de llamada simultáneo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bcdb0d30bccfe628fd02861d257d79268046b77
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Tono de llamada simultáneo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Cuando la persona a la que se llama tiene habilitado el timbre simultáneo, el enrutamiento basado en la ubicación analiza la ubicación de la persona que llama y los puntos finales de las partes a las que se llama para determinar si se debe distribuir la llamada.

En la siguiente tabla se muestra un usuario con la configuración de llamadas simultáneas habilitada y el destino de llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Llamada RTC entrante para</th>
<th>Ubicado en el mismo sitio de red que el destinatario</th>
<th>Ubicado en un sitio de red distinto del sitio del destinatario</th>
<th>Se encuentra en un sitio de red desconocido o no está habilitado para el enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync</p></td>
<td><p>Llamadas simultáneas permitidas</p></td>
<td><p>Llamadas simultáneas no permitidas</p></td>
<td><p>Llamadas simultáneas no permitidas</p></td>
</tr>
</tbody>
</table>

  
En la tabla siguiente se muestra una llamada de un usuario de Lync (es decir, el autor de la llamada de Lync) en el mismo sitio de red, en un sitio de red diferente o desde un sitio de red desconocido. El destinatario de la llamada tiene un punto final de la RTC (por ejemplo, teléfono móvil) configurado como un objetivo de llamada simultánea. En este escenario, el enrutamiento basado en la ubicación determinará si la llamada debe dirigirse al destino simultáneo (por ejemplo, teléfono móvil) del destinatario de la llamada.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de llamadas simultáneas</th>
<th>Ubicado en el mismo sitio de red que el destinatario</th>
<th>Ubicado en un sitio de red distinto del sitio del destinatario</th>
<th>Se encuentra en un sitio de red desconocido o no está habilitado para el enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Llamadas simultáneas permitidas a través de la directiva del enrutamiento de voz del sitio del autor de la llamada</p></td>
<td><p>Llamadas simultáneas permitidas a través de la directiva del enrutamiento de voz del sitio del autor de la llamada</p></td>
<td><p>Llamadas simultáneas permitidas a través de la directiva del enrutamiento de voz del autor de la llamada para troncos no habilitados para el enrutamiento basado en ubicación</p></td>
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


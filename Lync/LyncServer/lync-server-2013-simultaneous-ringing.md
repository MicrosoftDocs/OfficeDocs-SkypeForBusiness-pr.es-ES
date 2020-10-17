---
title: 'Lync Server 2013: llamadas simultáneas'
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
ms.openlocfilehash: 358a0dd6dab96b67b26c211c9f28dbc6c0842804
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519797"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a>Llamadas simultáneas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Cuando la persona llamada tiene habilitado el timbre simultáneo, el enrutamiento de Location-Based analiza la ubicación de la parte de llamada y los puntos de conexión de las partes a las que se llama para determinar si se debe enrutar la llamada.

En la tabla siguiente se muestra un usuario configurado con llamadas simultáneas y el destino de llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.


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
<th>Ubicado en el mismo sitio de red que el destinatario de la llamada</th>
<th>Ubicado en un sitio de red diferente del destinatario de la llamada</th>
<th>Ubicado en un sitio de red desconocido o no habilitado para el enrutamiento Location-Based</th>
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

  
En la tabla siguiente se muestra una llamada de un usuario de Lync (por ejemplo, llamador de Lync) en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido. El destinatario de la llamada tiene un punto de conexión de RTC (por ejemplo, un teléfono móvil) configurado como un destino de llamadas simultáneas. En este escenario, el enrutamiento de Location-Based determinará si la llamada se debe enrutar al destino de llamada simultánea (por ejemplo, teléfono móvil) del destinatario de la llamada.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de llamada simultánea</th>
<th>Ubicado en el mismo sitio de red que el destinatario de la llamada</th>
<th>Ubicado en un sitio de red diferente del destinatario de la llamada</th>
<th>Ubicado en un sitio de red desconocido o no habilitado para el enrutamiento Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Llamadas simultáneas permitidas a través de la Directiva de enrutamiento de voz del sitio del autor de la llamada</p></td>
<td><p>Llamadas simultáneas permitidas a través de la Directiva de enrutamiento de voz del sitio del autor de la llamada</p></td>
<td><p>Se permiten las llamadas simultáneas a través de la Directiva de voz del autor de la llamada a troncos que no están habilitados para Location-Based enrutamiento</p></td>
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


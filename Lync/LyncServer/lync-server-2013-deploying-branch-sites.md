---
title: 'Lync Server 2013: Implementación de sitios de sucursales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Implementación de sitios de sucursales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Los usuarios de un sitio de sucursal obtienen la mayor parte de su funcionalidad de 2013 de Lync Server en el servidor del sitio central al que está asociado el sitio de la sucursal. Cada sitio de sucursal está asociado con un solo sitio central. Para proporcionar llamadas a y desde la red de telefonía pública conmutada (RTC), un sitio de sucursal puede contener cualquiera de los siguientes elementos:

  - Una puerta de enlace RTC y posiblemente un servidor Meditation

  - Un tronco de SIP

  - Una infraestructura de voz existente con una central de conmutación (PBX)

  - Un equipo de sucursales con la supervivencia

  - Un servidor de sucursal con la supervivencia

Los sitios de sucursales con un equipo de sucursal o un servidor de sucursal con la supervivencia son más resistentes en las horas de la red de área amplia o errores de sitio central que las sucursales sin una de estas soluciones. Por ejemplo, en un sitio con una sucursal o un servidor de sucursal superviviente implementado, los usuarios pueden seguir realizando y recibiendo llamadas RTC si la red que conecta el sitio de la sucursal con el sitio central está desactivada. Otra forma de lograr la resistencia al sitio de la sucursal es usar una puerta de enlace PSTN o un tronco del SIP con una implementación de Lync Server de escala completa en el sitio de la sucursal.

Para obtener detalles sobre qué implementación de sitio de sucursal es adecuada para su organización, incluidos los requisitos previos y otras consideraciones de planeación, consulte [planificación de la conectividad RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) y [planeamiento de resistencia de voz de sitio de sucursal en Lync. Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) en la documentación de planificación.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Proporcionar conectividad RTC en un sitio de sucursal en Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


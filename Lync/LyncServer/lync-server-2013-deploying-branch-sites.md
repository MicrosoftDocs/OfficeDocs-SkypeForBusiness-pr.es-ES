---
title: 'Lync Server 2013: implementación de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed57a78637639d5e6402f88b7909114f3aabce7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531297"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a>Implementación de sitios de sucursal en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Los usuarios de sitios de sucursal obtienen la mayor parte de su funcionalidad de 2013 de Lync Server del servidor en el sitio central al que está asociado el sitio de sucursal. Todas y cada una de las sucursales están asociadas a exactamente un sitio central. Para poder realizar llamadas a y desde la red telefónica conmutada pública (RTC), una sucursal puede contener cualquiera de los siguientes elementos:

  - Una puerta de enlace RTC y, probablemente, un servidor de mediación

  - Un tronco SIP

  - Una infraestructura de voz existente con una central de conmutación (PBX)

  - Una aplicación de sucursal con funciones de supervivencia

  - Un servidor de sucursal con funciones de supervivencia

Los sitios de sucursal con una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia son más resistentes en las horas de la red de área extensa o errores de sitio central que los sitios de sucursal sin una de estas soluciones. Por ejemplo, en un sitio con una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia implementado, los usuarios aún pueden realizar y recibir llamadas RTC si la red que conecta el sitio de sucursal al sitio central no está disponible. Otra forma de lograr la resistencia del sitio de sucursal es usar una puerta de enlace RTC o un tronco SIP con una implementación de Lync Server a gran escala en el sitio de sucursal.

Para obtener información detallada sobre qué implementación de sitios de sucursal es la adecuada para su organización, incluidos los requisitos previos y otras consideraciones de planeación, consulte [Planning for RTC Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) y [Planning for Branch-site Voice Resiliency en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) en la documentación referente a la planeación.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Suministro de conectividad RTC en un sitio de sucursal en Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


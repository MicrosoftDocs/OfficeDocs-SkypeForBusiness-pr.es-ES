---
title: 'Lync Server 2013: Estimar el uso de voz y el tráfico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf321dc7668682e2c41765955c348a7e155214ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Estimar el uso de voz y el tráfico para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-07_

La herramienta de planeación de Microsoft Lync Server 2013 usa la siguiente métrica para estimar el tráfico de los usuarios en cada sitio y el número de puertos necesarios para ese tráfico.

  - <span></span>  
    Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.

  - <span></span>  
    Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.

  - <span></span>  
    Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.

El número de puertos, a su vez, determina la cantidad de servidores de mediación y puertas de enlace que se requerirán. Las puertas de enlace de red de telefonía pública conmutada (RTC) que la mayoría de las organizaciones consideran implementar intervalos de tamaño desde dos puertos hasta un máximo de 960 puertos. (Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía).

Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.

</div>

<span> </span>

</div>

</div>

</div>


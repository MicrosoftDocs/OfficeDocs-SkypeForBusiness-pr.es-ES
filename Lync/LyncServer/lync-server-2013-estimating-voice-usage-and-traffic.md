---
title: 'Lync Server 2013: estimar el uso de voz y el tráfico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 638e2ff873415236d11bae4486cd4642bd075c9d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Estimar el uso de voz y el tráfico para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-07_

La herramienta de planeación de Microsoft Lync Server 2013 usa la siguiente métrica para calcular el tráfico de usuarios en cada sitio y el número de puertos necesarios para admitir dicho tráfico.

  - <span></span>  
    Para **Tráfico reducido** (una llamada de RTC por usuario y hora) calcula 15 usuarios por puerto.

  - <span></span>  
    Para **Tráfico medio** (dos llamadas de RTC por usuario y hora) calcula 10 usuarios por puerto.

  - <span></span>  
    Para **Tráfico denso** (tres llamadas o más de RTC por usuario y hora) calcula 5 usuarios por puerto.

El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que se necesitarán. Las puertas de enlace de la red telefónica conmutada (RTC) que la mayoría de las organizaciones consideran que deben implementar intervalos de 2 puertos hasta un máximo de 960 puertos. (Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía).

Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. El número de puertas de enlace requeridas equivaldría al número total de puertos requeridos determinado por la capacidad total de las puertas de enlace.

</div>

<span> </span>

</div>

</div>

</div>


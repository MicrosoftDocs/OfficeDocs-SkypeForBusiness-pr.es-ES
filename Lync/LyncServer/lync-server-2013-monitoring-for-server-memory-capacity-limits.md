---
title: 'Lync Server 2013: supervisión de los límites de capacidad de la memoria del servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e969de7198eecf43b57ea00fa0591bbeb06da0b1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Supervisión de los límites de capacidad de la memoria del servidor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> La información de este tema que se refiere a la planeación de la capacidad solo se aplica a los clientes móviles de Lync 2010 y al servicio de movilidad (MCX). La planeación de capacidad para la API Web de comunicaciones unificadas (UCWA), usada por los clientes móviles de Lync 2013, se proporciona en Lync Server 2013, la herramienta de planeación.



</div>

Hay dos contadores de rendimiento de movilidad que pueden ayudarle a determinar su uso actual y a planear la capacidad del servicio de movilidad de Lync Server 2013 (MCX), así como supervisar el uso de memoria para UCWA. Para UCWA, la categoría de contador es **LS: Web – UCWA**. En el caso del servicio de movilidad (MCX), los contadores están bajo la categoría **LS: web-Mobile Communication Service**. Los contadores que se van a supervisar son:

  - **Recuento de sesiones actualmente activas con suscripciones de presencia activa**, que es el número actual de extremos registrados a través de UCWA o el servicio de movilidad (MCX) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)

  - **Recuento de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o el servicio de movilidad.

Si la diferencia entre el **número de sesiones actualmente activas con suscripciones de presencia activa** y el **recuento de sesiones actualmente activas** es pequeño con el tiempo, significa que la mayoría de los usuarios de dispositivos móviles tienen un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para MCX). Los dispositivos de UCWA Always-Connected incluyen los dispositivos Apple y Android que ejecutan clientes móviles de Lync 2013). Si el **recuento de sesiones actualmente activas** es mucho mayor que el **recuento de sesiones actualmente activas con suscripciones de presencia activa**, esto indica que más usuarios están usando un dispositivo de extremo en segundo plano, como un dispositivo iOS de Apple o Windows Phone en MCX. (Windows Phone es el único cliente móvil de Lync 2013 que se registrará como this).

Debe establecer un límite en el **recuento de sesiones actualmente activas con suscripciones de presencia activa** y contadores de rendimiento de **recuento de sesiones actualmente** en función del uso previsto, los resultados de la planeación de la capacidad y la supervisión continua del servicio de movilidad y otros contadores de servidores front-end. Los límites que establezca deben permitirle evaluar la capacidad del servidor y generar alertas cuando se supere la capacidad.

Para determinar los límites apropiados, primero debe determinar la cantidad de memoria disponible en el servidor front-end para el servicio de movilidad. Supervise los contadores para determinar cuándo es necesario planear la capacidad extra, de acuerdo con la siguiente fórmula:

Memoria total usada por el servicio de movilidad de MCX (MB) = 164 + (400 + 134)/1024 \* **recuento de sesiones actualmente activas con suscripciones de presencia activa** + 400/1024 \* (recuento de**sesiones actualmente activas** ; **número de sesiones actualmente activas con suscripciones de presencia activa**)

<div>


> [!IMPORTANT]  
> La calculadora de capacidad 2010 de Microsoft Lync Server es una hoja de cálculo que se rellena previamente con todas las fórmulas que permiten a un planificador determinar cuáles serán los requisitos para los servidores, incluidos la CPU, la memoria y el disco duro. Puede descargar la hoja de cálculo y un documento asociado en:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

El servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actual en el servidor front-end mediante el contador **memoria\\Mbytes disponibles** o mediante la ecuación mencionada anteriormente, para planear la cantidad de memoria que espera que use el servicio de movilidad.

Si la cantidad de memoria disponible en el servidor front-end es inferior a 1.500 MB cuando planea el número previsto de usuarios de movilidad, necesita agregar más hardware para admitir el servicio de movilidad. Para obtener más información, consulte [Monitoring Mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) en la documentación de operaciones.

<div>

## <a name="see-also"></a>Consulta también


[Supervisión de la movilidad para el rendimiento en Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


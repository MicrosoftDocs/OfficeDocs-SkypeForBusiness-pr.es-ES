---
title: 'Lync Server 2013: supervisión de los límites de capacidad de memoria del servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68728c85b14231644b445569857896f34abe535f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Supervisión de los límites de capacidad de memoria del servidor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> La información de este tema que se refiere a la planificación de capacidad solo se aplica a los clientes móviles de Lync 2010 y al servicio de movilidad (MCX). La planificación de capacidad de la API Web de comunicaciones unificadas (UCWA), usada por los clientes móviles de Lync 2013, se proporciona en Lync Server 2013, la herramienta de planeación.



</div>

Dos contadores de rendimiento de movilidad pueden ayudarle a determinar su uso actual y a ayudarle a planear la capacidad del servicio de movilidad de Lync Server 2013 (MCX), así como a supervisar el uso de memoria para UCWA. Para UCWA, la categoría de contador es **LS:WEB - UCWA**. En el caso de Mobility Service (Mcx), los contadores pertenecen a la categoría **LS:WEB - Mobile Communication Service**. Los contadores que se supervisan son los siguientes:

  - **Número de sesiones actualmente activas con suscripciones de presencia activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service (Mcx) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)

  - **Número de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service

Si la diferencia entre **Número de sesiones actualmente activas con suscripciones de presencia activas** y **Número de sesiones actualmente activas** es pequeña con el transcurso del tiempo, significa que la mayoría de los usuarios de dispositivos móviles tiene un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para Mcx). UCWA los dispositivos siempre conectados incluyen Apple y Android que ejecutan clientes móviles de Lync 2013). Si **Número de sesiones actualmente activas** es muy superior a **Número de sesiones actualmente activas con suscripciones de presencia activas**, quiere decir que hay más usuarios que usan un dispositivo de extremo en segundo plano, como un dispositivo Apple iOS o Windows Phone con Mcx. (Windows Phone es el único cliente móvil de Lync 2013 que se registrará como this).

Debe establecer un límite en el recuento de **sesiones activas actualmente con suscripciones de presencia activas** y contadores de rendimiento de recuento de **sesiones actualmente activos** según el uso previsto, los resultados de la planificación de capacidad y la supervisión continuada de Servicio de movilidad y otros contadores de servidor front-end. Los límites que establezca necesitan permitirle evaluar la capacidad del servidor y generar alertas cuando dicha capacidad se exceda.

Para determinar los límites adecuados, primero debe determinar cuánta memoria está disponible en el servidor front-end para el servicio de movilidad. Supervise los contadores para determinar cuándo hay que planear la capacidad adicional según la fórmula siguiente:

Memoria total usada por el servicio de movilidad de MCX (MB) = 164 + (400 + 134) \* /1024 recuento **de sesión activo actualmente con suscripciones de presencia activas** + 400/1024 \* (recuento de**sesiones actualmente** activas; recuento de **sesiones activas actualmente con suscripciones de presencia activas**)

<div>


> [!IMPORTANT]  
> La calculadora de capacidad 2010 de Microsoft Lync Server es una hoja de cálculo que se rellenó con todas las fórmulas que permiten a un planeador determinar cuáles serán los requisitos para los servidores, como la CPU, la memoria y el disco duro. Puede descargar la hoja de cálculo y un documento asociado en:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

El servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actual en el servidor front-end mediante el contador **memoria\\Mbytes disponibles** , o mediante la ecuación mencionada anteriormente, para planear la cantidad de memoria que espera que use el servicio de movilidad.

Si la cantidad de memoria disponible en el servidor front-end es inferior a 1.500 MB cuando se planea la cantidad de usuarios de movilidad esperada, necesita agregar más hardware para admitir el servicio de movilidad. Para obtener más información, vea [supervisión de la movilidad para el rendimiento en Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) en la documentación de operaciones.

<div>

## <a name="see-also"></a>Vea también


[Supervisión de la movilidad para el rendimiento en Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Supervisión de los límites de capacidad de la memoria del servidor
TOCTitle: Supervisión de los límites de capacidad de la memoria del servidor
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48274546
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supervisión de los límites de capacidad de la memoria del servidor

 

_**Última modificación del tema:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

> [!WARNING]  
> La información de este tema sobre la planeación de la capacidad solo se aplica a los clientes de Lync 2010 Mobile y al servicio de movilidad (Mcx). La planeación de la capacidad para la API web de comunicaciones unificadas (UCWA), usada por los clientes móviles de Lync 2013, se proporciona en la Lync Server 2013, herramienta de planeación.



Existen dos contadores de rendimiento de movilidad que pueden ayudarlo a determinar el uso actual y planear la capacidad para el servicio de movilidad (Mcx) de Lync Server 2013, así como también a supervisar el uso de memoria de UCWA. Para UCWA, la categoría de contador es **LS:WEB – UCWA**. Para el servicio de movilidad (Mcx), los contadores se incluyen en la categoría **LS:WEB - Mobile Communication Service**. Los contadores que se supervisan son los siguientes:

  - **Recuento de sesiones actualmente activas con suscripciones de presencia activas**, que es el número actual de extremos registrados a través de UCWA o el servicio de movilidad (Mcx) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)

  - **Recuento de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o el servicio de movilidad

Si la diferencia entre **Recuento de sesiones actualmente activas con suscripciones de presencia activas** y **Recuento de sesiones actualmente activas** es pequeña con el transcurso del tiempo, significa que la mayoría de los usuarios de dispositivos móviles tienen un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para Mcx). Los dispositivos conectados siempre de UCWA incluyen dispositivos Apple y Android que ejecutan clientes móviles de Lync 2013. Si **Recuento de sesiones actualmente activas** es muy superior a **Recuento de sesiones actualmente activas con suscripciones de presencia activas**, significa que una mayor cantidad de usuarios usan un dispositivo de extremo en segundo plano, como un dispositivo Apple iOS o Windows Phone con Mcx. (Windows Phone es el único cliente móvil de Lync 2013 que se registrará de este modo).

Debe establecer un límite en los contadores de rendimiento **Recuento de sesiones actualmente activas con suscripciones de presencia activas** y **Recuento de sesiones actualmente activas** según el uso previsto, los resultados de la planeación de la capacidad y la supervisión continua del servicio de movilidad y otros contadores de Servidor front-end. Los límites que establezca deben permitirle evaluar la capacidad del servidor y generar alertas cuando se exceda dicha capacidad.

Para determinar los límites adecuados, antes debe determinar cuánta memoria hay disponible en el Servidor front-end para el servicio de movilidad. Supervise los contadores para determinar cuándo debe planear la capacidad adicional según la fórmula siguiente:

Memoria total usada por el servicio de movilidad (Mcx) (MB) = 164 + (400 + 134) / 1024 \* **Recuento de sesiones actualmente activas con suscripciones de presencia activas** + 400 / 1024 \* (**Recuento de sesiones actualmente activas** – **Recuento de sesiones actualmente activas con suscripciones de presencia activas**)

> [!IMPORTANT]  
> La calculadora de capacidad de Microsoft Lync Server 2010 es una hoja de cálculo rellenada previamente con todas las fórmulas que permiten a una persona encargada de la planeación determinar los requisitos de los servidores, incluidas la CPU, la memoria y la unidad de disco duro. Puede descargar la hoja de cálculo y un documento asociado desde <a href="http://go.microsoft.com/fwlink/?linkid=212657" class="uri">http://go.microsoft.com/fwlink/?linkid=212657</a>



El Servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actualmente en el Servidor front-end usando el contador **Memoria\\Mbytes disponibles** o mediante le ecuación mencionada anteriormente para planear la cantidad de memoria que espera que use el servicio de movilidad.

Si la cantidad de memoria disponible en el Servidor front-end es inferior a 1.500 MB al planificar el número esperado de usuarios de movilidad, debe agregar más hardware para admitir el servicio de movilidad. Para obtener más información, vea [Supervisar el rendimiento de la movilidad](lync-server-2013-monitoring-mobility-for-performance.md) en la documentación relacionada con las operaciones.

## Vea también

#### Otros recursos

[Supervisar el rendimiento de la movilidad](lync-server-2013-monitoring-mobility-for-performance.md)


---
title: Supervisar el rendimiento de la movilidad
TOCTitle: Supervisar el rendimiento de la movilidad
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48276141
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supervisar el rendimiento de la movilidad

 

_**Última modificación del tema:** 2013-02-14_

El servicio de movilidad de Lync Server aumenta la carga en Servidores front-end y Grupos de servidores front-end. Los dispositivos móviles que mantienen una conexión con el servidor incluso si la aplicación móvil está minimizada, como los dispositivos Android y Nokia, exigen una mayor carga que los dispositivos que finalizan la conexión con el servidor cuando se minimiza la aplicación móvil. A medida que aumenta el uso de la movilidad, debe supervisar el rendimiento de la misma para determinar cuándo necesita aumentar su capacidad.

Hay varios límites que afectan al rendimiento de la movilidad:

  - Memoria disponible

  - Límite de la cola de solicitudes

  - Conexiones simultáneas

  - Longitud de la cola de IIS

Otros límites en los servidores que pueden afectar al rendimiento de la movilidad son un máximo de doce inicios de sesión simultáneos, autenticaciones y renovaciones y finalizaciones de sesión. Estos máximos no tienen que modificarse para la mayoría de implementaciones.

## En esta sección

  - [Supervisión de los límites de capacidad de la memoria del servidor](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Supervisar el uso de UCWA y del servicio de movilidad](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configurar el servicio de movilidad para alto rendimiento](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Supervisar archivos de registro de seguimiento de solicitudes de IIS](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Contadores de rendimiento de movilidad](lync-server-2013-mobility-performance-counters.md)


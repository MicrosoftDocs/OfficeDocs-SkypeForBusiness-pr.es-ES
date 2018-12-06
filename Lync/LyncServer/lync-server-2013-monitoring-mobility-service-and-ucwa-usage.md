---
title: Supervisar el uso de UCWA y del servicio de movilidad
TOCTitle: Supervisar el uso de UCWA y del servicio de movilidad
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48275878
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supervisar el uso de UCWA y del servicio de movilidad

 

_**Última modificación del tema:** 2013-02-14_

De forma periódica, le recomendamos supervisar la CPU y la memoria que usa el servicio Movilidad de Lync Server (Mcx) y la API web de comunicaciones unificadas (UCWA). Para supervisar el uso, haga lo siguiente:

**Para la API web de comunicaciones unificadas (UCWA):**

  - El proceso de trabajo de **LyncUcwa** en Administrador de Servicios de Internet Information Server (IIS). En el panel **Proceso de trabajo**, observe las columnas (de memoria) **CPU %** y **Bytes privados (KB)**.

  - Los contadores de rendimiento de **CPU** y **Procesador**.

Para la mayoría de implementaciones, el uso de la CPU de UCWA debería estar por debajo del 15 % como promedio. El uso de la memoria debería estar dentro de los límites descritos en [Supervisión de los límites de capacidad de la memoria del servidor](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:

  - **LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.

  - **ASP.NET\\Requests Queued** (debería ser siempre cero)


> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.



**Para el servicio Movilidad (Mcx):**

  - Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en Administrador de Servicios de Internet Information Server (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).

  - Los contadores de rendimiento **CPU** y **Procesador**.

En la mayoría de implementaciones, el uso de la CPU por parte del servicio Movilidad debería estar por debajo del 15 por ciento de media. El uso de la memoria debería estar entre los límites descritos en [Supervisión de los límites de capacidad de la memoria del servidor](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:

  - **ASP.NET v2.0.50727\\Requests Current**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.

  - **ASP.NET\\Requests Queued** (debería ser siempre cero)


> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.



## Vea también

#### Conceptos

[Supervisión de los límites de capacidad de la memoria del servidor](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)


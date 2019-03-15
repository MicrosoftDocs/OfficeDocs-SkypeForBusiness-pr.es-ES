---
title: Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.'
ms.openlocfilehash: 6856235e5e5a8179e52836901598f7fbe2852a57
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "21227019"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server
 
**Resumen:** Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.

> [!NOTE]
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
De forma continuada, debe supervisar la CPU y memoria que se usa en el Skype para el servicio de movilidad de Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA). Para supervisar el uso, haga lo siguiente:
  
 **Para la API web de comunicaciones unificadas (UCWA):**
  
- El proceso de trabajo de **LyncUcwa** en el Administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento **CPU** y **Procesador**.
    
Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio. El uso de memoria debe estar dentro de los límites que se describen en el [Monitor para los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md).
  
Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:
  
- **LS:WEB - limitación y Authentication\WEB - solicitudes totales en el procesamiento**, que indica el número de solicitudes web en el servidor pendientes. Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.
    
- **ASP.NET\Requests Queued** (siempre tendría que ser cero).
    
> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 
  
 **Para el servicio de movilidad (Mcx):**
  
- Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el Administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento **CPU** y **Procesador**.
    
En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media. El uso de memoria debe estar dentro de los límites que se describen en el [Monitor para los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md).
  
Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:
  
- **ASP.NET v2.0.50727\Requests Current**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.
    
- **ASP.NET\Requests Queued** (siempre tendría que ser cero).
    
> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 

> [!NOTE]
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
## <a name="see-also"></a>Consulte también

[Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md)
---
title: Supervisar el servicio de movilidad y el uso de UCWA en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: administrar el servicio de movilidad (MCX) y la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.'
ms.openlocfilehash: 5447eb0ac8ffe468fd52c7011824cc1f2f2f7b55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279798"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Supervisar el servicio de movilidad y el uso de UCWA en Skype empresarial Server
 
**Resumen:** Administrar el servicio de movilidad (MCX) y la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
De manera continua, debe supervisar la CPU y la memoria que usa el servicio de movilidad de Skype empresarial Server (MCX) y la API Web de comunicaciones unificadas (UCWA). Para supervisar el uso, haga lo siguiente:
  
 **Para la API web de comunicaciones unificadas (UCWA):**
  
- El proceso de trabajo **LyncUcwa** en el administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento **CPU** y **Procesador**.
    
Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio. El uso de memoria debe estar dentro de los límites descritos en [Monitor para los límites de capacidad de memoria del servidor en Skype empresarial Server](server-memory-capacity-limits.md).
  
Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:
  
- **LS: limitación web y Authentication\WEB-total de solicitudes en procesamiento**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.
    
- **ASP.NET\Requests Queued** (siempre tendría que ser cero).
    
> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 
  
 **Para el servicio de movilidad (Mcx):**
  
- Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento **CPU** y **Procesador**.
    
En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media. El uso de memoria debe estar dentro de los límites descritos en [Monitor para los límites de capacidad de memoria del servidor en Skype empresarial Server](server-memory-capacity-limits.md).
  
Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:
  
- **ASP.NET v2.0.50727\Requests Current**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.
    
- **ASP.NET\Requests Queued** (siempre tendría que ser cero).
    
> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
## <a name="see-also"></a>Vea también

[Supervisar los límites de capacidad de memoria del servidor en Skype empresarial Server](server-memory-capacity-limits.md)

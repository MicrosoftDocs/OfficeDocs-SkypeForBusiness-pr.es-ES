---
title: Supervisar el uso del servicio de movilidad y UCWA en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: administre el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814250"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Supervisar el uso del servicio de movilidad y UCWA en Skype Empresarial Server
 
**Resumen:** Administrar el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
De forma continua, debe supervisar la CPU y la memoria que usan el servicio de movilidad de Skype Empresarial Server (Mcx) y la API web de comunicaciones unificadas (UCWA). Para supervisar el uso, puede usar lo siguiente:
  
 **Para la API web de comunicaciones unificadas (UCWA):**
  
- Proceso **de trabajo de LyncUcwa** en el Administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento de **CPU** y **Procesador**.
    
Para la mayoría de las implementaciones, el uso de CPU de UCWA debe estar por debajo del 15 por ciento de media. El uso de memoria debe estar dentro de los límites descritos en Monitor para los límites de capacidad de memoria del [servidor en Skype Empresarial Server.](server-memory-capacity-limits.md)
  
Además de los contadores de uso de cpu y memoria, puede usar los siguientes contadores de rendimiento para ayudar a determinar cuándo un servidor está sobrecargado con solicitudes:
  
- **LS:WEB: limitación y autenticación\WEB:** solicitudes totales en procesamiento, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 10.000, se producirá un error en las solicitudes posteriores, con el mensaje de error "503 - Servicio no disponible".
    
- **ASP.NET\Requests Queued** (debería ser siempre cero)
    
> [!NOTE]
> Si cumple o supera estos valores, debe revisar y volver a calcular la planeación de capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 
  
 **Para el servicio de movilidad (Mcx):**
  
- Los **procesos de trabajo CSIntMcxAppPool** y **CSExtMcxAppPool** en el Administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento de **CPU** y **Procesador**.
    
Para la mayoría de las implementaciones, el uso de CPU del servicio de movilidad debe ser inferior al 15 por ciento, como promedio. El uso de memoria debe estar dentro de los límites descritos en Monitor para los límites de capacidad de memoria del [servidor en Skype Empresarial Server.](server-memory-capacity-limits.md)
  
Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:
  
- **ASP.NET v2.0.50727\Requests Current**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 5.000, se producirá un error en las solicitudes posteriores con el mensaje de error "503 - Servicio no disponible".
    
- **ASP.NET\Requests Queued** (debería ser siempre cero)
    
> [!NOTE]
> Si cumple o supera estos valores, debe revisar y volver a compilar la planeación de capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
## <a name="see-also"></a>Vea también

[Supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server](server-memory-capacity-limits.md)

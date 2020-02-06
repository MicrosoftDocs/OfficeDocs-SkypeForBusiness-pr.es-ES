---
title: Supervisar la movilidad para el rendimiento en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: Obtenga información sobre el servicio de movilidad (MCX) y la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.'
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817839"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Supervisar la movilidad para el rendimiento en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el servicio de movilidad (MCX) y la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.
  
El servicio de movilidad de Skype empresarial Server (MCX) y la API Web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y en las agrupaciones front-end. Dispositivos móviles que mantienen una conexión con el servidor incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Apple y Android que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que finalizar la conexión con el servidor cuando se minimice la aplicación móvil. A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
Hay varios límites que afectan al rendimiento de la movilidad: 
  
- Memoria disponible
    
- Límite de la cola de solicitudes
    
- Conexiones simultáneas
    
- Longitud de la cola de IIS
    
Otros límites en los servidores que pueden afectar al rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones y finalizaciones de sesión. Estos máximos no tienen que modificarse para la mayoría de implementaciones.
  
## <a name="in-this-section"></a>En esta sección

- [Supervisar los límites de capacidad de memoria del servidor en Skype empresarial Server](server-memory-capacity-limits.md)
    
- [Supervisar el servicio de movilidad y el uso de UCWA en Skype empresarial Server](service-and-ucwa-usage.md)
    
- [Configurar el servicio de movilidad para un alto rendimiento en Skype empresarial Server](configure-service.md)
    
- [Supervisar los archivos de registro de seguimiento de solicitudes de IIS en Skype empresarial Server](iis-request-tracing-log-files.md)
    
- [Contadores de rendimiento de movilidad en Skype empresarial Server](performance-counters.md)
    


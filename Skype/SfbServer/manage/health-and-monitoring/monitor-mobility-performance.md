---
title: Movilidad de Monitor de rendimiento en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: Obtenga información sobre el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.'
ms.openlocfilehash: 476d03fa17cad163fa9426ca35853cfe29f87bb1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886285"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Movilidad de Monitor de rendimiento en Skype para Business Server
 
**Resumen:** Información sobre el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.
  
El Skype para el servicio de movilidad de Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA) aumentan la carga de los grupos de servidores Front-End y servidores Front-End. Dispositivos móviles que mantienen una conexión con el servidor incluso cuando se minimiza la aplicación móvil, como dispositivos Android y Nokia ejecuta Lync 2010 Mobile, así como los dispositivos Android y Apple que ejecutan Lync Mobile de 2013, imponen una carga mayor que los dispositivos que finalizar su conexión con el servidor cuando se minimiza la aplicación móvil. A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.

> [!NOTE]
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
Hay varios límites que afectan al rendimiento de la movilidad: 
  
- Memoria disponible
    
- Límite de la cola de solicitudes
    
- Conexiones simultáneas
    
- Longitud de la cola de IIS
    
Otros límites en los servidores que pueden afectar al rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones y finalizaciones de sesión. Estos máximos no tienen que modificarse para la mayoría de implementaciones.
  
## <a name="in-this-section"></a>En esta sección

- [Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md)
    
- [Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server](service-and-ucwa-usage.md)
    
- [Configurar el servicio de movilidad para alto rendimiento en Skype para Business Server](configure-service.md)
    
- [Supervisión de solicitudes de IIS el seguimiento de los archivos de registro en Skype para Business Server](iis-request-tracing-log-files.md)
    
- [Contadores de rendimiento de movilidad en Skype para Business Server](performance-counters.md)
    


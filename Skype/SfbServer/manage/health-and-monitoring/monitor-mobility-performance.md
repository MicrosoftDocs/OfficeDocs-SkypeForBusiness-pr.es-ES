---
title: Supervisar la movilidad para el rendimiento en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: Conozca el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a>Supervisar la movilidad para el rendimiento en Skype Empresarial Server 2015
 
**Resumen:** Conozca el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.
  
El Skype para servicio de movilidad Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA) aumentan la carga de grupos de servidores frontales y Front-End. Los dispositivos móviles que mantienen una conexión con el servidor, incluso cuando se minimiza la aplicación móvil, como los dispositivos Android y Nokia ejecutan Lync 2010 Mobile, así como los dispositivos Android y Apple con Lync Mobile de 2013, imponen una carga mayor que los dispositivos que terminar su conexión con el servidor cuando se minimiza la aplicación móvil. A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.
  
Hay varios límites que afectan al rendimiento de la movilidad: 
  
- Memoria disponible
    
- Límite de la cola de solicitudes
    
- Conexiones simultáneas
    
- Longitud de la cola de IIS
    
Otros límites en los servidores que pueden afectar al rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones y finalizaciones de sesión. Estos máximos no tienen que modificarse para la mayoría de implementaciones.
  
## <a name="in-this-section"></a>En esta sección

- [Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015](server-memory-capacity-limits.md)
    
- [Supervisar el uso de servicios de movilidad y UCWA en Skype para Business Server 2015](service-and-ucwa-usage.md)
    
- [Configurar el servicio de movilidad de alto rendimiento de Skype para Business Server 2015](configure-service.md)
    
- [Archivos de registro de seguimiento de Skype de peticiones de IIS supervisión para Business Server 2015](iis-request-tracing-log-files.md)
    
- [Contadores de rendimiento de movilidad en Skype para Business Server 2015](performance-counters.md)
    


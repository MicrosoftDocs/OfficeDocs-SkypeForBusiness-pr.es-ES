---
title: Supervisar la movilidad para obtener rendimiento en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Summary: Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype Empresarial Server.'
ms.openlocfilehash: 5f8adbbdc653d8cdf2e19ce3f82fc4fdb0383505
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746926"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Supervisar la movilidad para obtener rendimiento en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el Servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.
  
El Skype Empresarial Server mobility service (Mcx) y la API web de comunicaciones unificadas (UCWA) aumentan la carga en servidores front-end y grupos de servidores front-end. Los dispositivos móviles que mantienen una conexión al servidor incluso cuando se minimiza la aplicación móvil, como dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como dispositivos Android y Apple que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que terminan su conexión con el servidor cuando se minimiza la aplicación móvil. A medida que aumenta el uso de la movilidad, debes supervisar el rendimiento de la movilidad para determinar cuándo necesitas aumentar la capacidad.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
Hay varios límites que afectan al rendimiento de la movilidad: 
  
- Memoria disponible
    
- Límite de la cola de solicitudes
    
- Conexiones simultáneas
    
- Longitud de la cola de IIS
    
Otros límites en los servidores que pueden influir en el rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones de sesión y terminaciones. Estos máximos no tienen que modificarse para la mayoría de implementaciones.
  
## <a name="in-this-section"></a>En esta sección

- [Supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server](server-memory-capacity-limits.md)
    
- [Supervisar el uso del servicio de movilidad y UCWA en Skype Empresarial Server](service-and-ucwa-usage.md)
    
- [Configurar el servicio de movilidad para un alto rendimiento en Skype Empresarial Server](configure-service.md)
    
- [Supervisión de archivos de registro de seguimiento de solicitudes iis en Skype Empresarial Server](iis-request-tracing-log-files.md)
    
- [Contadores de rendimiento de movilidad en Skype Empresarial Server](performance-counters.md)
    


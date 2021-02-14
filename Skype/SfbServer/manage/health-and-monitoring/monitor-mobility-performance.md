---
title: Supervisar la movilidad para el rendimiento en Skype Empresarial Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: obtenga información sobre el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816840"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Supervisar la movilidad para el rendimiento en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.
  
El servicio de movilidad de Skype Empresarial Server (Mcx) y la API web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y los grupos de servidores front-end. Los dispositivos móviles que mantienen una conexión con el servidor incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Android y Apple que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que finalizan su conexión con el servidor cuando la aplicación móvil está minimizada. A medida que aumenta el uso de la movilidad, debe supervisar el rendimiento de la movilidad para determinar cuándo necesita aumentar la capacidad.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
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
    
- [Supervisión de archivos de registro de seguimiento de solicitudes IIS en Skype Empresarial Server](iis-request-tracing-log-files.md)
    
- [Contadores de rendimiento de movilidad en Skype Empresarial Server](performance-counters.md)
    


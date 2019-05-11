---
title: Consideraciones acerca de la migración del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener más información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.
ms.openlocfilehash: f5e33c36b0c6a58d83f22e5c18f4de34ffb9d648
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895219"
---
# <a name="skype-room-system-migration-considerations"></a>Consideraciones acerca de la migración del Sistema de salas de Skype
 
Lea este tema para obtener más información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.
  
## <a name="migration-considerations"></a>Consideraciones acerca de la migración

En esta sección se proporciona instrucciones si va a implementar el sistema de sala de Skype en un entorno de grupo de varios servidores que incluya las diferentes versiones de Skype para Business Server o Lync Server. 
  
El componente Replicador de usuario (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos de SQL Server del back-end de Lync Server. Sólo el Replicador de usuarios en Lync Server 2013 está al tanto de objetos del sistema de salas de Skype. En anteriores versiones de Lync Server y Office Communications, el replicador de usuario no detecta los atributos de Active Directory que designan los objetos LRS y, por consiguiente, no los reconoce. 
  
Si una cuenta de sistema de salas de Skype intenta iniciar sesión en Lync y realiza la detección automática en función de registro SRV o el aspecto de registro DNS A copia de seguridad, y si los puntos de esas cuentas a una versión anterior de Lync Server u Office Communications Server, LRS recibirá una respuesta 404 no se encuentra en  el grupo heredado. El grupo heredado no podrán redirigir del sistema de sala de Skype a su grupo de servidores principal de Lync Server 2013. 
  
Puede abordar este problema con las siguientes opciones: 
  
- Señale el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) en el grupo de Lync Server 2013.
    
- Si la primera opción no es posible, debe configurar LRS manualmente y proporcione la dirección de grupo de servidores de Lync Server 2013 mediante su configuración directamente en la aplicación de consola del sistema de salas de Skype. 
    
- Si el sistema de sala de Skype se implementa fuera de la red corporativa y un servidor perimetral de Lync ha implementado y configurado para que apunte a un grupo de servidores heredado o director, un sitio secundario del servidor perimetral es necesario, que apunta al grupo de servidores de Lync Server 2013. Consulte la documentación de la implementación del servidor perimetral si desea obtener más información acerca de la implementación de un servidor perimetral secundario. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilidad del sistema de salas de Skype con un grupo de servidores de Lync Server 2010

Durante la migración, si un usuario alojado en un grupo de servidores de Lync Server 2010 programa una reunión y se invita a la cuenta del sistema de salas de Skype, el cliente del sistema de salas de Skype tendrán una funcionalidad limitada al asistir a la reunión. 
  
Cuando el cliente del sistema de salas de Skype se une a una llamada de conferencia programada que se ha organizado por un usuario alojado en Lync Server 2010, sistema de sala de Skype tiene las siguientes limitaciones en la reunión: 
  
- Sistema de sala de Skype no se puede mostrar la Galería de vídeo de varias vista.
    
- Si el cliente del sistema de salas de Skype es el moderador, no se aplican bloqueo de vídeo en los participantes.
    
- Sistema de sala de Skype no se puede mostrar la resolución de vídeo de 1080p (entrante o saliente), incluso si la directiva de conferencia de Lync Server 2013 lo permite, debido a lo siguiente: 
    
  - Lync Server 2010 no es compatible con resolución 1080p.
    
  - Sistema de sala de Skype siempre está limitado por la directiva del organizador de la conferencia para la resolución de vídeo. Por lo tanto, incluso si el grupo de servidores de Lync 2010 es compatible con la resolución 720p, sistema de sala de Skype no podrán aprovechar las ventajas de resolución 720p como la directiva del organizador no lo admite. 
    
- Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reunión y desactivan el audio automáticamente para evitar eco en la sala de reunión física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.
    
- Existen limitaciones en el rendimiento de escritorio compartido para reuniones hospedadas en Lync Server 2010.
    
- Los usuarios no podrán unirse a privada reuniones (restringidas) a las que se hospedan en Lync 2010 con el sistema de sala de Skype.
    


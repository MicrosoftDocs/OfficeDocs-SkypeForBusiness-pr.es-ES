---
title: Consideraciones acerca de la migración del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a>Consideraciones acerca de la migración del Sistema de salas de Skype
 
Lea este tema para obtener información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.
  
## <a name="migration-considerations"></a>Consideraciones acerca de la migración

Esta sección proporciona instrucciones si va a implementar el sistema del sitio de Skype en un entorno de grupo de múltiples que incluye diferentes versiones de Skype para Business Server, Lync Server o Office Communications Server 2007 R2. 
  
El componente Replicador de usuario (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos de SQL Server del back-end de Lync Server. Sólo la Ronda de URUGUAY en Lync Server 2013 es consciente de los objetos de sistema de sala de Skype. En anteriores versiones de Lync Server y Office Communications, el replicador de usuario no detecta los atributos de Active Directory que designan los objetos LRS y, por consiguiente, no los reconoce. 
  
Si una cuenta de Skype sala sistema intenta iniciar sesión en Lync y realiza descubrimiento automático basado en el registro SRV o DNS A registro de búsqueda y seleccione las cuentas a una versión anterior de Lync Server u Office Communications Server, LRS recibirá una respuesta 404 no se encuentra en  el grupo heredado. El grupo heredado no podrá redirigir el sistema del sitio de Skype a su grupo doméstico Lync Server 2013. 
  
Puede abordar este problema con las siguientes opciones: 
  
- Señale el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) en el grupo de Lync Server 2013.
    
- Si la primera opción no es posible, debe configurar LRS manualmente y proporcionar la dirección de grupo de Lync Server 2013 configurándolo directamente en la aplicación de consola de sistema de sala de Skype. 
    
- Si se implementa el sistema de sala de Skype fuera de la red corporativa y un borde de Lync Server se ha implementado y configurado para apuntar a un director o grupo heredado, es necesario, un sitio secundario del servidor perimetral que señala al grupo de Lync Server 2013. Consulte la documentación de la implementación del servidor perimetral si desea obtener más información acerca de la implementación de un servidor perimetral secundario. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Sala de Skype interoperabilidad del sistema con una agrupación de Lync Server 2010

Durante la migración, si un usuario que está alojado en un grupo de Lync Server 2010 programa una reunión e invita a la cuenta de sistema del sitio de Skype, el cliente de sistema de sala de Skype tendrán una funcionalidad limitada al asistir a la reunión. 
  
Cuando el cliente del sistema de sala de Skype une a una conferencia programada se ha organizado por un usuario alojados en Lync Server 2010, sistema de sala de Skype tiene las siguientes limitaciones en la reunión: 
  
- Sistema de sala de Skype no se puede mostrar la Galería de vídeos de múltiples vista.
    
- Si el cliente del sistema de sala de Skype es el presentador, no puede aplicar bloqueo de vídeo a los participantes.
    
- Sistema de sala de Skype no se puede mostrar la resolución de vídeo de 1080p (entrante o saliente), incluso si la directiva de la conferencia de Lync Server 2013 lo permite, por los motivos siguientes: 
    
  - Lync Server 2010 no admite una resolución de 1080p.
    
  - Sistema de sala de Skype está siempre limitado por la política del organizador de la conferencia para la resolución de vídeo. Por lo tanto, incluso si el grupo de Lync 2010 es compatible con resolución 720p, sistema de sala de Skype no podrá aprovechar las ventajas de resolución 720p como directiva del organizador no lo admite. 
    
- Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reunión y desactivan el audio automáticamente para evitar eco en la sala de reunión física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.
    
- Existen limitaciones en el rendimiento de escritorio compartido para reuniones hospedadas en Lync Server 2010.
    
- Los usuarios no podrán unirse a (restringidas) reuniones privadas que se hospedan en Lync 2010 con sistema de sala de Skype.
    


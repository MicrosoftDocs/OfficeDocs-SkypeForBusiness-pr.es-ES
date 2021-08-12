---
title: Skype Consideraciones de migración del sistema de sala
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener información sobre cómo implementar Skype room system en un entorno que tiene varias versiones de Skype Empresarial Server y Lync Server.
ms.openlocfilehash: bcbb8a14cf1d998c68f83875bce25935d73e92b7a755cd370526a65aef202e36
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310049"
---
# <a name="skype-room-system-migration-considerations"></a>Skype Consideraciones de migración del sistema de sala
 
Lea este tema para obtener información sobre cómo implementar Skype room system en un entorno que tiene varias versiones de Skype Empresarial Server y Lync Server.
  
## <a name="migration-considerations"></a>Consideraciones de migración

En esta sección se proporcionan instrucciones si va a implementar Skype room system en un entorno de varios grupos de servidores que incluye diferentes versiones de Skype Empresarial Server o Lync Server. 
  
El componente replicador de usuarios (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos back-end SQL Server Lync Server. Solo la UR de Lync Server 2013 es consciente de Skype room system. La UR en versiones anteriores de Lync Server y Office Communications Server no detecta los atributos de Active Directory que designan objetos LRS y, por lo tanto, no los conocía. 
  
Si una cuenta del sistema de sala de Skype intenta iniciar sesión en Lync y realiza la detección automática en función del registro SRV o dns, busque un registro A, y si esas cuentas apuntan a una versión anterior de Lync Server o Office Communications Server, LRS recibirá una respuesta 404 No encontrada del grupo heredado. El grupo heredado no podrá redirigir el sistema de Skype a su grupo de servidores principal de Lync Server 2013. 
  
Puede solucionar este problema con las siguientes opciones: 
  
- Apunte el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) al grupo de servidores de Lync Server 2013.
    
- Si la primera opción no es posible, debe configurar manualmente LRS y proporcionar la dirección del grupo de servidores de Lync Server 2013 configurándose directamente en la aplicación de consola del sistema de sala Skype. 
    
- Si Skype room system se implementa fuera de la red corporativa y se ha implementado y configurado un servidor perimetral de Lync para que apunte a un grupo o director heredado, se requiere un sitio de servidor perimetral secundario, que apunte al grupo de servidores de Lync Server 2013. Consulte la documentación de implementación del servidor perimetral para obtener más información acerca de la implementación de un servidor perimetral secundario. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype Interoperabilidad del sistema de sala con un grupo de servidores de Lync Server 2010

Durante la migración, si un usuario que se encuentra en un grupo de servidores de Lync Server 2010 programa una reunión e invita a la cuenta del sistema de salas de Skype, el cliente del sistema de salas de Skype tendrá una funcionalidad limitada mientras asiste a la reunión. 
  
Cuando el cliente Skype Room System se une a una llamada de conferencia programada que ha sido organizada por un usuario que se encuentra en Lync Server 2010, Skype Room System tiene las siguientes limitaciones en la reunión: 
  
- Skype El sistema de sala no puede mostrar la galería de vídeos de varias vistas.
    
- Si el Skype del sistema de sala es el moderador, no puede aplicar bloqueo de vídeo a los participantes.
    
- Skype El sistema de sala no puede mostrar una resolución de vídeo de 1080p (entrante o saliente), incluso si la directiva de conferencia de Lync Server 2013 lo permite, debido a lo siguiente: 
    
  - Lync Server 2010 no admite la resolución de 1080p.
    
  - Skype El sistema de sala siempre está limitado por la directiva de conferencia del organizador para la resolución de vídeo. Por lo tanto, incluso si el grupo de lync 2010 admite una resolución de 720p, Skype Room System no podrá aprovechar la resolución de 720p siempre que la directiva del organizador no la admita. 
    
- Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reuniones y se silencian automáticamente para evitar el eco en la sala de reuniones física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.
    
- Existen limitaciones en el rendimiento del uso compartido de escritorio para reuniones hospedadas en Lync Server 2010.
    
- Los usuarios no podrán unirse a reuniones privadas (restringidas) hospedadas en Lync 2010 con Skype room system.
    


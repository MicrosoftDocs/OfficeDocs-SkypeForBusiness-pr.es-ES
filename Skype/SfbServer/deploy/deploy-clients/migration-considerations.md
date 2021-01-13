---
title: Consideraciones sobre la migración del Sistema de sala de Skype
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
description: Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno que tiene varias versiones de Skype Empresarial Server y Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805790"
---
# <a name="skype-room-system-migration-considerations"></a>Consideraciones sobre la migración del Sistema de sala de Skype
 
Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno que tiene varias versiones de Skype Empresarial Server y Lync Server.
  
## <a name="migration-considerations"></a>Consideraciones de migración

En esta sección se proporcionan instrucciones para implementar el Sistema de sala de Skype en un entorno de varios grupos de servidores que incluya diferentes versiones de Skype Empresarial Server o Lync Server. 
  
El componente replicador de usuarios (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos back-end SQL Server lync Server. Solo la UR de Lync Server 2013 es consciente de los objetos del Sistema de sala de Skype. El UR de versiones anteriores de Lync Server y Office Communications Server no detecta los atributos de Active Directory que designan objetos LRS y, por lo tanto, no los conocía. 
  
Si una cuenta del Sistema de sala de Skype intenta iniciar sesión en Lync y realiza la detección automática en función del registro SRV o del registro A de DNS, y si esas cuentas apuntan a una versión anterior de Lync Server u Office Communications Server, LRS recibirá una respuesta 404 No encontrado del grupo heredado. El grupo heredado no podrá redirigir el Sistema de sala de Skype a su grupo principal de Lync Server 2013. 
  
Puede solucionar este problema con las siguientes opciones: 
  
- Apunte el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) al grupo de servidores de Lync Server 2013.
    
- Si la primera opción no es posible, debe configurar manualmente LRS y proporcionar la dirección del grupo de lync Server 2013 configurándose directamente en la aplicación de consola del Sistema de sala de Skype. 
    
- Si el Sistema de sala de Skype se implementa fuera de la red corporativa y se ha implementado y configurado un servidor perimetral de Lync para que apunte a un grupo o director heredado, se requiere un sitio secundario del servidor perimetral, que apunta al grupo de servidores de Lync Server 2013. Consulte la documentación de implementación del servidor perimetral para obtener más información acerca de la implementación de un servidor perimetral secundario. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilidad del sistema de sala de Skype con un grupo de servidores de Lync Server 2010

Durante la migración, si un usuario que se encuentra en un grupo de Lync Server 2010 programa una reunión e invita a la cuenta del Sistema de salas de Skype, el cliente del Sistema de salas de Skype tendrá una funcionalidad limitada mientras asiste a la reunión. 
  
Cuando el cliente del Sistema de salas de Skype se une a una llamada de conferencia programada organizada por un usuario que se encuentra en Lync Server 2010, el Sistema de salas de Skype tiene las siguientes limitaciones en la reunión: 
  
- El Sistema de sala de Skype no puede mostrar la galería de vídeos de varias vistas.
    
- Si el cliente del Sistema de sala de Skype es el moderador, no puede aplicar bloqueo de vídeo a los participantes.
    
- El Sistema de sala de Skype no puede mostrar una resolución de vídeo de 1080p (entrante o saliente), incluso si la directiva de conferencia de Lync Server 2013 lo permite, debido a lo siguiente: 
    
  - Lync Server 2010 no admite la resolución de 1080p.
    
  - El Sistema de sala de Skype siempre está limitado por la directiva de conferencias del organizador para la resolución de vídeo. Por lo tanto, incluso si el grupo de Lync 2010 admite una resolución de 720p, el Sistema de sala de Skype no podrá aprovechar la resolución de 720p siempre que la directiva del organizador no la admita. 
    
- Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reuniones y se silencian automáticamente para evitar eco en la sala de reuniones física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.
    
- Existen limitaciones en el rendimiento del uso compartido de escritorio para las reuniones hospedadas en Lync Server 2010.
    
- Los usuarios no podrán unirse a reuniones privadas (restringidas) hospedadas en Lync 2010 con el Sistema de salas de Skype.
    


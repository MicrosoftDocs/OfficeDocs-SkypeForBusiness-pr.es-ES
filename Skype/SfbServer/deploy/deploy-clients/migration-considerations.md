---
title: Consideraciones acerca de la migración del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno con varias versiones de Skype empresarial Server y Lync Server.
ms.openlocfilehash: 6524a7312644ec306185b952caf17818d29344af
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774678"
---
# <a name="skype-room-system-migration-considerations"></a>Consideraciones acerca de la migración del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno con varias versiones de Skype empresarial Server y Lync Server.
  
## <a name="migration-considerations"></a>Consideraciones acerca de la migración

Esta sección le proporciona instrucciones si va a implementar el sistema de salas de Skype en un entorno de varios grupos que incluye distintas versiones de Skype empresarial Server o Lync Server. 
  
El componente Replicador de usuario (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos de SQL Server del back-end de Lync Server. Solo el UR de Lync Server 2013 tiene constancia de los objetos de sistema de la sala de Skype. En anteriores versiones de Lync Server y Office Communications, el replicador de usuario no detecta los atributos de Active Directory que designan los objetos LRS y, por consiguiente, no los reconoce. 
  
Si una cuenta del sistema de Skype Room intenta iniciar sesión en Lync y realiza un descubrimiento automático basado en un registro SRV o DNS búsqueda de registros, y si esas cuentas apuntan a una versión anterior de Lync Server o de Office Communications Server, LRS recibirá una respuesta 404 no encontrada de  Grupo heredado. El grupo heredado no podrá redirigir el sistema de la sala de Skype a su grupo de inicio de Lync Server 2013. 
  
Puede abordar este problema con las siguientes opciones: 
  
- Señale el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) en el grupo de Lync Server 2013.
    
- Si la primera opción no es posible, debe configurar manualmente LRS y proporcionar la dirección de la agrupación de Lync Server 2013, configurándolo directamente en la aplicación de consola del sistema de salas de Skype. 
    
- Si el sistema de salas de Skype se implementa fuera de la red corporativa y se ha implementado y configurado un servidor perimetral de Lync para apuntar a un grupo o director heredado, se necesita un sitio de servidor perimetral secundario, que apunta al grupo de 2013 de Lync Server. Consulte la documentación de la implementación del servidor perimetral si desea obtener más información acerca de la implementación de un servidor perimetral secundario. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilidad de sistemas de salas de Skype con un grupo de 2010 de Lync Server

Durante la migración, si un usuario alojado en un grupo de servidores de Lync Server 2010 programa una reunión e invita a la cuenta del sistema de salas de Skype, el cliente del sistema de la sala de Skype dispondrá de una funcionalidad limitada mientras asiste a la reunión. 
  
Cuando el cliente del sistema de salas de Skype se une a una llamada de conferencia programada que ha sido organizada por un usuario alojado en Lync Server 2010, el sistema de salas de Skype tiene las siguientes limitaciones de la reunión: 
  
- El sistema de salas de Skype no puede mostrar la galería de vídeos de varias vistas.
    
- Si el cliente del sistema de Skype Room es el moderador, no puede aplicar el bloqueo de video a los participantes.
    
- El sistema de salas de Skype no puede mostrar resolución de video 1080p (entrante o saliente), incluso si la Directiva de conferencia de Lync Server 2013 lo permite, debido a lo siguiente: 
    
  - Lync Server 2010 no admite la resolución de 1080p.
    
  - El sistema de salas de Skype siempre está limitado por la política de conferencia del organizador para la resolución de video. Por lo tanto, incluso si el grupo de Lync 2010 admite la resolución 720p, el sistema de salas de Skype no podrá aprovechar la resolución de 720p mientras la Directiva del organizador no lo admita. 
    
- Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reunión y desactivan el audio automáticamente para evitar eco en la sala de reunión física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.
    
- Existen limitaciones en el rendimiento de escritorio compartido para reuniones hospedadas en Lync Server 2010.
    
- Los usuarios no podrán unirse a reuniones privadas (restringidas) hospedadas en Lync 2010 con el sistema de salas de Skype.
    


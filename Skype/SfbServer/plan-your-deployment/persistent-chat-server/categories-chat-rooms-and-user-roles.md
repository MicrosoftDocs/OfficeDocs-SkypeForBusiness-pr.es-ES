---
title: Categorías de chat persistente, salones de chat y roles de usuario en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Resumen: Lea este tema para obtener información sobre las categorías, los salones de chat y los roles de usuario y administrador para el servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: bffdebdf6bbb57165b902026083de5628cdbc404
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418472"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorías de chat persistente, salones de chat y roles de usuario en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre las categorías, los salones de chat y los roles de usuario y administrador para el servidor de chat persistente en Skype empresarial Server 2015.
  
Puede controlar el acceso a los salones de chat creando categorías de salones de chat, especificando el acceso a las categorías y a los salones de chat de las categorías. También puede especificar distintos roles de administrador. En este tema se describen los siguientes elementos: 
  
- Categorías para organizar salones de chat
    
- Salones de chat y roles de usuario
    
- Roles de administrador

> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorías para organizar salones de chat

Las categorías le permiten organizar los salones de chat y controlar los usuarios y los grupos que pueden crear o unirse a los salones de chat de dentro de estas categorías. Cada categoría tiene propiedades asociadas que determinan las opciones disponibles para los salones de chat de la categoría. Puede controlar el acceso a una determinada categoría especificando si un usuario tiene acceso permitido o denegado.
  
El principio básico del concepto de miembros permitidos/denegados son las zonas de protección. Por ejemplo, en las instituciones financieras y bancarias, es muy común disponer de límites de protección que impidan a los comerciantes y analistas compartir comunicaciones al implementar directivas y convenciones. Para abordar este requisito, el administrador puede crear categorías de manera que una categoría admita la creación y el uso de salones por parte de los comerciantes, mientras que la otra admita la creación y el uso de salones por parte de los analistas. No se pueden agregar usuarios como miembros del salón si la categoría principal lo prohíbe.
  
> [!IMPORTANT]
> Los miembros permitidos y rechazados de una categoría no son iguales a los de un rol de **miembro** , que se aplica a un salón de chat persistente. las búsquedas de > muestran todos los salones de chat abiertos y cerrados en los que el usuario está en la lista de miembros permitidos y denegados. Los salones secretos no se muestran a menos que el usuario que efectúa la búsqueda sea miembro del salón secreto. De este modo, el usuario solo puede buscar salones de los que sea miembro o aquellos a los que pueda solicitar ser miembro. 
  
## <a name="chat-rooms-and-user-roles"></a>Salones de chat y roles de usuario

Además de los miembros permitidos y denegados para las categorías, también puede controlar el acceso a los salones de chat especificando los roles de usuario siguientes: creador, jefe, miembro y moderador.
  
- **Autor**: usuarios que tienen permiso para crear salones de chat. Estos usuarios figuran en la lista de autores de determinadas categorías: pueden crear salones de chat en sus categorías, asignar miembros en función de la categoría y asignar administradores del salón de chat. El usuario que cree un salón de chat se agregará automáticamente como administrador del salón.
    
    > [!NOTE]
    > Los autores solo están autorizados a crear salones de chat. La promoción automática al rol de Administrador es la que permite al Autor delimitar las pertenencias a grupos, etc., en los servicios de chat creados. 
  
    Este rol ofrece la opción de controlar quién crea salones de chat en su organización, lo cual resulta de especial utilidad si desea administrar de forma centralizada creación de salones de chat para garantizar el cumplimiento de directivas y convenciones, con la consiguiente delegación de la administración de la sala de chat a los usuarios de la organización.
    
- **Administrador**: usuarios que administran las propiedades de un salón de chat. Los administradores de salones de chat pueden modificar la lista de miembros (agregar o quitar miembros), así como la lista de administradores de la sala de chat (agregar y quitar administradores). Los administradores de los salones de chat pueden agregarse a sí mismos a la lista de miembros o de moderadores (en salones de auditorio) para participar en el salón de chat. También pueden deshabilitar salones de chat (los administradores pueden consultar los salones de chat deshabilitados para eliminarlos de forma permanente). Los administradores pueden cambiar todas las propiedades de los salones de chat, excepto la categoría del salón de chat. Solo el administrador de chat persistente puede cambiar la categoría después de que se haya creado el salón de chat.
    
    > [!IMPORTANT]
    > En caso de que el administrador también sea autor en otra categoría, estará autorizado a cambiar la categoría a otra en la que esté autorizado a crear salones de chat. 
  
- **Miembro**: usuarios que son miembros de un salón de chat. Estos usuarios pueden ver los salones de chat en el directorio (incluso si el salón de chat es secreto), así como suscribirte al salón de chat (incluidas las opciones de metadatos como, por ejemplo, los mensajes no leídos, los filtros de ego y los filtros de palabras clave), y participar en el salón de chat (puede publicar, a menos que el salón es un salón de auditorio en el que solo los moderadores pueden publicar, obtener contenido y buscar). Los usuarios que no son miembros del salón de chat pueden buscar el salón de chat si están en la lista de miembros permitidos de la categoría, pero necesitan solicitar acceso para que se unan a estos salones de chat y tengan acceso al contenido. (No hay acceso ni aprobaciones de solicitudes integradas en el sistema; estas se realizan externamente por correo electrónico, teléfono u otras formas de contacto).
    
- **Moderador**: usuarios que pueden publicar contenido en un salón de auditorio.
    
## <a name="administrator-roles"></a>Roles de administrador

A continuación se muestran los roles de administrador para el servidor de chat persistente:
  
- **Administrador de chat persistente**: el rol de administrador de chat persistente puede administrar salones de chat (para modificar todas las propiedades, entre las que se incluyen Membership, Managers, categorías, marcar salas como deshabilitadas), así como crear y administrar categorías de salones de chat que definan quién permite crear y tener acceso a salones de chat. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Los administradores también pueden modificar y administrar la configuración de los chats persistentes (propiedades de grupo, configuración global y configuración de cumplimiento) y también pueden planear e implementar la migración desde una implementación de servidor de chat de grupo anterior a Skype empresarial Server 2015 Servidor de chat persistente.
    
    Los administradores de chats persistentes pueden administrar el servidor de chat persistente mediante cmdlets de Windows PowerShell de forma remota (es decir, desde un equipo distinto del servidor de chat persistente). El servidor de chat persistente comprueba que el administrador de chats persistentes sea miembro del grupo local RTC local Administrators en el servidor front-end del servidor de chat persistente.
    
- **Administrador de Skype empresarial 2015**: administrador general de la empresa de Skype empresarial Server 2015 responsable de la implementación.
    
- **Administrador de operaciones**: usuario responsable de la administración de las operaciones diarias.
    
- **Socios y desarrolladores externos**: desarrolladores externos que amplían el sistema, sobre todo al proporcionar soluciones de zonas de protección para conversaciones de grupos, herramientas de cumplimiento, clientes móviles/web y marcos de trabajo para el desarrollo de robots.
    
## <a name="for-more-information"></a>Para más información

Para más información sobre la configuración y la administración de los salones de chat y los roles de usuario, consulte los siguientes temas:
  
- [Crear un administrador de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/categories.md)
    
- [Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/chat-rooms.md)
    


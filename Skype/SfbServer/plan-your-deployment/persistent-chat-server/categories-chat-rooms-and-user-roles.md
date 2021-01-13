---
title: Categorías de chat persistente, salas de chat y roles de usuario en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Resumen: lea este tema para obtener información sobre categorías, salas de chat y roles de usuario y administrador para el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 50b5cd6df9cbaa8958d0f1036fe5474f2d7e47dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834570"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorías de chat persistente, salas de chat y roles de usuario en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre categorías, salas de chat y roles de usuario y administrador para el servidor de chat persistente en Skype Empresarial Server 2015.
  
Puede controlar el acceso a los salón de chat creando categorías de salón de chat y, a continuación, especificando el acceso a categorías y salas de chat dentro de las categorías. También puede especificar varios roles de administrador. En este tema se describe lo siguiente: 
  
- Categorías para organizar los salón de chat
    
- Salas de chat y roles de usuario
    
- Funciones de administrador

> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorías para organizar los salón de chat

Las categorías permiten organizar los salón de chat y controlar qué usuarios y grupos pueden crear o unirse a los salón de chat dentro de dichas categorías. Cada categoría tiene propiedades asociadas que determinan las opciones disponibles para los salón de chat dentro de la categoría. Puede controlar el acceso a una categoría determinada especificando si un usuario tiene acceso permitido o denegado.
  
La razón principal para el concepto de miembros permitidos y denegados son las paredes de ético. Por ejemplo, en las instituciones financieras y bancarias, es muy común disponer de límites de protección que impidan a los comerciantes y analistas compartir comunicaciones durante la implementación de directivas y convenciones. Para ello, el administrador puede crear categorías de manera que una categoría admita la creación y el uso de salones por parte de los comerciantes, mientras que la otra admita la creación y el uso de salones por parte de los analistas. Los usuarios no se pueden agregar como miembros de un salón de chat si la categoría principal lo impide.
  
> [!IMPORTANT]
> Los miembros permitidos y denegados de una categoría no son los mismos que un rol de miembro, que se aplica **a** un salón de chat persistente.Las búsquedas de > muestran todos los salón de chat abiertos y cerrados para los que el usuario que realiza la búsqueda se encuentra en la lista de miembros permitidos y denegados. Los salones secretos no se muestran a menos que el usuario que realiza la búsqueda sea miembro del salón secreto. De este modo, el usuario solo puede buscar salones de los que sea miembro o aquellos a los que pueda solicitar ser miembro. 
  
## <a name="chat-rooms-and-user-roles"></a>Salas de chat y roles de usuario

Además de los miembros permitidos y denegados para las categorías, también puede controlar el acceso a los salas de chat especificando los siguientes roles de usuario: Creador, Administrador, Miembro y Moderador.
  
- **Creador:** usuarios que tienen permiso para crear salas de chat. Estos usuarios figuran en la lista de autores de determinadas categorías: pueden crear salones de chat en sus categorías, asignar miembros en función de la categoría y asignar administradores del salón de chat. El usuario que cree un salón de chat se agregará automáticamente como administrador del salón.
    
    > [!NOTE]
    > Los autores solo están autorizados a crear salones de chat. La promoción automática al rol de Administrador es la que permite al Autor delimitar las pertenencias a grupos, etc., en los servicios de chat creados. 
  
    Este rol ofrece la opción de controlar quién crea salones de chat en su organización, lo cual resulta de especial utilidad si desea administrar de forma centralizada creación de salones de chat para garantizar el cumplimiento de directivas y convenciones, con la consiguiente delegación de la administración de la sala de chat a los usuarios de la organización.
    
- **Administrador**: usuarios que administran las propiedades de un salón de chat. Los administradores de salones de chat pueden modificar la lista de miembros (agregar o quitar miembros), así como la lista de administradores de la sala de chat (agregar y quitar administradores). Los administradores de los salones de chat pueden agregarse a sí mismos a la lista de miembros o de moderadores (en salones de auditorio) para participar en el salón de chat. También pueden deshabilitar salones de chat (los administradores pueden consultar los salones de chat deshabilitados para eliminarlos de forma permanente). Los administradores pueden cambiar todas las propiedades de los salones de chat, excepto la categoría del salón de chat. Solo el administrador de chat persistente puede cambiar la categoría después de haber creado el salón de chat.
    
    > [!IMPORTANT]
    > En caso de que el administrador también sea autor en otra categoría, estará autorizado a cambiar la categoría a otra en la que esté autorizado a crear salones de chat. 
  
- **Miembro:** usuarios que son miembros de un salón de chat. Estos usuarios pueden ver los salas de chat en el directorio (incluso si el salón de chat es secreto), así como suscribirse al salón de chat (incluidas las opciones de metadatos como mensajes no leídos, filtros ego y filtros de palabras clave) y participar en el salón de chat (puede publicar, a menos que el salón sea un salón de auditorio donde solo los presentadores pueden publicar, obtener contenido y buscar). Los usuarios que no son miembros del salón de chat pueden buscar el salón de chat si se encuentran en la lista de miembros permitidos de la categoría, pero necesitan solicitar acceso para unirse a estos salón de chat para acceder al contenido. (No hay ninguna solicitud de acceso o aprobaciones integradas en el sistema; se realizan externamente por correo electrónico, teléfono u otras formas de contacto).
    
- **Moderador**: usuarios que pueden publicar contenido en un salón de auditorio.
    
## <a name="administrator-roles"></a>Funciones de administrador

Los siguientes son roles de administrador para el servidor de chat persistente:
  
- Administrador de chat **persistente:** el rol de administrador de chat persistente puede administrar los salón de chat (modificar todas las propiedades, incluidas la pertenencia, los administradores, las categorías, marcar los salón como deshabilitados), así como crear y administrar categorías de salón de chat que definan quién puede crear y tener acceso a los salón de chat. Los administradores también pueden marcar salones de chat como deshabilitados y eliminar los salones de chat que ya no estén activos. Los administradores no están sujetos a las restricciones que tienen los Autores o los Miembros permitidos. Los administradores pueden crear cualquier tipo de salón de chat y agregarse a sí mismos como miembros de cualquier salón de chat. Los administradores también pueden modificar y administrar la configuración de chat persistente (propiedades de grupo, configuración global y configuración de cumplimiento) y también pueden planear e implementar la migración desde una implementación anterior del servidor de chat en grupo al servidor de chat persistente de Skype Empresarial Server 2015.
    
    Los administradores de chat persistente pueden administrar el servidor de chat persistente mediante cmdlets Windows PowerShell de forma remota (es decir, desde un equipo que no sea el servidor de chat persistente). El servidor de chat persistente comprueba que el administrador de chat persistente es miembro del grupo local de administradores locales de RTC en el servidor front-end del servidor de chat persistente.
    
- **Administrador de Skype Empresarial Server 2015:** administrador general de la empresa para Skype Empresarial Server 2015 responsable de la implementación.
    
- **Administrador de operaciones**: usuario responsable de la administración de las operaciones diarias.
    
- **Socios y desarrolladores externos**: desarrolladores externos que amplían el sistema, sobre todo al proporcionar soluciones de zonas de protección para conversaciones de grupos, herramientas de cumplimiento, clientes móviles/web y marcos de trabajo para el desarrollo de robots.
    
## <a name="for-more-information"></a>Más información

Para obtener más información acerca de cómo configurar y administrar los salas de chat y los roles de usuario, consulte los siguientes temas:
  
- [Crear un administrador de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/categories.md)
    
- [Administrar los salón de chat en el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/chat-rooms.md)
    


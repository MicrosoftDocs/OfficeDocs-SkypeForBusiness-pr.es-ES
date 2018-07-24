---
title: Categorías de chat persistente, salones de chat y roles de usuario en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Resumen: Lea este tema para obtener más información sobre las categorías, salones de chat y roles de usuario y Administrador de servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 83aa18d427c97ba54dcc3c66e684a4e13ed0c5df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983780"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorías de chat persistente, salones de chat y roles de usuario en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener más información sobre las categorías, salones de chat y roles de usuario y Administrador de servidor de Chat persistente en Skype para Business Server 2015.
  
Puede controlar el acceso a los salones de chat creando categorías de salones de chat, especificando el acceso a las categorías y a los salones de chat de las categorías. También puede especificar distintos roles de administrador. En este tema se describen los siguientes elementos: 
  
- Categorías para organizar salones de chat
    
- Salones de chat y roles de usuario
    
- Roles de administrador

> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorías para organizar salones de chat

Las categorías le permiten organizar los salones de chat y controlar los usuarios y los grupos que pueden crear o unirse a los salones de chat de dentro de estas categorías. Cada categoría tiene propiedades asociadas que determinan las opciones disponibles para los salones de chat de la categoría. Puede controlar el acceso a una determinada categoría especificando si un usuario tiene acceso permitido o denegado.
  
El principio básico del concepto de miembros permitidos/denegados son las zonas de protección. Por ejemplo, en las instituciones financieras y bancarias, es muy común disponer de límites de protección que impidan a los comerciantes y analistas compartir comunicaciones al implementar directivas y convenciones. Para abordar este requisito, el administrador puede crear categorías de manera que una categoría admita la creación y el uso de salones por parte de los comerciantes, mientras que la otra admita la creación y el uso de salones por parte de los analistas. No se pueden agregar usuarios como miembros del salón si la categoría principal lo prohíbe.
  
> [!IMPORTANT]
> Los miembros permitidos y denegados en una categoría no son los mismos que una función de **miembro** , que se aplica a un salón de Chat persistente. > búsquedas mostrar todos los salones de chat abiertos y cerrados para que el usuario que realiza la búsqueda se encuentra en la lista de miembros permitidos y denegados. Los salones secretos no se muestran a menos que el usuario que efectúa la búsqueda sea miembro del salón secreto. De este modo, el usuario solo puede buscar salones de los que sea miembro o aquellos a los que pueda solicitar ser miembro. 
  
## <a name="chat-rooms-and-user-roles"></a>Salones de chat y roles de usuario

Además de permitidos y miembros denegados para las categorías, también puede controlar el acceso a salones de chat mediante la especificación de los siguientes roles de usuario: autor, administrador, miembro y moderador.
  
- **Autor**: usuarios que tienen permiso para crear salones de chat. Estos usuarios figuran en la lista de autores de determinadas categorías: pueden crear salones de chat en sus categorías, asignar miembros en función de la categoría y asignar administradores del salón de chat. El usuario que cree un salón de chat se agregará automáticamente como administrador del salón.
    
    > [!NOTE]
    > Los autores solo están autorizados a crear salones de chat. La promoción automática al rol de Administrador es la que permite al Autor delimitar las pertenencias a grupos, etc., en los servicios de chat creados. 
  
    Este rol ofrece la opción de controlar quién crea salones de chat en su organización, lo cual resulta de especial utilidad si desea administrar de forma centralizada creación de salones de chat para garantizar el cumplimiento de directivas y convenciones, con la consiguiente delegación de la administración de la sala de chat a los usuarios de la organización.
    
- **Administrador**: usuarios que administran las propiedades de un salón de chat. Los administradores de salones de chat pueden modificar la lista de miembros (agregar o quitar miembros), así como la lista de administradores de la sala de chat (agregar y quitar administradores). Los administradores de los salones de chat pueden agregarse a sí mismos a la lista de miembros o de moderadores (en salones de auditorio) para participar en el salón de chat. También pueden deshabilitar salones de chat (los administradores pueden consultar los salones de chat deshabilitados para eliminarlos de forma permanente). Los administradores pueden cambiar todas las propiedades de los salones de chat, excepto la categoría del salón de chat. Sólo el Administrador de Chat persistente puede cambiar la categoría después de haber creado el salón de chat.
    
    > [!IMPORTANT]
    > En caso de que el administrador también sea autor en otra categoría, estará autorizado a cambiar la categoría a otra en la que esté autorizado a crear salones de chat. 
  
- **Miembro**: los usuarios que son miembros de un salón de chat. Estos usuarios pueden ver los salones de chat en el directorio (incluso si el salón de chat es secreto), así como suscribirse a la sala de chat (incluidas las opciones de metadatos, como los mensajes no leídos, ego filtros y filtros de palabras clave) y participar en el salón de chat (puede registrar, a menos que la sala es un salón de auditorio donde sólo los moderadores pueden publicar, obtener el contenido y buscar). Los usuarios que no son miembros del salón de chat pueden si están en la lista de miembros permitidos de la categoría de búsqueda para el salón de chat, pero necesitará solicitar acceso para unirse a estos salones de chat para tener acceso al contenido. (No hay ninguna solicitud de acceso o integradas en el sistema de aprobaciones; estos se realizan externamente por otras formas de contacto, teléfono o correo electrónico).
    
- **Moderador**: usuarios que pueden publicar contenido en un salón de auditorio.
    
## <a name="administrator-roles"></a>Roles de administrador

Los siguientes son roles de administrador para el servidor de Chat persistente:
  
- **Administrador de Chat persistente**: rol de administrador de Chat persistente el puede administrar salones de chat (modificar todas las propiedades incluida la pertenencia, los administradores, categorías, salones de marca como deshabilitado), así como crear y administrar categorías de salón de chat que definen quién puede crear y tener acceso a salones de chat. Los administradores también pueden marcar salones de chat como deshabilitados y eliminar los salones de chat que ya no estén activos. Los administradores no están sujetos a las restricciones que tienen los Autores o los Miembros permitidos. Los administradores pueden crear cualquier tipo de salón de chat y agregarse a sí mismos como miembros de cualquier salón de chat. Los administradores pueden también modificar y administrar la configuración de Chat persistente (propiedades de grupo de servidores, la configuración global y configuración de cumplimiento) y puede también planear e implementar la migración de una implementación de servidor de conversaciones en grupo más antiguos a Skype para Business Server 2015 Servidor de Chat persistente.
    
    Los administradores de charla persistente son capaces de administrar el servidor de Chat persistente mediante el uso de forma remota los cmdlets de Windows PowerShell (es decir, desde un equipo distinto del servidor de Chat persistente). Servidor de Chat persistente comprueba que el Administrador de Chat persistente es un miembro del grupo local de administrador Local de RTC en la Persistent Chat Server servidor Front-End.
    
- **Skype para Business Server 2015 administrador**: administrador empresarial general de Skype para Business Server 2015 responsable de la implementación.
    
- **Administrador de operaciones**: usuario responsable de la administración de las operaciones diarias.
    
- **Socios y desarrolladores externos**: desarrolladores externos que amplían el sistema, sobre todo al proporcionar soluciones de zonas de protección para conversaciones de grupos, herramientas de cumplimiento, clientes móviles/web y marcos de trabajo para el desarrollo de robots.
    
## <a name="for-more-information"></a>Para más información

Para más información sobre la configuración y la administración de los salones de chat y los roles de usuario, consulte los siguientes temas:
  
- [Crear un administrador de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/categories.md)
    
- [Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/chat-rooms.md)
    


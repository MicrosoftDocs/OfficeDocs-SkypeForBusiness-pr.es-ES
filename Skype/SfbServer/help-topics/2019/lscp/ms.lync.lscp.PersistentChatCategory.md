---
title: Categoría de chat persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: Puede usar la sección categorías de la página de Chat persistente para configurar categorías. Una categoría de salón de Chat en grupo es una estructura lógica para la organización de los salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que se pueden crear o unir a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
ms.openlocfilehash: e3daf85b6d20fcf5f56681dbda02b50d7122d4c1
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="persistent-chat-category"></a>Categoría de chat persistente
 
Puede usar la sección **Categoría** de la página **Chat persistente** para configurar categorías. Una categoría de salón de Chat en grupo es una estructura lógica para la organización de los salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que se pueden crear o unir a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
  
Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos, como el _nombre_ y _Descripción_. Además, la categoría tiene las propiedades que pueden establecer para controlar el comportamiento de los salones de chat que pertenecen a ella, por ejemplo, si los salones de chat permitir _invitaciones_ o _Cargas de archivos_, o contienen _El historial de Chat_.
  
Para crear una nueva categoría, vea [Administrar categorías en el servidor de Chat persistente en Skype para Business Server 2015](../../../manage/persistent-chat/categories.md). Si es un administrador de Chat persistente, puede crear categorías mediante el panel de control o los cmdlets de Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Categoría** puede realizar las siguientes tareas:
  
- Crear una categoría o editarla
    
- Mover un salón de chat de una categoría a otra
    
- Eliminar un salón de chat o una categoría
    
## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorías para salones de chat

1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator o CsAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Categoría**.
    
    Para implementaciones de varios grupos de servidores de Chat persistente, seleccione el grupo adecuado de la lista desplegable.
    
4. En la página **Categoría**, haga clic en **Nuevo** o en **Editar**.
    
5. En **Seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de Chat persistente en el que debe crearse la categoría. El servicio es el servidor de Chat persistente pertenece el grupo de servidores que el Chat persistente (cliente) se utiliza para identificar que la categoría del grupo de servidores. Una categoría puede pertenecer al grupo de un solo servidor de Chat persistente y no se mueve a otro equipo o compartida con otro grupo de servidores.
    
6. En **Nueva categoría**, haga lo siguiente:
    
1. En **Nombre**, especifique un nombre para la nueva categoría de salón.
    
2. En **Descripción**, proporcione una descripción detallada sobre la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
3. Para controlar si las invitaciones se pueden habilitar para salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar invitaciones**. Si está activada, los salones de esta categoría puedan tener invitaciones activas o inactivas y, si está desactivada, el salón de esta categoría no puede tener invitaciones. Si una sala tiene invitaciones en, cuando se agrega un nuevo miembro a un salón, navegará Obtiene una notificación de la nueva sala en su cliente de Chat persistente.
    
4. Para controlar las cargas de archivos en salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si está activada, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos y, si no está activada, los salones de esta categoría no pueden tener cargas de archivos.
    
    > [!IMPORTANT]
    > Esta configuración se aplica en el servidor debido a que las aplicaciones personalizadas o anterior conversaciones en grupo de los clientes que usan Office Communications Server 2007 R2 servidor conversaciones en grupo o Lync Server 2010, conversaciones en grupo pueden enviar archivos a un salón. El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación de Lync 2013 puro o cliente de Lync 2013, no es posible enviar archivos en un salón de chat Persistent Chat Server. 
  
5. Para controlar el historial de chat, active o desactive la casilla de verificación **Habilitar el historial de chat** . Si está activada, los salones de chat serán persistentes; en caso contrario, los mensajes de chats no persisten. Si el cumplimiento está habilitado, los chats del salón se guardarán en consecuencia, pero los usuarios no podrán tener acceso a los mensajes antiguos. Esta opción se puede usar para salones designados para colaboraciones en tiempo real, ad hoc que no es necesario que se va a conservar el historial de chat.
    
7. En **Editar categoría**, haga lo siguiente:
    
  - En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otras entidades de seguridad de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas y así sucesivamente) que se permiten que se agregará como miembros de los salones de chat que pertenecen a la categoría. Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).
    
  - En **pertenencia**, en la sección **miembros denegados** , agregue o quite usuarios y otras entidades de seguridad de Active Directory asociados con miembros denegados del salón.
    
  - En **pertenencia**, en la sección **los creadores** , agregue o quite usuarios y otras entidades de seguridad de Active Directory asociados con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de los salones de chat.
    
8. Haga clic en **Confirmar**.
    
### 

Para obtener información detallada sobre las características de servidor de Chat persistente y funciones, vea [Planear Persistent Chat Server in Skype para Business Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server en Skype para Business Server 2015](../../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Administrar Persistent Chat Server en Skype para Business Server 2015](../../../manage/persistent-chat/persistent-chat.md).
  


---
title: Categoría de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: Puede usar la sección Categoría de la página chat persistente para configurar categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar los salón de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
ms.openlocfilehash: f7718a5d6cc92c0036f28843d21c4c349c0bc38d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803750"
---
# <a name="persistent-chat-category"></a>Categoría de chat persistente
 
Puede usar la sección **Categoría de** la **página chat** persistente para configurar categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar los salón de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
  
Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos, como _Nombre_ y _Descripción._ Además, la categoría tiene propiedades que se pueden establecer para controlar el comportamiento de los  salón de chat que le pertenecen, como si los salón de chat permiten invitaciones o cargas de _archivos,_ o contienen historial de _chat._
  
Para crear una nueva categoría, consulte Administrar categorías en el servidor [de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/categories.md). Si es un administrador de chat persistente, puede crear categorías mediante el panel de control o los cmdlets Windows PowerShell usuario.
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Categoría**:
  
- Crear o editar una nueva categoría
    
- Mover un salón de chat de una categoría a otra
    
- Eliminar un salón de chat o una categoría
    
## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorías para salones de chat

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Categoría**.
    
    Para varias implementaciones de grupos de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.
    
4. En la página **Categoría**, haga clic en **Nueva** o **Editar**.
    
5. En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría. El servicio es el grupo de servidores de chat persistente que el chat persistente (cliente) usa para identificar a qué grupo pertenece la categoría. Una categoría solo puede pertenecer a un grupo de servidores de chat persistente y no se puede mover a otro, ni compartirse con otro grupo de servidores.
    
6. En **Nueva categoría**, haga lo siguiente:
    
7. En **Nombre**, especifique un nombre para el nuevo salón.
    
8. En  **Descripción**, proporcione una descripción detallada de la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
9. Para controlar si se pueden habilitar invitaciones para salones de chat, active o desactive la casilla **Habilitar invitaciones**. Si la activa, los salones de esta categoría pueden tener invitaciones activadas o desactivadas; si se desactiva, los salones de esta categoría no pueden tener invitaciones. Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación del nuevo salón en su cliente de chat persistente.
    
10. Para controlar las cargas de archivos en salones de chat que pertenezcan a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si se activa, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos; si se desactiva, los salones de esta categoría no pueden tener cargas de archivos.
    
     > [!IMPORTANT]
     > Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o clientes de chat en grupo anteriores que usan el servidor de chat en grupo de Office Communications Server 2007 R2 o Lync Server 2010, el chat en grupo puede publicar archivos en un salón. El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat del servidor de chat persistente. 
  
11. Para controlar el historial de chat, active o desactive la casilla Habilitar historial **de chat.** Si se activa, los salones de chat se vuelven persistentes; en caso contrario, los mensajes de chat no permanecen. Si se habilita el cumplimiento, los chats de los salones se guardarán en conformidad, pero los usuarios no podrán obtener acceso a los mensajes más antiguos. Esta opción se puede usar para salas designadas para colaboraciones ad hoc en tiempo real que no necesitan que se conserve el historial de chat.
    
12. En **Editar categoría**, haga lo siguiente:
    
    - En Pertenencia **,** en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de Servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otros) que puedan agregarse como miembros de los salón de chat que pertenecen a la categoría.  Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).
    
    - En **Pertenencia**, en la **sección Miembros** denegados, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con miembros denegados de la sala.
    
    - En **Pertenencia**, en la **sección Creadores,** agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.
    
13. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Vea también

Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  


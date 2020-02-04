---
title: Página principal de categoría de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: Puede usar la sección Categoría de la página Chat persistente para configurar categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que se pueden crear o unir a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
ms.openlocfilehash: 039286382e83d07bfa0c3aa2f88908748fb31ff2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699955"
---
# <a name="persistent-chat-category-main-page"></a>Página principal de categoría de chat persistente
 
Puede usar la sección **Categoría** de la página **Chat persistente** para configurar categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que se pueden crear o unir a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
  
Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos, como _el nombre_ y la _Descripción_. Además, la categoría tiene propiedades que pueden configurarse para controlar el comportamiento de los salones de chat que pertenecen a ella, por ejemplo, si los salones de chat permiten _invitaciones_ o _cargas de archivos_, o bien contienen _historial de conversaciones_.
  
Para crear una nueva categoría, consulte [administrar categorías en el servidor de chat persistente en Skype empresarial server 2015](../../manage/persistent-chat/categories.md). Si es un administrador de chat persistente, puede crear categorías con el panel de control o los cmdlets de Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Categoría** puede realizar las siguientes tareas:
  
- Crear una categoría o editarla
    
- Mover un salón de chat de una categoría a otra
    
- Eliminar un salón de chat o una categoría
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>Para configurar categorías para salas de chat persistentes

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. .
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Categoría**.
    
    Para varias implementaciones del grupo de servidores de chat persistentes, seleccione el grupo adecuado de la lista desplegable.
    
4. En la página **Categoría**, haga clic en **Nuevo** o en **Editar**.
    
5. En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría. El servicio es el grupo de servidores de chat persistente que usa el chat persistente (cliente) para identificar a qué grupo pertenece la categoría. Una categoría puede pertenecer a un único grupo de servidores de chat persistentes, no se puede mover a otro grupo o compartir con otro grupo.
    
6. En **Nueva categoría**, haga lo siguiente:
    
7. En **Nombre**, especifique un nombre para la nueva categoría de salón.
    
8. En **Descripción**, proporcione una descripción detallada sobre la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
9. Para controlar si las invitaciones se pueden habilitar para salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar invitaciones**. Si está activada, los salones de esta categoría puedan tener invitaciones activas o inactivas y, si está desactivada, el salón de esta categoría no puede tener invitaciones. Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación de la nueva sala en su cliente de chat persistente.
    
10. Para controlar las cargas de archivos en salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si está activada, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos y, si no está activada, los salones de esta categoría no pueden tener cargas de archivos.
    
11. Para controlar el historial de conversaciones, Active o desactive la casilla de verificación **Habilitar el historial de chat** . Si está activada, los salones de chat serán persistentes; en caso contrario, los mensajes de chats no persisten. Si el cumplimiento está habilitado, los chats del salón se guardarán en consecuencia, pero los usuarios no podrán tener acceso a los mensajes antiguos. Esta opción se puede usar para salas designadas para colaboraciones ad hoc y en tiempo real que no necesitan un historial de conversaciones.
    
12. En **Editar categoría**, haga lo siguiente:
    
    - En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otros principios de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que pueden agregarse como miembros de los salones de chat que pertenecen a la categoría. Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).
    
    - En **pertenencia**, en la sección **miembros denegados** , agregue o quite usuarios y otros principales de Active Directory asociados a miembros que se deniegan del salón.
    
    - En **pertenencia**, en la sección **creadores** , agregue o quite usuarios y otras entidades de Active Directory asociadas con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de los salones de chat.
    
13. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Vea también

Para obtener detalles sobre las funciones y características del servidor de chat persistentes, consulte [planear el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [implementar un servidor de chat persistente en skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [administrar el servidor de chat persistente en Skype empresarial Server 2015](../../manage/persistent-chat/persistent-chat.md).
  


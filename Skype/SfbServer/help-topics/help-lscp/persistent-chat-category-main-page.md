---
title: Página principal de categoría de chat persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: Puede usar la sección Categoría de la página Chat persistente para configurar categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar salas de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
ms.openlocfilehash: fbbfb0185b463a6f63bb9016b77e4539a003505e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836582"
---
# <a name="persistent-chat-category-main-page"></a>Página principal de categoría de chat persistente
 
Puede usar la sección **Categoría** de la **página Chat** persistente para configurar categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar salas de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.
  
Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos, como  _Name_ y _Description_. Además, la categoría tiene propiedades que se pueden establecer para controlar el comportamiento de los  salas de chat que pertenecen a ella, como si los salas de chat permiten invitaciones o cargas de archivos _o_ contienen historial de _chat._
  
Para crear una nueva categoría, vea [Manage categories in Persistent Chat Server in Skype Empresarial Server 2015](../../manage/persistent-chat/categories.md). Si es un administrador de chat persistente, puede crear categorías mediante el panel de control o los cmdlets Windows PowerShell usuario.
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Categoría**:
  
- Crear o editar una nueva categoría
    
- Mover un salón de chat de una categoría a otra
    
- Eliminar una categoría o un salón de chat
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>Para configurar categorías para los salas de chat persistente

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú** Inicio, seleccione Skype Empresarial Server Panel de control o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. .
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Categoría**.
    
    Para varias implementaciones de grupo de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.
    
4. En la página **Categoría**, haga clic en **Nueva** o **Editar**.
    
5. En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que debe crearse la categoría. El servicio es el grupo de servidores de chat persistente que usa el chat persistente (cliente) para identificar a qué grupo pertenece la categoría. Una categoría solo puede pertenecer a un grupo de servidores de chat persistente y no se puede mover a otro ni compartirse con otro grupo de servidores.
    
6. En **Nueva categoría**, haga lo siguiente:
    
7. En **Nombre**, especifique un nombre para el nuevo salón.
    
8. En  **Descripción**, proporcione una descripción detallada de la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
9. Para controlar si se pueden habilitar invitaciones para salones de chat, active o desactive la casilla **Habilitar invitaciones**. Si la activa, los salones de esta categoría pueden tener invitaciones activadas o desactivadas; si se desactiva, los salones de esta categoría no pueden tener invitaciones. Si una sala tiene invitaciones, cuando se agrega un nuevo miembro a una sala, recibe una notificación de la nueva sala en su cliente de chat persistente.
    
10. Para controlar las cargas de archivos en salones de chat que pertenezcan a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si se activa, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos; si se desactiva, los salones de esta categoría no pueden tener cargas de archivos.
    
11. Para controlar el historial de chat, active o desactive la casilla Habilitar historial de **chat.** Si se activa, los salones de chat se vuelven persistentes; en caso contrario, los mensajes de chat no permanecen. Si se habilita el cumplimiento, los chats de los salones se guardarán en conformidad, pero los usuarios no podrán obtener acceso a los mensajes más antiguos. Esta opción se puede usar para salas designadas para colaboraciones ad hoc en tiempo real que no necesitan que se conserve el historial de chat.
    
12. En **Editar categoría**, haga lo siguiente:
    
    - En **Pertenencia**,  en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otras) que puedan agregarse como miembros de salas de chat pertenecientes a la categoría. Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).
    
    - En **Pertenencia**, en la sección **Miembros** denegados, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con miembros que se denieguen de la sala.
    
    - En **Pertenencia**, en la **sección Creadores,** agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con creadores para la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.
    
13. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Consulte también

Para obtener más información sobre las características y capacidades del servidor de chat persistente, vea [Plan for Persistent Chat Server in Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), Deploy Persistent Chat Server in Skype Empresarial Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Manage Persistent Chat Server in Skype Empresarial Server 2015 ](../../manage/persistent-chat/persistent-chat.md).
  


---
title: Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Resumen: Aprenda a administrar categorías de servidores de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: 55cd4ef7e89e85bb78c061b05c612d6703c34221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279357"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar categorías de servidores de chat persistentes en Skype empresarial Server 2015.
  
Una categoría es una estructura lógica para organizar salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a los salones de chat. Las categorías de salones de chat contienen salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos como Name y Description. La categoría tiene propiedades que pueden establecerse para controlar el comportamiento de los salones de chat que pertenecen a ella; por ejemplo, si los salones de chat permiten invitaciones o cargas de archivos, o si contienen historial de conversaciones. 
  
El uso correcto de las categorías facilita considerablemente la creación y la administración de los salones de chat. Como administrador del servidor de chat persistente, puede definir los miembros permitidos (AllowedMembers) y los creadores para cada categoría, así como también definir los comportamientos y la configuración predeterminados de los salones de chat que se aplicarán a todos los salones de chat creados en la categoría. Por ejemplo, si establece la AllowedMembers de la categoría en contoso.com, puede agregar cualquier grupo o usuario de Contoso como miembro a los salones de chat de esa categoría. Si establece en Ventas los miembros permitidos de una categoría, solo los usuarios y los grupos en esa lista de distribución pueden agregarse como miembros de los salones de chat de esa categoría. La propiedad de los creadores permite controlar quién puede crear salones de chat en esa categoría. Una vez que se crea el salón de chat, se puede designar a cualquier miembro del grupo de miembros permitidos como director de las funciones de administración en curso en los salones (por ejemplo, los cambios y las aprobaciones de pertenencia).
  
Definir los miembros permitidos y los creadores para una categoría tiene las siguientes ventajas:
  
- Todos los salones de chat de esta categoría están vinculados por las restricciones establecidas en el nivel de categoría. Puedes usarlo para separar los salones de chat según las necesidades empresariales y las políticas de acceso.
    
- Un usuario de la lista de creadores puede crear salones de chat en esa categoría. Si quiere implementar un sistema en el que una cantidad restringida de personal de la organización pueda crear salones de chat, puede usar este control para cumplir ese requisito. 
    
Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Después de crear la categoría, pueden elegir usuarios, UO y grupos de usuarios de la lista de miembros permitidos de la categoría, como directores y miembros del salón de chat para administrar y participar en el salón. 
  
Antes de configurar las categorías, asegúrese de leer las [categorías de chat persistentes, los salones de chat y los roles de usuario en Skype empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
Puede configurar y administrar categorías por medio del Panel de control o por medio de los cmdlets de Windows PowerShell.

> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurar categorías con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Categoría**.
    
    Para varias implementaciones del grupo de servidores de chat persistentes, seleccione el grupo adecuado de la lista desplegable.
    
4. En la página **Categoría**, haga clic en **Nuevo** o en **Editar**.
    
5. En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría. El servicio es el grupo de servidores de chat persistente que usa el cliente de chat persistente para identificar a qué grupo pertenece la categoría. Una categoría puede pertenecer a un único grupo de servidores de chat persistentes, y no se puede mover a otro grupo o compartirlo con él.
    
6. En **Nueva categoría**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva categoría de salón.
    
   - En **Descripción**, proporcione una descripción detallada sobre la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
   - Para controlar si las invitaciones se pueden habilitar para salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar invitaciones**. Si está activada, los salones de esta categoría puedan tener invitaciones activas o inactivas y, si está desactivada, el salón de esta categoría no puede tener invitaciones. Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación de la nueva sala en su cliente de chat persistente.
    
   - Para controlar las cargas de archivos en salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si está activada, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos y, si no está activada, los salones de esta categoría no pueden tener cargas de archivos.
    
   - Para controlar el historial de conversaciones, Active o desactive la casilla de verificación **Habilitar el historial de chat** . Si está activada, los salones de chat serán persistentes; en caso contrario, los mensajes de chats no persisten. Si el cumplimiento está habilitado, los chats del salón se guardarán en consecuencia, pero los usuarios no podrán tener acceso a los mensajes antiguos. Esta opción se puede usar para salas designadas para colaboraciones ad hoc y en tiempo real que no necesitan un historial de conversaciones.
    
7. En **Editar categoría**, haga lo siguiente:
    
   - En **pertenencia**, en la sección **miembros permitidos** , agregar o quitar usuarios y otros principios de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que se pueden agregar como miembros de salones de chat pertenece a la categoría. Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).
    
   - En **pertenencia**, en la sección **miembros** denegados, agregue o quite usuarios y otros principales de Active Directory asociados a miembros que se deniegan del salón.
    
   - En **pertenencia**, en la sección **creadores** , agregue o quite usuarios y otras entidades de Active Directory asociadas con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de los salones de chat.
    
8. Haga clic en **Confirmar**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurar las categorías con Windows PowerShell

Puede configurar categorías por medio de los siguientes cmdlets de Windows PowerShell:
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crea una categoría  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura las opciones de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera información sobre las categorías  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Quita una categoría  <br/> |
   
Puede configurar los siguientes parámetros para las categorías:
  
- EnableFileUpload. Permite la carga de archivos a los salones de chat en la categoría.
    
- EnableInvitations. Habilita las invitaciones para la categoría. Los usuarios de la lista de miembros permitidos automáticamente recibirán una invitación para unirse a un nuevo salón de chat en el momento que se cree un salón.
    
- ChatHistory. Habilita o deshabilita la característica del historial de chat.
    
- Creators. Especifica los usuarios que tienen permiso para crear salones de chat en la categoría.
    
- AllowedMembers. Especifica los usuarios que tiene permiso para obtener acceso a los salones de chat en la categoría.
    
- DeniedMembers. Enumera los usuarios que no tienen permiso para obtener acceso a los salones de chat en la categoría.
    
Para ver información completa sobre la sintaxis del cmdlet, incluso todos los parámetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Crear una categoría

Puede crear una categoría con el cmdlet **New-CsPersistentChatRoom**. Por ejemplo, el siguiente comando crea una categoría denominada HelpDesk en el grupo atl-cs-001.contoso.com. En este ejemplo, la carga de archivos se encuentra habilitada:
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurar una categoría existente

Puede configurar una categoría existente con el cmdlet **Set-CsPersistentCategory**.
  
Por ejemplo, el siguiente comando especifica que user1 es un AllowedMember y un creador, mientras que usuario2 tiene denegado el acceso a las salas de la categoría:
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obtener información sobre las categorías

Puede obtener información sobre las categorías con el cmdlet **Get-CsPersistentChatCategory**. Por ejemplo, el siguiente comando devuelve información para todas las categorías de chat persistente en la organización:
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Quitar una categoría

Puede quitar una categoría con el cmdlet **Remove-CsPersistentChatCategory**. Antes de quitar una categoría, es preciso que primero elimine todos los salones de chat en ella o moverlos a una nueva categoría. Por ejemplo el siguiente comando quita la categoría que tiene el parámetro Identity "atl-cs-001.contoso.com\helpdesk":
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```

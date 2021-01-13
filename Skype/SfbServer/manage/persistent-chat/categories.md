---
title: Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Resumen: obtenga información sobre cómo administrar categorías de servidores de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815130"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar categorías de servidores de chat persistente en Skype Empresarial Server 2015.
  
Una categoría es una estructura lógica para organizar los salón de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a los salas de chat. Las categorías de salón de chat contienen salas de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos, como Nombre y Descripción. La categoría tiene propiedades que se pueden establecer para controlar el comportamiento de los salón de chat que le pertenecen; por ejemplo, si los salas de chat permiten invitaciones o cargas de archivos, o si contienen historial de chat. 
  
Crear y administrar salas de chat es mucho más fácil con el uso correcto de categorías. Como administrador del servidor de chat persistente, puede definir AllowedMembers y Creators para cada categoría, así como definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat creados en la categoría. Por ejemplo, si establece allowedMembers de la categoría en contoso.com, puede agregar cualquier grupo o usuario de Contoso como miembro a los salón de chat de esa categoría. Si establece los miembros permitidos en una categoría en Ventas, solo los grupos y usuarios de esta lista de distribución se pueden agregar como miembros a los salón de chat de esa categoría. La propiedad Creators permite controlar quién puede crear salas de chat en esa categoría. Una vez creado el salón de chat, cualquier miembro del grupo AllowedMembers puede designarse como administrador para las operaciones de administración continuas en los salas (por ejemplo, cambios de pertenencia y aprobación).
  
Definir AllowedMembers y Creators para una categoría tiene las siguientes ventajas:
  
- Todos los salones de chat de esta categoría se rigen por las restricciones establecidas en el nivel de la categoría. Puede usarlo para segregar salones de chat en función de las necesidades empresariales y las directivas de acceso.
    
- Un usuario de la lista Creators puede crear nuevos salones de chat en esa categoría. Si desea implementar un sistema en el que un número restringido de personal de la organización pueda crear salas de chat, este control se puede usar para cumplir con estos requisitos. 
    
Los usuarios, las unidades organizativas (unidades organizativas) y los grupos de usuarios identificados como creadores de la categoría son los únicos individuos y grupos que pueden crear salas en la categoría. Después de crear la categoría, puede elegir usuarios, us y grupos de usuarios de la lista AllowedMembers de la categoría como administradores y miembros del salón de chat para administrar y participar en el salón. 
  
Antes de configurar categorías, asegúrese de leer las categorías de chat persistente, los salón de chat y los roles de usuario [en Skype Empresarial Server 2015.](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)
  
Puede configurar y administrar categorías mediante el Panel de control o mediante cmdlets Windows PowerShell web.

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurar categorías mediante el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Categoría**.
    
    Para varias implementaciones de grupos de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.
    
4. En la página **Categoría**, haga clic en **Nueva** o **Editar**.
    
5. En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría. El servicio es el grupo de servidores de chat persistente que el cliente de chat persistente usa para identificar a qué grupo pertenece la categoría. Una categoría solo puede pertenecer a un grupo de servidores de chat persistente y no se puede mover a otro grupo ni compartir con él.
    
6. En **Nueva categoría**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para el nuevo salón.
    
   - En  **Descripción**, proporcione una descripción detallada de la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
   - Para controlar si se pueden habilitar invitaciones para salones de chat, active o desactive la casilla **Habilitar invitaciones**. Si la activa, los salones de esta categoría pueden tener invitaciones activadas o desactivadas; si se desactiva, los salones de esta categoría no pueden tener invitaciones. Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación del nuevo salón en su cliente de chat persistente.
    
   - Para controlar las cargas de archivos en salones de chat que pertenezcan a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si se activa, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos; si se desactiva, los salones de esta categoría no pueden tener cargas de archivos.
    
   - Para controlar el historial de chat, active o desactive la casilla Habilitar historial **de chat.** Si se activa, los salones de chat se vuelven persistentes; en caso contrario, los mensajes de chat no permanecen. Si se habilita el cumplimiento, los chats de los salones se guardarán en conformidad, pero los usuarios no podrán obtener acceso a los mensajes más antiguos. Esta opción se puede usar para salas designadas para colaboraciones ad hoc en tiempo real que no necesitan que se conserve el historial de chat.
    
7. En **Editar categoría**, haga lo siguiente:
    
   - En Pertenencia **,** en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de Servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otros) que puedan agregarse como miembros de los salón de chat que pertenecen a la categoría.  Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).
    
   - En **Pertenencia**, en la **sección Miembros** denegados, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con miembros denegados de la sala.
    
   - En **Pertenencia**, en la **sección Creadores,** agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.
    
8. Haga clic en **Confirmar**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurar categorías mediante el uso de Windows PowerShell

Puede configurar categorías mediante los siguientes cmdlets Windows PowerShell configuración:
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crear una nueva categoría  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configurar las opciones de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recuperar información sobre categorías  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Quitar una categoría  <br/> |
   
Puede configurar los siguientes parámetros para categorías:
  
- EnableFileUpload. Permite la carga de archivos en los salón de chat de la categoría.
    
- EnableInvitations. Habilita las invitaciones para la categoría. Los usuarios de la lista AllowedMembers recibirán automáticamente una invitación para unirse a un nuevo salón de chat en el momento en que se cree el nuevo salón.
    
- ChatHistory. Habilita o deshabilita la característica de historial de chat.
    
- Creadores. Especifica los usuarios que pueden crear salas de chat dentro de la categoría.
    
- AllowedMembers. Especifica los usuarios a los que se les permite tener acceso a los salón de chat dentro de la categoría.
    
- DeniedMembers. Enumera los usuarios que no tienen permiso para tener acceso a los salones de chat dentro de la categoría.
    
Para obtener información completa acerca de la sintaxis del cmdlet, incluidos todos los parámetros, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)
  
### <a name="create-a-new-category"></a>Crear una nueva categoría

Puede crear una categoría con el cmdlet **New-CsPersistentChatCategory.** Por ejemplo, el siguiente comando crea una nueva categoría denominada HelpDesk en el grupo atl-cs-001.contoso.com. En este ejemplo, la carga de archivos está habilitada:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurar una categoría existente

Puede configurar una categoría existente mediante el cmdlet **Set-CsPersistentCategory.**
  
Por ejemplo, el siguiente comando especifica que user1 es un AllowedMember y un Creator, mientras que user2 no tiene acceso a los salas de la categoría:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obtener información sobre categorías

Puede obtener información acerca de las categorías mediante el cmdlet **Get-CsPersistentChatCategory.** Por ejemplo, el siguiente comando devuelve información para todas las categorías de chat persistente de la organización:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Quitar una categoría

Puede quitar una categoría con el cmdlet **Remove-CsPersistentChatCategory.** Antes de quitar una categoría, primero debe eliminar todos los salón de chat que hay debajo o mover los salón de chat a una nueva categoría. Por ejemplo, el siguiente comando quita la categoría que tiene la identidad "atl-cs-001.contoso.com\helpdesk":
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```

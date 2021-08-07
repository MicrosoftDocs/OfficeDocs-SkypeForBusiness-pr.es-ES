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
description: 'Resumen: obtenga información sobre cómo administrar categorías de servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 1785f541765075160573907955630ee395d4f9773daebff7895842689327a3ef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276755"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar categorías en el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar categorías de servidor de chat persistente en Skype Empresarial Server 2015.
  
Una categoría es una estructura lógica para organizar salas de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a los salas de chat. Las categorías de salón de chat contienen salas de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos, como Nombre y Descripción. La categoría tiene propiedades que se pueden establecer para controlar el comportamiento de los salas de chat que pertenecen a ella; por ejemplo, si los salas de chat permiten invitaciones o cargas de archivos o contienen historial de chat. 
  
Crear y administrar salas de chat es mucho más fácil con el uso correcto de categorías. Como administrador del servidor de chat persistente, puede definir AllowedMembers y Creators para cada categoría y definir también la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat creados en la categoría. Por ejemplo, si establece allowedMembers de la categoría en contoso.com, puede agregar cualquier grupo o usuario de Contoso como miembro a los salón de chat de esa categoría. Si establece los miembros permitidos en una categoría en Ventas, solo los grupos y usuarios de esta lista de distribución se pueden agregar como miembros a los salas de chat de esa categoría. La propiedad Creators permite controlar quién puede crear salas de chat en esa categoría. Después de crear el salón de chat, cualquier usuario del grupo AllowedMembers puede ser designado como administrador para las operaciones de administración en curso en las salas (por ejemplo, cambios de pertenencia y aprobación).
  
Definir AllowedMembers y Creators para una categoría tiene las siguientes ventajas:
  
- Todos los salones de chat de esta categoría se rigen por las restricciones establecidas en el nivel de la categoría. Puede usarlo para segregar salones de chat en función de las necesidades empresariales y las directivas de acceso.
    
- Un usuario de la lista Creators puede crear nuevos salones de chat en esa categoría. Si desea implementar un sistema donde un número restringido de personal de la organización puede crear salas de chat, este control se puede usar para cumplir con los requisitos. 
    
Los usuarios, las unidades organizativas y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salas en la categoría. Después de crear la categoría, puede elegir usuarios, US y grupos de usuarios de la lista AllowedMembers de la categoría como administradores y miembros del salón de chat para administrar y participar en la sala. 
  
Antes de configurar categorías, asegúrese de leer categorías de chat persistente, salas de chat y roles de usuario [en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
Puede configurar y administrar categorías mediante el Panel de control o mediante Windows PowerShell cmdlets.

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurar categorías mediante el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú** Inicio, seleccione Skype Empresarial Server Panel de control o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Categoría**.
    
    Para varias implementaciones de grupo de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.
    
4. En la página **Categoría**, haga clic en **Nueva** o **Editar**.
    
5. En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que debe crearse la categoría. El servicio es el grupo de servidores de chat persistente que usa el cliente de chat persistente para identificar a qué grupo pertenece la categoría. Una categoría solo puede pertenecer a un grupo de servidores de chat persistente y no se puede mover a otro grupo ni compartir con él.
    
6. En **Nueva categoría**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para el nuevo salón.
    
   - En  **Descripción**, proporcione una descripción detallada de la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
   - Para controlar si se pueden habilitar invitaciones para salones de chat, active o desactive la casilla **Habilitar invitaciones**. Si la activa, los salones de esta categoría pueden tener invitaciones activadas o desactivadas; si se desactiva, los salones de esta categoría no pueden tener invitaciones. Si una sala tiene invitaciones, cuando se agrega un nuevo miembro a una sala, recibe una notificación de la nueva sala en su cliente de chat persistente.
    
   - Para controlar las cargas de archivos en salones de chat que pertenezcan a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si se activa, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos; si se desactiva, los salones de esta categoría no pueden tener cargas de archivos.
    
   - Para controlar el historial de chat, active o desactive la casilla Habilitar historial de **chat.** Si se activa, los salones de chat se vuelven persistentes; en caso contrario, los mensajes de chat no permanecen. Si se habilita el cumplimiento, los chats de los salones se guardarán en conformidad, pero los usuarios no podrán obtener acceso a los mensajes más antiguos. Esta opción se puede usar para salas designadas para colaboraciones ad hoc en tiempo real que no necesitan que se conserve el historial de chat.
    
7. En **Editar categoría**, haga lo siguiente:
    
   - En **Pertenencia**,  en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otras) que puedan agregarse como miembros de salas de chat pertenecientes a la categoría. Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).
    
   - En **Pertenencia**, en la sección **Miembros** denegados, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con miembros que se denieguen de la sala.
    
   - En **Pertenencia**, en la **sección Creadores,** agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con creadores para la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.
    
8. Haga clic en **Confirmar**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurar categorías mediante Windows PowerShell

Puede configurar categorías mediante los siguientes cmdlets Windows PowerShell:
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crear una nueva categoría  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configurar las opciones de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recuperar información sobre categorías  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Quitar una categoría  <br/> |
   
Puede configurar los siguientes parámetros para categorías:
  
- EnableFileUpload. Permite cargar archivos en los salas de chat de la categoría.
    
- EnableInvitations. Habilita las invitaciones para la categoría. Los usuarios de la lista AllowedMembers recibirán automáticamente una invitación para unirse a un nuevo salón de chat en el momento en que se cree la nueva sala.
    
- ChatHistory. Habilita o deshabilita la característica de historial de chat.
    
- Creadores. Especifica los usuarios a los que se les permite crear salas de chat dentro de la categoría.
    
- AllowedMembers. Especifica los usuarios a los que se les permite acceder a los salón de chat dentro de la categoría.
    
- DeniedMembers. Enumera los usuarios que no tienen permiso para tener acceso a los salones de chat dentro de la categoría.
    
Para obtener información completa acerca de la sintaxis del cmdlet, incluidos todos los parámetros, vea Skype Empresarial Server Shell de administración [de 2015](../management-shell.md).
  
### <a name="create-a-new-category"></a>Crear una nueva categoría

Puede crear una nueva categoría mediante el cmdlet **New-CsPersistentChatCategory.** Por ejemplo, el siguiente comando crea una nueva categoría denominada HelpDesk en el grupo atl-cs-001.contoso.com. En este ejemplo, la carga de archivos está habilitada:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurar una categoría existente

Puede configurar una categoría existente mediante el cmdlet **Set-CsPersistentCategory.**
  
Por ejemplo, el siguiente comando especifica que user1 es un AllowedMember y un Creator, mientras que user2 no tiene acceso a las salas de la categoría:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obtener información sobre categorías

Puede obtener información sobre categorías mediante el cmdlet **Get-CsPersistentChatCategory.** Por ejemplo, el siguiente comando devuelve información para todas las categorías de chat persistente de la organización:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Quitar una categoría

Puede quitar una categoría mediante el cmdlet **Remove-CsPersistentChatCategory.** Antes de quitar una categoría, primero debe eliminar todos los salas de chat que hay debajo o mover los salas de chat a una categoría nueva. Por ejemplo, el siguiente comando quita la categoría que tiene la identidad "atl-cs-001.contoso.com\helpdesk":
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```

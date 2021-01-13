---
title: Administrar los salón de chat en el servidor de chat persistente en Skype Empresarial Server 2015
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
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumen: obtenga información sobre cómo administrar los salas de chat del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815110"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar los salón de chat en el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar los salón de chat del servidor de chat persistente en Skype Empresarial Server 2015.
  
Crear y administrar salas de chat es mucho más fácil con el uso correcto de categorías. Una categoría define quién puede crear o unirse a los salón de chat. Antes de intentar administrar los salón de chat, asegúrese de leer las categorías de chat persistente, los salón de chat y los roles de usuario en [Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) y administrar las categorías en el servidor de chat persistente en [Skype Empresarial Server 2015.](categories.md)
  
> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

Puede configurar y administrar los salón de chat mediante la interfaz de línea de comandos de Windows PowerShell o mediante el cliente de Skype Empresarial si es miembro del salón de chat. En este tema se describe cómo administrar los salón de chat mediante la interfaz Windows PowerShell línea de comandos. Si desea administrar los salón de chat con el cliente de Skype Empresarial, consulte la ayuda del cliente. 
  
Los salón de chat pueden ser de dos tipos: Normal y Auditorio. Un salón de chat Normal permite a todos los miembros publicar y leer mensajes. Un auditorio es un tipo de salón de chat donde solo los presentadores pueden publicar, pero todos pueden leer.
  
Quién puede acceder a los salas de chat y administrarlos depende de los roles de usuario de la siguiente manera:
  
- Los usuarios deben ser miembros de un salón de chat para poder publicar y leer mensajes.
    
- Los presentadores pueden publicar en salas de auditorio.
    
- Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado. Los administradores también pueden quitar o reemplazar mensajes que se consideren inapropiados para un salón de chat en particular.
    
- Los usuarios finales, incluidos los autores de mensajes, no pueden eliminar contenido de ningún salón de chat.
    
- Los administradores de los salón de chat pueden realizar cambios en todas las propiedades del salón de chat, incluida la deshabilitación de salas. Sin embargo, los administradores no pueden eliminar un salón ni cambiar la categoría de un salón. 
    
- Solo los administradores pueden eliminar un salón de chat después de crearlo.
    
Puede configurar y administrar los salas de chat mediante los siguientes cmdlets Windows PowerShell web:
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Crear un nuevo salón de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurar las opciones de una sala existente; asignar usuarios y grupos de usuarios a la sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperar información sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Borrar una sala o mensajes de una sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Quitar un salón  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Quitar mensajes de una sala  <br/> |
   
Use el cmdlet **New-CsPersistentChatRoom** para crear salas de chat y el cmdlet **Set-CsPersistentChatRoom** para configurar un salón de chat existente, incluida la adición de usuarios al salón de chat. Puede configurar los siguientes parámetros para los salas de chat:
  
- Deshabilitado. Permite deshabilitar o habilitar un salón de chat. 
    
- Invitaciones. Permite habilitar o deshabilitar las invitaciones a salas de chat, que se usan para notificar a los usuarios cuando se han agregado como miembros del salón de chat. La configuración predeterminada para las invitaciones heredadas, que hizo que el salón de chat adoptara la configuración de invitación configurada en la categoría a la que pertenece. La configuración de las invitaciones en false en el nivel de salón de chat permite invalidar la configuración de categoría. 
    
- Privacidad. Permite especificar si un salón de chat es Abierto, Cerrado o Secreto. Cualquiera puede buscar en las salas abiertas y acceder a ellas. Cualquiera puede buscar salas cerradas, pero solo los miembros pueden acceder a ellas. Solo los miembros de la sala pueden buscar y tener acceso a los salas secretas. De forma predeterminada, cada nueva sala se configura inicialmente como Cerrada.
    
- Tipo. Permite especificar si un salón de chat es un salón Normal, que acepta mensajes publicados por cualquier miembro, o un salón de auditorio, que acepta mensajes publicados solo por un moderador.
    
- Addin. Permite asociar un complemento configurado previamente con un salón de chat, lo que permite que los miembros puedan ver el contenido de la dirección URL mientras participan.
    
Además de los parámetros anteriores, el cmdlet **Set-CsPersistentChatRoom** permite asignar usuarios al salón de chat de la siguiente manera:
  
- Miembros. Configura la pertenencia al salón de chat. Puede agregar o quitar miembros individuales o múltiples mediante un solo cmdlet especificando la dirección SIP de los usuarios. Para permitir que los usuarios se puedan agregar de forma masiva, también se pueden especificar unidades organizativas o grupos de distribución de Active Directory.
    
- Administradores. Permite asignar administradores al salón de chat. Los administradores tienen los permisos para definir la pertenencia a un salón de chat junto con otras opciones de configuración.
    
- Presentadores. Permite asignar presentadores a un salón de chat Auditorio. 
    
  Para obtener más información sobre la sintaxis, incluidos todos los parámetros, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)
  
## <a name="create-a-new-room"></a>Crear un nuevo salón

Puede crear un nuevo salón con el cmdlet **New-CsPersistentChatRoom.** Por ejemplo, el siguiente comando crea un nuevo salón de chat denominado ITChatRoom en el grupo atl-cs-001.contoso.com. En este ejemplo, el salón de chat se agrega a la categoría de IT:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Nota:** PersistentChatPoolFqdn no es necesario si se cumple una de las siguientes condiciones: 
  
- Solo hay un grupo de servidores de chat persistente.
    
- Proporciona un poolFqdn a la categoría.
    
- Proporciona un poolFqdn para agregar un salón.
    
## <a name="configure-an-existing-room"></a>Configurar una sala existente

Puede configurar un salón existente mediante el cmdlet **Set-CsPersistentChatRoom.** Por ejemplo, el siguiente comando asigna usuario1 como miembro y moderador, y usuario2 como administrador, de la sala de auditorio testCat:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 En el siguiente ejemplo se agregan todos los usuarios de la unidad organizativa NorthAmericaUsers de Active Directory al salón de chat NorthAmerica:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

En el siguiente ejemplo se agregan todos los miembros del grupo de distribución Finance al mismo salón de chat:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Deshabilitar o habilitar un salón

Si el tema de un salón de chat persistente ya no es relevante, puede hacer que el salón de chat no esté disponible para los usuarios si lo deshabilita. Cuando se deshabilita una salón de chat, todos los miembros se desconectan inmediatamente del salón. Después de deshabilitar un salón de chat, los usuarios no pueden unirse a él o encontrarlo en las búsquedas de salones de chat.
  
Si el historial del salón de chat persiste, el contenido se conserva cuando el salón de chat está deshabilitado. No obstante, ese contenido no aparecerá en las búsquedas durante el tiempo que el salón de chat permanezca deshabilitado. Si más tarde habilita el salón de chat, los usuarios pueden buscar mensajes que se publicaron antes de que lo deshabilitara. Para obtener información sobre cómo configurar el historial de salas de chat, consulte Administrar categorías en el servidor de [chat persistente en Skype Empresarial Server 2015.](categories.md) 
  
Al deshabilitar un salón de chat, su lista de miembros y otros ajustes se conservan. Como administrador, puede habilitar una sala que se ha deshabilitado y no es necesario volver a crear manualmente la configuración.
  
Puede deshabilitar una sala mediante el cmdlet **Set-CsPersistentChatRoom** y estableciendo el parámetro Disabled en True:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Para habilitar un salón de chat, establezca el parámetro Disabled en False:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Obtener información sobre salas

Para obtener información sobre las salas configuradas para su uso en la organización, puede usar el cmdlet **Get-CsPersistentChatRoom.**
  
El siguiente comando devuelve información sobre todos los salón de chat configurados para su uso en la organización:
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Quitar todo el contenido de un salón

Puede quitar contenido de un salón mediante el cmdlet **Clear-CsPersistentChatRoom.** Por ejemplo, el siguiente comando quita todo el contenido del salón de chat persistente ITChatRoom que se agregó a la sala el 1 de marzo de 2015 o antes:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Quitar un mensaje de un salón

Puede quitar uno o más mensajes de la base de datos de chat persistente y, opcionalmente, reemplazar el mensaje por un mensaje predeterminado o por un mensaje proporcionado por el administrador, mediante el cmdlet **Remove-CsPersistentChatMessage.** Por ejemplo, el siguiente comando quita todos los mensajes del salón de chat ITChatRoom que publicó el usuario kenmyer@contoso.com:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

En el siguiente ejemplo se reemplazan los mensajes eliminados con la nota de que el mensaje ya no está disponible:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Quitar un salón

Puede quitar un salón mediante el cmdlet **Remove-CsPersistentChatRoom.**
  
Por ejemplo, el siguiente comando quita el salón de chat RedmondChatRoom:
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Mover un salón de una categoría a otra

Si un administrador  del salón de chat tiene privilegios de creador en otra categoría, puede mover el salón de una categoría a otra. El salón no se eliminará y volverá a crearse. Es un cambio de asociación dentro de la base de datos.
  
El cambio de una categoría de salón de chat debe realizarse rara vez y con precaución. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se eliminan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro de la sala y ya no es miembro permitido en la nueva categoría, se modificará la pertenencia a la sala y el usuario se quitará de la sala.
  


---
title: Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumen: Obtenga información sobre cómo administrar Persistent Chat Server salones de chat de Skype para Business Server 2015.'
ms.openlocfilehash: 7febc9736f43f3168d7bc62b0ddf833fa6b5864b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569403"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar Persistent Chat Server salones de chat de Skype para Business Server 2015.
  
Con el uso correcto de las categorías, es mucho más fácil crear y administrar los salones de chat. Una categoría define quién puede crear o unirse a los salones de chat. Antes de intentar administrar salones de chat, asegúrese de leer [las categorías de chat persistente, salones de chat y funciones de usuario de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) y [Administrar categorías en el servidor de Chat persistente en Skype para Business Server 2015](categories.md).
  
Puede configurar y administrar salones de chat mediante el uso de la interfaz de línea de comandos de Windows PowerShell, o mediante el Skype para clientes empresariales si usted es un miembro del salón de chat. En este tema se describe cómo administrar salones de chat mediante el uso de la interfaz de línea de comandos de Windows PowerShell. Si desea administrar los salones de chat mediante el Skype para clientes empresariales, vea la Ayuda del cliente. 
  
Salones de chat puede ser uno de los dos tipos: Normal y tipo auditorio. Un salón de chat Normal permite que todos los miembros publicar y leer los mensajes. Un tipo de auditorio es un tipo de salón de chat donde sólo los moderadores pueden publicar, pero todos los usuarios pueden leer.
  
El acceso a los salones de chat y su administración dependen de los roles de usuario, de esta manera:
  
- Es preciso que los usuarios sean miembros de un salón de chat para poder publicar y leer mensajes.
    
- Los moderadores pueden publicar en los salones que son auditorios.
    
- Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado. También pueden quitar o cambiar mensajes que se consideren inapropiados para un salón de chat específico.
    
- Los usuarios finales, incluidos los autores de los mensajes, no pueden eliminar contenido de ningún salón de chat.
    
- Administradores de salones de chat pueden realizar cambios a todas las propiedades de salón de chat, incluida la deshabilitación de salas. Los administradores no se pueden, sin embargo, se eliminar una sala o cambiar la categoría de un salón de. 
    
- Solo los administradores pueden eliminar un salón de chat una vez creado.
    
Puede configurar y administrar los salones de chat por medio de los siguientes cmdlets de Windows PowerShell:
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Crea un salón de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperar información acerca de los salones  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Borra un salón o los mensajes de un salón  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Quita un salón  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Quita mensajes de un salón  <br/> |
   
Con el cmdlet **New-CsPersistentChatRoom** puede crear salones de chat y con **Set-CsPersistentChatRoom** puede configurar un salón de chat existente, incluso agregar usuarios al salón de chat. Puede configurar los siguientes parámetros del salón de chat:
  
- Disabled. Le permite deshabilitar o habilitar un salón de chat. 
    
- Invitaciones. Permite habilitar o deshabilitar las invitaciones de los salones de chat, que se usan para informar a los usuarios cuando se los agregó como miembros de un salón de chat. La configuración predeterminada para las invitaciones es la heredada, por lo que el salón de chat adopta las opciones de configuración de la invitación configuradas en la categoría al que pertenece. Al configurar las opciones de las invitaciones en False en el salón de chat, se cambia la configuración de la categoría. 
    
- Privacidad. Permite especificar si un salón de chat está abierto, cerrado o secreto. Salones abiertos puedan buscar y tener acceso a todos los usuarios. Salones de cerrado se pueden buscar por cualquier usuario, pero se pueden tener acceso sólo por los miembros. Secretas salones puedan buscar y tener acceso a sólo los miembros de la sala. De forma predeterminada, cada nueva sala se configura inicialmente como cerrado.
    
- Type. Permite especificar si un salón de chat es un salón Normal, que acepta mensajes enviados por cualquier miembro o un salón de tipo auditorio, que acepta mensajes expuestos sólo por un moderador.
    
- Addin. Permite asociar complementos previamente configurados con un salón de chat, por lo que los miembros pueden ver el contenido URL mientras participan.
    
Además de los parámetros anteriores, el cmdlet **Set-CsPersistentChatRoom** permite asignar a usuarios al salón de chat de la siguiente manera:
  
- Members. Configura la pertenencia del salón de chat. Puede agregar o quitar miembros individuales o varios miembros con un único cmdlet al especificar la dirección SIP de los usuarios. Para permitir la adición en masa de usuarios, puede especificar también grupos de distribución o unidades organizativas de Active Directory.
    
- Managers. Permite asignar directores al salón de chat. Los directores tienen los permisos para definir la pertenencia de un salón de chat junto con otras opciones de configuración.
    
- Presenters. Permite asignar moderadores a un salón de chat auditorio. 
    
 Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).
  
## <a name="create-a-new-room"></a>Crear un salón

Puede crear un salón con el cmdlet **New-CsPersistentChatRoom**. Por ejemplo, el siguiente comando crea un salón de chat denominado ITChatRoom on the pool atl-cs-001.contoso.com. En este ejemplo, el salón de chat se agrega a la categoría de TI:
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Nota:** PersistentChatPoolFqdn no es necesario si se cumple una de las siguientes opciones: 
  
- Hay un solo grupo de servidores de Chat persistente.
    
- Proporciona un FQDN del grupo de servidores a la categoría.
    
- Proporciona un FQDN del grupo de servidores para agregar el salón.
    
## <a name="configure-an-existing-room"></a>Configurar un salón existente

Puede configurar un salón existente mediante el cmdlet **Set-CsPersistentChatRoom** . Por ejemplo, el comando siguiente asigna user1 como un miembro y moderador y user2 como un administrador de la sala de auditorio testCat:
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 En el siguiente ejemplo, se agregan todos los usuarios de la UO de NorthAmericaUsers en Active Directory al salón de chat NorthAmerica:
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

En el siguiente ejemplo, se agregan todos los miembros del grupo de distribución Finanzas al mismo salón de chat:
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Habilitar o deshabilitar un salón

Si el tema de un salón de Chat en grupo ya no es relevante, puede que el salón de chat a no esté disponible para los usuarios deshabilitando el programa. Cuando un salón de chat está deshabilitado, todos los miembros inmediatamente están desconectados de la sala. Después de un salón de chat está deshabilitado, los usuarios no se pueden volver a unirse a él o buscar en las búsquedas de salón de chat.
  
Si continúa el historial del salón de chat, el contenido se conserva cuando se deshabilita el salón de chat. Pero, dicho contenido no aparecerá en las búsquedas mientras el salón de chat permanezca deshabilitado. Si vuelve a habilitar el salón de chat, los usuarios podrán buscar mensajes publicados antes de que se deshabilitara el salón de chat. Para obtener información acerca de cómo configurar el historial de salones de chat, vea [Administrar categorías en el servidor de Chat persistente en Skype para Business Server 2015](categories.md). 
  
Si un salón de chat se encuentra deshabilitado, se conservan su lista de pertenencia y otras opciones de configuración. Como administrador, puede habilitar un salón que se ha deshabilitado y no es necesario que vuelva a establecer la configuración de forma manual.
  
Puede deshabilitar un salón mediante el cmdlet **Set-CsPersistentChatRoom** y establecer el parámetro deshabilitado en True:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Para habilitar un salón de chat, establezca el parámetro Disabled en False:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Obtener información acerca de los salones

Para obtener información sobre los salones configurados para su organización, puede usar el cmdlet **Get-CsPersistentChatRoom**.
  
El siguiente comando devuelve información sobre todos los salones de chat configurados para la organización:
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Quitar todo el contenido de un salón

Puede quitar el contenido de un salón al usar el cmdlet **Clear-CsPersistentChatRoom**. Por ejemplo, el siguiente comando quita todo el contenido del salón de chat persistente ITChatRoom que se agregó al él el 1 de marzo de 2015 o antes de esa fecha:
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Quitar un mensaje de un salón

Puede quitar uno o más mensajes en la base de datos del chat persistente y, de forma opcional, cambiar el mensaje con un mensaje predeterminado o con un mensaje del administrador. Para ello, use el cmdlet **Remove-CsPersistentChatMessage**. Por ejemplo, el siguiente comando quita todos los mensajes del salón de chat ITChatRoom que kenmyer@contoso.com haya publicado:
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

En el siguiente ejemplo se cambian todos los mensajes quitados por una advertencia de que el mensaje ya no se encuentra disponible:
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Quitar un salón

Puede quitar un salón con el cmdlet **Remove-CsPersistentChatRoom**.
  
Por ejemplo, el siguiente comando quita el salón de chat RedmondChatRoom:
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Mover un salón de una categoría a otra

Si un director de un salón de chat tiene privilegios de **Creador** en otra categoría, puede mover el salón de una categoría a otra. El salón no se eliminará ni volverá a crearse, ya que es un cambio de asociación dentro de la base de datos.
  
El cambio de categoría de un salón de chat tiene que realizarse de forma ocasional y con precaución. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se purgan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro del salón y ya no es un miembro permitido en la nueva categoría, la pertenencia del salón se modificará y se quitará al usuario del salón.
  


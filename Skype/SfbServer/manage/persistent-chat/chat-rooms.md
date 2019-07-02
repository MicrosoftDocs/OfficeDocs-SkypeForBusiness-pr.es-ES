---
title: Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumen: Aprenda a administrar salones de chat del servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: 5b7345626a42073bf7ebd0cb5f9900c6e15f0e2b
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417949"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar salones de chat del servidor de chat persistente en Skype empresarial Server 2015.
  
Con el uso correcto de las categorías, es mucho más fácil crear y administrar los salones de chat. Una categoría define quién puede crear o unirse A los salones de chat. Antes de intentar administrar los salones de chat, asegúrese de leer las [categorías de chat persistentes, los salones de chat y los roles de usuario en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) y [administrar las categorías en el servidor de chat persistente en skype empresarial Server 2015](categories.md).
  
> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 

Puede configurar y administrar salones de chat con la interfaz de línea de comandos de Windows PowerShell o con el cliente de Skype empresarial si es miembro del salón de chat. En este tema se describe cómo administrar los salones de chat con la interfaz de línea de comandos de Windows PowerShell. Si desea administrar salones de chat con el cliente de Skype empresarial, consulte la ayuda del cliente. 
  
Los salones de chat pueden ser de dos tipos: normal y Auditorio. Un salón de chat normal permite a todos los miembros publicar y leer mensajes. Un auditorio es un tipo de salón de chat en el que solo pueden publicar los moderadores, pero todo el mundo puede leer.
  
El acceso a los salones de chat y su administración dependen de los roles de usuario, de esta manera:
  
- Es preciso que los usuarios sean miembros de un salón de chat para poder publicar y leer mensajes.
    
- Los moderadores pueden publicar en los salones que son auditorios.
    
- Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado. También pueden quitar o cambiar mensajes que se consideren inapropiados para un salón de chat específico.
    
- Los usuarios finales, incluidos los autores de los mensajes, no pueden eliminar contenido de ningún salón de chat.
    
- Los administradores de salones de chat pueden realizar cambios en todas las propiedades de los salones de chat, incluyendo la deshabilitación de salas. Sin embargo, los administradores no pueden eliminar una sala o cambiar la categoría de una sala. 
    
- Solo los administradores pueden eliminar un salón de chat una vez creado.
    
Puede configurar y administrar los salones de chat por medio de los siguientes cmdlets de Windows PowerShell:
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Crea un salón de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperar información sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Borra un salón o los mensajes de un salón  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Quita un salón  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Quita mensajes de un salón  <br/> |
   
Con el cmdlet **New-CsPersistentChatRoom** puede crear salones de chat y con **Set-CsPersistentChatRoom** puede configurar un salón de chat existente, incluso agregar usuarios al salón de chat. Puede configurar los siguientes parámetros del salón de chat:
  
- Disabled. Te permite deshabilitar o habilitar un salón de chat. 
    
- Invitaciones. Permite habilitar o deshabilitar las invitaciones de los salones de chat, que se usan para informar a los usuarios cuando se los agregó como miembros de un salón de chat. La configuración predeterminada para las invitaciones es la heredada, por lo que el salón de chat adopta las opciones de configuración de la invitación configuradas en la categoría al que pertenece. Al configurar las opciones de las invitaciones en False en el salón de chat, se cambia la configuración de la categoría. 
    
- Declaración. Le permite especificar si un salón de chat está abierto, cerrado o secreto. Cualquier persona puede buscar y acceder a las salas abiertas. Las salas cerradas pueden ser buscadas por cualquier persona, pero solo las pueden acceder los miembros. Solo los miembros del salón pueden buscar en ellas las salas de secretos. De forma predeterminada, cada nueva sala está configurada inicialmente como cerrada.
    
- Type. Permite especificar si un salón de chat es un salón normal, que acepta los mensajes publicados por cualquier miembro, o una sala de auditorio, que acepta los mensajes publicados solo por un moderador.
    
- Addin. Permite asociar complementos previamente configurados con un salón de chat, por lo que los miembros pueden ver el contenido URL mientras participan.
    
Además de los parámetros anteriores, el cmdlet **set-CsPersistentChatRoom** le permite asignar usuarios al salón de chat de la siguiente manera:
  
- Members. Configura la pertenencia del salón de chat. Puede agregar o quitar miembros individuales o varios miembros con un único cmdlet al especificar la dirección SIP de los usuarios. Para permitir la adición en masa de usuarios, puede especificar también grupos de distribución o unidades organizativas de Active Directory.
    
- Managers. Permite asignar directores al salón de chat. Los directores tienen los permisos para definir la pertenencia de un salón de chat junto con otras opciones de configuración.
    
- Presenters. Permite asignar moderadores a un salón de chat auditorio. 
    
  Para más detalles sobre la sintaxis, incluso todos los parámetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Crear un salón

Puede crear un salón con el cmdlet **New-CsPersistentChatRoom**. Por ejemplo, el siguiente comando crea un salón de chat denominado ITChatRoom on the pool atl-cs-001.contoso.com. En este ejemplo, el salón de chat se agrega a la categoría de TI:
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Nota:** PersistentChatPoolFqdn no es necesario si una de las siguientes condiciones es cierta: 
  
- Solo hay un grupo de servidores de chat persistente.
    
- Proporciona un FQDN del grupo de servidores a la categoría.
    
- Proporciona un FQDN del grupo de servidores para agregar el salón.
    
## <a name="configure-an-existing-room"></a>Configurar un salón existente

Puede configurar una sala existente con el cmdlet **set-CsPersistentChatRoom** . Por ejemplo, el siguiente comando asigna user1 como miembro y moderador, y usuario2 como director, de la sala testCat de auditorio:
  
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

Si el tema de un salón de chat persistente ya no es relevante, puede deshabilitarlo para hacer que el salón de chat no esté disponible para los usuarios. Cuando un salón de chat está deshabilitado, todos los miembros se desconectan inmediatamente del salón. Después de deshabilitar un salón de chat, los usuarios no pueden volver a unirse o encontrarlo en las búsquedas del salón de chat.
  
Si el historial del salón de chat continúa, el contenido se conserva cuando el salón de chat está deshabilitado. Pero, dicho contenido no aparecerá en las búsquedas mientras el salón de chat permanezca deshabilitado. Si vuelve a habilitar el salón de chat, los usuarios podrán buscar mensajes publicados antes de que se deshabilitara el salón de chat. Para obtener información sobre cómo configurar el historial del salón de chat, consulte [administrar categorías en el servidor de chat persistente en Skype empresarial server 2015](categories.md). 
  
Si un salón de chat se encuentra deshabilitado, se conservan su lista de pertenencia y otras opciones de configuración. Como administrador, puede habilitar un salón que se ha deshabilitado y no es necesario que vuelva a establecer la configuración de forma manual.
  
Para deshabilitar un salón, use el cmdlet **set-CsPersistentChatRoom** y establezca el parámetro disabled en true:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Para habilitar un salón de chat, establezca el parámetro Disabled en False:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Obtener información sobre salas

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
  


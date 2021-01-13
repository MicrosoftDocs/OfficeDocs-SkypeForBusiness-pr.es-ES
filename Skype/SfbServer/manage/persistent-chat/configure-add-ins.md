---
title: Configurar complementos para los salas de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumen: obtenga información sobre cómo configurar complementos para los salas de chat del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815086"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurar complementos para los salas de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.
  
Los complementos se usan para ampliar la experiencia en el salón mediante la asociación de direcciones URL con los salas de chat. Estas direcciones URL aparecen en el panel de extensibilidad de conversación de cliente. Un complemento típico puede incluir una dirección URL que apunta a una aplicación de Silverlight que intercepta cuando se publica un ticker de bolsa en un salón de chat y muestra el historial de acciones en el panel de extensibilidad. Otros ejemplos incluyen la incrustación de una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir determinado contexto compartido, como "Prioridades" o "Tema del día".
  
 Para que los usuarios puedan ver un complemento en el cliente, debe agregar el complemento a la lista de complementos registrados, y los administradores o creadores del salón de chat deben asociar salas con el complemento.
  
> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurar complementos para los salas de chat mediante el Panel de control

Para configurar complementos para los salas de chat mediante el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Complemento**.
    
    Para varias implementaciones de grupos de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.
    
4. En la página **Complemento**, haga clic en **Nuevo**.
    
5. En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento. Los complementos no se pueden mover de un grupo a otro ni compartir entre grupos distintos.
    
6. En **Nuevo complemento**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para el nuevo complemento.
    
   - En **Dirección URL**, especifique la dirección URL que se va a asociar con el complemento. Las direcciones URL están limitadas a los protocolos http y https.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurar complementos con Windows PowerShell

Puede configurar complementos para los salas de chat mediante los siguientes cmdlets Windows PowerShell web. Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Crear un nuevo complemento  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configurar las opciones de un complemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recuperar información sobre complementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Quitar un complemento  <br/> |
   
### <a name="create-a-new-add-in"></a>Crear un nuevo complemento

Puede crear un complemento con el cmdlet **New-CsPersistentChatAddin.**
  
Por ejemplo, el siguiente comando crea un nuevo complemento (con el nombre ITPersistentChatAddin) para el grupo de servidores atl-cs-001.contoso.com. El parámetro URL y el valor del parámetro especifican la ubicación de la página http://atl-cs-001.contoso.com/itchat web del complemento:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurar las opciones de un complemento existente

Puede configurar las opciones de un complemento existente mediante el cmdlet **Set-CsPersistentChatAddIn.** Por ejemplo, el siguiente comando modifica la dirección URL asignada al complemento de chat persistente ITPersistentChatAddin. En este caso, la dirección URL se cambia a http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Recuperar información sobre complementos

Puede obtener información acerca de los complementos con el cmdlet **Get-CsPersistentChatAddin.** Por ejemplo, el siguiente comando devuelve información sobre todos los complementos de chat persistente configurados para su uso en la organización:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Quitar un complemento

Puede quitar un complemento con el cmdlet **Remove-CsPersistentChatAddIn.** Por ejemplo, el siguiente comando quita el complemento de chat persistente ITChatAddin que se encuentra en el grupo atl-cs-001.contoso.com:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```



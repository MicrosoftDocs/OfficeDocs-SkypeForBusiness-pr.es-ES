---
title: Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumen: Obtenga información sobre cómo configurar extensiones de servidor de Chat persistente para salones de chat de Skype para Business Server 2015.'
ms.openlocfilehash: f96f000c4ac3a78f6ca3ba4972f295e45128ce50
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967736"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar extensiones de servidor de Chat persistente para salones de chat de Skype para Business Server 2015.
  
Los complementos sirven para ampliar la experiencia en el salón al asociar las direcciones URL con los salones de chat. Dichas direcciones URL aparecen en el panel de extensibilidad de las conversaciones del cliente. Un complemento típico puede incluir una dirección URL que apunte a una aplicación de Silverlight que intercepta cuando un tablero de cotizaciones se registra en un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".
  
 Antes de que los usuarios puedan ver un complemento en el cliente, es preciso que agregue el complemento a la lista de complementos registrados; los administradores o los creadores del salón de chat necesitan asociar los salones con el complemento.
  
> [!NOTE]
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurar complementos para los salones de chat con el Panel de control

Para configurar complementos para los salones de chat con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.
    
    Para implementaciones de varios grupos de servidores de Chat persistente, seleccione el grupo adecuado de la lista desplegable.
    
4. En la página **Complemento**, haga clic en **Nuevo**.
    
5. En **Seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de Chat persistente que necesita para crear el complemento. Los complementos no se pueden mover de un grupo a otro ni compartir entre diferentes grupos.
    
6. Haga lo siguiente en **Complemento nuevo**:
    
  - En **Nombre**, especifique un nombre para el nuevo complemento.
    
  - En **URL**, especifique la dirección URL que se asociará al complemento. Las direcciones URL se limitan a protocolos http y https.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurar los complementos con Windows PowerShell

Puede configurar complementos para los salones de chat con los siguientes cmdlets de Windows PowerShell. Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Crea un complemento.  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configura las opciones de un complemento existente.  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera información sobre los complementos.  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Quita un complemento.  <br/> |
   
### <a name="create-a-new-add-in"></a>Crear un complemento

Puede crear un nuevo complemento mediante el cmdlet **New-CsPersistentChatAddin** .
  
Por ejemplo, el comando siguiente crea un nuevo complemento (con el nombre ITPersistentChatAddin) para el grupo de servidores atl-cs-001.contoso.com. El parámetro de dirección URL y el valor del parámetro http://atl-cs-001.contoso.com/itchat especificar la ubicación de la página Web del complemento:
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurar las opciones de un complemento existente

Puede configurar las opciones para un complemento existente al usar el cmdlet **Set-CsPersistentChatAddIn**. Por ejemplo, el siguiente comando modifica la dirección URL asignada al complemento del chat persistente ITPersistentChatAddin. En este caso, se cambia la dirección URL ahttp://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Recuperar información sobre los complementos

Puede obtener información sobre los complementos al usar el cmdlet **Get-CsPersistentChatAddin**. Por ejemplo, el siguiente comando devuelve información sobre todos los complementos del chat persistente configurados para su uso en la organización:
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Quitar un complemento

Puede quitar un complemento mediante el cmdlet **Remove-CsPersistentChatAddIn** . Por ejemplo, el siguiente comando quita el complemento del chat persistente ITChatAddin que se encuentra en el grupo atl-cs-001.contoso.com:
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```



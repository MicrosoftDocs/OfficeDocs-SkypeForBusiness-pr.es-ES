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
description: 'Resumen: Conozca cómo configurar complementos para el servidor de charla persistente salones de chat de Skype para Business Server 2015.'
ms.openlocfilehash: dbd1eba6cf73783d02b502930f271ada93e28145
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a configurar complementos para el servidor de charla persistente salones de chat de Skype para Business Server 2015.
  
Los complementos sirven para ampliar la experiencia en el salón al asociar las direcciones URL con los salones de chat. Dichas direcciones URL aparecen en el panel de extensibilidad de las conversaciones del cliente. Un complemento típico podría incluir una dirección URL que señala a una aplicación de Silverlight que intercepta cuando un indicador de cotizaciones bursátiles se registra en un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".
  
 Antes de que los usuarios puedan ver un complemento en el cliente, es preciso que agregue el complemento a la lista de complementos registrados; los administradores o los creadores del salón de chat necesitan asociar los salones con el complemento.
  
## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurar complementos para los salones de chat con el Panel de control

Para configurar complementos para los salones de chat con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.
    
    Para varias implementaciones de grupo de servidor de charla persistente, seleccione el grupo adecuado de la lista desplegable.
    
4. En la página **Complemento**, haga clic en **Nuevo**.
    
5. En **Seleccione un servicio**, seleccione el servicio correspondiente al grupo de servidores de charla persistente que necesita para crear el complemento. Los complementos no se pueden mover de un grupo a otro ni compartir entre diferentes grupos.
    
6. Haga lo siguiente en **Complemento nuevo**:
    
  - En **Nombre**, especifique un nombre para el nuevo complemento.
    
  - En **URL**, especifique la dirección URL que se asociará al complemento. Las direcciones URL se limitan a protocolos http y https.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurar los complementos con Windows PowerShell

Puede configurar complementos para los salones de chat con los siguientes cmdlets de Windows PowerShell. Para obtener más información acerca de la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md).
  
| |
|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Nueva CsPersistentChatAddin  <br/> |Crea un complemento.  <br/> |
|Conjunto de CsPersistentChatAddin  <br/> |Configura las opciones de un complemento existente.  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera información sobre los complementos.  <br/> |
|Quitar CsPersistentChatAddin  <br/> |Quita un complemento.  <br/> |
   
### <a name="create-a-new-add-in"></a>Crear un complemento

Puede crear un nuevo complemento mediante el cmdlet **New-CsPersistentChatAddin** .
  
Por ejemplo, el comando siguiente crea un nuevo complemento (con el nombre ITPersistentChatAddin) para el grupo cs-atl-001.contoso.com. El parámetro de dirección URL y el valor del parámetro http://atl-cs-001.contoso.com/itchat especificar la ubicación del sitio Web del complemento:
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurar las opciones de un complemento existente

Puede configurar las opciones para un complemento existente al usar el cmdlet **Set-CsPersistentChatAddIn**. Por ejemplo, el siguiente comando modifica la dirección URL asignada al complemento del chat persistente ITPersistentChatAddin. En este caso, la URL se cambia ahttp://atl-cs-001.contoso.com/itchat2:
  
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



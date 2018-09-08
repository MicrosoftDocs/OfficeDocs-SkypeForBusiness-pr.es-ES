---
title: Configuración del estacionamiento de llamadas en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificar la configuración de estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 7ad0f5aec779392bdf79122a5c66ac2461f825e1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884796"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Configuración del estacionamiento de llamadas en Skype para la empresa
 
Modificar la configuración de estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
  
Si no desea usar la configuración predeterminada de estacionamiento de llamadas, puede personalizarlos. Cuando se instala la aplicación de estacionamiento de llamadas, la configuración global se configura de forma predeterminada. Puede modificar esta configuración global y, además, puede especificar opciones de configuración específicas del sitio. Use el cmdlet **New-CsCpsConfiguration** para crear una nueva configuración específica del sitio. Use el cmdlet **Set-CsCpsConfiguration** para modificar la configuración existente.
  
> [!NOTE]
> Como mínimo, se recomienda configurar la opción **OnTimeoutURI** para el destino de reserva que se usará cuando el tiempo de espera de una llamada estacionada se agote y deje de sonar.
  
Use el cmdlet **New-CsCpsConfiguration** o el cmdlet **Set-CsCpsConfiguration** para configurar cualquiera de las siguientes opciones:
  
|**Esta opción:**|**Especifica:**|
|:-----|:-----|
|**CallPickupTimeoutThreshold** <br/> |El tiempo que transcurre después de estacionar la llamada hasta que vuelve a sonar en el teléfono en el que se respondió.  <br/> El valor debe introducirse con el formato hh:mm:ss para especificar las horas, los minutos y los segundos. El valor mínimo es 10 segundos y el máximo, 10 minutos. El valor predeterminado es 00:01:30.  <br/> |
|**EnableMusicOnHold** <br/> |Si la persona que llama escuchará música mientras la llamada está estacionada.  <br/> Los valores son True o False. El valor predeterminado es True.  <br/> |
|**Valor de MaxCallPickupAttempts** <br/> |El número de veces que una llamada estacionada vuelve a sonar en el teléfono en que se respondió antes de transferirla al identificador uniforme de recursos (URI) de reserva que se especifique para **OnTimeoutURI**. El valor predeterminado es 1.<br/> |
|**OnTimeoutURI** <br/> |La dirección SIP del usuario o grupo de respuesta al que se enruta una llamada estacionada que no se responda cuando se supera el valor de **MaxCallPickupAttempts**. <br/> El valor debe ser un URI de SIP que comience por sip:. Por ejemplo, sip:bob@contoso.com. El valor predeterminado corresponde a sin dirección de transferencia.<br/> |
   
### <a name="to-configure-call-park-settings"></a>Para configurar las opciones de estacionamiento de llamadas

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute:
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Use el cmdlet **Get-CsSite** para identificar el sitio. Para obtener información detallada, vea Skype para la documentación del Shell de administración de servidor empresarial.
  
    Por ejemplo:
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Vea también

[Personalizar la música de espera para el estacionamiento de llamadas en Skype Empresarial 2015](customize-call-park-music-on-hold.md)

[Nueva CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
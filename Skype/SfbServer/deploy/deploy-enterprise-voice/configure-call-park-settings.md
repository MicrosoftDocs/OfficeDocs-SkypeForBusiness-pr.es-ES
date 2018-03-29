---
title: Configurar las opciones de estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificar la configuración de llamada Park en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 56b0e2508fda61bddc94a6f8813708e8186c99c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a>Configurar las opciones de estacionamiento de llamadas en Skype Empresarial 2015
 
Modificar la configuración de llamada Park en Skype para Telefonía IP empresarial de Business Server.
  
Si no desea utilizar la configuración predeterminada de llamada Park, puede personalizarlos. Cuando se instala la aplicación llamada Park, configuración global está configurada de forma predeterminada. Puede modificar esta configuración global y, además, puede especificar opciones de configuración específicas del sitio. Utilice el cmdlet **New-CsCpsConfiguration** para crear una nueva configuración específica del sitio. Use el cmdlet **Set-CsCpsConfiguration** para modificar la configuración existente.
  
> [!NOTE]
> Como mínimo, se recomienda configurar la opción **OnTimeoutURI** para el destino de reserva que se usará cuando el tiempo de espera de una llamada estacionada se agote y deje de sonar.
  
Utilice el cmdlet **New-CsCpsConfiguration** o el cmdlet **Set-CsCpsConfiguration** para configurar cualquiera de las siguientes opciones:
  
|**Esta opción:**|**Especifica esto:**|
|:-----|:-----|
|**CallPickupTimeoutThreshold** <br/> |El tiempo que transcurre después de estacionar la llamada hasta que vuelve a sonar en el teléfono en el que se respondió.  <br/> El valor debe introducirse con el formato hh:mm:ss para especificar las horas, los minutos y los segundos. El valor mínimo es 10 segundos y el máximo, 10 minutos. El valor predeterminado es 00:01:30.  <br/> |
|**EnableMusicOnHold** <br/> |Si la persona que llama escuchará música mientras la llamada está estacionada.  <br/> Los valores son True o False. El valor predeterminado es True.  <br/> |
|**MaxCallPickupAttempts** <br/> |El número de veces que una llamada estacionada vuelve a sonar en el teléfono en que se respondió antes de transferirla al identificador uniforme de recursos (URI) de reserva que se especifique para **OnTimeoutURI**. El valor predeterminado es 1.<br/> |
|**OnTimeoutURI** <br/> |La dirección SIP del usuario o grupo de respuesta al que se enruta una llamada estacionada que no se responda cuando se supera el valor de **MaxCallPickupAttempts**. <br/> El valor debe ser un URI de SIP que comience por sip:. Por ejemplo, sip:bob@contoso.com. El valor predeterminado corresponde a sin dirección de transferencia.<br/> |
   
### <a name="to-configure-call-park-settings"></a>Para configurar las opciones de llamada Park

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute:
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Use el cmdlet **Get-CsSite** para identificar el sitio. Para obtener más información, consulte la documentación del Shell de administración de Lync Server.
  
    Por ejemplo:
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Vea también

#### 

[Personalizar música llamada Park en suspensión inSkype de negocios 2015](customize-call-park-music-on-hold.md)
#### 

[Nueva CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[Conjunto de CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)


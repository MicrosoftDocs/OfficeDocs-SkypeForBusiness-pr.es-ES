---
title: Configurar las opciones de estacionamiento de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modifique la configuración de estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 09888fd0d22ce182688a2fbd0456ce7e5cc6564e1b33ebb1b957ebb0f23b02df
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294907"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Configurar las opciones de estacionamiento de llamadas en Skype Empresarial

Modifique la configuración de estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.

Si no quieres usar la configuración predeterminada de estacionamiento de llamadas, puedes personalizarlas. Al instalar la aplicación estacionamiento de llamadas, la configuración global se configura de forma predeterminada. Puede modificar esta configuración global y, además, puede especificar opciones de configuración específicas del sitio. Use el cmdlet **New-CsCpsConfiguration** para crear una nueva configuración específica del sitio. Use cmdlet **Set-CsCpsConfiguration** para modificar la configuración existente.

> [!NOTE]
> Como mínimo, se recomienda configurar la opción **OnTimeoutURI** para el destino de reserva que se usará cuando el tiempo de espera de una llamada estacionada se agote y deje de sonar.

Use el cmdlet **New-CsCpsConfiguration** o el cmdlet **Set-CsCpsConfiguration** para configurar las siguientes opciones:


| **Esta opción:**                     | **Especifica:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | El tiempo que transcurre después de estacionar la llamada hasta que vuelve a sonar en el teléfono en el que se respondió.  <br/> El valor debe introducirse con el formato hh:mm:ss para especificar las horas, los minutos y los segundos. El valor mínimo es 10 segundos y el máximo, 10 minutos. El valor predeterminado es 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Si la persona que llama escuchará música mientras la llamada está estacionada.  <br/> Los valores son True o False. El valor predeterminado es True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | El número de veces que una llamada estacionada vuelve a sonar en el teléfono en que se respondió antes de transferirla al identificador uniforme de recursos (URI) de reserva que se especifique para **OnTimeoutURI**. El valor predeterminado es 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | La dirección SIP del usuario o grupo de respuesta al que se enruta una llamada estacionada que no se responda cuando se supera el valor de **MaxCallPickupAttempts**. <br/> El valor debe ser un URI de SIP que comience por sip:. Por ejemplo, sip:bob@contoso.com. El valor predeterminado corresponde a sin dirección de transferencia.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Para configurar la configuración del estacionamiento de llamadas

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.

2. Ejecutar:

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Use el cmdlet **Get-CsSite** para identificar el sitio. Para obtener más información, consulte Skype Empresarial Server del Shell de administración.

    Por ejemplo:

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Ver también

[Personalizar la música de estacionamiento de llamadas en espera enSkype para Empresas 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)
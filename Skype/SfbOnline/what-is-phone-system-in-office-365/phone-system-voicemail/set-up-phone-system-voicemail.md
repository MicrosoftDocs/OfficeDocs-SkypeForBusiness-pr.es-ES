---
title: "Configurar correo de voz del sistema de teléfono"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: c0ea32a7e5792f00380c41c50cc69a2521a3eb37
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="set-up-phone-system-voicemail"></a>Configurar correo de voz del sistema de teléfono

Este artículo es para la [administración de Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que quiere configurar la característica de correo de voz de sistema telefónico para todos los usuarios del negocio.
  
> [!NOTE]
> Correo de voz de sistema de teléfono es compatible con mensajes de correo de voz para depositar sólo en un buzón de Exchange y no es compatible con los sistemas de correo de terceros. Como un mecanismo de reserva, correo de voz del sistema de teléfono puede reenviar mensajes mediante SMTP, lo que significa que los usuarios con un buzón en un sistema de correo de terceros recibirán sus mensajes de correo de voz con ningún tiempo de actividad de servicio garantizado u otras características de correo de voz, como el cambio sus saludos y otras configuraciones. 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Entornos sólo de nube: configurar correo de voz del sistema de teléfono

Para Skype para usuarios de negocios en línea y planes de llamada, correo de voz del sistema telefónico se configuran automáticamente y aprovisionado para los usuarios después de asignar una licencia de **Sistema de teléfono** y un número de teléfono a ellos.
  
1. Si la función de sistema de teléfono no está incluida en el plan, debe adquirir licencias adicionales de **Sistema telefónico** . También necesitará adquirir una licencia de Exchange Online. Consulte [Skype para negocios y equipos de Microsoft licencias adicionales](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias para Office 365 para el negocio](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asigne Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa. Después de hacerlo, podrán recibir mensajes del correo de voz.
    
3. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todas las organizaciones y los usuarios. Puede deshabilitar la transcripción para su organización mediante Windows PowerShell y los pasos siguientes.
    
## <a name="phone-system-with-on-premises-environments"></a>Sistema de teléfono con los entornos locales

Es la siguiente información acerca de cómo configurar el correo de voz del sistema telefónico para trabajar con entornos de Plan de llamadas locales.
  
1. Si la función de sistema de teléfono no está incluida en el plan, debe adquirir licencias adicionales de **Sistema telefónico** . También necesitará adquirir una licencia de Exchange Online. Consulte [Skype para negocios y equipos de Microsoft licencias adicionales](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias para Office 365 para el negocio](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asigne Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.
    
3. Siga las instrucciones en la sección **Habilitar usuarios para la voz del sistema de teléfono y los servicios de correo de voz** de la [Configurar Skype para conector de nube Business Edition Guía](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todas las organizaciones y los usuarios. Puede deshabilitar la transcripción para su organización mediante Windows PowerShell y los pasos siguientes. 
    
5. También puede ver el [correo de voz de PBX de Azure soporte para Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar la entrega de mensajes de correo de voz de Azure para los usuarios del sistema telefónico que tienen un buzones locales.
    
## <a name="setting-voicemail-policies-in-your-organization"></a>Configuración de directivas de correo de voz en su organización

Transcripción de correo de voz está activado por defecto y masking de palabras soeces de transcripción está deshabilitada de forma predeterminada para todas las organizaciones y usuarios; Sin embargo, puede controlar mediante el uso de los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) y [CsOnlineVoicemailPolicy de la concesión](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .
  
> [!IMPORTANT]
> No se puede crear una nueva instancia de directiva para la transcripción y palabras soeces de transcripción masking mediante el cmdlet **New-CsOnlineVoiceMailPolicy** , y no se puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy** .
  
Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz. Para ver todas las instancias de la directiva de correo de voz disponibles, puede utilizar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desactivar la transcripción para su organización

Debido a la configuración predeterminada de transcripción está activada para la organización, desea deshabilitar utilizando el [Conjunto CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para ello, ejecute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activar el enmascaramiento de palabras soeces de transcripción para su organización

Enmascaramiento de palabras soeces de transcripción está deshabilitada de forma predeterminada para su organización. Si hay un requerimientos del negocio para habilitarlo, puede habilitar palabras soeces de transcripción masking mediante el uso [Conjunto de CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para ello, ejecute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desactivar la transcripción para un usuario

Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización. Por ejemplo, si está habilitada la transcripción de correo de voz para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción para un usuario específico mediante el cmdlet de [Concesión CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .
  
Para deshabilitar la transcripción para un único usuario, ejecute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activar el enmascaramiento de palabras soeces de transcripción para un usuario

Para habilitar el enmascaramiento de palabras soeces de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de palabras soeces de transcripción para un usuario específico mediante el cmdlet de [Concesión CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .
  
Para habilitar palabras soeces de transcripción masking para un único usuario, ejecute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse. 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial

Tenemos información de capacitación y artículos para ayudar a los usuarios a tener éxito con Skype para correo de voz de negocio. Pídales que consulten los siguientes artículos:
  
- [Comprobar Skype para opciones y correo de voz de negocio](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar su correo de voz de Skype para el negocio, cambiar su saludo del correo de voz, cambiar la configuración de correo de voz y escuchar su correo de voz a diferentes velocidades.
    
- [Aprendizaje de Skype Empresarial 2016](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a>See also
[Configurar Skype Empresarial Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Esto es lo que conseguirá con Sistema telefónico en Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

## <a name="feedback"></a>¿Comentarios?
Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).
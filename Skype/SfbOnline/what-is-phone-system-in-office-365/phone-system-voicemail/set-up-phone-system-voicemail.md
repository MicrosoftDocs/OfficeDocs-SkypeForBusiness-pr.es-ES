---
title: Configurar el correo de voz del sistema de teléfono
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 93dd33eefe587c548e346974cc86fe2608b392ec
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="set-up-phone-system-voicemail"></a>Configurar el correo de voz del sistema de teléfono

En este artículo es para la [administración de Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que desea configurar la característica de correo de voz de sistema telefónico para todos los usuarios en la empresa.
  
> [!NOTE]
> Correo de voz de teléfono del sistema admite depositar los mensajes de correo de voz sólo en un buzón de Exchange y no es compatible con los sistemas de correo electrónico de otro fabricante. Como un mecanismo de reserva, correo de voz de sistema telefónico puede reenviar mensajes mediante SMTP, lo que significa que los usuarios con un buzón de correo en un sistema de correo electrónico de otro fabricante recibirán sus mensajes de correo de voz con ningún tiempo de actividad de servicio garantizado u otras características de correo de voz, como el cambio sus saludos y otras opciones de configuración. 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Entornos de nube: configurar el correo de voz del sistema de teléfono

Para Skype para los usuarios en línea de negocio y planes de llamada, correo de voz del sistema telefónico se configuran automáticamente y aprovisionar para los usuarios después de asignar una licencia de **Sistema telefónico** y un número de teléfono a ellos.
  
1. Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** . También es posible que necesite comprar una licencia de Exchange Online. Vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asignación de Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa. Después de hacerlo, podrán recibir mensajes del correo de voz.
    
3. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones. Puede deshabilitar transcripción para su organización mediante Windows PowerShell y los pasos siguientes.
    
## <a name="phone-system-with-on-premises-environments"></a>Sistema telefónico con entornos local

Es la siguiente información acerca de cómo configurar el correo de voz de sistema telefónico para trabajar con entornos de planeación de llamada local.
  
1. Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** . También necesitará comprar una licencia de Exchange Online. Vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asignación de Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.
    
3. Siga las instrucciones que aparecen en la sección **Permitir que los usuarios de voz de sistema telefónico y servicios de correo de voz** de la [Configuración de Skype para guía de Business Edition de conector en la nube](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones. Puede deshabilitar transcripción para su organización mediante Windows PowerShell y los pasos siguientes. 
    
5. También puede ver el [correo de voz de PBX de Azure compatibilidad para Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar la entrega de mensajes de correo de voz de Azure para los usuarios del sistema telefónico que tienen un buzones locales.
    
## <a name="setting-voicemail-policies-in-your-organization"></a>Configuración de directivas de correo de voz en su organización

Transcripción de correo de voz está habilitada de forma predeterminada y enmascaramiento de contenido ofensivo transcripción está deshabilitada de forma predeterminada para todas las organizaciones y a los usuarios; Sin embargo, se puede controlar mediante el uso de los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .
  
> [!IMPORTANT]
> No se puede crear una nueva instancia de directiva para transcripción y contenido ofensivo de transcripción de transparencias con el cmdlet **New-CsOnlineVoiceMailPolicy** y no se puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy** .
  
Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz. Para ver todas las instancias de la directiva de correo de voz disponibles, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desactivar la transcripción para su organización

Debido a que el valor predeterminado de transcripción está activada para la organización, desea deshabilitar mediante el uso de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para ello, ejecute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>La activación de enmascaramiento de contenido ofensivo transcripción para su organización

Enmascaramiento de contenido ofensivo transcripción está deshabilitada de forma predeterminada para la organización. Si no hay un requisitos empresariales para habilitarlo, puede habilitar contenido ofensivo de transcripción de transparencias mediante el uso de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para ello, ejecute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desactivar la transcripción para un usuario

Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización. Por ejemplo, si está habilitada la transcripción de correo de voz para todos los usuarios, puede asignar una directiva para deshabilitar transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .
  
Para deshabilitar la transcripción para un único usuario, ejecute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>La activación de enmascaramiento de contenido ofensivo transcripción para un usuario

Para habilitar el enmascaramiento de contenido ofensivo transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .
  
Para habilitar contenido ofensivo de transcripción de transparencias para un único usuario, ejecute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse. 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial

Disponemos de información de recursos de aprendizaje y artículos para ayudar a los usuarios a tener éxito con Skype para correo de voz empresarial. Pídales que consulten los siguientes artículos:
  
- [Comprobación de Skype para opciones y correo de voz empresarial](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar el correo de voz de Skype para la empresa, cambiar el saludo del correo de voz, cambiar la configuración del correo de voz y escuchar el correo de voz a diferentes velocidades.
    
- [Aprendizaje de Skype Empresarial 2016](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a>See also
[Configurar Skype Empresarial Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Esto es lo que conseguirá con Sistema telefónico en Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 
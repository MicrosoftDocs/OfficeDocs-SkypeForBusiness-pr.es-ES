---
title: Planear el Correo de voz en la nube
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el correo de voz en la nube para los usuarios. '
ms.openlocfilehash: 26594c9d955cb21dc5751491e1857525660bdcae
ms.sourcegitcommit: 7ca70e8a2108462afd505258b455169ead30f33f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31041937"
---
# <a name="set-up-cloud-voicemail"></a>Planear el Correo de voz en la nube

En este artículo es para la [administración de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que desea configurar la característica de correo de voz en la nube para todos los usuarios en la empresa.

> [!NOTE]
> Correo de voz en la nube admite depositar los mensajes de correo de voz sólo en un buzón de Exchange y no es compatible con los sistemas de correo electrónico de otro fabricante. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Entornos de nube: configurar el correo de voz en la nube

Para Skype para los usuarios en línea de negocio y planes de llamada, correo de voz en la nube se configuran automáticamente y aprovisionar para los usuarios después de asignar una licencia de **Sistema telefónico** y un número de teléfono a ellos.
  
1. Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** . También es posible que necesite comprar una licencia de Exchange Online. Vea [las licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa. Después de hacerlo, podrán recibir mensajes del correo de voz.
    
3. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones. Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.

## <a name="phone-system-with-on-premises-environments"></a>Sistema telefónico con entornos locales

Es la siguiente información acerca de cómo configurar el correo de voz en la nube para trabajar con entornos de planeación de llamada local.
  
1. Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** . También necesitará comprar una licencia de Exchange Online. Vea [las licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.
    
3. Siga las instrucciones que coincidan con RTC local al llamar a la solución de implementada para los usuarios. Edition de conector en la nube, siga las instrucciones que aparecen en la sección **Permitir que los usuarios de servicios de voz y correo de voz del sistema de teléfono** de la [Configuración de Skype para guía de Business Edition de conector en la nube](https://technet.microsoft.com/library/mt605228.aspx). Para llamar a con Skype para Business Server de RTC, siga [Habilitar a los usuarios para Enterprise Voice en local](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises). Para el enrutamiento directo de los equipos, siga la sección **Configurar el número de teléfono y habilitar enterprise voice y correo de voz** de [Configurar el enrutamiento directo](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).

4. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones. Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.

5. Los mensajes de correo de voz se envían al buzón de Exchange de los usuarios a través de SMTP que se enrutan a través de Exchange Online Protection. Para habilitar la entrega de estos mensajes se realizó correctamente, asegúrese de que los conectores de Exchange se han configurado correctamente entre los servidores de Exchange y Exchange Online Protection. [Usar conectores para configurar el flujo de correo](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

6. Para habilitar las características de correo de voz como personalizar saludo, marcado en access y correo de voz visual, se requiere conectividad de Office 365 para el buzón de correo de Exchange server a través de servicios Web de Exchange. Para habilitar esta conectividad debe configurar el nuevo Oauth de Exchange se describe el protocolo de autenticación de [OAuth de configurar la autenticación entre organizaciones de Exchange y Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx) 

> [!NOTE]
> El Asistente de Exchange híbrida ejecución desde Exchange 2013 CU5 o mayor controlará los requisitos en los pasos 5 y 6 automáticamente. 

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuración de directivas de correo de voz en su organización

La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

> [!IMPORTANT]
> No se puede crear una nueva instancia de directiva para transcripción y contenido ofensivo de transcripción de transparencias con el cmdlet **New-CsOnlineVoiceMailPolicy** y no se puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy** .

Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz. Para ver todas las instancias de la directiva de correo de voz disponibles, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desactivar la transcripción para su organización

Debido a que el valor predeterminado de transcripción está activada para la organización, desea deshabilitar mediante el uso de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para ello, ejecute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activar el enmascaramiento de contenido ofensivo de transcripción para su organización

El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización. Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para ello, ejecute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desactivar la transcripción para un usuario

Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización. Por ejemplo, si está habilitada la transcripción de correo de voz para todos los usuarios, puede asignar una directiva para deshabilitar transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

Para deshabilitar la transcripción para un único usuario, ejecute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario

Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial

Disponemos de información de recursos de aprendizaje y artículos para ayudar a los usuarios a tener éxito con Skype para correo de voz empresarial. Pídales que consulten los siguientes artículos:

- [Comprobación de Skype para opciones y correo de voz empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar el correo de voz de Skype para la empresa, cambiar el saludo del correo de voz, cambiar la configuración del correo de voz y escuchar el correo de voz a diferentes velocidades.

- [Aprendizaje de Skype Empresarial 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Esto es lo que conseguirá con Sistema telefónico en Office 365](here-s-what-you-get-with-phone-system.md)



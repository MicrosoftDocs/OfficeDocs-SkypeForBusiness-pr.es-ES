---
title: Configurar el correo de voz del Sistema telefónico
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
description: 'Aprenda a configurar el correo de voz del sistema telefónico (Cloud PBX) para los usuarios de Skype for Business. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252893"
---
# <a name="set-up-phone-system-voicemail"></a>Configurar el correo de voz del Sistema telefónico

Este artículo está destinado a los [administradores de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseen configurar el correo de voz del Sistema telefónico para todos los miembros de sus organizaciones.

> [!NOTE]
> El correo de voz del Sistema telefónico permite depositar mensajes de voz solo en un buzón de Exchange y no admite sistemas de correo electrónico de terceros. Como mecanismo de reserva, el correo de voz del Sistema telefónico puede reenviar mensajes mediante SMTP, lo que significa que los usuarios que tengan un buzón de un sistema de correo electrónico de terceros recibirán sus mensajes del correo de voz sin ninguna garantía del tiempo de actividad del servicio u otras funciones del correo de voz, como poder cambiar los saludos y otras configuraciones.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Entornos de solo nube: configurar el correo de voz del Sistema telefónico

Para los usuarios de Skype for Business Online y de los planes de llamadas, el buzón de voz del Sistema telefónico se configura y aprovisiona automáticamente para los usuarios después de asignarles una licencia del **Sistema telefónico** y un número de teléfono.

1. Si la característica del Sistema telefónico no está incluida en su plan, es posible que tenga que adquirir licencias de complementos de **Sistema telefónico**. También puede que tenga que comprar una licencia de Exchange Online. Vea [Licencias de complementos de Skype for Business y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Asignar o cancelar licencias para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [Asignar licencias de Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) y las licencias de Exchange Online a los miembros de su organización. Después de hacerlo, podrán recibir mensajes del correo de voz.

3. La compatibilidad de la transcripción del correo de voz se agregó en marzo de 2017 y está habilitada de manera predeterminada para todos los usuarios y organizaciones. Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.

## <a name="phone-system-with-on-premises-environments"></a>Sistema telefónico con entornos locales

La siguiente información se refiere a la configuración del correo de voz del Sistema telefónico para que funcione con los entornos locales del Plan de llamadas.

1. Si la característica del Sistema telefónico no está incluida en su plan, es posible que tenga que adquirir licencias de complementos de **Sistema telefónico**. También debe comprar una licencia de Exchange Online. Vea [Licencias de complementos de Skype for Business y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Asignar o cancelar licencias para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [Asignar licencias de Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) y las licencias de Exchange Online a los miembros de su organización.

3. Siga las instrucciones de la sección **Habilitar usuarios para servicios de voz del Sistema telefónico y correo de voz** de la[Guía de configuración de Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).

4. La compatibilidad de la transcripción del correo de voz se agregó en marzo de 2017 y está habilitada de manera predeterminada para todos los usuarios y organizaciones. Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.

5. También puede ver el [soporte de correo de voz de Azure PBX para Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar la entrega de mensajes de correo de voz de Azure para usuarios del Sistema telefónico con buzones de correo locales.

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuración de directivas de correo de voz en su organización

La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).

> [!IMPORTANT]
> No puede crear una nueva instancia de la directiva para la transcripción y el enmascaramiento de contenido ofensivo de transcripción mediante el cmdlet **New-CsOnlineVoiceMailPolicy**, y no puede quitar una instancia de directiva existente mediante el cmdlet **Remove-CsOnlineVoiceMailPolicy**.

Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz. Para ver todas las instancias de directivas disponibles de correo de voz, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

 **PS C:\\> Get-CsOnlineVoicemailPolicy**

![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a>Desactivar la transcripción para su organización

Como la configuración predeterminada de la transcripción está activada para su organización, podrá deshabilitarla si lo desea mediante el cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para ello, ejecute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activar el enmascaramiento de contenido ofensivo de transcripción para su organización

El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización. Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para ello, ejecute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desactivar la transcripción para un usuario

Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización. Por ejemplo, si la transcripción del correo de voz está habilitada para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción de un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Para deshabilitar la transcripción para un único usuario, ejecute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario

Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).

Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype for Business

Disponemos de información instructiva y artículos que pueden servir de ayuda a los usuarios para que alcancen el éxito con el correo de voz de Skype for Business. Pídales que consulten los siguientes artículos:

- [Comprobar el correo de voz y las opciones de Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): este artículo explica cómo escuchar el correo de voz en Skype for Business, cambiar su saludo, cambiar su configuración y escucharlo a diferentes velocidades.

- [Aprendizaje de Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Esto es lo que conseguirá con el Sistema telefónico de Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)



---
title: "Configurar el correo de voz del sistema telefónico Ayuda de administración"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
description: "Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. "
---

# Configurar el correo de voz del sistema telefónico: Ayuda de administración

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Este artículo es para el [Acerca de los roles de administrador de Office 365](http://technet.microsoft.com/library/da585eea-f576-4f55-a1e0-87090b6aaa9d%28Office.14%29.aspx) que desea configurar la característica de correo de voz del sistema telefónico para todos los usuarios de su empresa.
  
> [!NOTE]
> Correo de voz de sistema de teléfono es compatible con los mensajes de correo de voz depositar solo en un buzón de Exchange y no es compatible con los sistemas de correo electrónico de terceros. Como mecanismo de reserva, correo de voz del sistema telefónico puede volver a enviar mensajes mediante SMTP, lo que significa que los usuarios con un buzón en un sistema de correo electrónico de terceros recibirán sus mensajes de correo de voz con ninguna actividad de servicio garantiza u otras características de correo de voz, como cambiar los saludos y otras opciones de configuración. 
  
## Entornos sólo de nube: configurar el correo de voz del sistema telefónico

Para Skype para empresarial Online y planes de llamar a los usuarios, correo de voz del sistema telefónico se configuran automáticamente y aprovisionado para los usuarios después de asignar una licencia de **Sistema telefónico** y un número de teléfono a los.
  
1. Si la característica de sistema de teléfono no está incluida en su plan, debe comprar licencias de complemento de **Sistema telefónico**. También debe comprar una licencia de Exchange Online. Vea [Skype para Business y Microsoft Teams licencias de complemento](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Asignar o cancelar licencia para Office 365 para empresas](http://technet.microsoft.com/library/997596b5-4173-4627-b915-36abac6786dc%28Office.14%29.aspx), el [Asignar Skype para Business y Microsoft Teams licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa. Después de eso, podrá recibir mensajes de correo de voz.
    
3. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitado de forma predeterminada para todos los usuarios y organizaciones. Puede deshabilitar transcripción para su organización con Windows PowerShell y los pasos siguientes.
    
## Sistema telefónico con entornos locales

Es la siguiente información acerca de cómo configurar el correo de voz del sistema telefónico para trabajar con entornos de llamar a planear locales.
  
1. Si la característica de sistema de teléfono no está incluida en su plan, debe comprar licencias de complemento de **Sistema telefónico**. También debe comprar una licencia de Exchange Online. Vea [Skype para Business y Microsoft Teams licencias de complemento](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Asignar o cancelar licencia para Office 365 para empresas](http://technet.microsoft.com/library/997596b5-4173-4627-b915-36abac6786dc%28Office.14%29.aspx), el [Asignar Skype para Business y Microsoft Teams licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.
    
3. Siga las instrucciones en la sección **Permitir que los usuarios de voz del sistema telefónico y servicios de correo de voz** de la[Configurar Skype para Business Cloud conector Edition Guía](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitado de forma predeterminada para todos los usuarios y organizaciones. Puede deshabilitar transcripción para su organización con Windows PowerShell y los pasos siguientes.
    
5. También puede ver el [correo de voz de Azure PBX de soporte técnico para Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar la entrega de mensajes de correo de voz de Azure para los usuarios de sistema telefónico que tienen un buzones locales.
    
## Configuración de directivas de correo de voz en su organización

Transcripción de correo de voz está habilitado de forma predeterminada para todas las organizaciones y los usuarios; Sin embargo, puede controlar los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) y[Conceder CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .
  
> [!IMPORTANT]
> No se puede crear una nueva instancia de directiva transcripción mediante el cmdlet **New-CsOnlineVoiceMailPolicy** y no se puede quitar una instancia de directiva existente mediante el cmdlet **Remove-CsOnlineVoiceMailPolicy**.
  
Puede administrar la configuración de transcripción para los usuarios con las directivas de correo de voz. Para ver todas las instancias de la directiva de correo de voz disponibles, puede usar la [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)[]()cmdlet.
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### Desactivar la transcripción para su organización

Debido a la configuración predeterminada de transcripción está activada para su organización, desea deshabilitar utilizando [Conjunto CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para ello, ejecute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### Desactivar la transcripción para un usuario

Directivas de usuario se evalúan antes de la configuración predeterminada de organización. Por ejemplo, si está habilitada la transcripción de correo de voz para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción para un usuario específico mediante el cmdlet [Conceder CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .
  
Para deshabilitar la transcripción para un único usuario, ejecute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse. 
  
## Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial

Tenemos información de aprendizaje y artículos para ayudar a los usuarios a tener éxito con el correo de voz de Skype Empresarial. Dirigir a los siguientes artículos:
  
- [Comprobar el correo de voz y las opciones de Skype Empresarial](http://technet.microsoft.com/library/2deea7f8-831f-4e85-a0d4-b34da55945a8%28Office.14%29.aspx): en este artículo se explica cómo escuchar su correo de voz de Skype empresarial, cambiar su saludo del correo de voz, cambiar la configuración de correo de voz y escuchar su correo de voz a diferentes velocidades.
    
- [Aprendizaje de Skype Empresarial 2016](http://technet.microsoft.com/library/eb2081bc-fd0a-4eda-94da-5a39f369ee74%28Office.14%29.aspx)
    
## Temas relacionados

[Configurar Skype Empresarial Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Aquí es lo que obtiene con el sistema telefónico en Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system-in-office-365.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  


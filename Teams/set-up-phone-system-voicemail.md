---
title: Configurar el Correo de voz en la nube
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el correo de voz en la nube para los usuarios. '
ms.openlocfilehash: fa30184d38822141d0f30404fb55b79eefd5d33d
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997428"
---
# <a name="set-up-cloud-voicemail"></a>Configurar el Correo de voz en la nube

Este artículo es para el administrador de Microsoft 365 u Office 365, como se describe en Acerca de los [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) de administrador que desea configurar la característica Correo de voz en la nube para todos los usuarios de la empresa.

> [!NOTE]
> El correo de voz en la nube admite el depósito de mensajes de correo de voz solo en un buzón de Exchange y no admite ningún sistema de correo electrónico de terceros. 

> [!NOTE]
> Cuando un delegado responde a una llamada en nombre de un delegado, las notificaciones no están disponibles en el correo de voz en la nube. Los usuarios pueden recibir notificaciones de llamadas perdidas.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Entornos solo en la nube: Configurar el correo de voz en la nube para los usuarios del sistema telefónico en línea

Para los usuarios del sistema telefónico en línea, el correo de voz en la nube se configura y aprovisiona automáticamente para los usuarios después de asignar una licencia del **sistema** telefónico a los usuarios. 

> [!NOTE]
> Para los usuarios del sistema telefónico de Skype Empresarial en línea con números de teléfono proporcionados localmente, es posible que deba habilitar el correo de voz hospedado con [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps). 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar el correo de voz en la nube para Exchange Server usuarios del buzón de correo

La siguiente información es sobre cómo configurar el correo de voz en la nube para trabajar con usuarios que están en línea para Phone System pero que tienen su buzón en Exchange Server. 
  
1. Los mensajes de correo de voz se entregan al buzón de Exchange de los usuarios mediante SMTP enrutados a través de Exchange Online Protection. Para habilitar la entrega correcta de estos mensajes, asegúrese de que los conectores de Exchange están configurados correctamente entre los servidores de Exchange y Exchange Online Protection; [Usar conectores para configurar el flujo de correo](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

2. Para habilitar las características del correo de voz, como personalizar saludos y mensajes de voz visuales en clientes de Skype Empresarial, es necesaria la conectividad desde Microsoft 365 u Office 365 al buzón del servidor Exchange a través de los servicios web de Exchange. Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de Oauth de Exchange descrito en Configurar autenticación de OAuth entre organizaciones de Exchange y [Exchange Online,](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)o ejecutar el Asistente híbrido de Exchange desde Exchange 2013 CU5 o posterior. Además, debe configurar la integración y Oauth entre Skype Empresarial Online y exchange server descrito en Configurar integración y [OAuth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)entre Skype Empresarial Online y Exchange Server . 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurar el correo de voz en la nube para usuarios de Skype Empresarial Server

Para configurar usuarios de Skype Empresarial Server para correo de voz en la nube, consulte Planear el servicio de correo de voz en la nube [para usuarios locales.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Habilitar el correo de voz protegido en su organización

Cuando alguien deja un mensaje de correo de voz para un usuario de su organización, el correo de voz se entrega al buzón del usuario como datos adjuntos de un mensaje de correo electrónico. Si usa reglas de flujo de correo para aplicar el cifrado de mensajes, puede evitar que esos mensajes de correo de voz se reenván a otros destinatarios. Al habilitar el correo de voz protegido, los usuarios pueden escuchar mensajes de correo de voz protegidos llamando a su buzón de voz o abriendo el mensaje en Outlook, Outlook en la Web o en Outlook para Android o iOS. Los mensajes de correo de voz protegidos no se pueden abrir en Skype Empresarial ni en Microsoft Teams.

Para obtener más información sobre el cifrado de mensajes, vea [Cifrado de correo electrónico.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Para configurar el correo de voz protegido, haga lo siguiente:

1. Vaya a https://admin.microsoft.com e inicie sesión con una cuenta con permisos de administrador global.
2. Seleccione **Mostrar todo y,** a continuación, vaya a Centros **de administración de**  >  **Exchange.**
3. En el Centro de administración de Exchange, seleccione **Reglas de flujo de**  >  **correo.**
4. Seleccione **+** **Agregar** y, a continuación, seleccione Aplicar cifrado de mensajes de **Office 365 y** protección de derechos a los mensajes.
5. Proporcione un nombre para la nueva regla de flujo de correo y, a continuación, en Aplicar **esta** regla si , seleccione Las propiedades del mensaje Incluya el tipo  >  **de mensaje Correo** de  >  **voz.** Seleccione **Aceptar**.
6. En **Hacer lo siguiente,** seleccione Aplicar cifrado de mensajes de **Office 365** y protección de derechos al mensaje con y, a continuación, **seleccione Seleccionar uno.** En **Plantilla RMS,** seleccione **No reenviar**. Seleccione **Aceptar** y, a **continuación, Guardar**.
    > [!NOTE]
    > Si la **lista de plantillas rms** está vacía, debe configurar el cifrado de mensajes. Para obtener más información sobre cómo configurar el cifrado de mensajes, vea los siguientes artículos:
    > - [Configurar nuevas funcionalidades de cifrado de mensajes](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configurar y administrar plantillas para Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Opción No reenviar para correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuración de directivas de correo de voz en su organización

> [!WARNING]
> Para los clientes de Skype Empresarial, deshabilitar el correo de voz a través de una directiva de llamadas de Microsoft Teams también puede deshabilitar el servicio de correo de voz para los usuarios de Skype Empresarial.

La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Los mensajes de correo de voz recibidos por los usuarios de su organización se transcribieron en la región donde se hospeda su organización de Microsoft 365 u Office 365. Es posible que la región donde se hospeda el inquilino no sea la misma región donde se encuentra el usuario que recibe el mensaje de correo de voz. Para ver la región donde se hospeda [](https://go.microsoft.com/fwlink/p/?linkid=2067339) el inquilino, vaya a la página Perfil de la organización y, a continuación, haga clic en **Ver detalles** junto a Ubicación **de datos.**

> [!IMPORTANT]
> No puede crear una nueva instancia de directiva para la transcripción y la transcripción con el cmdlet **New-CsOnlineVoiceMailPolicy** y no puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz. Para ver todas las instancias de directiva de correo de voz disponibles, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798311.aspx)

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
### <a name="turning-off-transcription-for-your-organization"></a>Desactivar la transcripción para su organización

Dado que la configuración predeterminada para la transcripción está en su organización, es posible que desee deshabilitarla mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para ello, ejecute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activar el enmascaramiento de contenido ofensivo de transcripción para su organización

El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización. Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para ello, ejecute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desactivar la transcripción para un usuario

Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización. Por ejemplo, si la transcripción del correo de voz está habilitada para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción de un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798309.aspx)

Para deshabilitar la transcripción para un único usuario, ejecute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario

Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> El servicio de correo de voz de Microsoft 365 y Office 365 almacena en caché directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ayudar a los usuarios a aprender las características del correo de voz de Teams

Tenemos la siguiente información para los usuarios sobre cómo administrar la configuración del correo de voz, así como otras características de llamadas en Teams:

- [Administrar la configuración de la llamada en Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) En este artículo se explica cómo administrar todas las características de llamadas de Teams para usuarios finales. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial

Tenemos información de aprendizaje y artículos para ayudar a los usuarios a tener éxito con el correo de voz de Skype Empresarial. Pídales que consulten los siguientes artículos:

- [Consulte el correo](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)de voz y las opciones de Skype Empresarial: en este artículo se explica cómo escuchar el correo de voz en Skype Empresarial, cambiar el saludo de correo de voz, cambiar la configuración del correo de voz y escuchar el correo de voz a diferentes velocidades.

- [Aprendizaje de Skype Empresarial 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Planificar la migración de Skype Empresarial Server y Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

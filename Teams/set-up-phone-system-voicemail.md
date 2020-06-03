---
title: Planear el Correo de voz en la nube
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el buzón de voz en la nube para sus usuarios. '
ms.openlocfilehash: 5526bee2bd365a4047e3641ea223941227858d1a
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523123"
---
# <a name="set-up-cloud-voicemail"></a>Planear el Correo de voz en la nube

Este artículo es para el [Administrador de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que desea configurar la característica de buzón de voz de la nube para todos los usuarios de la empresa.

> [!NOTE]
> El buzón de voz de nube admite el depósito de mensajes de voz solo en un buzón de Exchange y no es compatible con ningún sistema de correo de terceros. 

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-phone-system-users"></a>Entornos solo de nube: configurar el buzón de voz en la nube para usuarios del sistema telefónico

Para los usuarios de Skype empresarial online y planes de llamadas, el buzón de voz de nube se configura y se aprovisiona automáticamente para los usuarios después de asignarle una licencia de **sistema telefónico** y un número de teléfono.
  
1. Si la característica del sistema telefónico no está incluida en su plan, es posible que tenga que comprar licencias de complemento de **sistema telefónico** . Es posible que también necesite comprar una licencia de Exchange Online. Consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias de Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)y las licencias de Exchange Online para las personas de su empresa. Después de hacerlo, podrán recibir mensajes del correo de voz.
    
3. Se ha agregado la ayuda para la transcripción del buzón de voz a partir del 2017 de marzo y está habilitada de forma predeterminada para todas las organizaciones y todos los usuarios. Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar el buzón de voz en la nube para usuarios de buzones de Exchange Server

La siguiente información está relacionada con la configuración del buzón de voz de la nube para trabajar con usuarios que están conectados para el sistema telefónico pero que tienen su buzón en Exchange Server. 
  
1. Si la característica del sistema telefónico no está incluida en su plan, es posible que tenga que comprar licencias de complemento de **sistema telefónico** . Consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Asigne licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) a las personas de su empresa.
    
3. Se ha agregado la ayuda para la transcripción del buzón de voz a partir del 2017 de marzo y está habilitada de forma predeterminada para todas las organizaciones y todos los usuarios. Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.

4. Los mensajes de voz se entregan al buzón de Exchange de los usuarios mediante SMTP enrutado a través de Exchange Online Protection. Para habilitar la entrega correcta de estos mensajes, asegúrese de que los conectores de Exchange están configurados correctamente entre los servidores de Exchange y Exchange Online Protection; [Use conectores para configurar el flujo de correo](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

6. Para habilitar características de buzón de voz, como la personalización de saludos y el buzón de voz en Skype empresarial, se requiere conectividad de Office 365 al buzón de Exchange Server a través de los servicios Web de Exchange. Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de OAuth de Exchange que se describe en [configurar la autenticación de OAuth entre Exchange y Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), o ejecutar el Asistente de implementación híbrida de Exchange 2013 CU5 o superior. Además, debe configurar la integración y OAuth entre Skype empresarial online y Exchange Server que se describen en [configurar la integración y OAuth entre Skype empresarial online y Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises). 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurar el buzón de voz en la nube para usuarios de Skype empresarial Server

La siguiente información está relacionada con la configuración del buzón de voz de la nube para trabajar con usuarios que están conectados para Exchange y en el entorno local de Skype empresarial. 
  
1. Es posible que necesite comprar licencias de Exchange Online para las personas de su empresa. Consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Asignar o quitar licencias de Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) las licencias de Exchange Online para las personas de su empresa.
    
3. Se ha agregado la ayuda para la transcripción del buzón de voz a partir del 2017 de marzo y está habilitada de forma predeterminada para todas las organizaciones y todos los usuarios. Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.

4. Para configurar los usuarios de Skype empresarial Server para el buzón de voz de nube, consulte [planear el servicio de buzón de voz en la nube para usuarios locales](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)


> [!NOTE]
> Cuando un delegado responde a una llamada en nombre de un delegador, las notificaciones no están disponibles en el buzón de voz de la nube. Los usuarios pueden recibir notificaciones de llamadas perdidas.

## <a name="enabling-protected-voicemail-in-your-organization"></a>Habilitar el buzón de voz protegido en su organización

Cuando alguien deja un mensaje de voz para un usuario de su organización, el buzón de voz se envía al buzón del usuario como datos adjuntos de un mensaje de correo electrónico. Con las reglas de flujo de correo para aplicar el cifrado de mensajes, puede evitar que estos mensajes de voz se desvíen a otros destinatarios. Al habilitar el buzón de voz protegido, los usuarios pueden escuchar mensajes de voz protegidos llamando a su buzón de voz o abriendo el mensaje en Outlook, en Outlook en la web o en Outlook para Android o iOS. Los mensajes de buzón de voz protegidos no se pueden abrir en Skype empresarial.

Para obtener más información sobre el cifrado de mensajes, consulte [cifrado de correo electrónico](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).

Para configurar el buzón de voz protegido, haga lo siguiente:

1. Vaya a https://admin.microsoft.com e inicie sesión con una cuenta que tenga permisos de administrador global.
2. Seleccione **Mostrar todo** y, a continuación, vaya a **centro de administración**de  >  **Exchange**.
3. En el centro de administración de Exchange, seleccione reglas de **flujo de correo**  >  **Rules**.
4. Seleccione **+** **Agregar**y, a continuación, seleccione **aplicar el cifrado de mensajes de Office 365 y la protección de derechos a los mensajes**.
5. Escriba un nombre para la nueva regla de flujo de correo y, a continuación, en **aplicar esta regla si**, seleccione **el mensaje las propiedades**  >  **incluyen el**  >  **correo de voz**. Seleccione **Aceptar**.
6. En **hacer lo siguiente**, seleccione **aplicar el cifrado de mensajes de Office 365 y la protección de derechos al mensaje con** y, después, seleccione **seleccionar uno**. En **plantilla RMS**, seleccione no **reenviar**. Seleccione **Aceptar** y, a continuación, **Guardar**.
    > [!NOTE]
    > Si la lista de **plantillas de RMS** está vacía, debe configurar el cifrado de mensajes de Office 365. Para obtener más información sobre cómo configurar el cifrado de mensajes de Office 365, consulte los artículos siguientes:
    > - [Configurar nuevas capacidades de cifrado de mensajes de Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configuración y administración de plantillas para Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Opción no reenviar para correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuración de directivas de correo de voz en su organización

> [!WARNING]
> Para los clientes de Skype empresarial, deshabilitar el buzón de voz a través de una directiva de llamadas de Microsoft Teams también puede deshabilitar el servicio de buzón de voz para los usuarios de Skype empresarial.

La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Los mensajes de voz recibidos por los usuarios de su organización se transforman en la región donde está hospedada su organización de Office 365. Es posible que la región en la que se hospeda el inquilino no sea la misma región en la que se encuentra el usuario que recibe el mensaje de voz. Para ver la región donde se hospeda el inquilino, vaya a la página del perfil de la [organización](https://go.microsoft.com/fwlink/p/?linkid=2067339) y haga clic en **Ver detalles** junto a **Ubicación de datos**.

> [!IMPORTANT]
> No puede crear una nueva instancia de directiva para transcripción y máscaras de blasfemias por transcripción con el cmdlet **New-CsOnlineVoiceMailPolicy** y no puede quitar una instancia de directiva existente mediante el cmdlet **Remove-CsOnlineVoiceMailPolicy** .

Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz. Para ver todas las instancias disponibles de la Directiva del buzón de voz, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desactivar la transcripción para su organización

Dado que la configuración predeterminada de transcripción está activada para su organización, es posible que desee deshabilitarla mediante [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para ello, ejecute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activar el enmascaramiento de contenido ofensivo de transcripción para su organización

El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización. Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para ello, ejecute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desactivar la transcripción para un usuario

Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización. Por ejemplo, si la transcripción del buzón de voz está habilitada para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

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
> El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ayudar a los usuarios a aprender las características del buzón de voz

Tenemos la siguiente información para los usuarios sobre la administración de la configuración del buzón de voz, así como otras características de llamadas en Teams:

- [Administre la configuración de llamadas en Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). En este artículo se explica cómo administrar todas las características de las llamadas de los equipos de los usuarios finales. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial

Tenemos información de aprendizaje y artículos que ayudan a los usuarios a tener éxito con el buzón de voz de Skype empresarial. Pídales que consulten los siguientes artículos:

- [Consulta el buzón de voz y las opciones de Skype empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar el buzón de voz en Skype empresarial, cambiar el saludo del correo de voz, cambiar la configuración del buzón de voz y escuchar el buzón de voz a velocidades diferentes.

- [Aprendizaje de Skype Empresarial 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Esto es lo obtiene con el Sistema telefónico de Office 365](here-s-what-you-get-with-phone-system.md)

[Planificar la migración de Skype Empresarial Server y Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


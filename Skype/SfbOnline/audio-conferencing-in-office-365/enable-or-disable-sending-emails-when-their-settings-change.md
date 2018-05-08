---
title: Habilitar o deshabilitar el envío de los correos electrónicos al cambia su configuración
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: a588c5b425fe3d71ecd6d73193348b98e8e2f298
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio

Cuando están habilitados para conferencias de Audio, se notificación automáticamente a los usuarios por correo electrónico. Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a Skype para usuarios profesionales y Microsoft Teams. En estos casos, puede deshabilitar el envío de correo electrónico.
  
Si se deshabilitación el envío de los correos electrónicos, mensajes de correo electrónico de conferencia de Audio no se enviará a los usuarios, incluidos los correos electrónicos para cuando los usuarios se habilitan o deshabilitan para conferencias de audio, cuando se restablezca su NIP y cuando el identificador de conferencia y la conferencia predeterminado cambios del número de teléfono .
  
Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:
  
![Correo electrónico de conferencia audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que están habilitados para conferencias de audio:
    
  - Cuando se asigna una licencia de **Conferencias de Audio** a ellos.
    
  - Al restablecer manualmente PIN de conferencia de audio del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando la licencia de **Conferencias de Audio** se quita de ellos.
    
  - Cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a otro proveedor o **Ninguno**.
    
  - Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar el correo electrónico no se envía a los usuarios

Puede usar Microsoft Teams, el Skype para el centro de administración de negocio o Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**
1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.

4. Haga clic en **Guardar**.
  
![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
    
1. En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
2. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.
    
3. Click **Save**.
    
    > [!TIP]
    > También puede enviar correo electrónico a un usuario con la configuración de conferencias de audio, vaya a la **conferencia de Audio** > **a los usuarios**, seleccione el usuario y haga clic en **Enviar información de conferencia a través de correo electrónico**.  Si lo hace, se enviará un correo electrónico que incluye solo identificador de conferencia y el número de teléfono de conferencia, pero no el PIN.  Para obtener más información, vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
- Ejecute el siguiente procedimiento para deshabilitar el envío de los correos electrónicos: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para obtener ayuda con este cmdlet, vea [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?

- Cuando están deshabilitados los correos electrónicos, puede desencadenar manualmente enviar un correo electrónico con el número de identificador y el teléfono de conferencia utilizando el Skype para el centro de administración de negocio. Sin embargo, si lo hace, no se incluirá el PIN. Si desea restablecer el PIN de conferencia de audio y enviar mensajes de correo electrónico está deshabilitado, debe enviar al usuario en otra forma.
    
- El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Puede usar estos cmdlets para ahorrar tiempo o automatizar esto.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Correos electrónicos enviados a los usuarios cuando cambie su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)



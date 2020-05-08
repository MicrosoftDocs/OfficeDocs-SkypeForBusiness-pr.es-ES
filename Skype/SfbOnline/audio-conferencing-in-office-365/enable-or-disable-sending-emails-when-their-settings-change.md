---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando cambia la configuración de las conferencias de audio en Skype empresarial online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164269"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Habilitar o deshabilitar el envío de correos electrónicos cuando cambia la configuración de las conferencias de audio en Skype empresarial online

> [!Note]
> Si desea habilitar o deshabilitar el envío de correos electrónicos en Microsoft Teams, consulte [habilitar o deshabilitar el envío de correos electrónicos cuando cambia la configuración de las conferencias de audio en Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

A los usuarios se les notifica automáticamente por correo electrónico cuando están habilitadas para audioconferencia. Sin embargo, puede haber ocasiones en las que desee reducir el número de mensajes de correo electrónico que se envían a los usuarios de Skype empresarial. En estos casos, puede deshabilitar el envío de correo electrónico.
  
Si deshabilita el envío de correos electrónicos, los correos electrónicos de las conferencias de audio no se enviarán a los usuarios, incluidos los mensajes de correo electrónico para cuando los usuarios se habilitan o deshabilitan para las conferencias de audio, cuando se restablece el PIN y cuando cambia el identificador de conferencia y el número de teléfono de conferencia predeterminado.
  
Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para las conferencias de audio:
  
![Correo electrónico de audioconferencia](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Se envían varios correos electrónicos a los usuarios de su organización después de que estén habilitados para las conferencias de audio:
    
  - Cuando se les asigna una licencia de **conferencias de audio** .
    
  - Cuando restablece manualmente el PIN de conferencia de audio del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se quita la licencia de **audioconferencias** .
    
  - Cuando se cambia el proveedor de conferencias de audio de un usuario de Microsoft a otro proveedor o a **ninguno**.
    
  - Cuando se cambia el proveedor de servicios de audioconferencia de un usuario a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar el envío de mensajes de correo electrónico a los usuarios

Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local

 
![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**
    
1. En el **centro de administración de Skype empresarial**, en la barra de navegación izquierda, haga clic en **audioconferencia**.
    
2. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.
    
3. Haga clic en **Guardar**.
    
    > [!TIP]
    > También puede enviar correo electrónico a un usuario con la configuración de la audioconferencia yendo a **Audio conferencing** > **usuarios**de la Conferencia de audio, selecciona el usuario y haciendo clic en **enviar información de conferencia por correo electrónico**.  Si lo hace, se enviará un correo electrónico que solo incluya el identificador de la Conferencia y el número de teléfono de la Conferencia, pero no el PIN.  Consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md) para obtener más información.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
- Para deshabilitar el envío de correos electrónicos, ejecute lo siguiente: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para obtener ayuda con este cmdlet, vea [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Cuando los correos electrónicos automáticos están deshabilitados, aún puede desencadenar manualmente el envío de un correo electrónico con la identificación de la Conferencia y el número de teléfono con el centro de administración de Skype empresarial. Sin embargo, si lo haces, no se incluirá el PIN. Si desea restablecer el PIN de audioconferencia y enviar mensajes de correo electrónico está deshabilitado, tendrá que enviarlo al usuario de otra manera.
    
- El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Puede usar estos cmdlets para ahorrar tiempo o automatizar este.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Correos electrónicos enviados a los usuarios cuando cambia la configuración de la audioconferencia](emails-sent-to-users-when-their-settings-change.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)



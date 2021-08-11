---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando la configuración de conferencias de audio cambie en Skype Empresarial Online
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
ms.openlocfilehash: f2c0112f3817bfd64184018770348ee50ecb5f31c9b6dd161c90f70bdae97eb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335740"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Habilitar o deshabilitar el envío de correos electrónicos cuando la configuración de conferencias de audio cambie en Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Si desea habilitar o deshabilitar el envío de correos electrónicos en Microsoft Teams, vea Habilitar o deshabilitar el envío de correos electrónicos cuando la configuración de conferencias de audio cambie [en Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Los usuarios se notifican automáticamente por correo electrónico cuando están habilitados para las audioconferencias. Sin embargo, puede haber ocasiones en las que quiera reducir el número de correos electrónicos que se envían a Skype Empresarial usuarios. En estos casos, puede deshabilitar el envío de correo electrónico.
  
Si deshabilita el envío de correos electrónicos, los correos electrónicos de audioconferencia no se enviarán a los usuarios, incluidos los correos electrónicos para cuando los usuarios estén habilitados o deshabilitados para las audioconferencias, cuando se restablezca su PIN y cuando cambie el id. de conferencia y el número de teléfono de conferencia predeterminado.
  
Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para las audioconferencias:
  
![Correo electrónico de audioconferencia](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que estén habilitados para las audioconferencias:
    
  - Cuando se les asigna una licencia **de** audioconferencia.
    
  - Cuando restablezca manualmente el PIN de audioconferencia del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se **quita la licencia de conferencias** de audio.
    
  - Cuando el proveedor de audioconferencias de un usuario se cambia de Microsoft a otro proveedor o **Ninguno.**
    
  - Cuando el proveedor de audioconferencias de un usuario se cambia a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar el correo electrónico para que no se envíe a los usuarios

Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local

 
![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**
    
1. En el **Skype Empresarial de administración**, en el panel de navegación izquierdo, haga clic en **Audioconferencia.**
    
2. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.
    
3. Haga clic en **Guardar**.
    
    > [!TIP]
    > También puede enviar correo electrónico a un usuario con la configuración de audioconferencia yendo a **Usuarios** de audioconferencia, seleccionando al usuario y haciendo clic en Enviar información de conferencia  >  por **correo electrónico.**  Si lo hace, se enviará un correo electrónico que solo incluye el id. de conferencia y el número de teléfono de conferencia, pero no el PIN.  Vea Enviar un correo electrónico a un usuario con su información de [audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md) para obtener más información.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
- Ejecute lo siguiente para deshabilitar el envío de correos electrónicos: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para obtener ayuda con este cmdlet, vea [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Cuando los correos electrónicos automáticos están deshabilitados, todavía puede desencadenar manualmente el envío de un correo electrónico con el id. de conferencia y el número de teléfono con el Skype Empresarial de administración. Sin embargo, si lo hace, el PIN no se incluirá. Si desea restablecer el PIN de audioconferencia y enviar correos electrónicos está deshabilitado, tendrá que enviarlo al usuario de otra forma.
    
- El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Puede usar estos cmdlets para ahorrar tiempo o automatizar esto.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso de la Centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Correos electrónicos enviados a los usuarios cuando cambian sus opciones de audioconferencia](emails-sent-to-users-when-their-settings-change.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)

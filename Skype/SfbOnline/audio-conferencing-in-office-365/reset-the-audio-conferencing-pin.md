---
title: Restablecer el PIN de audioconferencia en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Descubra lo que debe saber acerca de los PINs y cómo restablecerlos en Skype Empresarial Online. '
ms.openlocfilehash: 4b042775a5a0525099c0116d7d55d0092f560cdf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114206"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Restablecer el PIN de audioconferencia en Skype Empresarial Online

> [!Note]
> Para obtener información sobre cómo restablecer los PIN de audioconferencia en Microsoft Teams, vea Restablecer el PIN de audioconferencia [en Microsoft Teams.](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)

Un PIN es un código que se crea con números para cada usuario de Skype Empresarial habilitado para las audioconferencias. Los organizadores de la reunión usan los PIN de audioconferencia para identificar que son el organizador de la reunión y permitirles iniciar una reunión por teléfono. Si usan la aplicación de Skype Empresarial para iniciar la reunión, no se requiere un PIN. Si los usuarios olvidan su PIN y no pueden encontrarlo en el correo electrónico que se les envió cuando se habilitaron para las audioconferencias, un administrador puede restablecer su PIN o puede restablecer su propio PIN.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une con la aplicación de Skype Empresarial o cuando el organizador se une con su PIN por teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.
  
## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

1. Inicie sesión con su cuenta de trabajo o escuela.
    
2. Vaya al centro de administración > **Skype Empresarial** y, en el panel de navegación izquierdo, haga clic en **Audioconferencia.**
    
3. Haga clic **en Usuarios** y seleccione el usuario para el que desea restablecer el PIN.
    
4. In the Action pane, under **PIN**, click **Reset**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Hacer que un usuario restablezca su propio PIN

Un usuario puede restablecer un PIN con la opción **Restablecer PIN** en la página **Conferencias de acceso** telefónico local. Se puede acceder a esta página de tres maneras:

* En un explorador, vaya a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) .
* En Skype Empresarial, haga clic en la flecha **Mostrar menú** junto a **Opciones** y, a continuación, haga clic en **Herramientas** configuración de conferencia de  >  **acceso telefónico.**
* En Skype Empresarial, haga  clic en **Opciones,** haga clic en  Reenvío de llamadas en el menú izquierdo y, a continuación, en la sección Más configuración de llamada, haga clic **en Editar configuración en línea.** 

## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Una vez que un administrador restablezca el PIN, el PIN se mostrará como *********** en el Centro de administración de **Skype** Empresarial y en los resultados cuando usen Get-CsCsOnlineDialInConfencingUser en Windows PowerShell.
    
- El envío automático de correos electrónicos a los usuarios está habilitado de forma predeterminada y los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para audioconferencias o cuando se restablezca el PIN. Pero si ha deshabilitado el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN a un usuario y tendrá que enviar manualmente la información del PIN al usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada es no permitir que los autores de llamadas anónimos puedan iniciar una reunión.
    
- Cuando habilita a un usuario para las audioconferencias, de forma predeterminada se envían correos electrónicos que incluyen información de conferencias y su PIN. El usuario debe tener un buzón de Microsoft 365 u Office 365, ya que cuando se restablezca un PIN, se enviará un nuevo PIN al usuario por correo electrónico a su dirección SMTP principal (alias) establecida para el usuario.
    
- Al configurar las audioconferencias, se establecen los dígitos necesarios para los PIN de su organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud del PIN, la configuración solo se aplica a los PIN generados recientemente y no se aplica a la configuración de PIN para los usuarios existentes habilitados para las audioconferencias. Vea Establecer la longitud del PIN para las reuniones [de audioconferencia.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)
    
- El correo electrónico de forma predeterminada se establecerá en la dirección SMTP principal de Microsoft 365 u Office 365 del usuario. Puede enviar un correo electrónico a una dirección que no sea de Microsoft 365 o que no sea de Office 365, como una dirección de correo electrónico de Hotmail MSN. Puede invalidar la dirección de correo electrónico predeterminada mediante Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Microsoft 365 u Office 365.
    
- Para invalidar la dirección de usuario predeterminada donde se envía el correo electrónico, el administrador de inquilinos puede usar el siguiente cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". El parámetro SendEmail es necesario para invalidar la dirección de correo electrónico del usuario.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Para establecer el PIN para Guillermo Rodarte, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Por qué necesita usar Microsoft 365 u Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad frente solo al uso del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md)
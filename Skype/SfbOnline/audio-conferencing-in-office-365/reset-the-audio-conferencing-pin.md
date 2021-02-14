---
title: Restablecer el PIN de Audioconferencia en Skype Empresarial Online
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
description: 'Descubra lo que debe saber sobre los números PIN y cómo restablecerlos en Skype Empresarial Online. '
ms.openlocfilehash: 21e2742653e72919df0647c0539fdb335585cc84
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164699"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Restablecer el PIN de Audioconferencia en Skype Empresarial Online

> [!Note]
> Para obtener información sobre cómo restablecer los PIN de Audioconferencia en Microsoft Teams, consulte Restablecer el PIN de [Audioconferencia en Microsoft Teams.](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)

Un PIN es un código creado a partir de números que se crea para cada usuario de Skype Empresarial habilitado para las audioconferencias. Los NÚMEROS PIN de audioconferencia son utilizados por el organizador de la reunión para identificar que es el organizador de la reunión y permitirles iniciar una reunión por teléfono. Si usan la aplicación Skype Empresarial para iniciar la reunión, no se necesita un PIN. Si los usuarios olvidan su PIN y no pueden encontrarlo en el correo electrónico que se les envió cuando se les habilitó para la audioconferencia, un administrador puede restablecer su PIN o restablecer su propio PIN.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une mediante la aplicación de Skype Empresarial o cuando el organizador se une con su PIN por teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.
  
## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

1. Inicie sesión con su cuenta del trabajo o de la escuela.
    
2. Vaya al centro de administración > **Skype Empresarial** y, en el panel de navegación izquierdo, haga clic en **Audioconferencia.**
    
3. Haga clic **en** Usuarios, seleccione el usuario para el que desea restablecer el PIN.
    
4. In the Action pane, under **PIN**, click **Reset**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Hacer que un usuario restablezca su propio PIN

Un usuario puede restablecer un PIN usando la opción **Restablecer PIN** en la página Conferencia **de acceso** telefónico local. Puede acceder a esta página de tres maneras:

* En un explorador, vaya a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) .
* En Skype Empresarial, haga clic en **la** flecha Mostrar menú junto a Opciones **y,** a continuación, haga clic en **Herramientas** de configuración de conferencia  >  **de acceso telefónico.**
* En Skype Empresarial, haga  clic en **Opciones,** haga clic en  Reenvío de llamadas en el menú izquierdo y, a continuación, en la sección Más configuraciones de llamadas, haga clic en Editar **configuración en línea.** 

## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Después de que un administrador restablezca el PIN, este aparecerá como *********** en el Centro de administración de **Skype** Empresarial y en los resultados cuando usen Get-CsCsOnlineDialInConfencingUser en Windows PowerShell.
    
- El envío automático de correos electrónicos a los usuarios está habilitado de forma predeterminada, y los usuarios recibirán un correo electrónico con su PIN cuando están habilitados para audioconferencia o cuando se restablece el PIN. Pero si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar manualmente la información del PIN al usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada es no permitir que autores de llamadas anónimos puedan iniciar una reunión.
    
- Cuando se habilita a un usuario para las audioconferencias, de forma predeterminada se envían correos electrónicos con información sobre la conferencia y su PIN. El usuario debe tener un buzón de Microsoft 365 u Office 365, porque cuando se restablece un PIN, se enviará un nuevo PIN al usuario por correo electrónico a su dirección SMTP principal (alias) configurada para el usuario.
    
- Al configurar la audioconferencia, establezca los dígitos necesarios para los NÚMEROS PIN de su organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud del PIN, la configuración solo se aplicará en los nuevos PIN y no se aplicará a la configuración de PIN de los usuarios existentes habilitados para audioconferencia. Vea [Establecer la longitud del PIN para las reuniones de Audioconferencia.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)
    
- El correo electrónico se establecerá de forma predeterminada en la dirección SMTP principal de Microsoft 365 u Office 365 del usuario. Puede enviar un correo electrónico a una dirección que no sea de Microsoft 365 o que no sea de Office 365, como una dirección de Hotmail o MSN. Puede reemplazar la dirección de correo electrónico predeterminada usando Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Microsoft 365 u Office 365.
    
- Para reemplazar la dirección de usuario predeterminada a la que se envía el correo electrónico, el administrador de inquilinos puede usar el siguiente cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". El parámetro SendEmail es necesario para invalidar la dirección de correo electrónico del usuario.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Para establecer el PIN para Guillermo Rodarte, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md)

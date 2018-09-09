---
title: Restablecer el PIN en Skype de conferencia de Audio para la empresa en línea
mms.author: tonysmit
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información acerca de cómo restablecer en Skype para profesionales en línea y lo que debe saber acerca de PIN. '
ms.openlocfilehash: 257f59f59d4fc86c91aa5496fe3db42573269065
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882142"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Restablecer el PIN en Skype de conferencia de Audio para la empresa en línea

> [!Note]
> Para obtener información acerca del restablecimiento de PIN de conferencia de Audio en Microsoft Teams, consulte [Restablecer el PIN de conferencia de Audio en los equipos de Microsoft](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Un NIP es un código formado por los números que se crean para cada Skype para usuarios de empresa que está habilitada para conferencias de audio. PIN de conferencia de audio se usan por los organizadores de reuniones para identificar que son el organizador de la reunión y que puedan iniciar una reunión a través del teléfono. Si usan el Skype para la aplicación empresarial para iniciar la reunión, un PIN no es necesario. Si los usuarios olvidan su PIN y no pueden encontrar en el correo electrónico que se envió a ellos cuando se han habilitado para conferencias de audio, un administrador puede restablecer su NIP, o pueden restablecer su propios NIP.
  
Las reuniones se pueden iniciar cuando se une a un usuario autenticado mediante la Skype para la aplicación empresarial o cuando se une el organizador con su PIN a través del teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.
  
## <a name="reset-a-users-pin"></a>Restablecer un PIN de usuario

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype para la empresa**y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
3. Haga clic en **usuarios**, seleccione el usuario que desea restablecer el PIN para.
    
4. En el panel Acción, en **PIN**, haga clic en **Restablecer**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Tener un usuario restablezca el NIP de su propia

Un usuario puede restablecer un PIN mediante el uso de la opción de **Restablecimiento de PIN** en la página de **conferencia de acceso telefónico** . Puede tener acceso a esta página en una de estas tres maneras:

* En un explorador, vaya a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* En Skype para la empresa, haga clic en la flecha **Mostrar menú** situada junto a **Opciones**y, a continuación, haga clic en **Herramientas de** > **Configuración conferencia de acceso telefónico**.
* En Skype para la empresa, haga clic en **Opciones**, haga clic en **Desvío de llamadas** en el menú de la izquierda y, a continuación, en la sección **Configuración de llamadas más** , haga clic en **Editar configuración en línea**. 

## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Después de restablece el PIN por un administrador, el NIP se mostrará como *** en el **Skype para el centro de administración de negocio** y en los resultados al usar Get-CsCsOnlineDialInConfencingUser en Windows PowerShell.
    
- Enviar automáticamente mensajes de correo electrónico a los usuarios está habilitado de forma predeterminada, y los usuarios recibirán un correo electrónico con su NIP cuando están habilitados para conferencias de audio o cuando se restablece el NIP. Pero si ha deshabilitado automáticamente enviar mensajes de correo electrónico, no se enviará un correo electrónico de restablecimiento PIN a un usuario y tendrá que enviar manualmente la información de PIN para el usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- El valor predeterminado es no permitir que una reunión sea iniciado por los autores de llamadas anónimas.
    
- Cuando se habilita un usuario para conferencias de audio, de forma predeterminada se envían mensajes de correo electrónico que incluyen información de conferencia y su PIN. El usuario debe tener un buzón de Office 365, porque cuando se restablece un NIP, un nuevo NIP se van a enviar al usuario por correo electrónico a su dirección SMTP principal (alias) que se establece para el usuario.
    
- Cuando se establece una conferencia con audio, establezca los dígitos que se requieren para el PIN en la organización. Los PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud PIN, la configuración se aplica solo a los PIN generados recientemente y no se aplica a la configuración de PIN para los usuarios existentes que están habilitados para conferencias de audio. Vea [establecer la longitud del eje para las reuniones de conferencia de Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- El correo electrónico de forma predeterminada se establecerá en la dirección SMTP principal de Office 365 del usuario. Puede enviar un correo electrónico a una dirección que no sean Office 365, como Hotmail o la dirección de correo electrónico MSN. Puede invalidar la dirección de correo electrónico predeterminada mediante el uso de Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Office 365.
    
- Para invalidar la dirección del usuario predeterminada donde se envía el correo electrónico, la administración de inquilinos puede usar el siguiente cmdlet: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - EnviarCorreoElectrónico - SendEmailToAddress "u@hotmail.com". El parámetro EnviarCorreoElectrónico es necesaria para reemplazar la dirección de correo electrónico del usuario.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Para establecer el PIN para Guillermo Rodarte, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplificidad y productividad respecto a utilizar únicamente el centro de administración de Office 365 como, por ejemplo, al realizar cambios de configuración para muchos usuarios en una única ubicación. Obtenga más información sobre estas ventajas en los temas siguientes:
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md)

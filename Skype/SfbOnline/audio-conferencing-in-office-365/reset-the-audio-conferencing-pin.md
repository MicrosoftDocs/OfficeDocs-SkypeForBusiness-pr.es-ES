---
title: Restablecer el PIN de audioconferencia en Skype empresarial online
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
description: 'Descubra lo que debe saber sobre los pin y cómo restablecerlos en Skype empresarial online. '
ms.openlocfilehash: a2f91e1ccae53f08507a63ea56b499a3ad968c73
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777705"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Restablecer el PIN de audioconferencia en Skype empresarial online

> [!Note]
> Para obtener información sobre cómo restablecer los pin de audioconferencia en Microsoft Teams, consulte [restablecer el PIN de audioconferencia en Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Un PIN es un código compuesto de números que se crean para cada usuario de Skype empresarial que tiene habilitada la audioconferencia. Los separadores de audioconferencias los usan los organizadores de la reunión para identificar que son el organizador de la reunión y le permiten iniciar una reunión a través del teléfono. Si usan la aplicación de Skype empresarial para iniciar la reunión, no se necesita un PIN. Si los usuarios olvidan su PIN y no pueden encontrarlo en el correo electrónico que se les envió cuando se habilitaron para la Conferencia de audio, un administrador puede restablecer su PIN o puede restablecer su propio PIN.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une con la aplicación de Skype empresarial o cuando el organizador se une a su PIN a través del teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.
  
## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

1. Inicie sesión con su cuenta profesional o educativa.
    
2. Vaya al centro de administración > **Skype empresarial**y, a continuación, en la barra de navegación izquierda, haga clic en **audioconferencia**.
    
3. Haga clic en **usuarios**y seleccione el usuario para el que desea restablecer el PIN.
    
4. In the Action pane, under **PIN**, click **Reset**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Hacer que un usuario restablezca su propio PIN

Un usuario puede restablecer un PIN con la opción **restablecer PIN** de la página de **conferencias de acceso telefónico local** . Puede acceder a esta página de una de tres maneras:

* En un explorador, vaya a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* En Skype empresarial, haga clic en la flecha del **menú Mostrar** junto a **Opciones**y, a continuación, haga clic en **herramientas** > **configuración de conferencia de acceso telefónico local**.
* En Skype empresarial, haga clic en **Opciones**, haga clic en **desvío de llamadas** en el menú de la izquierda y, a continuación, en la sección **más opciones de configuración** , haga clic en **Editar configuración en línea**. 

## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Una vez que un administrador restablezca el PIN, el PIN aparecerá como * * * * * * * * * * * en el centro de **Administración de Skype empresarial** y en los resultados cuando use Get-CsCsOnlineDialInConfencingUser en Windows PowerShell.
    
- El envío automático de correos electrónicos a los usuarios está habilitado de forma predeterminada y los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para conferencias de audio o cuando se restablezca el PIN. Pero si deshabilitaste el envío automático de correos electrónicos, no se enviará un mensaje de correo electrónico de restablecimiento de PIN a un usuario y tendrá que enviar manualmente la información del PIN al usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada es no permitir que los autores de llamadas anónimos inicien una reunión.
    
- Cuando habilita a un usuario para las conferencias de audio, se le envían mensajes de correo electrónico que incluyen información sobre conferencias y su PIN de forma predeterminada. El usuario debe tener un buzón de Office 365, porque cuando se restablece un PIN, se envía un PIN nuevo al usuario por correo electrónico a su dirección SMTP principal (alias) que está configurada para el usuario.
    
- Al configurar las conferencias de audio, se establecen los dígitos necesarios para los pin de la organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia el valor de longitud del PIN, la configuración solo se aplicará a los pin recién generados y no se aplicará a la configuración de PIN de los usuarios existentes que estén habilitados para las conferencias de audio. Consulte [establecer la longitud del PIN para las reuniones de audioconferencia](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- De forma predeterminada, el correo electrónico se establecerá en la dirección SMTP principal de Office 365 del usuario. Puede enviar un correo electrónico a una dirección que no sea de Office 365, como una dirección de correo electrónico de hotmail o MSN. Puede omitir la dirección de correo electrónico predeterminada mediante Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Office 365.
    
- Para invalidar la dirección de usuario predeterminada a la que se envía el correo electrónico, el administrador de inquilinos puede usar el siguiente cmdlet: set-CsOnlineDialInConferencingUser-amos. Marble-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com". El parámetro SendEmail es necesario para reemplazar la dirección de correo electrónico del usuario.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Para establecer el PIN para Guillermo Rodarte, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md)

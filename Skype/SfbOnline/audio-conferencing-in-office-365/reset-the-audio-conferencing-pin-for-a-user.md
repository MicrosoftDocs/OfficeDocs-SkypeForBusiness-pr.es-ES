---
title: Restablecer el PIN de conferencia de Audio para un usuario
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Find out what you should know about PINs and how to reset them for your users. '
ms.openlocfilehash: 1e0f91982f5ec81e9f82efb87a3e551bf8f7f8d0
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a>Restablecer el PIN de conferencia de Audio para un usuario

Un PIN es un código formado por números que se crean para cada Skype para usuarios empresariales y Teams de Microsoft está habilitado para conferencias de audio. Alfileres de conferencia de audio se utilizan los organizadores de la reunión para identificar que el organizador de la reunión y que les permiten iniciar una conferencia por teléfono. Si utilizan el Skype para la aplicación de negocios o Teams de Microsoft para iniciar la reunión, no se requiere un PIN. Si los usuarios olvidan su NIP y no puede encontrarla en el correo electrónico que se envió a ellos cuando se habilitaron para conferencias de audio, un administrador deberá restablecer su NIP. Un usuario no puede restablecer su propio PIN.
  
Las reuniones se pueden iniciar cuando se une a un usuario autenticado con un Skype para negocios o Teams Microsoft app o cuando el organizador se une con su PIN por teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.
  
## <a name="reset-a-conference-organizers-pin"></a>Restablecer el PIN del organizador de una conferencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Ir al **Centro de administración de Office 365** > **Skype para el negocio**y la exploración de la izquierda, haga clic en **conferencias de Audio**.
    
3. Haga clic en **usuarios**, seleccione el usuario que desea restablecer el PIN para.
    
4. In the Action pane, under **PIN**, click **Reset**.
    
## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Después de que un administrador la restablezca el NIP, el NIP se denominarán *** en el **Skype para el centro de administración de negocios** y en los resultados al usar Get-CsCsOnlineDialInConfencingUser en Windows PowerShell.
    
- Enviar automáticamente mensajes de correo electrónico a los usuarios está habilitado de forma predeterminada y los usuarios recibirán un correo electrónico con su NIP cuando están habilitados para conferencias de audio o cuando se restablece el NIP. Pero si ha deshabilitado automáticamente enviar mensajes de correo electrónico, no se enviará un correo electrónico de restablecimiento PIN al usuario y tendrá que enviar manualmente la información de PIN al usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada no permite una reunión sea iniciado por llamadores anónimos.
    
- Cuando se habilita un usuario para conferencias de audio, de forma predeterminada se envían mensajes de correo electrónico que incluyen información de la conferencia y su NIP. El usuario debe tener un buzón de Office 365, porque cuando se restablece un NIP, se enviará un nuevo NIP al usuario por correo electrónico a su dirección SMTP principal (alias) que se establece para el usuario.
    
- Cuando configura la audioconferencia, establezca los dígitos que se requieren para las patillas de la organización. Los PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud de NIP, la configuración sólo se aplica en los pines recién generados y no se aplica a la configuración de PIN para los usuarios existentes que están habilitados para conferencias de audio. Consulte [establecer la longitud del perno para las reuniones de conferencia de Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- El correo electrónico de forma predeterminada se establecerá en la dirección SMTP principal de Office 365 del usuario. Puede enviar un correo electrónico a una dirección de no Office 365 como un Hotmail o una dirección de correo electrónico MSN. Puede reemplazar la dirección de correo electrónico predeterminado mediante Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Office 365.
    
- Para reemplazar la dirección de usuario predeterminado que se envía el correo electrónico, la administración de inquilinos puede usar el cmdlet siguiente: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress "u@hotmail.com". El parámetro SendEmail es necesario reemplazar la dirección de correo electrónico del usuario.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Para establecer el PIN para Guillermo Rodarte, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md)

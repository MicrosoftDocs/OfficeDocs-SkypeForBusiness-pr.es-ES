---
title: "Restablecer el PIN de conferencia de Audio para un usuario"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
description: "Find out what you should know about PINs and how to reset them for your users. "
---

# Restablecer el PIN de conferencia de Audio para un usuario

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Un PIN es un código formado por números que se crean para cada Skype para Business y Microsoft Teams usuario que está habilitada para conferencias de audio. Los PIN de conferencia de audio se utilizan los organizadores de reuniones para identificar que el organizador de la reunión y que les permiten iniciar una reunión por teléfono. Si usa la Skype para empresas o Microsoft Teams la aplicación para iniciar la reunión, no se requiere un PIN. Si los usuarios olvidan su PIN y no puede encontrarla en el correo electrónico que se envió a ellos cuando se ha habilitado para conferencias de audio, será necesario un administrador restablecer su PIN. Un usuario no puede restablecer su propia PIN.
  
Cuando se une a un usuario autenticado con un Skype para empresas o Microsoft Teams la aplicación o cuando el Organizador entre con su PIN por teléfono, se pueden iniciar las reuniones. Se inicia cuando una reunión requiere un PIN para iniciar, los usuarios que unirse por teléfono se pondrán en la sala de espera y escuchar música en espera hasta que la reunión. Si el organizador de una reunión no requiere un PIN iniciar la reunión por teléfono, las personas que llaman no pedirá que proporcione un PIN al unirse a la reunión.
  
## Restablecer el PIN del organizador de una conferencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial**y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**
    
3. Haga clic en **usuarios**, seleccione el usuario que desea restablecer el PIN para.
    
4. En el panel Acción, **PIN**, haga clic en **Restablecer**.
    
## ¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, solo se muestra el PIN a un administrador en una sola vez, cuando se restablece el PIN. Después de restablece el PIN por un administrador, el PIN se mostrarán como ***** en **Skype centro de administración de la empresa** y en los resultados al usar Get-CsCsOnlineDialInConfencingUser en Windows PowerShell.
    
- Enviar automáticamente mensajes de correo electrónico a los usuarios está habilitado de forma predeterminada y los usuarios recibirán un correo electrónico con su PIN cuando se encuentran habilitadas para conferencias de audio o cuando se restablece el PIN. Pero, si ha deshabilitado automáticamente enviar correos electrónicos, no se enviará un correo electrónico de restablecimiento PIN a un usuario y tendrá que enviar manualmente la información de PIN para el usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada para no permitir una reunión para que se inicie anónimos autores de llamadas.
    
- Al habilitar un usuario para conferencias de audio, de forma predeterminada se envían mensajes de correo electrónico que incluyen información de conferencia y su PIN. El usuario debe tener un buzón de Office 365, porque cuando se restablece un PIN, se enviará un nuevo PIN para el usuario de correo electrónico a su dirección SMTP principal (alias) que se establece para el usuario.
    
- Al configurar conferencias de audio, establezca los dígitos necesarios para el PIN de su organización. PIN pueden ser de 4 a 12 dígitos: el valor predeterminado es 5. Si cambia la configuración de longitud PIN, la configuración se aplica solo a recién generados PIN y no se aplica a la configuración de PIN para los usuarios existentes que están habilitados para conferencias de audio. Vea [Establecer la longitud del PIN para reuniones de conferencia de Audio](set-the-length-of-the-pin-for-audio-conferencing-meetings.md).
    
- El correo electrónico de forma predeterminada se establecerá en la dirección SMTP principal de Office 365 del usuario. Puede enviar un correo electrónico a una dirección no sean Office 365, como Hotmail o la dirección de correo electrónico MSN. Puede omitir la dirección de correo electrónico predeterminada con Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Office 365.
    
- Para reemplazar la dirección de usuario predeterminada que se envía el correo electrónico, el Administrador de inquilinos puede usar el siguiente cmdlet: Set-CsOnlineDialInConferencingUser-amos.marble-ResetLeaderPIN - SendEmail - SendEmailToAddress "u@hotmail.com". El parámetro SendEmail es necesaria para reemplazar la dirección de correo electrónico del usuario.
    
## ¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
- Para establecer el PIN para Guillermo Rodarte, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no hacer. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas a realizar. Para empezar con Windows PowerShell, consulte estos temas:
    
  - [¿Por qué necesita usar PowerShell de Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas velocidad, simplificar y productividad sobre usando solo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios a la vez. Obtenga más información sobre estas ventajas en los siguientes temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  


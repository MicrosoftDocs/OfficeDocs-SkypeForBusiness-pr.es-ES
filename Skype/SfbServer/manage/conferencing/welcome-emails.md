---
title: Enviar correo electrónico de bienvenida para el marcado de los usuarios de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Resumen: Obtenga información sobre cómo dar la bienvenida a los usuarios a la conferencia de acceso telefónico en Skype para Business Server.'
ms.openlocfilehash: 51c4dbc04b44cb33e27cbe09f22608836485e9ad
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898497"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Enviar correo electrónico de bienvenida para el marcado de los usuarios de Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo dar la bienvenida a los usuarios a la conferencia de acceso telefónico en Skype para Business Server.
  
Después de configurar la conferencia de acceso telefónico local y de comprobar que funciona correctamente, necesita definir números de identificación personal (PIN) iniciales para usuarios e informar a los usuarios sobre la disponibilidad de la característica. Puede incluir instrucciones introductorias como el PIN inicial y el vínculo a la página web de configuración de conferencia de acceso telefónico local. 
  
Normalmente, use el cmdlet **Set-CsClientPin** para restablecer el PIN, pero puede usar el procedimiento de este tema si desea enviar un correo electrónico de bienvenida introductorio con la información de PIN. SI no quiere enviar el correo electrónico, puede usar **Set-CsClientPin**.
  
Puede usar el script **Set-CsPinSendCAWelcomeMail** para establecer el PIN y enviar un mensaje de bienvenida a un único usuario. De forma predeterminada, el script no restablece un PIN si ya está establecido, pero puede usar el parámetro Force para imponer el restablecimiento del PIN. El mensaje de correo electrónico se envía mediante el Protocolo simple de transferencia de correo (SMTP).
  
Puede crear un script que ejecute repetidamente el script **Set-CsPinSendCAWelcomeMail** para establecer PIN y enviar mensajes de correo electrónico a grupos de usuarios. Puede modificar la plantilla de mensaje de correo electrónico (es decir, el archivo CAWelcomeEmailTemplate.html) para agregar más vínculos a páginas de la intranet o modificar el texto del mensaje.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Establecer un PIN inicial y enviar un mensaje de correo electrónico de bienvenida

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer** De forma predeterminada, la secuencia de comandos utiliza el valor de la variable entorno reservadas **$PSEmailServer** para este parámetro. Si la variable **$PSEmailServer** no está establecida, debe especificar este parámetro.
    
**Credenciales** De forma predeterminada, la secuencia de comandos usa las credenciales del usuario actual. Si el usuario actual no tiene permisos para enviar un mensaje de correo electrónico en nombre de la dirección que aparece en "Desde" (From) especificada, debe especificar este parámetro. Como regla general, especifique este parámetro si no especifica su dirección de correo electrónico como la dirección que aparece en "Desde" (From).
    
En este ejemplo se crea un PIN y después se envía un mensaje de correo electrónico de bienvenida de Marco a Bob. Usa el texto del mensaje de la plantilla predeterminada y crea el mensaje de correo electrónico en formato HTML. El asunto (Subject) predeterminado es "Bienvenida a la conferencia de acceso telefónico local".
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

En este ejemplo se impone un PIN nuevo con un valor de "383042650" para Bob, aunque Bob tenía un PIN existente y luego se envía un mensaje de bienvenida de Marco a Bob. Dado que se especifica el parámetro Credential, se pide a la persona que ejecuta el comando que escriba una contraseña. El mensaje de correo electrónico se envía mediante la Capa de sockets seguros (SSL).
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```

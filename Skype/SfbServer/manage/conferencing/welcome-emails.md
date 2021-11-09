---
title: Enviar correo electrónico de bienvenida a los usuarios de acceso telefónico Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Summary: Learn how to welcome users to dial-in conferencing in Skype Empresarial Server.'
ms.openlocfilehash: 672e386c223e2b5b9f872334634ac315c9e900e1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848543"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Enviar correo electrónico de bienvenida a los usuarios de acceso telefónico Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo dar la bienvenida a los usuarios a las conferencias de acceso telefónico local en Skype Empresarial Server.
  
Después de configurar las conferencias de acceso telefónico local y la prueba para comprobar que funciona correctamente, debe establecer números de identificación personal (PIN) iniciales para los usuarios y notificar a los usuarios sobre la disponibilidad de la característica. Puede incluir instrucciones introductorias, como el PIN inicial y el vínculo a la página web de conferencias de acceso telefónico local Configuración web. 
  
Normalmente, usa el cmdlet **Set-CsClientPin** para restablecer los PIN, pero puede usar el procedimiento de este tema si desea enviar un correo electrónico de bienvenida introductorio con la información de PIN. Si no desea enviar el mensaje, puede usar **Set-CsClientPin**.
  
Puede usar el script **Set-CsPinSendCAWelcomeMail** para establecer el PIN y enviar un mensaje de bienvenida a un único usuario. De forma predeterminada, el script no restablece un PIN si ya está establecido, pero puede usar el parámetro Force para imponer el restablecimiento del PIN. El mensaje de correo electrónico se envía mediante el Protocolo simple de transferencia de correo (SMTP).
  
Puede crear un script que ejecute repetidamente el script **Set-CsPinSendCAWelcomeMail** para establecer PIN y enviar mensajes de correo electrónico a grupos de usuarios. Puede modificar la plantilla de mensaje de correo electrónico (es decir, el archivo CAWelcomeEmailTemplate.html) para agregar más vínculos a páginas de la intranet o modificar el texto del mensaje.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Establecer un PIN inicial y enviar correo electrónico de bienvenida

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
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

**SmtpServer** De forma predeterminada, el script usa el valor de la variable de **entorno reservado $PSEmailServer** para este parámetro. Si la variable **$PSEmailServer** no está establecida, debe especificar este parámetro.
    
**Credential** De forma predeterminada, el script usa las credenciales del usuario actual. Si el usuario actual no tiene permisos para enviar un mensaje de correo electrónico en nombre de la dirección que aparece en "Desde" (From) especificada, debe especificar este parámetro. Como regla general, especifique este parámetro si no especifica su dirección de correo electrónico como la dirección que aparece en "Desde" (From).
    
En el ejemplo siguiente se crea un NUEVO PIN y, a continuación, se envía un correo electrónico de bienvenida de Marco a Bob. Usa el texto del mensaje de la plantilla predeterminada y crea el mensaje de correo electrónico en formato HTML. El asunto predeterminado es "Welcome to Dial In Conferencing":
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

El siguiente ejemplo fuerza un NUEVO PIN con un valor de "383042650" para Bob, aunque Bob tuviera un PIN existente y, a continuación, envía un correo electrónico de bienvenida de Marco a Bob. Dado que se especifica el parámetro Credential, se pide a la persona que ejecuta el comando que escriba una contraseña. El correo electrónico se envía mediante la capa de sockets seguros (SSL):
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```

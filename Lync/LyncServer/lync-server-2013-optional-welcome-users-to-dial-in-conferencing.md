---
title: 'Lync Server 2013: (Opcional) Dar la bienvenida a los usuarios de la conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27abf5da520f1c5befd3a477783bc3f9ae67e1b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>(Opcional) Dar la bienvenida a los usuarios de la conferencia de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Después de configurar las conferencias de acceso telefónico local y las pruebas para comprobar que funciona correctamente, debe establecer números de identificación personales iniciales (PIN) para los usuarios y notificar a los usuarios la disponibilidad de la característica, incluidas instrucciones introductorias, como, por ejemplo, como PIN inicial y vínculo a la Página Web de la configuración de conferencias de acceso telefónico local. Este paso es opcional. Normalmente, se usa el cmdlet **set-CsClientPin** para restablecer los pin, pero puedes usar el procedimiento de este tema la primera vez si deseas enviar un mensaje de bienvenida con la información. SI no quiere enviar el correo electrónico, puede usar **Set-CsClientPin**.

Puede usar el script **Set-CsPinSendCAWelcomeMail** para establecer el PIN y enviar un mensaje de bienvenida a un único usuario. De forma predeterminada, el script no restablece un PIN si ya está establecido, pero puede usar el parámetro **Force** para forzar el restablecimiento de un PIN. El mensaje de correo electrónico se envía mediante el Protocolo simple de transferencia de correo (SMTP).

Puede crear un script que ejecute repetidamente el script **Set-CsPinSendCAWelcomeMail** para establecer PIN y enviar mensajes de correo electrónico a grupos de usuarios. Puede modificar la plantilla de correo electrónico (es decir, el archivo **CAWelcomeEmailTemplate. html** ) para agregar más vínculos a las páginas de la intranet o modificar el texto de correo electrónico.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Para establecer un PIN inicial y enviar correo electrónico de bienvenida

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
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
    
    **SmtpServer**   de forma predeterminada, la secuencia de comandos usa el valor de la variable de entorno reservada **$PSEmailServer** para este parámetro. Si la variable **$PSEmailServer** no está establecida, debe especificar este parámetro.
    
    **Credencial**   de forma predeterminada, la secuencia de comandos usa las credenciales del usuario actual. Si el usuario actual no tiene permisos para enviar un mensaje de correo electrónico en nombre de la dirección que aparece en "Desde" (From) especificada, debe especificar este parámetro. Como regla general, especifique este parámetro si no especifica su dirección de correo electrónico como la dirección que aparece en "Desde" (From).
    
    Por ejemplo:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    En este ejemplo se crea un PIN nuevo y, a continuación, se envía un correo electrónico de bienvenida de marco a Bob. Usa el texto del mensaje de la plantilla predeterminada y crea el mensaje de correo electrónico en formato HTML. El asunto predeterminado es "Bienvenido a marcar en conferencia".
    
    Otro ejemplo:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    En este ejemplo se fuerza a un nuevo PIN con un valor de "383042650" para Bob, aunque Bob tuviera un PIN existente y, después, envíe un correo electrónico de bienvenida de marco a Bob. Dado que se especifica el parámetro Credential, se pide a la persona que ejecuta el comando que escriba una contraseña. El correo electrónico se envía mediante la capa de sockets seguros (SSL).

</div>

</div>

<span> </span>

</div>

</div>

</div>


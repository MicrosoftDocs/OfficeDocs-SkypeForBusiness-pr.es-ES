---
title: Enviar correo electrónico de bienvenida a los usuarios de acceso telefónico local en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Resumen: obtenga información sobre cómo dar la bienvenida a los usuarios a las conferencias de acceso telefónico local en Skype Empresarial Server.'
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817500"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="d036f-103">Enviar correo electrónico de bienvenida a los usuarios de acceso telefónico local en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d036f-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="d036f-104">**Resumen:** Obtenga información sobre cómo dar la bienvenida a los usuarios a las conferencias de acceso telefónico local en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d036f-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="d036f-105">Después de configurar la conferencia de acceso telefónico local y probarla para comprobar que funciona correctamente, debe establecer números de identificación personal (PIN) iniciales para los usuarios y notificar a los usuarios sobre la disponibilidad de la característica.</span><span class="sxs-lookup"><span data-stu-id="d036f-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="d036f-106">Puede incluir instrucciones introductorias, como el PIN inicial y el vínculo a la página web Configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="d036f-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="d036f-107">Normalmente, se usa el cmdlet **Set-CsClientPin** para restablecer los PIN, pero puede usar el procedimiento de este tema si desea enviar un correo electrónico de bienvenida introductorio con la información del PIN.</span><span class="sxs-lookup"><span data-stu-id="d036f-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="d036f-108">Si no desea enviar el mensaje, puede usar **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="d036f-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="d036f-109">Puede usar el script **Set-CsPinSendCAWelcomeMail** para establecer el PIN y enviar un mensaje de bienvenida a un único usuario.</span><span class="sxs-lookup"><span data-stu-id="d036f-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="d036f-110">De forma predeterminada, el script no restablece un PIN si ya está establecido, pero puede usar el parámetro Force para imponer el restablecimiento del PIN.</span><span class="sxs-lookup"><span data-stu-id="d036f-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="d036f-111">El mensaje de correo electrónico se envía mediante el Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="d036f-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="d036f-112">Puede crear un script que ejecute repetidamente el script **Set-CsPinSendCAWelcomeMail** para establecer PIN y enviar mensajes de correo electrónico a grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d036f-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="d036f-113">Puede modificar la plantilla de mensaje de correo electrónico (es decir, el archivo CAWelcomeEmailTemplate.html) para agregar más vínculos a páginas de la intranet o modificar el texto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d036f-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="d036f-114">Establecer un PIN inicial y enviar correo electrónico de bienvenida</span><span class="sxs-lookup"><span data-stu-id="d036f-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="d036f-115">Inicie sesión como miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d036f-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="d036f-116">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d036f-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d036f-117">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d036f-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="d036f-118">**SmtpServer** De forma predeterminada, el script usa el valor de la variable de entorno **reservada $PSEmailServer** para este parámetro.</span><span class="sxs-lookup"><span data-stu-id="d036f-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="d036f-119">Si la variable **$PSEmailServer** no está establecida, debe especificar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="d036f-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="d036f-120">**Credencial** De forma predeterminada, el script usa las credenciales del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="d036f-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="d036f-121">Si el usuario actual no tiene permisos para enviar un mensaje de correo electrónico en nombre de la dirección que aparece en "Desde" (From) especificada, debe especificar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="d036f-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="d036f-122">Como regla general, especifique este parámetro si no especifica su dirección de correo electrónico como la dirección que aparece en "Desde" (From).</span><span class="sxs-lookup"><span data-stu-id="d036f-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="d036f-123">En el siguiente ejemplo se crea un NUEVO PIN y, a continuación, se envía un correo electrónico de bienvenida de Marco a Bob.</span><span class="sxs-lookup"><span data-stu-id="d036f-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="d036f-124">Usa el texto del mensaje de la plantilla predeterminada y crea el mensaje de correo electrónico en formato HTML.</span><span class="sxs-lookup"><span data-stu-id="d036f-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="d036f-125">El asunto predeterminado es "Bienvenido a las conferencias de acceso telefónico local":</span><span class="sxs-lookup"><span data-stu-id="d036f-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="d036f-126">El siguiente ejemplo fuerza un NUEVO PIN con un valor de "383042650" para Bob, aunque Bob tuviera un PIN existente y, a continuación, envía un correo electrónico de bienvenida de Marco a Bob.</span><span class="sxs-lookup"><span data-stu-id="d036f-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="d036f-127">Dado que se especifica el parámetro Credential, se pide a la persona que ejecuta el comando que escriba una contraseña.</span><span class="sxs-lookup"><span data-stu-id="d036f-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="d036f-128">El correo electrónico se envía mediante la Capa de sockets seguros (SSL):</span><span class="sxs-lookup"><span data-stu-id="d036f-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```

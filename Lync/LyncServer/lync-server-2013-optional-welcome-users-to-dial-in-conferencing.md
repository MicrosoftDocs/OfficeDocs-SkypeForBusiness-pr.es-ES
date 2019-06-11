---
title: 'Lync Server 2013: (Opcional) Dar la bienvenida a los usuarios de la conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3defde18a01ed09ac529ba9b289749f28c4cdd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="5f936-102">(Opcional) Dar la bienvenida a los usuarios de la conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f936-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f936-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="5f936-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="5f936-104">Después de configurar las conferencias de acceso telefónico local y las pruebas para comprobar que funciona correctamente, debe establecer números de identificación personales iniciales (PIN) para los usuarios y notificar a los usuarios la disponibilidad de la característica, incluidas instrucciones introductorias, como, por ejemplo, como PIN inicial y vínculo a la Página Web de la configuración de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="5f936-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="5f936-105">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="5f936-105">This step is optional.</span></span> <span data-ttu-id="5f936-106">Normalmente, se usa el cmdlet **set-CsClientPin** para restablecer los pin, pero puedes usar el procedimiento de este tema la primera vez si deseas enviar un mensaje de bienvenida con la información.</span><span class="sxs-lookup"><span data-stu-id="5f936-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="5f936-107">SI no quiere enviar el correo electrónico, puede usar **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="5f936-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="5f936-108">Puede usar el script **Set-CsPinSendCAWelcomeMail** para establecer el PIN y enviar un mensaje de bienvenida a un único usuario.</span><span class="sxs-lookup"><span data-stu-id="5f936-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="5f936-109">De forma predeterminada, el script no restablece un PIN si ya está establecido, pero puede usar el parámetro **Force** para forzar el restablecimiento de un PIN.</span><span class="sxs-lookup"><span data-stu-id="5f936-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="5f936-110">El mensaje de correo electrónico se envía mediante el Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="5f936-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="5f936-111">Puede crear un script que ejecute repetidamente el script **Set-CsPinSendCAWelcomeMail** para establecer PIN y enviar mensajes de correo electrónico a grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="5f936-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="5f936-112">Puede modificar la plantilla de correo electrónico (es decir, el archivo **CAWelcomeEmailTemplate. html** ) para agregar más vínculos a las páginas de la intranet o modificar el texto de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5f936-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="5f936-113">Para establecer un PIN inicial y enviar correo electrónico de bienvenida</span><span class="sxs-lookup"><span data-stu-id="5f936-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="5f936-114">Inicie sesión como miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5f936-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="5f936-115">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5f936-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5f936-116">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="5f936-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="5f936-117">**SmtpServer**   de forma predeterminada, la secuencia de comandos usa el valor de la variable de entorno reservada **$PSEmailServer** para este parámetro.</span><span class="sxs-lookup"><span data-stu-id="5f936-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="5f936-118">Si la variable **$PSEmailServer** no está establecida, debe especificar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="5f936-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="5f936-119">**Credencial**   de forma predeterminada, la secuencia de comandos usa las credenciales del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="5f936-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="5f936-120">Si el usuario actual no tiene permisos para enviar un mensaje de correo electrónico en nombre de la dirección que aparece en "Desde" (From) especificada, debe especificar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="5f936-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="5f936-121">Como regla general, especifique este parámetro si no especifica su dirección de correo electrónico como la dirección que aparece en "Desde" (From).</span><span class="sxs-lookup"><span data-stu-id="5f936-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="5f936-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5f936-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="5f936-123">En este ejemplo se crea un PIN nuevo y, a continuación, se envía un correo electrónico de bienvenida de marco a Bob.</span><span class="sxs-lookup"><span data-stu-id="5f936-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="5f936-124">Usa el texto del mensaje de la plantilla predeterminada y crea el mensaje de correo electrónico en formato HTML.</span><span class="sxs-lookup"><span data-stu-id="5f936-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="5f936-125">El asunto predeterminado es "Bienvenido a marcar en conferencia".</span><span class="sxs-lookup"><span data-stu-id="5f936-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="5f936-126">Otro ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5f936-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="5f936-127">En este ejemplo se fuerza a un nuevo PIN con un valor de "383042650" para Bob, aunque Bob tuviera un PIN existente y, después, envíe un correo electrónico de bienvenida de marco a Bob.</span><span class="sxs-lookup"><span data-stu-id="5f936-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="5f936-128">Dado que se especifica el parámetro Credential, se pide a la persona que ejecuta el comando que escriba una contraseña.</span><span class="sxs-lookup"><span data-stu-id="5f936-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="5f936-129">El correo electrónico se envía mediante la capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="5f936-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


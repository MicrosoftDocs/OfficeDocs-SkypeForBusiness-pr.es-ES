---
title: 'Lync Server 2013: (opcional) da la bienvenida a los usuarios a la Conferencia de acceso telefónico local'
description: 'Lync Server 2013: (opcional) da la bienvenida a los usuarios a la Conferencia de acceso telefónico local.'
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
ms.openlocfilehash: 0d33c7184a8cf22699b4ebe8d8ea8b4ef1c133a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546906"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="4c888-103">Opcional Le damos la bienvenida a los usuarios a conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c888-103">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c888-104">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="4c888-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="4c888-105">Después de configurar la conferencia de acceso telefónico local y de comprobar que funciona correctamente, debe definir números de identificación personal (PIN) iniciales para usuarios e informar a los usuarios sobre la disponibilidad de la característica, incluidos las instrucciones introductorias como el PIN inicial y el vínculo a la página web de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4c888-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="4c888-106">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="4c888-106">This step is optional.</span></span> <span data-ttu-id="4c888-107">Normalmente, debe usar el cmdlet **Set-CsClientPin** para restablecer los PIN, pero puede seguir el procedimiento en este tema la primera vez si desea enviar un enviar un mensaje de correo electrónico de bienvenida con la información.</span><span class="sxs-lookup"><span data-stu-id="4c888-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="4c888-108">Si no desea enviar el mensaje, puede usar **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="4c888-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="4c888-109">Puede usar el script **Set-CsPinSendCAWelcomeMail** para establecer el PIN y enviar un mensaje de bienvenida a un único usuario.</span><span class="sxs-lookup"><span data-stu-id="4c888-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="4c888-110">De forma predeterminada, el script no restablece un PIN si ya está establecido, pero puede usar el parámetro **Force** para imponer el restablecimiento del PIN.</span><span class="sxs-lookup"><span data-stu-id="4c888-110">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="4c888-111">El mensaje de correo electrónico se envía mediante el Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="4c888-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="4c888-112">Puede crear un script que ejecute repetidamente el script **Set-CsPinSendCAWelcomeMail** para establecer PIN y enviar mensajes de correo electrónico a grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="4c888-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="4c888-113">Puede modificar la plantilla de mensaje de correo electrónico (es decir, el archivo **CAWelcomeEmailTemplate.html**) para agregar más vínculos a páginas de la intranet o modificar el texto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4c888-113">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="4c888-114">Para establecer un PIN inicial y enviar un mensaje de correo electrónico de bienvenida</span><span class="sxs-lookup"><span data-stu-id="4c888-114">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="4c888-115">Inicie sesión como miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4c888-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4c888-116">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4c888-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4c888-117">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="4c888-117">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="4c888-118">**SmtpServer**     De forma predeterminada, el script usa el valor de la variable de entorno reservada **$PSEmailServer** para este parámetro.</span><span class="sxs-lookup"><span data-stu-id="4c888-118">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="4c888-119">Si la variable **$PSEmailServer** no está establecida, debe especificar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="4c888-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="4c888-120">**Credenciales**     De forma predeterminada, el script usa las credenciales del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="4c888-120">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="4c888-121">Si el usuario actual no tiene permisos para enviar un mensaje de correo electrónico en nombre de la dirección que aparece en "Desde" (From) especificada, debe especificar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="4c888-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="4c888-122">Como regla general, especifique este parámetro si no especifica su dirección de correo electrónico como la dirección que aparece en "Desde" (From).</span><span class="sxs-lookup"><span data-stu-id="4c888-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="4c888-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c888-123">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="4c888-p106">En este ejemplo se crea un PIN nuevo y, a continuación, se envía un mensaje de correo electrónico de bienvenida de Marco a Bob. Usa el texto del mensaje de la plantilla predeterminada y crea el mensaje de correo electrónico en formato HTML. El asunto (Subject) predeterminado es "Bienvenida a la conferencia de acceso telefónico local".</span><span class="sxs-lookup"><span data-stu-id="4c888-p106">This example creates a new PIN and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="4c888-127">Otro ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c888-127">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="4c888-p107">En este ejemplo se impone un PIN nuevo con un valor de "383042650" para Bob, aunque Bob tenía un PIN existente y, a continuación, se envía un mensaje de bienvenida de Marco a Bob. Dado que se especifica el parámetro Credential, se pide a la persona que ejecuta el comando que escriba una contraseña. El mensaje de correo electrónico se envía mediante la Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="4c888-p107">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando cambia su configuración
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 9db213285a24ad0a67d305a84f275f21ce741013
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="acbb7-103">Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="acbb7-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="acbb7-104">Los usuarios se notifican automáticamente por correo electrónico cuando están habilitados para conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="acbb7-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="acbb7-105">Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a Skype para usuarios empresariales y Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="acbb7-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="acbb7-106">En tales casos, puede deshabilitar el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="acbb7-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="acbb7-107">Si deshabilita el envío de correos electrónicos, mensajes de correo electrónico de conferencia de Audio no se enviará a los usuarios, incluidos los mensajes de correo electrónico para cuando los usuarios están habilitados o deshabilitados para conferencias de audio, cuando se restablezca su NIP y el identificador de la conferencia y la conferencia predeterminado cambios del número de teléfono .</span><span class="sxs-lookup"><span data-stu-id="acbb7-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="acbb7-108">Aquí es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:</span><span class="sxs-lookup"><span data-stu-id="acbb7-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Correo de conferencia de audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="acbb7-110">¿Cuándo se envían correos electrónicos a los usuarios?</span><span class="sxs-lookup"><span data-stu-id="acbb7-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="acbb7-111">Hay varios correos electrónicos que se envían a los usuarios de la organización después de que se hayan habilitado para conferencias de audio:</span><span class="sxs-lookup"><span data-stu-id="acbb7-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="acbb7-112">Cuando se asigna una licencia de **Conferencia de Audio** a ellos.</span><span class="sxs-lookup"><span data-stu-id="acbb7-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="acbb7-113">Cuando restablece manualmente conferencias de audio PIN del usuario.</span><span class="sxs-lookup"><span data-stu-id="acbb7-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="acbb7-114">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="acbb7-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="acbb7-115">Cuando se quita la licencia de **Conferencia de Audio** de ellos.</span><span class="sxs-lookup"><span data-stu-id="acbb7-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="acbb7-116">Cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a otro proveedor, o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="acbb7-117">Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="acbb7-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="acbb7-118">Habilitar o deshabilitar el correo electrónico se envíe a los usuarios</span><span class="sxs-lookup"><span data-stu-id="acbb7-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="acbb7-119">Puede utilizar Microsoft Teams, el Skype para el centro de administración de negocios o de Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="acbb7-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="acbb7-120">**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**</span><span class="sxs-lookup"><span data-stu-id="acbb7-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="acbb7-121">En la exploración de la izquierda, vaya a **reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="acbb7-122">En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="acbb7-123">En el panel **configuración de puente** , habilitar o deshabilitar **automáticamente enviar correos electrónicos a los usuarios si cambia su configuración de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="acbb7-124">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-124">Click **Apply**.</span></span>
  
<span data-ttu-id="acbb7-125">Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="acbb7-125">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="acbb7-126">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, haga clic en **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="acbb7-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="acbb7-128">Click **Save**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-128">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="acbb7-129">También puede enviar correo electrónico a un usuario con la configuración de conferencia de audio yendo a las **conferencias de Audio** > **usuarios**, seleccionar el usuario y hacer clic en **Enviar información de conferencia a través de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="acbb7-130">Si lo hace, se enviará un correo electrónico que sólo incluye los Id. de conferencia y número de teléfono de conferencia, pero no el PIN.</span><span class="sxs-lookup"><span data-stu-id="acbb7-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="acbb7-131">Para obtener más información, vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="acbb7-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
<span data-ttu-id="acbb7-132">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="acbb7-132">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="acbb7-133">Ejecute el siguiente procedimiento para deshabilitar el envío de correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="acbb7-133">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="acbb7-134">Para obtener ayuda con este cmdlet, vea [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="acbb7-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="acbb7-135">¿Qué más tengo que saber?</span><span class="sxs-lookup"><span data-stu-id="acbb7-135">What else should you know?</span></span>

- <span data-ttu-id="acbb7-136">Cuando están deshabilitados los correos electrónicos, puede desencadenar manualmente sigue enviando un correo electrónico con el número de ID y teléfono de conferencia usando el Skype para el centro de administración de negocios.</span><span class="sxs-lookup"><span data-stu-id="acbb7-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="acbb7-137">Sin embargo, si lo hace, no se incluirán el NIP.</span><span class="sxs-lookup"><span data-stu-id="acbb7-137">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="acbb7-138">Si desea restablecer el PIN de conferencias de audio y enviar mensajes de correo electrónico está deshabilitado, debe enviar al usuario en otra forma.</span><span class="sxs-lookup"><span data-stu-id="acbb7-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="acbb7-139">El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="acbb7-139">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="acbb7-140">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="acbb7-140">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="acbb7-141">Puede usar estos cmdlets para ahorrar tiempo o automatizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="acbb7-141">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="acbb7-142">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="acbb7-142">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="acbb7-143">Quitar CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="acbb7-143">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="acbb7-144">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="acbb7-144">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="acbb7-145">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="acbb7-145">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="acbb7-p104">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="acbb7-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="acbb7-149">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="acbb7-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="acbb7-150">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="acbb7-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="acbb7-p105">Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="acbb7-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="acbb7-153">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="acbb7-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="acbb7-154">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="acbb7-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="acbb7-155">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="acbb7-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="acbb7-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="acbb7-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="acbb7-158">See also</span><span class="sxs-lookup"><span data-stu-id="acbb7-158">Related topics</span></span>

[<span data-ttu-id="acbb7-159">Correos electrónicos enviados a los usuarios cuando cambia su configuración de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="acbb7-159">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="acbb7-160">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="acbb7-160">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)



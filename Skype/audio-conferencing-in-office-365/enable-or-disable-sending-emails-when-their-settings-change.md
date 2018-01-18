---
title: "Habilitar o deshabilitar el envío de correos electrónicos cuando cambia su configuración"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4efabf42f7253d89b37282103a3046cf7b2b0d26
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="59975-103">Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="59975-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="59975-104">Los usuarios se notifican automáticamente por correo electrónico cuando están habilitados para conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="59975-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="59975-105">Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a Skype para usuarios empresariales y Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59975-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="59975-106">En tales casos, puede deshabilitar el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="59975-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="59975-107">Si deshabilita el envío de correos electrónicos, mensajes de correo electrónico de conferencia de Audio no se enviará a los usuarios, incluidos los mensajes de correo electrónico para cuando los usuarios están habilitados o deshabilitados para conferencias de audio, cuando se restablezca su NIP y el identificador de la conferencia y la conferencia predeterminado cambios del número de teléfono .</span><span class="sxs-lookup"><span data-stu-id="59975-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="59975-108">Aquí es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:</span><span class="sxs-lookup"><span data-stu-id="59975-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Correo de conferencia de audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="59975-110">¿Cuándo se envían correos electrónicos a los usuarios?</span><span class="sxs-lookup"><span data-stu-id="59975-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="59975-111">Hay varios correos electrónicos que se envían a los usuarios de la organización después de que se hayan habilitado para conferencias de audio:</span><span class="sxs-lookup"><span data-stu-id="59975-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="59975-112">Cuando se asigna una licencia de **Conferencia de Audio** a ellos.</span><span class="sxs-lookup"><span data-stu-id="59975-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="59975-113">Cuando restablece manualmente conferencias de audio PIN del usuario.</span><span class="sxs-lookup"><span data-stu-id="59975-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="59975-114">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="59975-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="59975-115">Cuando se quita la licencia de **Conferencia de Audio** de ellos.</span><span class="sxs-lookup"><span data-stu-id="59975-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="59975-116">Cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a otro proveedor, o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="59975-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="59975-117">Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59975-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="59975-118">Habilitar o deshabilitar el correo electrónico se envíe a los usuarios</span><span class="sxs-lookup"><span data-stu-id="59975-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="59975-119">Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="59975-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="59975-120">Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="59975-120">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="59975-121">Usar el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="59975-121">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="59975-122">Ir al **Centro de administración de Office 365** > **Skype para el negocio**y la exploración de la izquierda, haga clic en **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="59975-122">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="59975-123">En la página **configuración de puente de Microsoft** , active o desactive la **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencia de audio**.</span><span class="sxs-lookup"><span data-stu-id="59975-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="59975-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="59975-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="59975-125">También puede enviar correo electrónico a un usuario con la configuración de conferencia de audio yendo a las **conferencias de Audio** > **usuarios**, seleccionar el usuario y hacer clic en **Enviar información de conferencia a través de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="59975-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="59975-126">Si lo hace, se enviará un correo electrónico que sólo incluye los Id. de conferencia y número de teléfono de conferencia, pero no el PIN.</span><span class="sxs-lookup"><span data-stu-id="59975-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="59975-127">Para obtener más información, vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="59975-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
 <span data-ttu-id="59975-128">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="59975-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="59975-129">Ejecute el siguiente procedimiento para deshabilitar el envío de correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="59975-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="59975-130">Para obtener ayuda con este cmdlet, vea [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="59975-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="59975-131">¿Qué más tengo que saber?</span><span class="sxs-lookup"><span data-stu-id="59975-131">What else should you know?</span></span>

- <span data-ttu-id="59975-132">Cuando están deshabilitados los correos electrónicos, puede desencadenar manualmente sigue enviando un correo electrónico con el número de ID y teléfono de conferencia usando el Skype para el centro de administración de negocios.</span><span class="sxs-lookup"><span data-stu-id="59975-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="59975-133">Sin embargo, si lo hace, no se incluirán el NIP.</span><span class="sxs-lookup"><span data-stu-id="59975-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="59975-134">Si desea restablecer el PIN de conferencias de audio y enviar mensajes de correo electrónico está deshabilitado, debe enviar al usuario en otra forma.</span><span class="sxs-lookup"><span data-stu-id="59975-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="59975-135">De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y Mostrar nombre mediante Windows PowerShell y también usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="59975-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="59975-136">Si desea cambiar la información de la dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico entrante de su entorno permiten correos electrónicos procedentes de personalizado especificado en la dirección.</span><span class="sxs-lookup"><span data-stu-id="59975-136">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="59975-137">Escriba la dirección de correo electrónico en el parámetro  _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="59975-137">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="59975-138">Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="59975-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="59975-139">Establezca el parámetro _SendEmailOverride_ en _True_.</span><span class="sxs-lookup"><span data-stu-id="59975-139">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="59975-140">El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59975-140">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="59975-141">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="59975-141">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="59975-142">Puede usar estos cmdlets para ahorrar tiempo o automatizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="59975-142">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="59975-143">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="59975-143">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="59975-144">Quitar CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="59975-144">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="59975-145">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="59975-145">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="59975-146">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="59975-146">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="59975-147">Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no realizar.</span><span class="sxs-lookup"><span data-stu-id="59975-147">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="59975-148">Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="59975-148">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="59975-149">Para empezar a utilizar Windows PowerShell, consulte estos temas:</span><span class="sxs-lookup"><span data-stu-id="59975-149">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="59975-150">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="59975-150">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="59975-151">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="59975-151">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="59975-152">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="59975-152">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="59975-153">Obtenga información acerca de estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="59975-153">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="59975-154">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="59975-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="59975-155">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="59975-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="59975-156">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="59975-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="59975-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="59975-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="59975-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="59975-159">Related topics</span></span>

[<span data-ttu-id="59975-160">Correos electrónicos enviados a los usuarios cuando cambia su configuración de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="59975-160">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="59975-161">Enviar un correo electrónico a un usuario con su información de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="59975-161">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)

[<span data-ttu-id="59975-162">Configurar Audioconferencia para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59975-162">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)


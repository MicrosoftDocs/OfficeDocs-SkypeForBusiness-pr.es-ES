---
title: Habilitar o deshabilitar el envío de los correos electrónicos cuando cambie la configuración de conferencias de Audio en Skype para profesionales en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: a9100de01fc835916af54d08b84dbd03a06ec1d6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229821"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="4d470-103">Habilitar o deshabilitar el envío de los correos electrónicos cuando cambie la configuración de conferencias de Audio en Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="4d470-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="4d470-104">Si desea habilitar o deshabilitar el envío de correos electrónicos en Microsoft Teams, vea [Habilitar o deshabilitar el envío por correo electrónico cuando el cambio de configuración de la conferencia de Audio en los equipos de Microsoft](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4d470-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="4d470-105">Cuando están habilitados para conferencias de Audio, se notificación automáticamente a los usuarios por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4d470-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="4d470-106">Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a Skype para los usuarios empresariales.</span><span class="sxs-lookup"><span data-stu-id="4d470-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="4d470-107">En estos casos, puede deshabilitar el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4d470-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="4d470-108">Si se deshabilitación el envío de los correos electrónicos, mensajes de correo electrónico de conferencia de Audio no se enviará a los usuarios, incluidos los correos electrónicos para cuando los usuarios se habilitan o deshabilitan para conferencias de audio, cuando se restablezca su NIP y cuando el identificador de conferencia y la conferencia predeterminado cambios del número de teléfono .</span><span class="sxs-lookup"><span data-stu-id="4d470-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="4d470-109">Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:</span><span class="sxs-lookup"><span data-stu-id="4d470-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Correo electrónico de conferencia audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="4d470-111">¿Cuándo se envían correos electrónicos a los usuarios?</span><span class="sxs-lookup"><span data-stu-id="4d470-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="4d470-112">Hay varios correos electrónicos que se envían a los usuarios de su organización después de que están habilitados para conferencias de audio:</span><span class="sxs-lookup"><span data-stu-id="4d470-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="4d470-113">Cuando se asigna una licencia de **Conferencias de Audio** a ellos.</span><span class="sxs-lookup"><span data-stu-id="4d470-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="4d470-114">Al restablecer manualmente PIN de conferencia de audio del usuario.</span><span class="sxs-lookup"><span data-stu-id="4d470-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="4d470-115">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="4d470-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="4d470-116">Cuando la licencia de **Conferencias de Audio** se quita de ellos.</span><span class="sxs-lookup"><span data-stu-id="4d470-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="4d470-117">Cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a otro proveedor o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="4d470-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="4d470-118">Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d470-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="4d470-119">Habilitar o deshabilitar el correo electrónico no se envía a los usuarios</span><span class="sxs-lookup"><span data-stu-id="4d470-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="4d470-120">Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="4d470-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="4d470-121">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="4d470-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="4d470-122">En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="4d470-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="4d470-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="4d470-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="4d470-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4d470-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="4d470-125">También puede enviar correo electrónico a un usuario con la configuración de conferencias de audio, vaya a la **conferencia de Audio** > **a los usuarios**, seleccione el usuario y haga clic en **Enviar información de conferencia a través de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="4d470-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="4d470-126">Si lo hace, se enviará un correo electrónico que incluye solo identificador de conferencia y el número de teléfono de conferencia, pero no el PIN.</span><span class="sxs-lookup"><span data-stu-id="4d470-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="4d470-127">Para obtener más información, vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="4d470-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="4d470-128">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="4d470-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="4d470-129">Ejecute el siguiente procedimiento para deshabilitar el envío de los correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="4d470-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="4d470-130">Para obtener ayuda con este cmdlet, vea [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="4d470-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="4d470-131">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="4d470-131">What else should you know?</span></span>

- <span data-ttu-id="4d470-132">Cuando están deshabilitados los correos electrónicos, puede desencadenar manualmente enviar un correo electrónico con el número de identificador y el teléfono de conferencia utilizando el Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="4d470-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="4d470-133">Sin embargo, si lo hace, no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="4d470-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="4d470-134">Si desea restablecer el PIN de conferencia de audio y enviar mensajes de correo electrónico está deshabilitado, debe enviar al usuario en otra forma.</span><span class="sxs-lookup"><span data-stu-id="4d470-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="4d470-135">El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d470-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4d470-136">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4d470-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4d470-137">Puede usar estos cmdlets para ahorrar tiempo o automatizar esto.</span><span class="sxs-lookup"><span data-stu-id="4d470-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="4d470-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="4d470-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="4d470-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="4d470-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="4d470-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="4d470-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="4d470-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="4d470-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="4d470-p104">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="4d470-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4d470-145">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="4d470-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4d470-146">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d470-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4d470-p105">Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4d470-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="4d470-149">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4d470-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4d470-150">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4d470-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4d470-151">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4d470-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4d470-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="4d470-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4d470-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4d470-154">Related topics</span></span>

[<span data-ttu-id="4d470-155">Correos electrónicos enviados a los usuarios cuando cambie su configuración de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="4d470-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="4d470-156">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="4d470-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)



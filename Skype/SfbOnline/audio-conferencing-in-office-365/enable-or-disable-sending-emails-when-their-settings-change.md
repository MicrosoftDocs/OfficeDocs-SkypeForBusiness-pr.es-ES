---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando la configuración de conferencias de audio cambie en Skype Empresarial Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 6b9e67d8c87b023409b7934a944f298487f91289
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114256"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="3337d-103">Habilitar o deshabilitar el envío de correos electrónicos cuando la configuración de conferencias de audio cambie en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3337d-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="3337d-104">Si desea habilitar o deshabilitar el envío de correos electrónicos en Microsoft Teams, vea Habilitar o deshabilitar el envío de correos electrónicos cuando la configuración de conferencias de audio cambie [en Microsoft Teams.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="3337d-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="3337d-105">Los usuarios se notifican automáticamente por correo electrónico cuando están habilitados para las audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="3337d-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="3337d-106">Sin embargo, puede haber ocasiones en las que quiera reducir el número de correos electrónicos que se envían a los usuarios de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3337d-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="3337d-107">En estos casos, puede deshabilitar el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3337d-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="3337d-108">Si deshabilita el envío de correos electrónicos, los correos electrónicos de audioconferencia no se enviarán a los usuarios, incluidos los correos electrónicos para cuando los usuarios estén habilitados o deshabilitados para las audioconferencias, cuando se restablezca su PIN y cuando cambie el id. de conferencia y el número de teléfono de conferencia predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3337d-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="3337d-109">Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para las audioconferencias:</span><span class="sxs-lookup"><span data-stu-id="3337d-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Correo electrónico de audioconferencia](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="3337d-111">¿Cuándo se envían correos electrónicos a los usuarios?</span><span class="sxs-lookup"><span data-stu-id="3337d-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="3337d-112">Hay varios correos electrónicos que se envían a los usuarios de su organización después de que estén habilitados para las audioconferencias:</span><span class="sxs-lookup"><span data-stu-id="3337d-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="3337d-113">Cuando se les asigna una licencia **de** audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="3337d-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="3337d-114">Cuando restablezca manualmente el PIN de audioconferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="3337d-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="3337d-115">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="3337d-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="3337d-116">Cuando se **quita la licencia de conferencias** de audio.</span><span class="sxs-lookup"><span data-stu-id="3337d-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="3337d-117">Cuando el proveedor de audioconferencias de un usuario se cambia de Microsoft a otro proveedor o **Ninguno.**</span><span class="sxs-lookup"><span data-stu-id="3337d-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="3337d-118">Cuando el proveedor de audioconferencias de un usuario se cambia a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3337d-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="3337d-119">Habilitar o deshabilitar el correo electrónico para que no se envíe a los usuarios</span><span class="sxs-lookup"><span data-stu-id="3337d-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="3337d-120">Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="3337d-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="3337d-121">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="3337d-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="3337d-122">En el **Centro de administración de Skype Empresarial,** en el panel de navegación izquierdo, haga clic en **Audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="3337d-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="3337d-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="3337d-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="3337d-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3337d-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3337d-125">También puede enviar correo electrónico a un usuario con la configuración de audioconferencia yendo a **Usuarios** de audioconferencia, seleccionando al usuario y haciendo clic en Enviar información de conferencia  >  por **correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="3337d-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="3337d-126">Si lo hace, se enviará un correo electrónico que solo incluye el id. de conferencia y el número de teléfono de conferencia, pero no el PIN.</span><span class="sxs-lookup"><span data-stu-id="3337d-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="3337d-127">Vea Enviar un correo electrónico a un usuario con su información de [audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3337d-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="3337d-128">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="3337d-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="3337d-129">Ejecute lo siguiente para deshabilitar el envío de correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="3337d-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="3337d-130">Para obtener ayuda con este cmdlet, vea [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span><span class="sxs-lookup"><span data-stu-id="3337d-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="3337d-131">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="3337d-131">What else should you know?</span></span>

- <span data-ttu-id="3337d-132">Cuando los correos electrónicos automáticos están deshabilitados, aún puede activar manualmente el envío de un correo electrónico con el id. de conferencia y el número de teléfono con el Centro de administración de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3337d-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="3337d-133">Sin embargo, si lo hace, el PIN no se incluirá.</span><span class="sxs-lookup"><span data-stu-id="3337d-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="3337d-134">Si desea restablecer el PIN de audioconferencia y enviar correos electrónicos está deshabilitado, tendrá que enviarlo al usuario de otra forma.</span><span class="sxs-lookup"><span data-stu-id="3337d-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="3337d-135">El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3337d-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3337d-136">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3337d-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3337d-137">Puede usar estos cmdlets para ahorrar tiempo o automatizar esto.</span><span class="sxs-lookup"><span data-stu-id="3337d-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="3337d-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="3337d-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="3337d-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="3337d-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="3337d-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="3337d-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="3337d-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="3337d-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="3337d-142">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="3337d-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3337d-143">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="3337d-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="3337d-144">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="3337d-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3337d-145">Por qué necesita usar Microsoft 365 u Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3337d-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="3337d-146">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="3337d-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="3337d-147">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del Centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="3337d-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3337d-148">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3337d-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3337d-149">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3337d-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="3337d-150">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3337d-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="3337d-151">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3337d-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="3337d-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="3337d-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3337d-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3337d-154">Related topics</span></span>

[<span data-ttu-id="3337d-155">Correos electrónicos enviados a los usuarios cuando cambian sus opciones de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="3337d-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="3337d-156">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="3337d-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
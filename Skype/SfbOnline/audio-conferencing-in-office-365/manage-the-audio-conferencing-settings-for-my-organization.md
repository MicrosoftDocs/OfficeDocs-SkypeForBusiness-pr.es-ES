---
title: Administrar la configuración de Audioconferencia de mi organización en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'Consulte Skype Empresarial en línea para asignar una licencia de conferencia de acceso telefónico local e id. de conferencia a un usuario y a muchas otras opciones de configuración de conferencias de acceso telefónico local. '
ms.openlocfilehash: 3a0f6d37612c345c8561fbd2a64b4c90fdb27957
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237252"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="a0930-103">Administrar la configuración de Audioconferencia de mi organización en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a0930-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="a0930-104">Si desea administrar esta configuración en Teams, vea [Administrar la configuración de Audioconferencia de mi organización en Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a0930-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="a0930-105">Es posible que le resulte más fácil ver todas las opciones de configuración de audioconferencia Skype Empresarial en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="a0930-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="a0930-106">Asignar una licencia de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a0930-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="a0930-107">You can't assign licenses using the **Skype for Business admin center**.</span><span class="sxs-lookup"><span data-stu-id="a0930-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="a0930-108">Debe usar el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="a0930-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="a0930-109">Consulte [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a0930-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="a0930-110">**To assign a license for a user**</span><span class="sxs-lookup"><span data-stu-id="a0930-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="a0930-111">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-112">En la navegación izquierda del centro de administración, vaya a Usuarios usuarios activos y, a continuación, seleccione el usuario o los usuarios de  >  la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="a0930-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0930-113">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista.</span><span class="sxs-lookup"><span data-stu-id="a0930-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="a0930-114">Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="a0930-115">También puede asignar licencias a varios usuarios con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0930-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="a0930-116">Para obtener instrucciones y scripts de PowerShell de ejemplo, [vea Asignar Skype Empresarial licencias.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="a0930-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="a0930-117">En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="a0930-118">En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="a0930-119">Para obtener más información sobre las [licencias, vea Skype Empresarial de complementos.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="a0930-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a0930-120">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a0930-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="a0930-121">Si esto sucede, cierre sesión en el centro de administración o presione CTRL+F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="a0930-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="a0930-122">Enable or disable emails sent to audio conferencing users</span><span class="sxs-lookup"><span data-stu-id="a0930-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="a0930-123">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="a0930-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a0930-124">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-125">Vaya al centro de administración > **Skype Empresarial y, en** el panel de navegación izquierdo, haga clic en **Audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="a0930-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="a0930-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="a0930-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="a0930-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-127">Click **Save**.</span></span>

    <span data-ttu-id="a0930-p105">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="a0930-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="a0930-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="a0930-131">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="a0930-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="a0930-132">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0930-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="a0930-133">También puede usar Windows PowerShell y ejecutar:[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a0930-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="a0930-134">Change the sender's contact information in email messages sent to users</span><span class="sxs-lookup"><span data-stu-id="a0930-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="a0930-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span><span class="sxs-lookup"><span data-stu-id="a0930-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="a0930-136">De forma predeterminada, el remitente de los correos electrónicos es Microsoft 365 o Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a0930-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="a0930-137">To make changes to the email address that is sending the email to the users, you must:</span><span class="sxs-lookup"><span data-stu-id="a0930-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="a0930-138">Escriba la dirección de correo electrónico en el _parámetro SendEmailFromAddress._</span><span class="sxs-lookup"><span data-stu-id="a0930-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="a0930-139">Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="a0930-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="a0930-140">Establezca el parámetro _SendEmailOverride_ en _True_.</span><span class="sxs-lookup"><span data-stu-id="a0930-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="a0930-141">Puede realizar cambios en el correo electrónico enviado a los usuarios, como por ejemplo la dirección de correo electrónico desde la que se envía el correo electrónico o el nombre para mostrar para el correo electrónico haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0930-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="a0930-142">Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:</span><span class="sxs-lookup"><span data-stu-id="a0930-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="a0930-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span><span class="sxs-lookup"><span data-stu-id="a0930-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="a0930-144">Vea Correos electrónicos que se envían automáticamente a los usuarios cuando cambian sus [opciones de audioconferencia.](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="a0930-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="a0930-145">Reset the meeting conference ID</span><span class="sxs-lookup"><span data-stu-id="a0930-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="a0930-146">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-147">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="a0930-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span><span class="sxs-lookup"><span data-stu-id="a0930-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="a0930-p107">En la ventana **¿Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un Id. de conferencia y se enviará un correo electrónico al usuario con el nuevo Id. de conferencia si está habilitado el envío de correo electrónico a los usuarios. De manera predeterminada está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a0930-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="a0930-152">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="a0930-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a0930-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="a0930-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="a0930-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="a0930-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="a0930-155">Para ver cómo descargar, instalar y ejecutar la Herramienta de actualización de reuniones de Skype Empresarial, vea: Herramienta de actualización de reuniones para [Skype Empresarial](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)y Lync , Skype Empresarial Online, Herramienta de migración de reuniones [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)y Skype Empresarial Online, Herramienta de migración de reuniones [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="a0930-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="a0930-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a0930-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="a0930-157">Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="a0930-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="a0930-158">Se asignará un id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="a0930-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="a0930-159">Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o los usuarios no puedan recordar o haber perdido su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a0930-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="a0930-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="a0930-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="a0930-161">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-162">Vaya al centro de administración > **Skype Empresarial y, en** el panel de navegación izquierdo, haga clic en **Audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="a0930-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="a0930-163">Click **Users**, and then select the user that you want to reset the PIN for.</span><span class="sxs-lookup"><span data-stu-id="a0930-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="a0930-164">In the Action pane, under **PIN**, click **Reset**.</span><span class="sxs-lookup"><span data-stu-id="a0930-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="a0930-p110">Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="a0930-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="a0930-169">Vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="a0930-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="a0930-170">Send an email with Audio Conferencing information to a user</span><span class="sxs-lookup"><span data-stu-id="a0930-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="a0930-171">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-172">Vaya al centro de administración > **Skype Empresarial y, en** el panel de navegación izquierdo, haga clic en **Audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="a0930-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="a0930-173">Click **Users**, and then select the user that you want to reset the PIN for.</span><span class="sxs-lookup"><span data-stu-id="a0930-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="a0930-174">Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="a0930-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0930-175">When you do this, the audio conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="a0930-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="a0930-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="a0930-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="a0930-177">Establecer los números de teléfono incluidos en las invitaciones</span><span class="sxs-lookup"><span data-stu-id="a0930-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="a0930-178">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-179">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="a0930-p111">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="a0930-182">En el panel Acción, puede establecer el **Número de teléfono de pago** y, si se permite, el **Número de teléfono gratuito**.</span><span class="sxs-lookup"><span data-stu-id="a0930-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="a0930-183">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-183">Click **Save**.</span></span>

<span data-ttu-id="a0930-184">Vea [Establecer los números de teléfono incluidos en las invitaciones.](set-the-phone-numbers-included-on-invites.md)</span><span class="sxs-lookup"><span data-stu-id="a0930-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="a0930-185">Elegir la configuración del puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="a0930-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="a0930-186">**Set the meeting experience when callers join a meeting**</span><span class="sxs-lookup"><span data-stu-id="a0930-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="a0930-187">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-188">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="a0930-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="a0930-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="a0930-190">Under **Meeting join experience**, select the following actions:</span><span class="sxs-lookup"><span data-stu-id="a0930-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="a0930-p112">En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0930-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="a0930-193">Esto se puede establecer de forma individual cuando un usuario se une a una  reunión con una aplicación de Skype Empresarial y  modifica la configuración Anunciar cuando los usuarios entran o salen del menú Opciones de reunión de Skype de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a0930-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="a0930-p113">Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype for Business y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a0930-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="a0930-196">**Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="a0930-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="a0930-197">Después de realizar los cambios, haga clic en [Guardar](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="a0930-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="a0930-198">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0930-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="a0930-199">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-200">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="a0930-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="a0930-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="a0930-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="a0930-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="a0930-p114">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="a0930-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="a0930-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="a0930-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="a0930-206">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0930-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="a0930-207">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-208">Vaya al centro de administración > **Skype Empresarial y, en** el panel de navegación izquierdo, haga clic en **Audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="a0930-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="a0930-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="a0930-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="a0930-210">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-210">Click **Save**.</span></span>

    <span data-ttu-id="a0930-211">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a0930-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="a0930-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="a0930-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="a0930-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="a0930-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="a0930-214">Ver y establecer los idiomas principal (predeterminado) y secundario (alternativo) en un puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="a0930-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="a0930-215">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-216">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="a0930-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span><span class="sxs-lookup"><span data-stu-id="a0930-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="a0930-218">En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0930-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="a0930-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span><span class="sxs-lookup"><span data-stu-id="a0930-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="a0930-221">También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="a0930-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="a0930-222">See audio conferencing dial-in numbers</span><span class="sxs-lookup"><span data-stu-id="a0930-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="a0930-223">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-224">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="a0930-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span><span class="sxs-lookup"><span data-stu-id="a0930-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

   - <span data-ttu-id="a0930-227">Vea los números de teléfono establecidos por Microsoft 365 o Office 365 que se van a usar para las audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="a0930-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="a0930-228">Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a0930-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="a0930-p117">También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a0930-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="a0930-231">Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará. > </span><span class="sxs-lookup"><span data-stu-id="a0930-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="a0930-232">Vea [Ver una lista de números de audioconferencia.](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="a0930-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="a0930-233">See a list of users that are enabled</span><span class="sxs-lookup"><span data-stu-id="a0930-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="a0930-234">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="a0930-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="a0930-235">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0930-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="a0930-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span><span class="sxs-lookup"><span data-stu-id="a0930-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="a0930-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="a0930-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a0930-238">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a0930-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="a0930-239">Hay varias opciones de configuración que puede administrar en el nivel de la organización con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0930-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="a0930-240">Esto facilita la aplicación de la configuración a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a0930-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="a0930-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="a0930-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="a0930-242">Estas son las opciones de configuración de nivel de organización:</span><span class="sxs-lookup"><span data-stu-id="a0930-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="a0930-243">**Configuración de notificaciones de entrada o salida** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="a0930-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="a0930-244">**Configuración de grabación de nombre** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="a0930-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="a0930-245">**Establecer la longitud de PIN** El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="a0930-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="a0930-246">**Establecer sólo marcado en reuniones desde un teléfono** El valor predeterminado es _$false_.</span><span class="sxs-lookup"><span data-stu-id="a0930-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="a0930-247">**Establecer si se enviará un correo electrónico a los usuarios** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="a0930-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="a0930-248">**Establecer si se enviará un correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.</span><span class="sxs-lookup"><span data-stu-id="a0930-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="a0930-249">**Establecer la dirección de correo electrónico de remitente que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="a0930-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="a0930-250">**Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="a0930-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a0930-251">¿Desea obtener más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0930-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="a0930-252">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="a0930-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a0930-253">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="a0930-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a0930-254">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="a0930-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="a0930-255">¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a0930-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="a0930-256">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="a0930-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="a0930-257">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="a0930-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="a0930-258">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0930-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="a0930-259">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a0930-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="a0930-260">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a0930-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="a0930-261">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a0930-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="a0930-p121">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="a0930-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0930-264">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a0930-264">Related topics</span></span>

[<span data-ttu-id="a0930-265">Administrar la configuración de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="a0930-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

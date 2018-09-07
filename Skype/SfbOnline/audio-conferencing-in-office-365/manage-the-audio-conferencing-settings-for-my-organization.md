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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte los pasos de Skype for Business Online para asignar un id. de conferencia y una licencia de conferencia de acceso telefónico a un usuario y para muchas otras opciones de conferencias telefónicas. '
ms.openlocfilehash: 9babf0d9df978708f231e0e3dced1329ce0af437
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851471"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="16a43-103">Administrar la configuración de Audioconferencia de mi organización en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="16a43-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="16a43-104">Si desea administrar esta configuración en Teams, vea [Administrar la configuración de Audioconferencia de mi organización en Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="16a43-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="16a43-105">Puede que le resulte más sencillo ver toda la configuración de las audioconferencias de Skype for Business en un mismo lugar.</span><span class="sxs-lookup"><span data-stu-id="16a43-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="16a43-106">Asignar una licencia de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="16a43-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="16a43-107">No puede asignar licencias mediante el **centro de administración de Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="16a43-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="16a43-108">Debe utilizar el centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="16a43-108">You must use the Office 365 admin center.</span></span> <span data-ttu-id="16a43-109">Consulte [Asignar licencias de Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="16a43-110">**Para asignar una licencia a un usuario**</span><span class="sxs-lookup"><span data-stu-id="16a43-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="16a43-111">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-112">En la navegación izquierda del **Centro de administración de Office 365**, vaya a **Usuarios** > **Usuarios activos** y a continuación seleccione el usuario o los usuarios en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="16a43-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="16a43-113">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista.</span><span class="sxs-lookup"><span data-stu-id="16a43-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="16a43-114">Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="16a43-115">También puede asignar licencias a varios usuarios con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16a43-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="16a43-116">Para obtener instrucciones y ejemplos de scripts de PowerShell, consulte [Asignar licencias de Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="16a43-117">En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="16a43-118">En la página **Asignar licencia**, active **Conferencias RTC de Skype for Business** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="16a43-119">Para obtener más información sobre licencias, consulte [Licencias de complementos de Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-119">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="16a43-p104">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="16a43-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="16a43-122">Habilitar o deshabilitar los correos electrónicos enviados a los usuarios de audiconferencia</span><span class="sxs-lookup"><span data-stu-id="16a43-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="16a43-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Con el centro de administración de Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="16a43-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="16a43-124">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-125">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="16a43-126">En la página **Configuración de puente de Microsoft**, seleccione o deseleccione **Enviar automáticamente correos electrónicos a los usuarios si la configuración de audioconferencia cambia**.</span><span class="sxs-lookup"><span data-stu-id="16a43-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="16a43-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-127">Click **Save**.</span></span>

    <span data-ttu-id="16a43-p105">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="16a43-130">Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="16a43-131">**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**</span><span class="sxs-lookup"><span data-stu-id="16a43-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="16a43-132">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16a43-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="16a43-133">También puede usar Windows PowerShell y ejecutar:[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="16a43-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="16a43-134">Cambiar la información de contacto del remitente en los mensajes de correo electrónico enviados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="16a43-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="16a43-p106">Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De forma predeterminada, el remitente de los mensajes de correo electrónico es Office 365, pero se puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285). Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:</span><span class="sxs-lookup"><span data-stu-id="16a43-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="16a43-138">Escriba la dirección de correo electrónico en el parámetro _SendEmailFromAddress_.
</span><span class="sxs-lookup"><span data-stu-id="16a43-138">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="16a43-139">Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="16a43-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="16a43-140">Establezca el parámetro _SendEmailOverride_ en _True_.</span><span class="sxs-lookup"><span data-stu-id="16a43-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="16a43-141">Puede realizar cambios en el correo electrónico enviado a los usuarios, como por ejemplo la dirección de correo electrónico desde la que se envía el correo electrónico o el nombre para mostrar para el correo electrónico haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16a43-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="16a43-142">Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:</span><span class="sxs-lookup"><span data-stu-id="16a43-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="16a43-143">Puede utilizar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para administrar otras configuraciones para su organización, incluido el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="16a43-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="16a43-144">Vea [Correos electrónicos que se envían automáticamente a los usuarios cuando su configuración de Audioconferencia cambia](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-144">See [Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="16a43-145">Restablecer el id. de conferencia de reunión</span><span class="sxs-lookup"><span data-stu-id="16a43-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="16a43-146">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-147">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="16a43-148">En el **Centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y, en el panel Acción en **Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="16a43-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="16a43-p107">En la ventana **¿Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un Id. de conferencia y se enviará un correo electrónico al usuario con el nuevo Id. de conferencia si está habilitado el envío de correo electrónico a los usuarios. De manera predeterminada está habilitado.</span><span class="sxs-lookup"><span data-stu-id="16a43-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="16a43-152">Tras la creación de un nuevo id. de conferencia, las personas que llaman ya no pueden utilizar el id. de conferencia anterior.</span><span class="sxs-lookup"><span data-stu-id="16a43-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="16a43-153">Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="16a43-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="16a43-154">Los usuarios pueden utilizar la herramienta de migración de reuniones de Skype for Business para actualizar sus reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="16a43-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="16a43-155">Para ver cómo descargar, instalar y ejecutar la herramienta de actualización de reuniones de Skype for Business, consulte: [Herramienta de actualización de reuniones de Skype for Business y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047) y [Skype for Business Online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="16a43-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

<span data-ttu-id="16a43-156">Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="16a43-157">Restablecer el PIN del organizador de una conferencia</span><span class="sxs-lookup"><span data-stu-id="16a43-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="16a43-158">Se asignará un id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="16a43-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="16a43-159">Aunque se creará y asignará automáticamente un id. de conferencia a un usuario, en ocasiones es posible que un usuario no desee utilizarlo y quiera establecerlo en un número determinado, o bien que los usuarios hayan olvidado o perdido su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="16a43-159">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="16a43-160">Puede utilizar el centro de administración de Skype for Business y Windows PowerShell para ver, cambiar y restablecer su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="16a43-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="16a43-161">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-162">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="16a43-163">Haga clic en **Usuarios** y a continuación seleccione el usuario para el que desea restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="16a43-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="16a43-164">En el panel Acción, en **PIN**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="16a43-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="16a43-p110">Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="16a43-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="16a43-169">Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-169">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="16a43-170">Enviar un correo electrónico al usuario con la información de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="16a43-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="16a43-171">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-172">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="16a43-173">Haga clic en **Usuarios** y a continuación seleccione el usuario para el que desea restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="16a43-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="16a43-174">Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="16a43-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="16a43-175">Cuando hace esto, el PIN de audioconferencia no se envía al usuario.</span><span class="sxs-lookup"><span data-stu-id="16a43-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="16a43-176">Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="16a43-177">Establecer los números de teléfono incluidos en las invitaciones</span><span class="sxs-lookup"><span data-stu-id="16a43-177">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="16a43-178">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-179">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="16a43-p111">Vaya a **Centro de administración de Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="16a43-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="16a43-182">En el panel Acción, puede establecer el **Número de teléfono de pago** y, si se permite, el **Número de teléfono gratuito**.</span><span class="sxs-lookup"><span data-stu-id="16a43-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="16a43-183">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-183">Click **Save**.</span></span>

<span data-ttu-id="16a43-184">Vea [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-184">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md)</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="16a43-185">Elegir la configuración de puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="16a43-185">Setting audio conferencing bridge settings</span></span>

<span data-ttu-id="16a43-186">**Establecer la experiencia de reunión cuando personas que llaman se unen a una reunión**</span><span class="sxs-lookup"><span data-stu-id="16a43-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="16a43-187">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-188">Vaya a **Centro de administración de Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="16a43-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="16a43-189">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsof**.</span><span class="sxs-lookup"><span data-stu-id="16a43-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="16a43-190">En **Experiencia de participación en reuniones**, seleccione las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="16a43-190">Under **Meeting join experience**, select the following actions:</span></span>

  - <span data-ttu-id="16a43-p112">En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="16a43-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="16a43-193">Esta opción se puede configurar de manera específica para cada reunión cuando un usuario se une a una reunión mediante la aplicación Skype for Business y modifica la opción **Anunciar cuando entra o sale gente** en el menú **Opciones** de Reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="16a43-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business client and they modify the **Announce when people enter or leave** setting in the Skype Meeting Options menu of the meeting.</span></span>

  - <span data-ttu-id="16a43-p113">Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype for Business y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.</span><span class="sxs-lookup"><span data-stu-id="16a43-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="16a43-196">**Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="16a43-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="16a43-197">Después de realizar los cambios, haga clic en [Guardar](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="16a43-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="16a43-198">**Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="16a43-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="16a43-199">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-200">Vaya a **Centro de administración de Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="16a43-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="16a43-201">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsof**.</span><span class="sxs-lookup"><span data-stu-id="16a43-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="16a43-202">En **Seguridad**, especifique el número de dígitos que desea para el PIN en la lista **Longitud de PIN** y a continuación haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="16a43-p114">El PIN debe tener entre 4 y 12 dígitos. El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="16a43-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="16a43-205">El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="16a43-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="16a43-206">**Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="16a43-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="16a43-207">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-208">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="16a43-209">En la página **Configuración de puente de Microsoft**, seleccione o deseleccione **Enviar automáticamente correos electrónicos a los usuarios si la configuración de audioconferencia cambia**.</span><span class="sxs-lookup"><span data-stu-id="16a43-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="16a43-210">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-210">Click **Save**.</span></span>

    <span data-ttu-id="16a43-211">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16a43-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="16a43-212">Si hace esto, se enviará un correo electrónico que incluye solo el Id. de conferencia y el número de teléfono de conferencia, pero no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="16a43-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="16a43-213">Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="16a43-214">Ver y establecer los idiomas principales (predeterminado) y secundarios (alternativo) en un puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="16a43-214">See and set the primary and secondary languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="16a43-215">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-216">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="16a43-217">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y a continuación haga clic en **Puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="16a43-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="16a43-218">En el **Centro de administración de Skype for Business**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="16a43-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="16a43-p115">También puede establecer los idiomas principal y secundarios admitidos al seleccionar Microsoft como proveedor de audioconferencia. El orden de selección en la lista equivale al orden en que se presentarán los idiomas a las personas que llamen.</span><span class="sxs-lookup"><span data-stu-id="16a43-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="16a43-221">También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="16a43-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="16a43-222">Ver los números de acceso telefónico de la audioconferencia</span><span class="sxs-lookup"><span data-stu-id="16a43-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="16a43-223">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-224">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="16a43-p116">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Puente de Microsoft**. Aquí puede:</span><span class="sxs-lookup"><span data-stu-id="16a43-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

  - <span data-ttu-id="16a43-227">Vea los números de teléfono que ha establecido Office 365 para utilizar para Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="16a43-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

  - <span data-ttu-id="16a43-228">Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="16a43-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  - <span data-ttu-id="16a43-p117">También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="16a43-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="16a43-231">Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="16a43-232">Vea [Consultar una lista de números de Audioconferencia](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-232">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md)</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="16a43-233">Ver una lista de usuarios habilitados</span><span class="sxs-lookup"><span data-stu-id="16a43-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="16a43-234">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="16a43-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="16a43-235">Inicie sesión en Office 365 con su cuenta profesional o educativa.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16a43-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="16a43-236">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y a continuación **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="16a43-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="16a43-237">Vea [Consultar una lista de usuarios habilitados para Audioconferencia](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="16a43-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="16a43-238">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="16a43-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="16a43-239">Hay varias opciones de configuración que puede administrar en el nivel de organización mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16a43-239">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users. Here are the organization-level settings:</span></span> <span data-ttu-id="16a43-240">Esto facilita la aplicación de la configuración a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="16a43-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="16a43-241">Para obtener más ayuda sobre cada cmdlet, consulte [Cmdlets de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=627324).
</span><span class="sxs-lookup"><span data-stu-id="16a43-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="16a43-242">A continuación presentamos la configuración de nivel de la organización:</span><span class="sxs-lookup"><span data-stu-id="16a43-242">Here are the performance settings:</span></span>

- <span data-ttu-id="16a43-243">**Configuración de notificaciones de entrada o salida** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="16a43-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="16a43-244">**Configuración de grabación de nombre** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="16a43-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="16a43-245">**Establecer la longitud de PIN** El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="16a43-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="16a43-246">**Establecer sólo marcado en reuniones desde un teléfono** El valor predeterminado es _$false_.</span><span class="sxs-lookup"><span data-stu-id="16a43-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="16a43-247">**Establecer si se enviará un correo electrónico a los usuarios** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="16a43-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="16a43-248">**Establecer si se enviará un correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.</span><span class="sxs-lookup"><span data-stu-id="16a43-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="16a43-249">**Establecer la dirección de correo electrónico de remitente que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="16a43-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="16a43-250">**Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="16a43-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="16a43-251">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="16a43-251">Want to know more about Windows Powershell?</span></span>
- <span data-ttu-id="16a43-p119">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="16a43-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="16a43-255">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="16a43-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="16a43-256">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16a43-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="16a43-p120">Windows PowerShell tiene muchas ventajas en velocidad, simplificidad y productividad respecto a utilizar únicamente el centro de administración de Office 365 como, por ejemplo, al realizar cambios de configuración para muchos usuarios en una única ubicación. Obtenga más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="16a43-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="16a43-259">Introducción a Windows PowerShell y Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="16a43-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="16a43-260">Usar Windows PowerShell para administrar Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="16a43-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="16a43-261">Usar Windows PowerShell para realizar tareas de administración comunes de Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="16a43-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="16a43-p121">El módulo Windows PowerShell para Skype for Business Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype for Business Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="16a43-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="16a43-264">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="16a43-264">Related topics</span></span>

[<span data-ttu-id="16a43-265">Administrar la configuración de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="16a43-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)



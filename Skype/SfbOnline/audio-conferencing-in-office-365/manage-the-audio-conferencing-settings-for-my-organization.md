---
title: Administrar la configuración de la conferencia de acceso telefónico local en mi organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b2759e4ee1f8e8cac2f753eb5afecbf13642abb0
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="bb384-103">Administrar la configuración de la conferencia de acceso telefónico local en mi organización</span><span class="sxs-lookup"><span data-stu-id="bb384-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="bb384-104">[] Puede que le resulte más sencillo ver todas las opciones de configuración de conferencia de acceso telefónico local en un mismo lugar.</span><span class="sxs-lookup"><span data-stu-id="bb384-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="bb384-105">Asignar una licencia de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="bb384-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="bb384-109">Para asignar una licencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="bb384-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="bb384-110">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span><span class="sxs-lookup"><span data-stu-id="bb384-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb384-p102">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows PowerShell. Para obtener instrucciones y scripts de PowerShell de ejemplo, vea [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="bb384-116">En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="bb384-p103">En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb384-p104">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="bb384-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="bb384-121">Asignar un id. de conferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="bb384-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="bb384-122">Asignar un id.</span><span class="sxs-lookup"><span data-stu-id="bb384-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="bb384-123">El identificador de conferencia se envía en la invitación a la reunión cuando la reunión está programada.</span><span class="sxs-lookup"><span data-stu-id="bb384-123">The conference ID is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="bb384-124">Cada reunión que un usuario programa obtener asignará un identificador de conferencia único.</span><span class="sxs-lookup"><span data-stu-id="bb384-124">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>
  
<span data-ttu-id="bb384-125">El Centro de administración de Skype Empresarial no se puede usar para asignar un id. de conferencia a un usuario, pero se puede usar el cmdlet de Windows PowerShell para esta finalidad.</span><span class="sxs-lookup"><span data-stu-id="bb384-125">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="bb384-126">El Centro de administración de Skype Empresarial no se puede usar para asignar un id. de conferencia a un usuario, pero se puede usar el cmdlet de Windows PowerShell para esta finalidad.</span><span class="sxs-lookup"><span data-stu-id="bb384-126">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="bb384-127">Para establecer el id. de conferencia de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bb384-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="bb384-128">Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="bb384-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="bb384-129">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="bb384-129">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="bb384-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="bb384-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="bb384-131">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="bb384-131">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="bb384-132">Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión de Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para Online de negocio, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para en línea de negocio, reunión Herramienta de migración (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="bb384-132">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="bb384-133">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-133">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
    
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="bb384-134">Habilitar o deshabilitar los correos electrónicos enviados a los usuarios de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="bb384-134">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="bb384-135">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-135">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-136">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bb384-136">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bb384-137">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="bb384-137">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bb384-138">En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="bb384-138">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="bb384-139">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-139">Click **Save**.</span></span>

<span data-ttu-id="bb384-140">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="bb384-141">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-141">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-142">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-142">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="bb384-143">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="bb384-143">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="bb384-144">Click **Save**.</span><span class="sxs-lookup"><span data-stu-id="bb384-144">Click **Save**.</span></span>
    
    <span data-ttu-id="bb384-p107">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-p107">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="bb384-147">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-147">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="bb384-148">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="bb384-148">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="bb384-149">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb384-149">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="bb384-150">También puede usar Windows PowerShell y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="bb384-150">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="bb384-151">Cambiar la información de contacto de la dirección del remitente en los mensajes de correo electrónico enviados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="bb384-151">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="bb384-p108">Cambiar la información de contacto de los remitentes de mensajes de correo electrónico enviados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="bb384-p108">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="bb384-155">Escriba la dirección de correo electrónico en el parámetro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="bb384-155">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="bb384-156">Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="bb384-156">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="bb384-157">Establezca el parámetro _SendEmailOverride_ en _True_.</span><span class="sxs-lookup"><span data-stu-id="bb384-157">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="bb384-158">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span><span class="sxs-lookup"><span data-stu-id="bb384-158">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="bb384-159">Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:</span><span class="sxs-lookup"><span data-stu-id="bb384-159">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="bb384-160">Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.</span><span class="sxs-lookup"><span data-stu-id="bb384-160">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="bb384-161">Vea los [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-161">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="bb384-162">Restablecer el id. de conferencia de reunión</span><span class="sxs-lookup"><span data-stu-id="bb384-162">Reset the meeting conference ID</span></span>

<span data-ttu-id="bb384-163">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-163">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-164">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb384-164">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bb384-165">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-165">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bb384-166">En **Conferencias de Audio**, haga clic en **Restablecer el identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bb384-166">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="bb384-167">En la **Restablecer el identificador de conferencia?** ventana, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="bb384-167">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="bb384-168">Se creará automáticamente un identificador de conferencia y un correo electrónico enviado al usuario con el nuevo identificador de conferencia si está habilitado el envío de correo electrónico a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bb384-168">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="bb384-169">Está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb384-169">It's enabled by default.</span></span>

<span data-ttu-id="bb384-170">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-170">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="bb384-171">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-171">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-172">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-172">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-173">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span><span class="sxs-lookup"><span data-stu-id="bb384-173">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="bb384-p110">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="bb384-p110">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="bb384-177">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="bb384-177">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="bb384-178">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="bb384-178">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="bb384-179">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="bb384-179">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="bb384-180">Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión de Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para Online de negocio, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para en línea de negocio, reunión Herramienta de migración (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="bb384-180">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="bb384-181">Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-181">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="bb384-182">Restablecer el PIN del organizador de una conferencia</span><span class="sxs-lookup"><span data-stu-id="bb384-182">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="bb384-183">Cada reunión que un usuario programa obtener asignará un identificador de conferencia único.</span><span class="sxs-lookup"><span data-stu-id="bb384-183">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="bb384-184">Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar este y que desea establecer para un cierto número, o los usuarios no pueden recordar o han perdido su identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bb384-184">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="bb384-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="bb384-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="bb384-186">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-186">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-187">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb384-187">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bb384-188">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-188">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bb384-189">En **Conferencias de Audio**, haga clic en **Restablecer PIN**y, a continuación, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="bb384-189">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="bb384-190">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-190">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="bb384-191">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-191">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-192">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-192">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="bb384-193">Click **Users**, and then select the user that you want to reset the PIN for.</span><span class="sxs-lookup"><span data-stu-id="bb384-193">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="bb384-194">In the Action pane, under **PIN**, click **Reset**.</span><span class="sxs-lookup"><span data-stu-id="bb384-194">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="bb384-p113">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span><span class="sxs-lookup"><span data-stu-id="bb384-p113">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="bb384-199">Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-199">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="bb384-200">Enviar un correo electrónico con información de conferencia de Audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="bb384-200">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="bb384-201">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-202">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb384-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bb384-203">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-203">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bb384-204">En **Conferencias de Audio**, haga clic en **Enviar información de conferencia en el correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="bb384-204">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="bb384-205">When you do this, the audio conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="bb384-205">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="bb384-206">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="bb384-207">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-208">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="bb384-209">Click **Users**, and then select the user that you want to reset the PIN for.</span><span class="sxs-lookup"><span data-stu-id="bb384-209">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="bb384-210">Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="bb384-210">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb384-211">When you do this, the audio conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="bb384-211">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="bb384-212">Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.</span><span class="sxs-lookup"><span data-stu-id="bb384-212">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="bb384-213">Establecer el número de teléfono de conferencia de audio predeterminada para los organizadores de reuniones</span><span class="sxs-lookup"><span data-stu-id="bb384-213">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="bb384-214">Configurar el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones</span><span class="sxs-lookup"><span data-stu-id="bb384-214">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="bb384-215">Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones cuando está habilitando un usuario para las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-215">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-216">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-p114">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bb384-p114">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="bb384-219">In the Action pane, in the user's properties, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="bb384-219">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="bb384-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="bb384-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="bb384-221">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span><span class="sxs-lookup"><span data-stu-id="bb384-221">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="bb384-p115">Si selecciona Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bb384-p115">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number. These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="bb384-224">Si selecciona un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito. Estos números de teléfono serán el número de teléfono predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bb384-224">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="bb384-225">El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una.</span><span class="sxs-lookup"><span data-stu-id="bb384-225">Click **Save**.</span></span> 
    
<span data-ttu-id="bb384-226">Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-226">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="bb384-227">Vea **Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones**.</span><span class="sxs-lookup"><span data-stu-id="bb384-227">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="bb384-228">Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado después de haber habilitado un usuario para las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-229">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="bb384-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="bb384-231">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="bb384-231">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="bb384-232">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span><span class="sxs-lookup"><span data-stu-id="bb384-232">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="bb384-233">Si el usuario usa Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bb384-233">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="bb384-234">Si el usuario usa un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito.</span><span class="sxs-lookup"><span data-stu-id="bb384-234">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="bb384-235">El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una.</span><span class="sxs-lookup"><span data-stu-id="bb384-235">Click **Save**.</span></span> 
    
<span data-ttu-id="bb384-236">Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-236">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="bb384-237">Elegir la configuración de puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="bb384-237">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="bb384-238">Configuración del puente de audioconferencia o de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-238">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="bb384-239">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-239">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-240">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bb384-240">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bb384-241">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="bb384-241">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bb384-242">En el panel **configuración de puente** , habilitar o deshabilitar la **entrada de la reunión y salir de las notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="bb384-242">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="bb384-243">Esto está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb384-243">This is enabled by default.</span></span> <span data-ttu-id="bb384-244">Si deshabilita esta opción, no se le notificará a los usuarios que ya se han unido a la reunión de forma predeterminada cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="bb384-244">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="bb384-245">En **tipo de anuncio de entrada o salida**, elija **tonos** o **nombres o números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="bb384-245">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="bb384-246">Si elige **los nombres o números de teléfono**, también puede elegir habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="bb384-246">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="bb384-247">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-247">Click **Save**.</span></span>

<span data-ttu-id="bb384-248">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-248">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="bb384-249">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-249">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-250">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bb384-250">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-251">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="bb384-251">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="bb384-252">Under **Meeting join experience**, select the following actions:</span><span class="sxs-lookup"><span data-stu-id="bb384-252">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="bb384-p117">En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb384-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="bb384-255">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span><span class="sxs-lookup"><span data-stu-id="bb384-255">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="bb384-p118">Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype Empresarial y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.</span><span class="sxs-lookup"><span data-stu-id="bb384-p118">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="bb384-258">**Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="bb384-258">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="bb384-259">Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-259">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="bb384-260">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="bb384-260">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="bb384-261">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-261">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-262">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bb384-262">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bb384-263">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="bb384-263">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bb384-264">En el panel **configuración de puente** , escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-264">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="bb384-p119">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="bb384-p119">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

<span data-ttu-id="bb384-267">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-267">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="bb384-268">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-268">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-269">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bb384-269">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-270">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="bb384-270">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="bb384-271">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="bb384-271">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="bb384-p120">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="bb384-p120">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="bb384-274">El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="bb384-274">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="bb384-275">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="bb384-275">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="bb384-276">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-276">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-277">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bb384-277">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bb384-278">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="bb384-278">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bb384-279">En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.</span><span class="sxs-lookup"><span data-stu-id="bb384-279">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="bb384-280">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-280">Click **Save**.</span></span> 
 
    <span data-ttu-id="bb384-281">También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, vaya a las propiedades del usuario conferencias de audio y haciendo clic en **Enviar información de conferencia en el correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="bb384-281">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="bb384-282">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="bb384-282">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="bb384-283">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-283">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="bb384-284">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-284">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-285">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-285">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="bb384-286">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="bb384-286">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="bb384-287">Click **Save**.</span><span class="sxs-lookup"><span data-stu-id="bb384-287">Click **Save**.</span></span>
    
    <span data-ttu-id="bb384-288">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-288">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="bb384-289">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="bb384-289">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="bb384-290">Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="bb384-290">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="bb384-291">Vea y establezca la primaria (valor predeterminado) y los idiomas (alternativos) secundarios en un puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="bb384-291">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="bb384-292">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-292">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb384-293">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bb384-293">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bb384-294">Seleccione un número de teléfono de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb384-294">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="bb384-295">Elija los idiomas que desee en **idioma predeterminado** e **idiomas alternativos (opcionales)**.</span><span class="sxs-lookup"><span data-stu-id="bb384-295">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="bb384-296">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="bb384-296">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="bb384-297">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-297">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-298">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-298">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-299">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span><span class="sxs-lookup"><span data-stu-id="bb384-299">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="bb384-300">En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="bb384-300">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="bb384-p121">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span><span class="sxs-lookup"><span data-stu-id="bb384-p121">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="bb384-303">También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="bb384-303">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png)  <span data-ttu-id="bb384-305">Vea los números de acceso telefónico de conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="bb384-305">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="bb384-306">Ver números de acceso telefónico para conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bb384-306">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-307">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-307">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-p122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span><span class="sxs-lookup"><span data-stu-id="bb384-p122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>
    
  - <span data-ttu-id="bb384-310">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="bb384-310">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="bb384-311">Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bb384-311">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="bb384-p123">También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bb384-p123">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="bb384-314">Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.</span><span class="sxs-lookup"><span data-stu-id="bb384-314">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="bb384-315">Vea [una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-315">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="bb384-317">Ver una lista de usuarios habilitados</span><span class="sxs-lookup"><span data-stu-id="bb384-317">See a list of users that are enabled</span></span>

1. <span data-ttu-id="bb384-318">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-318">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bb384-319">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bb384-319">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bb384-320">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span><span class="sxs-lookup"><span data-stu-id="bb384-320">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="bb384-321">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="bb384-321">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bb384-322">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bb384-322">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="bb384-323">Hay varias opciones de configuración que puede administrar en el nivel de organización mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb384-323">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="bb384-324">Esto facilita la configuración se aplican a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bb384-324">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="bb384-325">Existen varias opciones que puede configurar en el nivel de la organización con Windows PowerShell. Esto facilita la configuración de estas opciones y las aplica a todos los usuarios. Estas son las opciones de configuración de nivel de organización:</span><span class="sxs-lookup"><span data-stu-id="bb384-325">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="bb384-326">A continuación presentamos la configuración de nivel de la organización:</span><span class="sxs-lookup"><span data-stu-id="bb384-326">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="bb384-327">**Configuración de notificaciones de entrada o salida** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="bb384-327">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="bb384-328">**Configuración de grabación de nombre** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="bb384-328">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="bb384-329">**Establecer la longitud PIN** El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="bb384-329">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="bb384-330">**Establecer sólo marcado en reuniones desde un teléfono** El valor predeterminado _$false_.</span><span class="sxs-lookup"><span data-stu-id="bb384-330">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="bb384-331">**Establecer si se enviará un correo electrónico a los usuarios** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="bb384-331">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="bb384-332">**Establecer si se enviará un correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.</span><span class="sxs-lookup"><span data-stu-id="bb384-332">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="bb384-333">**Configuración de la dirección de correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="bb384-333">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="bb384-334">**Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="bb384-334">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bb384-335">Desea saber más acerca de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb384-335">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="bb384-p125">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bb384-p125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bb384-339">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="bb384-339">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bb384-340">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb384-340">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="bb384-p126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="bb384-p126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="bb384-343">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb384-343">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bb384-344">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb384-344">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bb384-345">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb384-345">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="bb384-p127">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="bb384-p127">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="bb384-348">See also</span><span class="sxs-lookup"><span data-stu-id="bb384-348">Related topics</span></span>

[<span data-ttu-id="bb384-349">Administrar la configuración de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="bb384-349">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)



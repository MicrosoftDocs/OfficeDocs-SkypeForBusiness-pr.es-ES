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
description: 'Vea los pasos para asignar un identificador de conferencia y licencia de conferencia de acceso telefónico a un usuario y muchas otras opciones de conferencia de acceso telefónico. '
ms.openlocfilehash: 26d80b71344227aeaec7089e2bb9f9a9dfe32ad2
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703672"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="a180b-103">Administrar la configuración de la conferencia de acceso telefónico local en mi organización</span><span class="sxs-lookup"><span data-stu-id="a180b-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="a180b-104">[] Puede que le resulte más sencillo ver todas las opciones de configuración de conferencia de acceso telefónico local en un mismo lugar.</span><span class="sxs-lookup"><span data-stu-id="a180b-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="a180b-105">Asignar una licencia de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a180b-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="a180b-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="a180b-109">Para asignar una licencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="a180b-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="a180b-110">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span><span class="sxs-lookup"><span data-stu-id="a180b-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a180b-p102">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows PowerShell. Para obtener instrucciones y scripts de PowerShell de ejemplo, vea [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="a180b-116">En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="a180b-p103">En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a180b-p104">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="a180b-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="a180b-121">Habilitar o deshabilitar los correos electrónicos enviados a los usuarios de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="a180b-121">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="a180b-122">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-122">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-123">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a180b-123">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a180b-124">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="a180b-124">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a180b-125">En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="a180b-125">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="a180b-126">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-126">Click **Save**.</span></span>

<span data-ttu-id="a180b-127">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-127">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a180b-128">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a180b-128">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-129">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-129">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a180b-130">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="a180b-130">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="a180b-131">Click **Save**.</span><span class="sxs-lookup"><span data-stu-id="a180b-131">Click **Save**.</span></span>
    
    <span data-ttu-id="a180b-p105">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="a180b-134">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-134">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="a180b-135">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="a180b-135">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="a180b-136">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a180b-136">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="a180b-137">También puede usar Windows PowerShell y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="a180b-137">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="a180b-138">Cambiar la información de contacto de la dirección del remitente en los mensajes de correo electrónico enviados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="a180b-138">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="a180b-p106">Cambiar la información de contacto de los remitentes de mensajes de correo electrónico enviados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="a180b-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="a180b-142">Escriba la dirección de correo electrónico en el parámetro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="a180b-142">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="a180b-143">Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="a180b-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="a180b-144">Establezca el parámetro _SendEmailOverride_ en _True_.</span><span class="sxs-lookup"><span data-stu-id="a180b-144">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="a180b-145">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span><span class="sxs-lookup"><span data-stu-id="a180b-145">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="a180b-146">Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:</span><span class="sxs-lookup"><span data-stu-id="a180b-146">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="a180b-147">Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.</span><span class="sxs-lookup"><span data-stu-id="a180b-147">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="a180b-148">Vea los [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-148">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="a180b-149">Restablecer el id. de conferencia de reunión</span><span class="sxs-lookup"><span data-stu-id="a180b-149">Reset the meeting conference ID</span></span>

<span data-ttu-id="a180b-150">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-150">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-151">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="a180b-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a180b-152">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a180b-153">En **Conferencias de Audio**, haga clic en **Restablecer el identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a180b-153">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="a180b-154">En la **Restablecer el identificador de conferencia?** ventana, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="a180b-154">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="a180b-155">Se creará automáticamente un identificador de conferencia y un correo electrónico enviado al usuario con el nuevo identificador de conferencia si está habilitado el envío de correo electrónico a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a180b-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="a180b-156">Está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a180b-156">It's enabled by default.</span></span>

<span data-ttu-id="a180b-157">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="a180b-158">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-158">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-159">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-159">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a180b-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span><span class="sxs-lookup"><span data-stu-id="a180b-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="a180b-p108">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="a180b-p108">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="a180b-164">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="a180b-164">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a180b-165">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="a180b-165">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="a180b-166">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="a180b-166">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="a180b-167">Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión de Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para Online de negocio, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para en línea de negocio, reunión Herramienta de migración (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="a180b-167">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="a180b-168">Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-168">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="a180b-169">Restablecer el PIN del organizador de una conferencia</span><span class="sxs-lookup"><span data-stu-id="a180b-169">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="a180b-170">Cada reunión que un usuario programa obtener asignará un identificador de conferencia único.</span><span class="sxs-lookup"><span data-stu-id="a180b-170">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="a180b-171">Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar este y que desea establecer para un cierto número, o los usuarios no pueden recordar o han perdido su identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a180b-171">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="a180b-172">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="a180b-172">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="a180b-173">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-173">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-174">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="a180b-174">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a180b-175">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-175">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a180b-176">En **Conferencias de Audio**, haga clic en **Restablecer PIN**y, a continuación, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="a180b-176">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="a180b-177">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-177">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="a180b-178">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a180b-178">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-179">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-179">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a180b-180">Click **Users**, and then select the user that you want to reset the PIN for.</span><span class="sxs-lookup"><span data-stu-id="a180b-180">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="a180b-181">In the Action pane, under **PIN**, click **Reset**.</span><span class="sxs-lookup"><span data-stu-id="a180b-181">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="a180b-p111">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span><span class="sxs-lookup"><span data-stu-id="a180b-p111">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="a180b-186">Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-186">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="a180b-187">Enviar un correo electrónico con información de conferencia de Audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="a180b-187">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="a180b-188">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-188">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-189">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="a180b-189">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a180b-190">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-190">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a180b-191">En **Conferencias de Audio**, haga clic en **Enviar información de conferencia en el correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="a180b-191">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="a180b-192">When you do this, the audio conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="a180b-192">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="a180b-193">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-193">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="a180b-194">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a180b-194">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-195">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-195">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a180b-196">Click **Users**, and then select the user that you want to reset the PIN for.</span><span class="sxs-lookup"><span data-stu-id="a180b-196">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="a180b-197">Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="a180b-197">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a180b-198">When you do this, the audio conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="a180b-198">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="a180b-199">Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.</span><span class="sxs-lookup"><span data-stu-id="a180b-199">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="a180b-200">Configuración del teléfono los números incluidos en invitaciones</span><span class="sxs-lookup"><span data-stu-id="a180b-200">Setting the phone numbers included on invites</span></span>

<span data-ttu-id="a180b-201">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-202">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="a180b-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a180b-203">Junto a **Conferencias de Audio**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-203">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="a180b-204">En el panel de **Conferencia de Audio** , puede establecer el **número de teléfono de pago** y, si se permite, el **número de teléfono gratuito**.</span><span class="sxs-lookup"><span data-stu-id="a180b-204">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="a180b-205">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-205">Click **Save**.</span></span>

<span data-ttu-id="a180b-206">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  
  
1. <span data-ttu-id="a180b-207">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-208">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-208">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a180b-p112">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a180b-p112">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="a180b-211">En el panel de acciones, puede establecer el **número de teléfono de pago** y, si se permite, el **número de teléfono gratuito**.</span><span class="sxs-lookup"><span data-stu-id="a180b-211">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="a180b-212">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-212">Click **Save**.</span></span>
    
<span data-ttu-id="a180b-213">Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-213">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="a180b-214">Elegir la configuración de puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="a180b-214">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="a180b-215">Configuración del puente de audioconferencia o de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a180b-215">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="a180b-216">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-216">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-217">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a180b-217">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a180b-218">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="a180b-218">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a180b-219">En el panel **configuración de puente** , habilitar o deshabilitar la **entrada de la reunión y salir de las notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="a180b-219">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="a180b-220">Esto está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a180b-220">This is enabled by default.</span></span> <span data-ttu-id="a180b-221">Si deshabilita esta opción, no se le notificará a los usuarios que ya se han unido a la reunión de forma predeterminada cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a180b-221">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="a180b-222">En **tipo de anuncio de entrada o salida**, elija **tonos** o **nombres o números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="a180b-222">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="a180b-223">Si elige **los nombres o números de teléfono**, también puede elegir habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="a180b-223">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="a180b-224">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-224">Click **Save**.</span></span>

<span data-ttu-id="a180b-225">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-225">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="a180b-226">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-226">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-227">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a180b-227">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a180b-228">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="a180b-228">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="a180b-229">Under **Meeting join experience**, select the following actions:</span><span class="sxs-lookup"><span data-stu-id="a180b-229">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="a180b-p114">En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a180b-p114">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="a180b-232">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span><span class="sxs-lookup"><span data-stu-id="a180b-232">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="a180b-p115">Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype Empresarial y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a180b-p115">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="a180b-235">**Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="a180b-235">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="a180b-236">Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-236">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="a180b-237">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a180b-237">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="a180b-238">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-238">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-239">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a180b-239">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a180b-240">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="a180b-240">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a180b-241">En el panel **configuración de puente** , escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-241">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="a180b-p116">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="a180b-p116">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

<span data-ttu-id="a180b-244">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-244">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="a180b-245">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-245">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-246">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a180b-246">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a180b-247">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="a180b-247">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="a180b-248">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="a180b-248">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="a180b-p117">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="a180b-p117">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="a180b-251">El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="a180b-251">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="a180b-252">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a180b-252">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="a180b-253">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-253">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-254">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a180b-254">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a180b-255">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="a180b-255">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a180b-256">En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.</span><span class="sxs-lookup"><span data-stu-id="a180b-256">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="a180b-257">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-257">Click **Save**.</span></span> 
 
    <span data-ttu-id="a180b-258">También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, vaya a las propiedades del usuario conferencias de audio y haciendo clic en **Enviar información de conferencia en el correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="a180b-258">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="a180b-259">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="a180b-259">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="a180b-260">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-260">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="a180b-261">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a180b-261">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-262">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-262">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a180b-263">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="a180b-263">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="a180b-264">Click **Save**.</span><span class="sxs-lookup"><span data-stu-id="a180b-264">Click **Save**.</span></span>
    
    <span data-ttu-id="a180b-265">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-265">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="a180b-266">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="a180b-266">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="a180b-267">Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="a180b-267">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="a180b-268">Vea y establezca la primaria (valor predeterminado) y los idiomas (alternativos) secundarios en un puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="a180b-268">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="a180b-269">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-269">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-270">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a180b-270">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a180b-271">Seleccione un número de teléfono de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-271">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="a180b-272">Elija los idiomas que desee en **idioma predeterminado** e **idiomas alternativos (opcionales)**.</span><span class="sxs-lookup"><span data-stu-id="a180b-272">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="a180b-273">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-273">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="a180b-274">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-274">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-275">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-275">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a180b-276">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span><span class="sxs-lookup"><span data-stu-id="a180b-276">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="a180b-277">En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a180b-277">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="a180b-p118">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span><span class="sxs-lookup"><span data-stu-id="a180b-p118">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="a180b-280">También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="a180b-280">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="a180b-281">Vea los números de acceso telefónico de conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="a180b-281">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="a180b-282">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-282">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a180b-283">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a180b-283">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a180b-284">Seleccione un número de teléfono de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a180b-284">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="a180b-285">Here you can:</span><span class="sxs-lookup"><span data-stu-id="a180b-285">Here you can:</span></span>
    
  - <span data-ttu-id="a180b-286">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="a180b-286">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="a180b-287">Ver la ubicación y el idioma principal, que se utilizará en el operador automático de conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="a180b-287">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>


<span data-ttu-id="a180b-288">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="a180b-288">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="a180b-289">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-289">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-290">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-290">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a180b-p120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span><span class="sxs-lookup"><span data-stu-id="a180b-p120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>
    
  - <span data-ttu-id="a180b-293">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="a180b-293">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="a180b-294">Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a180b-294">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="a180b-p121">También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a180b-p121">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="a180b-297">Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.</span><span class="sxs-lookup"><span data-stu-id="a180b-297">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="a180b-298">Vea [una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-298">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="a180b-300">Ver una lista de usuarios habilitados</span><span class="sxs-lookup"><span data-stu-id="a180b-300">See a list of users that are enabled</span></span>

1. <span data-ttu-id="a180b-301">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-301">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a180b-302">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a180b-302">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a180b-303">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span><span class="sxs-lookup"><span data-stu-id="a180b-303">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="a180b-304">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="a180b-304">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a180b-305">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a180b-305">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="a180b-306">Hay varias opciones de configuración que puede administrar en el nivel de organización mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a180b-306">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="a180b-307">Esto facilita la configuración se aplican a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a180b-307">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="a180b-308">Existen varias opciones que puede configurar en el nivel de la organización con Windows PowerShell. Esto facilita la configuración de estas opciones y las aplica a todos los usuarios. Estas son las opciones de configuración de nivel de organización:</span><span class="sxs-lookup"><span data-stu-id="a180b-308">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="a180b-309">A continuación presentamos la configuración de nivel de la organización:</span><span class="sxs-lookup"><span data-stu-id="a180b-309">Here are the organization-level settings:</span></span> 
 
- <span data-ttu-id="a180b-310">**Configuración de notificaciones de entrada o salida** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="a180b-310">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="a180b-311">**Configuración de grabación de nombre** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="a180b-311">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="a180b-312">**Establecer la longitud PIN** El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="a180b-312">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="a180b-313">**Establecer sólo marcado en reuniones desde un teléfono** El valor predeterminado _$false_.</span><span class="sxs-lookup"><span data-stu-id="a180b-313">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="a180b-314">**Establecer si se enviará un correo electrónico a los usuarios** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="a180b-314">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="a180b-315">**Establecer si se enviará un correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.</span><span class="sxs-lookup"><span data-stu-id="a180b-315">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="a180b-316">**Configuración de la dirección de correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="a180b-316">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="a180b-317">**Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="a180b-317">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a180b-318">Desea saber más acerca de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a180b-318">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="a180b-p123">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="a180b-p123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a180b-322">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="a180b-322">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a180b-323">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a180b-323">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a180b-p124">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="a180b-p124">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a180b-326">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a180b-326">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a180b-327">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a180b-327">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a180b-328">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a180b-328">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="a180b-p125">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="a180b-p125">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a180b-331">See also</span><span class="sxs-lookup"><span data-stu-id="a180b-331">Related topics</span></span>

[<span data-ttu-id="a180b-332">Administrar la configuración de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="a180b-332">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)



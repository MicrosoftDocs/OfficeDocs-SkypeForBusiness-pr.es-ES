---
title: "Administrar la configuración de la conferencia de acceso telefónico local en mi organización"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="c096b-103">Administrar la configuración de la conferencia de acceso telefónico local en mi organización</span><span class="sxs-lookup"><span data-stu-id="c096b-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="c096b-104">[] Puede que le resulte más sencillo ver todas las opciones de configuración de conferencia de acceso telefónico local en un mismo lugar.</span><span class="sxs-lookup"><span data-stu-id="c096b-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="c096b-105">Asignar una licencia de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="c096b-106">No se puede asignar licencias usando el **Skype para el centro de administración de negocios**.</span><span class="sxs-lookup"><span data-stu-id="c096b-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="c096b-107">Debe utilizar el centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c096b-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="c096b-108">Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="c096b-109">Para asignar una licencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="c096b-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="c096b-110">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-111">En la exploración de la izquierda del **Centro de administración de Office 365**, vaya a **usuarios** > **usuarios activos**y a continuación, seleccione el usuario o usuarios de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="c096b-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c096b-p102">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows PowerShell. Para obtener instrucciones y scripts de PowerShell de ejemplo, vea [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="c096b-116">En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="c096b-p103">En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c096b-p104">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="c096b-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="c096b-121">Asignar un ID de conferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="c096b-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="c096b-p105">Asignar un id. de conferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="c096b-p105">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider. The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="c096b-124">Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o elija uno que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="c096b-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="c096b-125">Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia.</span><span class="sxs-lookup"><span data-stu-id="c096b-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="c096b-126">Si desea asignar el dinámico en lugar de conferencia estática identificadores, vea [conferencias de Audio utilizando identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="c096b-127">El Skype para el centro de administración de negocios no puede utilizarse para asignar un ID de conferencia a un usuario, pero puede utilizar el cmdlet de Windows PowerShell para ello.</span><span class="sxs-lookup"><span data-stu-id="c096b-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="c096b-128">El Centro de administración de Skype Empresarial no se puede usar para asignar un id. de conferencia a un usuario, pero se puede usar el cmdlet de Windows PowerShell para esta finalidad.</span><span class="sxs-lookup"><span data-stu-id="c096b-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="c096b-129">Para establecer el id. de conferencia de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c096b-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="c096b-130">El id. de conferencia tiene que contener siete dígitos y no se puede cambiar en el Centro de administración de Skype Empresarial ni con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c096b-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="c096b-131">Después de crea un nuevo ID de conferencia, no se puede utilizar el ID de conferencia antigua por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="c096b-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c096b-132">Debe notificar a los usuarios a programar sus invitaciones para asegurarse de que la nueva conferencia que ID se agrega a las invitaciones para reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="c096b-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c096b-133">Los usuarios pueden utilizar el Skype para la herramienta de migración de reuniones de negocios para actualizar sus reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="c096b-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="c096b-134">Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión para Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para los negocios en línea, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para los negocios en línea, reunión Herramienta de migración (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="c096b-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="c096b-135">Consulte [Ver, cambiar y restablecer un ID de conferencia asignado a un usuario](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="c096b-136">Cambiar el proveedor de conferencia de audio de Microsoft a un proveedor de terceros</span><span class="sxs-lookup"><span data-stu-id="c096b-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="c096b-137">Cambiar el proveedor de servicios de conferencia de acceso telefónico local de Microsoft a un proveedor de terceros</span><span class="sxs-lookup"><span data-stu-id="c096b-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-138">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-139">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **los usuarios**y a continuación seleccione el usuario que desea cambiar el proveedor de conferencia de audio para.</span><span class="sxs-lookup"><span data-stu-id="c096b-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="c096b-140">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="c096b-141">En la página de **Propiedades** , en **nombre del proveedor**, elija el proveedor de conferencia de audio para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c096b-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c096b-142">Sólo puede seleccionar Microsoft como proveedor de conferencia de audio o **Ninguno** , si ha seleccionado varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="c096b-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="c096b-143">Solo puede seleccionar Microsoft como el proveedor de servicios de conferencia de acceso telefónico local o **Ninguno** si ha seleccionado varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="c096b-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="c096b-144">Habilitar o deshabilitar los mensajes de correo electrónico enviados a los usuarios de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="c096b-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="c096b-145">Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="c096b-146">Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c096b-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="c096b-147">Usar el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c096b-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-148">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c096b-149">En la página **configuración de puente de Microsoft** , active o desactive la **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencia de audio**.</span><span class="sxs-lookup"><span data-stu-id="c096b-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="c096b-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-150">Click **Save**.</span></span>
    
    <span data-ttu-id="c096b-p108">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-p108">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="c096b-153">Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="c096b-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="c096b-154">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="c096b-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="c096b-155">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c096b-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="c096b-156">También puede usar Windows PowerShell y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="c096b-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="c096b-157">Cambiar información de contacto del remitente en los mensajes de correo electrónico enviados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="c096b-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="c096b-p109">Cambiar la información de contacto de los remitentes de mensajes de correo electrónico enviados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="c096b-p109">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="c096b-161">Escriba la dirección de correo electrónico en el parámetro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="c096b-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="c096b-162">Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="c096b-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="c096b-163">Establezca el parámetro _SendEmailOverride_ en _True_.</span><span class="sxs-lookup"><span data-stu-id="c096b-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="c096b-164">Puede realizar cambios en el correo electrónico enviado a los usuarios, como el correo electrónico se envía desde la dirección de correo electrónico o el nombre para mostrar para el correo electrónico mediante la ejecución de:</span><span class="sxs-lookup"><span data-stu-id="c096b-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="c096b-165">Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:</span><span class="sxs-lookup"><span data-stu-id="c096b-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="c096b-166">Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.</span><span class="sxs-lookup"><span data-stu-id="c096b-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="c096b-167">Ver [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="c096b-168">Restablecer la reunión Id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="c096b-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="c096b-169">Restablecer el id. de conferencia de reunión</span><span class="sxs-lookup"><span data-stu-id="c096b-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-170">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-171">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**y, en el panel de acción en el **Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="c096b-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="c096b-172">En el **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c096b-172">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="c096b-173">Se creará automáticamente un Id. de conferencia y un correo electrónico al usuario con el nuevo ID de conferencia si está habilitado el envío de correo electrónico a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c096b-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="c096b-174">Está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c096b-174">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="c096b-175">Después de crea un nuevo ID de conferencia, no se puede utilizar el ID de conferencia antigua por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="c096b-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c096b-176">Debe notificar a los usuarios a programar sus invitaciones para asegurarse de que la nueva conferencia que ID se agrega a las invitaciones para reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="c096b-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c096b-177">Los usuarios pueden utilizar el Skype para la herramienta de migración de reuniones de negocios para actualizar sus reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="c096b-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="c096b-178">Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte: [herramienta de actualización de la reunión para Skype para empresas y Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negocios en línea Reunión de la herramienta de migración (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para negocios en línea, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="c096b-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="c096b-179">Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="c096b-180">Restablecer el PIN del organizador de una conferencia</span><span class="sxs-lookup"><span data-stu-id="c096b-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="c096b-181">Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="c096b-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="c096b-182">Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia.</span><span class="sxs-lookup"><span data-stu-id="c096b-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="c096b-183">Si desea asignar el dinámico en lugar de conferencia estática IDs, [conferencias de Audio utilizando identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="c096b-184">Aunque crea automáticamente un ID de conferencia estática y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar esta y desea establecerla en un número determinado, o los usuarios no recuerdan o han perdido su ID de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c096b-184">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="c096b-185">Puede utilizar el Skype para el centro de administración de negocios y de Windows PowerShell para ver, cambiar y restablecer su ID de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c096b-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="c096b-186">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-187">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c096b-188">Haga clic en **usuarios**y, a continuación, seleccione el usuario que desea restablecer el PIN para.</span><span class="sxs-lookup"><span data-stu-id="c096b-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="c096b-189">En el panel de acción, **PIN**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="c096b-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="c096b-190">Los usuarios recibirán un correo electrónico con su NIP cuando están habilitados para conferencias de audio o cuando se restablece el NIP.</span><span class="sxs-lookup"><span data-stu-id="c096b-190">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="c096b-191">Pero si ha deshabilitado automáticamente enviar mensajes de correo electrónico, no se enviará un correo electrónico de restablecimiento PIN y tendrá que enviar manualmente el PIN al usuario.</span><span class="sxs-lookup"><span data-stu-id="c096b-191">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="c096b-192">El PIN sólo aparecerá una vez después de que se ha restablecido.</span><span class="sxs-lookup"><span data-stu-id="c096b-192">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="c096b-193">Después se muestra inmediatamente después de que se restablezca, el PIN no se muestra ya en las propiedades del usuario; en su lugar, \*\*\* aparecerá.</span><span class="sxs-lookup"><span data-stu-id="c096b-193">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="c096b-194">Los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para la conferencia de acceso telefónico local o cuando se restablezca el PIN. Pero, si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar el PIN al usuario de forma manual. El PIN solo se mostrará una vez después de que se haya restablecido. Una vez que se muestra inmediatamente después de haberse restablecido, el PIN no se mostrará más en las propiedades del usuario y en su lugar se mostrará \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="c096b-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c096b-195">Enviar un correo electrónico con información de conferencia de Audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="c096b-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="c096b-196">Enviar un correo electrónico con información sobre la conferencia de acceso telefónico local a un usuario</span><span class="sxs-lookup"><span data-stu-id="c096b-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-197">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c096b-198">Haga clic en **usuarios**y, a continuación, seleccione el usuario que desea restablecer el PIN para.</span><span class="sxs-lookup"><span data-stu-id="c096b-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="c096b-199">Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="c096b-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c096b-200">Al hacerlo, la conferencia de audio PIN no se envía al usuario.</span><span class="sxs-lookup"><span data-stu-id="c096b-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="c096b-201">Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.</span><span class="sxs-lookup"><span data-stu-id="c096b-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="c096b-202">Establecer el número de teléfono de conferencia de audio predeterminado para los organizadores de la reunión</span><span class="sxs-lookup"><span data-stu-id="c096b-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="c096b-203">Configurar el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones</span><span class="sxs-lookup"><span data-stu-id="c096b-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="c096b-204">Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones cuando está habilitando un usuario para las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-205">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-p115">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="c096b-p115">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="c096b-208">En el panel de acciones, en las propiedades del usuario, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="c096b-209">En la página de **Propiedades** , en **nombre del proveedor**, utilice la lista desplegable para seleccionar el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="c096b-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="c096b-210">Si selecciona Microsoft como proveedor de conferencia de audio, puede elegir el número de teléfono de conferencia de audio predeterminado en la lista.</span><span class="sxs-lookup"><span data-stu-id="c096b-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="c096b-p116">Si selecciona Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c096b-p116">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number. These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="c096b-213">Si selecciona un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito. Estos números de teléfono serán el número de teléfono predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c096b-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="c096b-214">El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una.</span><span class="sxs-lookup"><span data-stu-id="c096b-214">Click **Save**.</span></span> 
    
<span data-ttu-id="c096b-215">Consulte [el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="c096b-216">Vea **Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones**.</span><span class="sxs-lookup"><span data-stu-id="c096b-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="c096b-217">Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado después de haber habilitado un usuario para las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-218">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-219">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**, seleccione el usuario que desee y, en la página acción, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="c096b-220">En la página de **Propiedades** , en **nombre del proveedor**, utilice la lista desplegable para seleccionar el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="c096b-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="c096b-221">Si el usuario utiliza Microsoft como proveedor de conferencia de audio, puede elegir el número de teléfono de conferencia de audio predeterminado en la lista.</span><span class="sxs-lookup"><span data-stu-id="c096b-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="c096b-222">Si el usuario usa Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c096b-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="c096b-223">Si el usuario usa un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito.</span><span class="sxs-lookup"><span data-stu-id="c096b-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="c096b-224">El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una.</span><span class="sxs-lookup"><span data-stu-id="c096b-224">Click **Save**.</span></span> 
    
<span data-ttu-id="c096b-225">Consulte [el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="c096b-226">Configuración de puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="c096b-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="c096b-227">Configuración del puente de audioconferencia o de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="c096b-228">Establecer la experiencia de reunión cuando las personas que llaman se unen a una reunión</span><span class="sxs-lookup"><span data-stu-id="c096b-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-229">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-230">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c096b-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="c096b-231">En **experimentar la combinación de reunión**, seleccione las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c096b-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="c096b-p117">En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c096b-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="c096b-234">Se puede establecer de forma reunión cuando un usuario une a una reunión mediante un Skype para la aplicación de negocios o Teams de Microsoft y modifican la configuración de **anunciar cuando entran o salen** del menú reunión de Skype o Microsoft Teams **Opciones** de la reunión.</span><span class="sxs-lookup"><span data-stu-id="c096b-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="c096b-p118">Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype Empresarial y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.</span><span class="sxs-lookup"><span data-stu-id="c096b-p118">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="c096b-237">**Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="c096b-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="c096b-238">Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="c096b-239">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c096b-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="c096b-240">Configurar la longitud del PIN de las reuniones</span><span class="sxs-lookup"><span data-stu-id="c096b-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-241">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-242">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c096b-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="c096b-243">En **seguridad**, especifique el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="c096b-244">El NIP debe tener entre 4 y 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="c096b-244">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="c096b-245">El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="c096b-245">The default is 5.</span></span>
    
<span data-ttu-id="c096b-246">El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="c096b-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="c096b-247">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c096b-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="c096b-248">Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-249">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c096b-250">En la página **configuración de puente de Microsoft** , active o desactive la **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencia de audio**.</span><span class="sxs-lookup"><span data-stu-id="c096b-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="c096b-251">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-251">Click **Save**.</span></span>
    
    <span data-ttu-id="c096b-252">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c096b-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="c096b-253">Si lo hace, se enviará un correo electrónico que sólo incluye los Id. de conferencia y número de teléfono de conferencia, pero el PIN no se incluirán.</span><span class="sxs-lookup"><span data-stu-id="c096b-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="c096b-254">Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="c096b-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="c096b-255">Ver y configurar los idiomas primarios y secundarios en un puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="c096b-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="c096b-256">Ver y configurar el idioma principal y los secundarios en un puente de conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-257">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-258">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**y, a continuación, haga clic en **puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c096b-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="c096b-259">En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c096b-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="c096b-260">También puede establecer los idiomas primarios y secundarios que son compatibles cuando se selecciona Microsoft como proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="c096b-260">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c096b-261">El orden en que se selecciona en la lista es el mismo orden en el que se presentará idiomas a los llamadores.</span><span class="sxs-lookup"><span data-stu-id="c096b-261">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="c096b-262">También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="c096b-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="c096b-263">Ver números de acceso telefónico de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="c096b-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="c096b-264">Ver números de acceso telefónico para conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c096b-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-265">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="c096b-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-266">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c096b-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="c096b-267">Aquí puede:</span><span class="sxs-lookup"><span data-stu-id="c096b-267">Here you can:</span></span>
    
  - <span data-ttu-id="c096b-268">Ver los números de teléfono que se configuran mediante Office 365 para utilizarse para conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="c096b-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="c096b-269">Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c096b-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="c096b-p122">También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c096b-p122">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="c096b-272">Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.</span><span class="sxs-lookup"><span data-stu-id="c096b-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="c096b-273">Vea [una lista de números de conferencia de Audio](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="c096b-274">Ver una lista de usuarios que están habilitados</span><span class="sxs-lookup"><span data-stu-id="c096b-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="c096b-275">Ver una lista de usuarios habilitados</span><span class="sxs-lookup"><span data-stu-id="c096b-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c096b-276">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c096b-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c096b-277">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**> y, a continuación, **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c096b-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="c096b-278">Vea [una lista de usuarios que están habilitados para conferencias de Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="c096b-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c096b-279">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c096b-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="c096b-280">Hay varias configuraciones que se pueden administrar en el nivel de organización mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c096b-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="c096b-281">Esto facilita la configuración se aplican a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c096b-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="c096b-282">Existen varias opciones que puede configurar en el nivel de la organización con Windows PowerShell. Esto facilita la configuración de estas opciones y las aplica a todos los usuarios. Estas son las opciones de configuración de nivel de organización:</span><span class="sxs-lookup"><span data-stu-id="c096b-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="c096b-283">Aquí está la configuración de nivel de organización:</span><span class="sxs-lookup"><span data-stu-id="c096b-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="c096b-284">**Establecimiento de notificaciones de entrada y salida** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="c096b-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="c096b-285">**Configuración de grabación de nombre** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="c096b-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="c096b-286">**Establecer la longitud del perno** El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="c096b-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="c096b-287">**Configuración de sólo marcado en reuniones desde el teléfono** El valor predeterminado _$false_.</span><span class="sxs-lookup"><span data-stu-id="c096b-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="c096b-288">**Si desea enviar correo electrónico a los usuarios establecer** El valor predeterminado es _$true_.</span><span class="sxs-lookup"><span data-stu-id="c096b-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="c096b-289">**Establecer si se va a enviar correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.</span><span class="sxs-lookup"><span data-stu-id="c096b-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="c096b-290">**Establecer la dirección de correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="c096b-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="c096b-291">**Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.</span><span class="sxs-lookup"><span data-stu-id="c096b-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c096b-292">Para obtener más información acerca de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c096b-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="c096b-293">Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no realizar.</span><span class="sxs-lookup"><span data-stu-id="c096b-293">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c096b-294">Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="c096b-294">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c096b-295">Para empezar a utilizar Windows PowerShell, consulte estos temas:</span><span class="sxs-lookup"><span data-stu-id="c096b-295">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="c096b-296">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="c096b-296">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="c096b-297">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="c096b-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c096b-298">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c096b-298">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="c096b-299">Obtenga información acerca de estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="c096b-299">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c096b-300">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c096b-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c096b-301">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c096b-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c096b-302">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c096b-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="c096b-p126">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="c096b-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c096b-305">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c096b-305">Related topics</span></span>

[<span data-ttu-id="c096b-306">Administrar la configuración de conferencia de Audio para un usuario</span><span class="sxs-lookup"><span data-stu-id="c096b-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="c096b-307">Configurar Audioconferencia para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c096b-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)


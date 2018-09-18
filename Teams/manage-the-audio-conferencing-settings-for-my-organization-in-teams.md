---
title: Administrar la configuración de Audioconferencia para mi organización en Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea los pasos que hay que seguir en Microsoft Teams para asignar una licencia de conferencia de acceso telefónico local y un Id. de conferencia a un usuario y muchas otras opciones de la conferencia de acceso telefónico local. '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884708"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="2963c-103">Administrar la configuración de Audioconferencia para mi organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2963c-103">If you want to manage these settings in Teams, see Manage the Audio Conferencing settings for my organization in Microsoft Teams.</span></span>

<span data-ttu-id="2963c-104">Puede que le resulte más sencillo ver todas las opciones de audioconferencias para Microsoft Teams en un mismo lugar.</span><span class="sxs-lookup"><span data-stu-id="2963c-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="2963c-105">Asignar una licencia de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2963c-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="2963c-106">No es posible asignar licencias con Teams.</span><span class="sxs-lookup"><span data-stu-id="2963c-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="2963c-107">Hay que usar el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2963c-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="2963c-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="2963c-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="2963c-109">**Para asignar una licencia a un usuario**</span><span class="sxs-lookup"><span data-stu-id="2963c-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="2963c-110">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="2963c-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2963c-111">En la navegación izquierda del **Centro de administración de Office 365**, vaya a **Usuarios** > **Usuarios activos** y a continuación seleccione el usuario o los usuarios en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2963c-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2963c-112">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista.</span><span class="sxs-lookup"><span data-stu-id="2963c-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="2963c-113">Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="2963c-114">En el panel de acciones, en **Product licenses** (Licencias de producto), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="2963c-p103">En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="2963c-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="2963c-p104">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="2963c-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="2963c-119">Habilitar o deshabilitar los correos electrónicos que se envían a usuarios de audioconferencias</span><span class="sxs-lookup"><span data-stu-id="2963c-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="2963c-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**</span><span class="sxs-lookup"><span data-stu-id="2963c-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="2963c-121">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2963c-122">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="2963c-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="2963c-123">En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="2963c-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="2963c-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-124">Click **Save**.</span></span>

    
<span data-ttu-id="2963c-125">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2963c-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="2963c-126">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2963c-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="2963c-127">Cambiar la información de contacto del remitente en los mensajes de correo electrónico que se envían a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2963c-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="2963c-128">Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, incluidos la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente.</span><span class="sxs-lookup"><span data-stu-id="2963c-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="2963c-129">De manera predeterminada, el remitente de los mensajes será Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2963c-129">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and theSet-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="2963c-130">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2963c-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="2963c-131">Restablecer el Id. de conferencia de reunión</span><span class="sxs-lookup"><span data-stu-id="2963c-131">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="2963c-132">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2963c-132">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="2963c-133">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-133">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="2963c-134">En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="2963c-135">En la ventana **¿desea restablecer el id. de conferencia?**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="2963c-135">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="2963c-136">El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo siempre que el envío de correos electrónicos a los usuarios esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="2963c-136">In the Reset conference ID? window, click Yes. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span> <span data-ttu-id="2963c-137">Está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2963c-137">It's enabled by default.</span></span>

<span data-ttu-id="2963c-138">Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2963c-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="2963c-139">Restablecer el PIN de un organizador de conferencia</span><span class="sxs-lookup"><span data-stu-id="2963c-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="2963c-140">Se asignará un id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="2963c-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="2963c-141">Aunque el Id. de conferencia se crea y se asigna automáticamente a un usuario, puede suceder que un usuario no quiera usar este Id. y quiera configurar un número concreto, o que los usuarios no lo recuerden o lo hayan perdido.</span><span class="sxs-lookup"><span data-stu-id="2963c-141">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

1. <span data-ttu-id="2963c-142">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2963c-142">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="2963c-143">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-143">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="2963c-144">En **Audioconferencia**, haga clic en **Restablecer PIN** y, a continuación, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="2963c-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
    
<span data-ttu-id="2963c-p108">Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="2963c-p108">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="2963c-149">Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2963c-149">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="2963c-150">Enviar un correo electrónico con la información de audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="2963c-150">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="2963c-151">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2963c-151">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="2963c-152">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-152">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="2963c-153">En **Audioconferencia**, haga clic en **Enviar información de conferencia por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="2963c-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2963c-154">Cuando hace esto, el PIN de audioconferencia no se envía al usuario.</span><span class="sxs-lookup"><span data-stu-id="2963c-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

  
<span data-ttu-id="2963c-155">Consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2963c-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="2963c-156">Establecer los números de teléfono incluidos en las invitaciones</span><span class="sxs-lookup"><span data-stu-id="2963c-156">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="2963c-157">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2963c-157">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="2963c-158">Junto a **Audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-158">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="2963c-159">En el panel **Audioconferencia**, puede establecer el **Número de pago** y, si está permitido, el **Número gratuito**.</span><span class="sxs-lookup"><span data-stu-id="2963c-159">In the Action pane, you can set the Toll number and, if allowed, the Toll-free number.</span></span>

4. <span data-ttu-id="2963c-160">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-160">Click **Save**.</span></span>
    
<span data-ttu-id="2963c-161">Consulte [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2963c-161">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="2963c-162">Elegir la configuración del puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2963c-162">Setting audio conferencing bridge settings</span></span>

<span data-ttu-id="2963c-163">**Establecer la experiencia de reunión cuando los autores de llamada se unen a una reunión**</span><span class="sxs-lookup"><span data-stu-id="2963c-163">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="2963c-164">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-164">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2963c-165">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="2963c-165">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="2963c-166">En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="2963c-166">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="2963c-167">Esta opción está habilitada de forma predeterminada,</span><span class="sxs-lookup"><span data-stu-id="2963c-167">CDR is enabled by default.</span></span> <span data-ttu-id="2963c-168">pero, si la deshabilita, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación de forma predeterminada cuando alguien entre en la reunión o la abandone.</span><span class="sxs-lookup"><span data-stu-id="2963c-168">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="2963c-169">En **Tipo de anuncios de entrada/salida**, elija **Tonos** o **Nombres o números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="2963c-169">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="2963c-170">Si elige **Nombres o números de teléfono**, también puede elegir si prefiere habilitar o deshabilitar **Pida a los autores de llamadas que registren su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="2963c-170">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="2963c-171">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-171">Click **Save**.</span></span>

    
<span data-ttu-id="2963c-172">El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="2963c-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="2963c-173">**Configurar la longitud del PIN para las reuniones**</span><span class="sxs-lookup"><span data-stu-id="2963c-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="2963c-174">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2963c-175">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="2963c-175">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="2963c-176">En **Seguridad**, introduzca el número de dígitos que quiere para el PIN en la lista **Longitud del PIN** y después haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-176">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="2963c-p110">El PIN debe ser un valor entre 4 y 12 dígitos. El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="2963c-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="2963c-179">El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="2963c-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="2963c-180">**Habilitar o deshabilitar que el correo electrónico se envíe a los usuarios de audioconferencias**</span><span class="sxs-lookup"><span data-stu-id="2963c-180">**Enable or disable email from being sent to audio users**</span></span>


1. <span data-ttu-id="2963c-181">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2963c-182">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="2963c-182">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="2963c-183">En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de audioconferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="2963c-184">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="2963c-185">También puede enviar un correo electrónico al usuario con la configuración de la audioconferencia. Para ello, tiene que ir a las propiedades de la audioconferencia para el usuario y hacer clic en **Enviar la información de conferencia por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="2963c-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="2963c-186">Si hace esto, se enviará un correo electrónico que incluye solo el Id. de conferencia y el número de teléfono de conferencia, pero no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="2963c-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="2963c-187">Consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2963c-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="2963c-188">Ver y establecer los idiomas principales (predeterminados) y secundarios (alternativos) en un puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2963c-188">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="2963c-189">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-189">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2963c-190">Seleccione un número de teléfono de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-190">Select a number from the list of phone numbers and click **Assign**.</span></span>

3. <span data-ttu-id="2963c-191">Elija los idiomas que quiere en **Idioma predeterminado** y en **Idiomas alternativos (opcionales)**.</span><span class="sxs-lookup"><span data-stu-id="2963c-191">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>


<span data-ttu-id="2963c-192">Consulte [Establecer los idiomas del operador automático para Audioconferencia](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2963c-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="2963c-193">Ver los números de acceso telefónico local de audioconferencias</span><span class="sxs-lookup"><span data-stu-id="2963c-193">See audio conferencing dial-in numbers</span></span>


1. <span data-ttu-id="2963c-194">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2963c-194">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2963c-195">Seleccione un número de teléfono de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2963c-195">Select a number from the list of phone numbers and click **Assign**.</span></span> <span data-ttu-id="2963c-196">Aquí puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2963c-196">Here you can:</span></span>
    
  - <span data-ttu-id="2963c-197">Ver los números de teléfono que establece Office 365 para usarlos con Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="2963c-197">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="2963c-198">Ver la ubicación y el idioma principal que usará el operador automático de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="2963c-198">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="2963c-199">Vea [Consultar una lista de números de Audioconferencia](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2963c-199">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2963c-200">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2963c-200">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="2963c-p112">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="2963c-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2963c-204">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="2963c-204">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2963c-205">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2963c-205">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="2963c-206">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="2963c-206">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="2963c-207">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2963c-207">Related topics</span></span>

[<span data-ttu-id="2963c-208">Administrar la configuración de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="2963c-208">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)



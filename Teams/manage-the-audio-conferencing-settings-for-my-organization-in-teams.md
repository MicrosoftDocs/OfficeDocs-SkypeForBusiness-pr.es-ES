---
title: Administrar la configuración de conferencia de Audio para su organización en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea los pasos que hay que seguir en Microsoft Teams para asignar una licencia de conferencia de acceso telefónico local y un Id. de conferencia a un usuario y muchas otras opciones de la conferencia de acceso telefónico local. '
ms.openlocfilehash: bc2f51cabe73db326c5a070f75d55c30fb1af367
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2018
ms.locfileid: "26283189"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="79e55-103">Administrar la configuración de conferencia de Audio para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79e55-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="79e55-104">Puede que le resulte más sencillo ver todas las opciones de audioconferencias para Microsoft Teams en un mismo lugar.</span><span class="sxs-lookup"><span data-stu-id="79e55-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="79e55-105">Asignar una licencia de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="79e55-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="79e55-106">No es posible asignar licencias con Teams.</span><span class="sxs-lookup"><span data-stu-id="79e55-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="79e55-107">Hay que usar el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="79e55-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="79e55-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="79e55-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="79e55-109">**Para asignar una licencia a un usuario**</span><span class="sxs-lookup"><span data-stu-id="79e55-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="79e55-110">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="79e55-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="79e55-111">En la navegación izquierda del **Centro de administración de Office 365**, vaya a **Usuarios** > **Usuarios activos** y a continuación seleccione el usuario o los usuarios en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="79e55-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79e55-112">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista.</span><span class="sxs-lookup"><span data-stu-id="79e55-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="79e55-113">Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="79e55-114">En el panel de acciones, en **Product licenses** (Licencias de producto), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="79e55-p103">En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="79e55-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="79e55-p104">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="79e55-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="79e55-119">Habilitar o deshabilitar los correos electrónicos que se envían a usuarios de audioconferencias</span><span class="sxs-lookup"><span data-stu-id="79e55-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="79e55-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**</span><span class="sxs-lookup"><span data-stu-id="79e55-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-121">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="79e55-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="79e55-122">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="79e55-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="79e55-123">En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="79e55-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="79e55-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-124">Click **Save**.</span></span>

    
<span data-ttu-id="79e55-125">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="79e55-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="79e55-126">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79e55-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="79e55-127">Restablecer el id. de conferencia de reunión</span><span class="sxs-lookup"><span data-stu-id="79e55-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="79e55-128">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="79e55-128">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-129">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="79e55-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="79e55-130">En **Conferencias de Audio**, haga clic en **Restablecer el identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="79e55-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="79e55-131">En la **Restablecer el identificador de conferencia?** ventana, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="79e55-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="79e55-132">Se creará automáticamente un identificador de conferencia y un correo electrónico enviado al usuario con el nuevo identificador de conferencia si está habilitado el envío de correo electrónico a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="79e55-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="79e55-133">Está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="79e55-133">It's enabled by default.</span></span>

<span data-ttu-id="79e55-134">Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="79e55-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="79e55-135">Restablecer el PIN del organizador de una conferencia</span><span class="sxs-lookup"><span data-stu-id="79e55-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="79e55-136">Se asignará un Id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="79e55-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="79e55-137">Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar este y que desea establecer para un cierto número, o los usuarios no pueden recordar o han perdido su identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="79e55-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="79e55-138">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="79e55-138">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-139">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="79e55-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="79e55-140">En **Conferencias de Audio**, haga clic en **Restablecer PIN**y, a continuación, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="79e55-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="79e55-p107">Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="79e55-p107">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="79e55-145">Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="79e55-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="79e55-146">Send an email with Audio Conferencing information to a user</span><span class="sxs-lookup"><span data-stu-id="79e55-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="79e55-147">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="79e55-147">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-148">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="79e55-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="79e55-149">En **Conferencias de Audio**, haga clic en **Enviar información de conferencia en el correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="79e55-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="79e55-150">Cuando hace esto, el PIN de audioconferencia no se envía al usuario.</span><span class="sxs-lookup"><span data-stu-id="79e55-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="79e55-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="79e55-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="79e55-152">Establecer los números de teléfono incluidos en las invitaciones</span><span class="sxs-lookup"><span data-stu-id="79e55-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="79e55-153">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="79e55-153">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-154">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="79e55-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="79e55-155">Junto a **Conferencias de Audio**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="79e55-156">En el panel de **Conferencia de Audio** , puede establecer el **número de teléfono de pago** y, si se permite, el **número de teléfono gratuito**.</span><span class="sxs-lookup"><span data-stu-id="79e55-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="79e55-157">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-157">Click **Save**.</span></span>
    
<span data-ttu-id="79e55-158">Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="79e55-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="79e55-159">Elija Configuración de puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="79e55-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="79e55-160">**Set the meeting experience when callers join a meeting**</span><span class="sxs-lookup"><span data-stu-id="79e55-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="79e55-161">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="79e55-161">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-162">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="79e55-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="79e55-163">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="79e55-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="79e55-164">En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="79e55-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="79e55-165">Esto está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="79e55-165">This is enabled by default.</span></span> <span data-ttu-id="79e55-166">Si deshabilita esta opción, no se le notificará a los usuarios que ya se han unido a la reunión de forma predeterminada cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="79e55-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="79e55-167">En **tipo de anuncio de entrada o salida**, elija **tonos** o **nombres o números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="79e55-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="79e55-168">Si elige **los nombres o números de teléfono**, también puede elegir habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="79e55-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="79e55-169">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-169">Click **Save**.</span></span>

    
<span data-ttu-id="79e55-170">Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="79e55-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="79e55-171">**Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="79e55-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="79e55-172">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="79e55-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="79e55-173">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="79e55-173">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="79e55-174">En el panel **configuración de puente** , escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-174">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="79e55-p109">El PIN debe tener entre 4 y 12 dígitos. El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="79e55-p109">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="79e55-177">El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="79e55-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="79e55-178">**Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="79e55-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="79e55-179">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="79e55-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="79e55-180">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="79e55-180">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="79e55-181">En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.</span><span class="sxs-lookup"><span data-stu-id="79e55-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="79e55-182">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="79e55-183">También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, vaya a las propiedades del usuario conferencias de audio y haciendo clic en **Enviar información de conferencia en el correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="79e55-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="79e55-184">Si hace esto, se enviará un correo electrónico que incluye solo el Id. de conferencia y el número de teléfono de conferencia, pero no se incluirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="79e55-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="79e55-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="79e55-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="79e55-186">Vea y establezca la primaria (valor predeterminado) y los idiomas (alternativos) secundarios en un puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="79e55-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="79e55-187">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="79e55-187">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-188">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="79e55-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="79e55-189">Seleccione un número de teléfono de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-189">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="79e55-190">Elija los idiomas que desee en **idioma predeterminado** e **idiomas alternativos (opcionales)**.</span><span class="sxs-lookup"><span data-stu-id="79e55-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="79e55-191">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-191">Click **Save**.</span></span>


<span data-ttu-id="79e55-192">También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="79e55-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="79e55-193">See audio conferencing dial-in numbers</span><span class="sxs-lookup"><span data-stu-id="79e55-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="79e55-194">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="79e55-194">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="79e55-195">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="79e55-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="79e55-196">Seleccione un número de teléfono de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79e55-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="79e55-197">Here you can:</span><span class="sxs-lookup"><span data-stu-id="79e55-197">Here you can:</span></span>
    
   - <span data-ttu-id="79e55-198">Vea los números de teléfono que ha establecido Office 365 para utilizar para Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="79e55-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="79e55-199">Ver la ubicación y el idioma principal, que se utilizará en el operador automático de conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="79e55-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="79e55-200">Vea [una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="79e55-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="79e55-201">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="79e55-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="79e55-p111">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="79e55-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="79e55-205">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="79e55-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="79e55-206">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79e55-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="79e55-207">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="79e55-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="79e55-208">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="79e55-208">Related topics</span></span>

[<span data-ttu-id="79e55-209">Administrar la configuración de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="79e55-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)



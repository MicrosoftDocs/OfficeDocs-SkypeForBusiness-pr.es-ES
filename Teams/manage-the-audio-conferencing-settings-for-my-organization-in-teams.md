---
title: Administrar la configuración de audioconferencia
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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Consulte Pasos de Microsoft Teams para asignar una licencia de conferencia de acceso telefónico local y un id. de conferencia a un usuario y muchas otras opciones de configuración de conferencias de acceso telefónico local. '
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101096"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="47251-103">Administrar la configuración de Audioconferencia para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47251-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="47251-104">Es posible que le resulte más fácil ver todas las opciones de configuración de audioconferencia para Microsoft Teams en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="47251-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="47251-105">Asignar una licencia de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="47251-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="47251-106">No puede asignar licencias con Teams.</span><span class="sxs-lookup"><span data-stu-id="47251-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="47251-107">Debe usar el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="47251-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="47251-108">Vea [Asignar licencias de complementos de Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="47251-108">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> 
  
 <span data-ttu-id="47251-109">**To assign a license for a user**</span><span class="sxs-lookup"><span data-stu-id="47251-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="47251-110">Inicie sesión en Microsoft 365 con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="47251-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="47251-111">En la navegación izquierda del Centro de administración de **Microsoft 365,** vaya a Usuarios usuarios activos y, a continuación, seleccione el usuario o los usuarios de la lista de  >  usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="47251-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47251-112">Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista.</span><span class="sxs-lookup"><span data-stu-id="47251-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="47251-113">Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="47251-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="47251-114">En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47251-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="47251-115">En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47251-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="47251-116">Para obtener más información sobre las licencias, vea [Licencias de complementos de Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="47251-116">For more on licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="47251-117">Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="47251-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="47251-118">Si esto sucede, cierre sesión en el centro de administración o presione CTRL+F5 para actualizar la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="47251-118">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="47251-119">Enable or disable emails sent to audio conferencing users</span><span class="sxs-lookup"><span data-stu-id="47251-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="47251-120">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="47251-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-121">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="47251-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="47251-122">En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**</span><span class="sxs-lookup"><span data-stu-id="47251-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="47251-123">En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambia la configuración **de acceso telefónico.**</span><span class="sxs-lookup"><span data-stu-id="47251-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="47251-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47251-124">Click **Save**.</span></span>

    
<span data-ttu-id="47251-125">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="47251-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="47251-126">Vea la [referencia de PowerShell de Microsoft Teams](/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="47251-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="47251-127">Reset the meeting conference ID</span><span class="sxs-lookup"><span data-stu-id="47251-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="47251-128">![Icono que muestra el logotipo de Teams ](media/teams-logo-30x30.png) **Con el Centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="47251-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-129">En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="47251-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="47251-130">En **Audioconferencia, haga** clic **en Restablecer id. de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="47251-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="47251-131">En la ventana **¿Restablecer id. de conferencia?,** haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="47251-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="47251-132">Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia si el envío de correo electrónico a los usuarios está habilitado.</span><span class="sxs-lookup"><span data-stu-id="47251-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="47251-133">Está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47251-133">It's enabled by default.</span></span>

<span data-ttu-id="47251-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="47251-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="47251-135">Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="47251-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="47251-136">Se asignará un id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="47251-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="47251-137">Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o los usuarios no puedan recordar o haber perdido su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="47251-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="47251-138">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="47251-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-139">En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="47251-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="47251-140">En **Audioconferencia,** haga clic **en Restablecer PIN** y, a continuación, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="47251-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="47251-p107">Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="47251-p107">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="47251-145">Vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="47251-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="47251-146">Send an email with Audio Conferencing information to a user</span><span class="sxs-lookup"><span data-stu-id="47251-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="47251-147">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="47251-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-148">En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="47251-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="47251-149">En **Audioconferencia,** haga clic **en Enviar información de conferencia por correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="47251-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="47251-150">When you do this, the audio conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="47251-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="47251-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="47251-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="47251-152">Establecer los números de teléfono incluidos en las invitaciones</span><span class="sxs-lookup"><span data-stu-id="47251-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="47251-153">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="47251-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-154">En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="47251-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="47251-155">Junto a **Audioconferencia,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="47251-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="47251-156">En el **panel Audioconferencia,** puede  establecer el número de pago y, si se permite, el **número gratuito**.</span><span class="sxs-lookup"><span data-stu-id="47251-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="47251-157">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47251-157">Click **Save**.</span></span>
    
<span data-ttu-id="47251-158">Vea [Establecer los números de teléfono incluidos en las invitaciones.](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="47251-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="47251-159">Elegir la configuración del puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="47251-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="47251-160">**Set the meeting experience when callers join a meeting**</span><span class="sxs-lookup"><span data-stu-id="47251-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="47251-161">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="47251-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-162">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="47251-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="47251-163">En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**</span><span class="sxs-lookup"><span data-stu-id="47251-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="47251-164">En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="47251-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="47251-165">Esta opción está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47251-165">This is enabled by default.</span></span> <span data-ttu-id="47251-166">Si deshabilita esta opción, los usuarios que ya se han unido a la reunión de forma predeterminada no se les notificará cuando alguien entre o abandone la reunión.</span><span class="sxs-lookup"><span data-stu-id="47251-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="47251-167">En **Tipo de anuncio de entrada o salida,** elija **Tonos** o Nombres o números **de teléfono.**</span><span class="sxs-lookup"><span data-stu-id="47251-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="47251-168">Si elige **Nombres o números de teléfono,** también puede habilitar o deshabilitar Pedir a los autores de llamadas que graben su nombre antes de **unirse a la reunión.**</span><span class="sxs-lookup"><span data-stu-id="47251-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="47251-169">De forma predeterminada, los participantes externos no pueden ver los números de teléfono de los participantes marcados.</span><span class="sxs-lookup"><span data-stu-id="47251-169">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="47251-170">Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** de **entrada/salida tipo de anuncio** (esto evita que los Teams lean los números).</span><span class="sxs-lookup"><span data-stu-id="47251-170">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>


5. <span data-ttu-id="47251-171">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47251-171">Click **Save**.</span></span>

    
<span data-ttu-id="47251-172">Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="47251-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="47251-173">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="47251-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="47251-174">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="47251-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="47251-175">En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**</span><span class="sxs-lookup"><span data-stu-id="47251-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="47251-176">En el **panel Configuración de puente,** escriba el número de dígitos que desea para el PIN en la lista Longitud del **PIN** y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="47251-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="47251-p110">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="47251-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="47251-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="47251-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="47251-180">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="47251-180">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="47251-181">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="47251-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="47251-182">En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**</span><span class="sxs-lookup"><span data-stu-id="47251-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="47251-183">En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambian sus opciones de **audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="47251-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="47251-184">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47251-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="47251-185">También puede enviar correo electrónico al usuario con la configuración de audioconferencia, yendo a las propiedades de audioconferencia del usuario y haciendo clic en Enviar información de conferencia **por correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="47251-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="47251-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="47251-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="47251-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="47251-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="47251-188">Ver y establecer los idiomas principal (predeterminado) y secundario (alternativo) en un puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="47251-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="47251-189">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="47251-189">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-190">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="47251-190">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="47251-191">Seleccione un número de teléfono de la lista y haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="47251-191">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="47251-192">Elija los idiomas que desee en **Idioma predeterminado** e **Idiomas alternativos (opcional).**</span><span class="sxs-lookup"><span data-stu-id="47251-192">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="47251-193">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47251-193">Click **Save**.</span></span>


<span data-ttu-id="47251-194">También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="47251-194">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="47251-195">See audio conferencing dial-in numbers</span><span class="sxs-lookup"><span data-stu-id="47251-195">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="47251-196">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="47251-196">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="47251-197">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="47251-197">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="47251-198">Seleccione un número de teléfono de la lista y haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="47251-198">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="47251-199">Here you can:</span><span class="sxs-lookup"><span data-stu-id="47251-199">Here you can:</span></span>
    
   - <span data-ttu-id="47251-200">Vea los números de teléfono que se van a usar para las audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="47251-200">View the phone numbers that are to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="47251-201">Vea la ubicación y el idioma principal que usará el operador automático de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="47251-201">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="47251-202">Vea [Ver una lista de números de audioconferencia.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="47251-202">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="47251-203">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="47251-203">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="47251-204">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="47251-204">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="47251-205">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="47251-205">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="47251-206">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="47251-206">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="47251-207">Por qué necesita usar Microsoft 365 u Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="47251-207">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="47251-208">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="47251-208">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="47251-209">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="47251-209">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="47251-210">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="47251-210">Related topics</span></span>

[<span data-ttu-id="47251-211">Administrar la configuración de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="47251-211">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
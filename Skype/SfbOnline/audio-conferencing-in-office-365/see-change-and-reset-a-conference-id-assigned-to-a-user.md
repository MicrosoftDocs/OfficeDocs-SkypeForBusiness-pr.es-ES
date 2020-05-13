---
title: Ver, cambiar y restablecer un identificador de conferencia asignado a un usuario en Skype empresarial online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Obtenga información sobre cómo asignar un identificador de conferencia a un usuario en Skype empresarial online y cuáles deben ser los parámetros de IDs de conferencia. '
ms.openlocfilehash: caa94984b06ff73d8f14acf4727870a988298974
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163919"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="bfc91-103">Ver y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bfc91-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="bfc91-104">Para obtener información acerca de los identificadores de conferencia de usuario en Microsoft Teams, consulte [ver y restablecer un ID de conferencia asignado a un usuario en Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="bfc91-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="bfc91-p101">Un identificador de conferencia se asigna automáticamente a un usuario de Skype empresarial cuando está configurado para conferencias de audio en Microsoft 365 u Office 365 y usa Microsoft como proveedor de servicios de audioconferencia. El identificador de conferencia asignado se envía en la invitación a la reunión cuando la reunión está programada. A cada una de las reuniones que una programación de usuario obtiene se les asigna un identificador de conferencia único.</span><span class="sxs-lookup"><span data-stu-id="bfc91-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="bfc91-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="bfc91-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="bfc91-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bfc91-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="bfc91-112">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="bfc91-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="bfc91-113">Para ver el identificador de conferencia</span><span class="sxs-lookup"><span data-stu-id="bfc91-113">To view the conference ID</span></span>

<span data-ttu-id="bfc91-114">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="bfc91-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="bfc91-115">Puede ver el Id. de conferencia y enviárselo a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bfc91-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="bfc91-116">Inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bfc91-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="bfc91-117">Vaya al centro de administración > **Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfc91-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="bfc91-118">En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, seleccione el usuario que necesita el Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bfc91-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="bfc91-119">En la página Acción, busque en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bfc91-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="bfc91-120">Puede enviar toda la información de la Conferencia al usuario en un correo electrónico que incluya el identificador de la Conferencia y los números de teléfono de audio haciendo clic en el vínculo **enviar información de conferencia por correo electrónico** después de seleccionar al usuario en la página **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="bfc91-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="bfc91-121">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="bfc91-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="bfc91-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="bfc91-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="bfc91-124">Para obtener más información sobre el cmdlet [, vea Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) .</span><span class="sxs-lookup"><span data-stu-id="bfc91-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="bfc91-125">Para restablecer el identificador de conferencia</span><span class="sxs-lookup"><span data-stu-id="bfc91-125">To reset the conference ID</span></span>

<span data-ttu-id="bfc91-126">Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.</span><span class="sxs-lookup"><span data-stu-id="bfc91-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="bfc91-127">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="bfc91-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="bfc91-128">Inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bfc91-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="bfc91-129">Vaya al centro de administración > **Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfc91-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="bfc91-130">En el **Centro**> de administración de Skype empresarial,**los usuarios**de la**Conferencia** > de audio, en el panel de acciones, en **ID de conferencia**, haga clic en **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="bfc91-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="bfc91-131">En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bfc91-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="bfc91-132">Se creará automáticamente un ID de conferencia y un mensaje de correo electrónico con el nuevo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bfc91-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="bfc91-133">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="bfc91-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="bfc91-134">Puede restablecer el id. de conferencia de un usuario mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfc91-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="bfc91-135">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfc91-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="bfc91-136">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="bfc91-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="bfc91-137">Una vez que se crea un nuevo identificador de conferencia o se restablece uno, la persona que llama no puede usar el antiguo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bfc91-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="bfc91-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="bfc91-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="bfc91-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="bfc91-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="bfc91-140">Para ver cómo descargar, instalar y ejecutar la herramienta, consulte la herramienta [de actualización de reuniones para Skype empresarial y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype empresarial online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)y [Skype empresarial online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="bfc91-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="bfc91-141">Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="bfc91-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="bfc91-142">El identificador de conferencia debe cumplir la longitud en dígitos establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="bfc91-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="bfc91-143">No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.</span><span class="sxs-lookup"><span data-stu-id="bfc91-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="bfc91-144">El identificador de conferencia de todos los usuarios de la audioconferencia será de 7 dígitos de forma predeterminada, y no se podrá cambiar el número de dígitos.</span><span class="sxs-lookup"><span data-stu-id="bfc91-144">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bfc91-145">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bfc91-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bfc91-146">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bfc91-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bfc91-147">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="bfc91-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bfc91-148">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bfc91-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="bfc91-149">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bfc91-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="bfc91-150">¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bfc91-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="bfc91-151">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bfc91-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bfc91-152">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="bfc91-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="bfc91-153">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfc91-153">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="bfc91-154">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bfc91-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="bfc91-155">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bfc91-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="bfc91-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bfc91-156">Related topics</span></span>

[<span data-ttu-id="bfc91-157">Probar o comprar audioconferencia en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="bfc91-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


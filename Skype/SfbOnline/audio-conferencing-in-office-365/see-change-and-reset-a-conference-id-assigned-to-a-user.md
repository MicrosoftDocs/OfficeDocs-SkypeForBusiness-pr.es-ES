---
title: Ver, modificar y restablecer un identificador de conferencia asignado a un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: eccbcd31add14026d2b5f3a57348ae5d6f1db2a5
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703408"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="f4940-103">Ver y restablecer un identificador de conferencia asignado a un usuario</span><span class="sxs-lookup"><span data-stu-id="f4940-103">View and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="f4940-104">Un identificador de conferencia se asigna automáticamente a un Skype para usuario empresarial o Teams de Microsoft cuando se configuran para conferencias de Audio en Office 365 y usar Microsoft como el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="f4940-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="f4940-105">El identificador de conferencia asignado se envía en la invitación a la reunión cuando la reunión está programada.</span><span class="sxs-lookup"><span data-stu-id="f4940-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="f4940-106">Cada reunión que un usuario programa obtener asignará un identificador de conferencia único.</span><span class="sxs-lookup"><span data-stu-id="f4940-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="f4940-107">Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea usar este uno y que desea establecer para un cierto número, o cuando los usuarios no pueden recordar o que han perdido su identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f4940-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="f4940-108">Puede usar el **Skype para el centro de administración de negocio** y Windows PowerShell para ver, cambiar y restablecer su identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f4940-108">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="f4940-109">Se enviará un correo electrónico al usuario con el identificador de conferencia y los números de teléfono de conferencia de audio predeterminada o, si restablece el identificador de conferencia se van a enviar un correo electrónico de diferente que incluirá el identificador de conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="f4940-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="f4940-110">Para obtener más información acerca de cómo restablecer el PIN del organizador de la conferencia, [haga clic aquí](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="f4940-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="f4940-111">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="f4940-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="f4940-112">Para ver el identificador de conferencia</span><span class="sxs-lookup"><span data-stu-id="f4940-112">To view the conference ID</span></span>

<span data-ttu-id="f4940-113">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="f4940-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="f4940-114">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="f4940-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f4940-115">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f4940-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f4940-116">En las **Conferencias de Audio**, mire en el **Identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="f4940-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f4940-117">Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y los números de teléfono de audio, haga clic en el vínculo **Enviar información de conferencia en el correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="f4940-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="f4940-118">Puede usar Windows PowerShell para ver el identificador de conferencia para un usuario.</span><span class="sxs-lookup"><span data-stu-id="f4940-118">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="f4940-119">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f4940-119">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


<span data-ttu-id="f4940-120">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="f4940-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="f4940-121">Puede ver su identificador de conferencia y enviar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f4940-121">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="f4940-122">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="f4940-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f4940-123">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="f4940-123">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f4940-124">En el **Skype para el centro de administración de negocio**> **conferencias de Audio** > **a los usuarios**, seleccione el usuario que necesita identificador de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="f4940-124">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="f4940-125">En la página acción, mire en el **Identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="f4940-125">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f4940-126">Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y los números de teléfono de audio, haga clic en el vínculo **Enviar información de conferencia a través de correo electrónico** después de seleccionar el usuario en la página **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="f4940-126">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="f4940-127">Puede usar Windows PowerShell para ver el identificador de conferencia para un usuario.</span><span class="sxs-lookup"><span data-stu-id="f4940-127">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="f4940-128">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f4940-128">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="f4940-129">Para restablecer el identificador de conferencia</span><span class="sxs-lookup"><span data-stu-id="f4940-129">To reset the conference ID</span></span>

<span data-ttu-id="f4940-130">Puede restablecer un identificador de conferencia para un usuario si, por ejemplo, si olvida.</span><span class="sxs-lookup"><span data-stu-id="f4940-130">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
<span data-ttu-id="f4940-131">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="f4940-131">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="f4940-132">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="f4940-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f4940-133">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f4940-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f4940-134">En **Conferencias de Audio**, haga clic en **Restablecer el identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="f4940-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="f4940-135">En la ventana **Restablecer Id. de conferencia** , haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="f4940-135">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="f4940-136">Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f4940-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="f4940-137">Puede restablecer el identificador de conferencia para un usuario mediante el uso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4940-137">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="f4940-138">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f4940-138">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

<span data-ttu-id="f4940-139">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="f4940-139">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="f4940-140">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="f4940-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f4940-141">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="f4940-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f4940-142">En el **Skype para el centro de administración de negocio**> **conferencias de Audio** > **a los usuarios**, en el panel de acciones en **Identificador de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="f4940-142">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="f4940-143">En la **Restablecer el identificador de conferencia?** ventana, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f4940-143">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="f4940-144">Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f4940-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="f4940-145">Puede restablecer el identificador de conferencia para un usuario mediante el uso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4940-145">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="f4940-146">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f4940-146">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="f4940-147">¿Qué más tengo que saber?</span><span class="sxs-lookup"><span data-stu-id="f4940-147">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="f4940-148">Una vez que se crea un nuevo identificador de conferencia o uno se restablece, no se puede usar el identificador de conferencia antigua por los autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f4940-148">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f4940-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="f4940-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="f4940-150">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="f4940-150">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="f4940-151">Para ver cómo descargar, instalar y ejecutar la herramienta, vea: [Herramienta de actualización de la reunión de Skype para empresas y Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para Online de negocio, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para Online de negocio, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="f4940-151">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="f4940-152">Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="f4940-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="f4940-153">El identificador de conferencia debe cumplir la longitud en dígitos establecer en el puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="f4940-153">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="f4940-154">No se puede usar caracteres especiales o alfabéticos en conferencia identificadores; se pueden usar solo números.</span><span class="sxs-lookup"><span data-stu-id="f4940-154">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="f4940-155">El identificador de conferencia para todos los usuarios de conferencia de audio será 7 dígitos de forma predeterminada y no se puede cambiar el número de dígitos.</span><span class="sxs-lookup"><span data-stu-id="f4940-155">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f4940-156">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f4940-156">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f4940-p112">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="f4940-p112">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f4940-160">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f4940-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f4940-161">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="f4940-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f4940-p113">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f4940-p113">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f4940-164">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4940-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f4940-165">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f4940-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f4940-166">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f4940-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f4940-167">See also</span><span class="sxs-lookup"><span data-stu-id="f4940-167">Related topics</span></span>

[<span data-ttu-id="f4940-168">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="f4940-168">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


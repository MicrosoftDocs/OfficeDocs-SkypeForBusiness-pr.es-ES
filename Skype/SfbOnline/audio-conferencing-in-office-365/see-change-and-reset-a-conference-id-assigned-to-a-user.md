---
title: Ver, cambiar y restablecer un id. de conferencia asignado a un usuario en Skype Empresarial Online
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
description: 'Obtenga información sobre cómo asignar un id. de conferencia a un usuario en Skype Empresarial Online y cuáles deben ser los parámetros de id. de conferencia. '
ms.openlocfilehash: f12982298903485d93582fae3a4f39aaed49170c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237056"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="fab79-103">Ver y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fab79-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="fab79-104">Para obtener información sobre los identificadores de conferencia de usuario en Microsoft Teams, vea Ver y restablecer un [id.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)de conferencia asignado a un usuario en Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="fab79-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="fab79-105">Un id. de conferencia se asigna automáticamente Skype Empresarial un usuario de Skype Empresarial cuando se configura para conferencias de audio en Microsoft 365 o Office 365 y usa Microsoft como proveedor de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="fab79-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="fab79-106">El id. de conferencia asignado se envía en la invitación a la reunión cuando se programa la reunión.</span><span class="sxs-lookup"><span data-stu-id="fab79-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="fab79-107">Se asignará un Id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="fab79-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="fab79-108">Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o cuando los usuarios no puedan recordar o haber perdido su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fab79-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="fab79-109">Puede usar el centro **Skype Empresarial administración** y Windows PowerShell para ver, cambiar y restablecer su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fab79-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="fab79-110">Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="fab79-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="fab79-111">Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="fab79-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="fab79-112">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="fab79-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="fab79-113">Para ver el id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="fab79-113">To view the conference ID</span></span>

<span data-ttu-id="fab79-114">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="fab79-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="fab79-115">Puede ver el Id. de conferencia y enviárselo a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fab79-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="fab79-116">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="fab79-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="fab79-117">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="fab79-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fab79-118">En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, seleccione el usuario que necesita el Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fab79-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="fab79-119">En la página Acción, busque en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="fab79-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fab79-120">Puede enviar toda la información de conferencia al usuario en un correo electrónico que  incluya el id. de conferencia y  los números de teléfono de audio haciendo clic en el vínculo Enviar información de conferencia por correo electrónico después de seleccionar el usuario en la página Usuarios.</span><span class="sxs-lookup"><span data-stu-id="fab79-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="fab79-121">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="fab79-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="fab79-122">Puede usar Windows PowerShell para ver el Id. de conferencia para un usuario.</span><span class="sxs-lookup"><span data-stu-id="fab79-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="fab79-123">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="fab79-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="fab79-124">Vea [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) para obtener más información sobre el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fab79-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="fab79-125">Para restablecer el id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="fab79-125">To reset the conference ID</span></span>

<span data-ttu-id="fab79-126">Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.</span><span class="sxs-lookup"><span data-stu-id="fab79-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="fab79-127">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="fab79-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="fab79-128">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="fab79-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="fab79-129">Vaya al centro de administración > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="fab79-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fab79-130">En el **Skype Empresarial usuarios de** >  **audioconferencia** del centro de administración , en el panel de acciones en Id. de  >  conferencia, haga clic en **Restablecer**. </span><span class="sxs-lookup"><span data-stu-id="fab79-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="fab79-131">En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fab79-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="fab79-132">Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fab79-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="fab79-133">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="fab79-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="fab79-134">Puede restablecer el id. de conferencia de un usuario mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fab79-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="fab79-135">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="fab79-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="fab79-136">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="fab79-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="fab79-137">Después de crear un id. de conferencia nuevo o restablecer uno, los autores de la llamada no pueden usar el id. de conferencia antiguo.</span><span class="sxs-lookup"><span data-stu-id="fab79-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="fab79-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="fab79-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="fab79-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="fab79-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="fab79-140">Para ver cómo descargar, instalar y ejecutar la herramienta, vea: Herramienta de actualización de reuniones para [Skype Empresarial](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)y Lync , Skype Empresarial Online, Herramienta de migración de reuniones [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)y Skype Empresarial Online, Herramienta de migración de reuniones [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="fab79-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="fab79-141">Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="fab79-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="fab79-142">El id. de conferencia debe cumplir la longitud de los dígitos establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="fab79-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="fab79-143">No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.</span><span class="sxs-lookup"><span data-stu-id="fab79-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="fab79-144">El id. de conferencia de todos los usuarios de audioconferencia será de 9 dígitos de forma predeterminada y el número de dígitos no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="fab79-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fab79-145">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="fab79-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="fab79-146">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fab79-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fab79-147">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="fab79-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="fab79-148">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="fab79-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="fab79-149">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="fab79-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="fab79-150">¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="fab79-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="fab79-151">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="fab79-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="fab79-152">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="fab79-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="fab79-153">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="fab79-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="fab79-154">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="fab79-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="fab79-155">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="fab79-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="fab79-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fab79-156">Related topics</span></span>

[<span data-ttu-id="fab79-157">Pruebe o compre Audioconferencia en Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="fab79-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

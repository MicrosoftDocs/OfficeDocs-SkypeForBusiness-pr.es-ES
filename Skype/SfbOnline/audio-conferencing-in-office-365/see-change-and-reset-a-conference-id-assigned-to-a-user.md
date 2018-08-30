---
title: Ver, modificar y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a asignar un Id. de conferencia a un usuario de Skype for Business Online y cuáles deben ser los parámetros de los identificadores de conferencia. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252312"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="02d29-103">Ver y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="02d29-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="02d29-104">Para obtener información acerca de los identificadores de conferencia de usuario en equipos de Microsoft, consulte [Ver y restablecer un Id. de conferencia asignado a un usuario de Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="02d29-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="02d29-105">Se asigna automáticamente un Id. de conferencia a un usuario de Skype for Business cuando está configurado para audioconferencias en Office 365 y utiliza Microsoft como proveedor de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="02d29-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="02d29-106">El Id. de conferencia asignado se envía en la invitación a la reunión cuando se programa esta última.</span><span class="sxs-lookup"><span data-stu-id="02d29-106">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="02d29-107">Se asignará un Id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="02d29-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="02d29-108">Aunque se creará y asignará a un usuario automáticamente un Id. de conferencia estático, en ocasiones es posible que un usuario no desee utilizarlo y se desee establecerlo en un número determinado, o bien que los usuarios hayan olvidado o perdido su Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="02d29-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="02d29-109">Puede utilizar el **centro de administración de Skype for Business** y Windows PowerShell para ver, cambiar y restablecer su Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="02d29-109">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="02d29-110">Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="02d29-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="02d29-111">Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="02d29-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="02d29-112">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="02d29-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="02d29-113">Para ver el Id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="02d29-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="02d29-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando el centro de administración de Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="02d29-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="02d29-115">Puede ver el Id. de conferencia y enviárselo a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="02d29-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="02d29-116">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="02d29-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="02d29-117">Vaya a **Centro de administración de Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="02d29-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="02d29-118">En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, seleccione el usuario que necesita el Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="02d29-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="02d29-119">En la página Acción, busque en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="02d29-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="02d29-120">Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de audio haciendo clic en el enlace **Enviar información de la conferencia por correo electrónico** después de seleccionar el usuario en la página **Usuarios** .</span><span class="sxs-lookup"><span data-stu-id="02d29-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="02d29-121">**Usar Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="02d29-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="02d29-122">Puede usar Windows PowerShell para ver el Id. de conferencia para un usuario.</span><span class="sxs-lookup"><span data-stu-id="02d29-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="02d29-123">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="02d29-123">To do so:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="02d29-124">Para restablecer el Id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="02d29-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="02d29-125">Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.</span><span class="sxs-lookup"><span data-stu-id="02d29-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="02d29-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando el centro de administración de Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="02d29-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="02d29-127">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="02d29-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="02d29-128">Vaya a **Centro de administración de Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="02d29-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="02d29-129">En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, en el panel Acción en **Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="02d29-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="02d29-130">En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="02d29-130">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="02d29-131">Se creará automáticamente un Id. de conferencia y se enviará un correo electrónico al usuario con el nuevo Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="02d29-131">In the Reset conference ID? window, click Yes. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

<span data-ttu-id="02d29-132">**Usar Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="02d29-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="02d29-133">Puede restablecer el Id. de conferencia de un usuario mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02d29-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="02d29-134">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="02d29-134">To do this run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="02d29-135">¿Qué más tengo que saber?</span><span class="sxs-lookup"><span data-stu-id="02d29-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="02d29-136">Tras la creación de un nuevo Id. de conferencia o tras restablecer uno, las personas que llaman ya no pueden utilizar el Id. de conferencia anterior.</span><span class="sxs-lookup"><span data-stu-id="02d29-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="02d29-137">Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="02d29-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="02d29-138">Los usuarios pueden utilizar la herramienta de migración de Skype for Business para actualizar sus reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="02d29-138">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="02d29-139">Para ver cómo descargar, instalar y ejecutar la herramienta, vea: [Herramienta de actualización de reunión de Skype for Business y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, herramienta de migración de reunión (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047) y [Skype for Business Online, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="02d29-139">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

- <span data-ttu-id="02d29-140">Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="02d29-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="02d29-141">El Id. de conferencia tiene que cumplir con los requisitos de longitud de dígitos configurados en el puente de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="02d29-141">The conference ID must meet the length in digits set on the dial-in conferencing bridge. You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span> <span data-ttu-id="02d29-142">No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.</span><span class="sxs-lookup"><span data-stu-id="02d29-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="02d29-143">El Id. de conferencia de todos los usuarios de conferencia de audioconferencia será de siete dígitos de manera predeterminada, y el número de dígitos no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="02d29-143">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="02d29-144">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="02d29-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="02d29-p109">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="02d29-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="02d29-148">Una introducción a Windows PowerShell y Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="02d29-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="02d29-149">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="02d29-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="02d29-p110">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="02d29-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="02d29-152">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02d29-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="02d29-153">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="02d29-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="02d29-154">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="02d29-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="02d29-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="02d29-155">Related topics</span></span>

[<span data-ttu-id="02d29-156">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="02d29-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


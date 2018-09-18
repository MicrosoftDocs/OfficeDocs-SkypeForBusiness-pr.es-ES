---
title: Consultar, cambiar y restablecer un Id. de conferencia asignado a un usuario en Microsoft Teams
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a asignar un Id. de conferencia a un usuario en Microsoft Teams y cuáles deben ser los parámetros del Id. de conferencia. '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892036"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="28d6e-103">Ver y restablecer un Id. de conferencia asignado a un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28d6e-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

<span data-ttu-id="28d6e-104">Un Id. de conferencia se asigna automáticamente a un usuario de Microsoft Teams cuando está configurado para la Audioconferencia en Office 365 y usa Microsoft como proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="28d6e-104">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="28d6e-105">El Id. de conferencia asignado se envía en la invitación de la reunión cuando esta se programa.</span><span class="sxs-lookup"><span data-stu-id="28d6e-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="28d6e-106">Se asignará un Id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="28d6e-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="28d6e-107">Aunque el Id. de conferencia se crea y se asigna automáticamente a un usuario, puede suceder que un usuario no quiera usar este Id. y quiera configurar un número concreto, o que los usuarios no lo recuerden o lo hayan perdido.</span><span class="sxs-lookup"><span data-stu-id="28d6e-107">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="28d6e-108">En esos casos, puede usar el Centro de administración de Microsoft Teams o Windows PowerShell para ver, modificar y restablecer el Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="28d6e-108">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="28d6e-109">Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="28d6e-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="28d6e-110">Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="28d6e-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="28d6e-111">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="28d6e-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="28d6e-112">Para ver el Id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="28d6e-112">To reset the meeting conference ID</span></span>

<span data-ttu-id="28d6e-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**</span><span class="sxs-lookup"><span data-stu-id="28d6e-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="28d6e-114">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="28d6e-114">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="28d6e-115">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="28d6e-115">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="28d6e-116">En **Audioconferencia**, mire en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="28d6e-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="28d6e-117">Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de audioconferencia haciendo clic en el vínculo **Enviar información de conferencia por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="28d6e-117">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>
  
<span data-ttu-id="28d6e-118">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="28d6e-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="28d6e-119">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="28d6e-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="28d6e-120">Para restablecer el Id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="28d6e-120">To reset the meeting conference ID</span></span>

<span data-ttu-id="28d6e-121">El Id. de conferencia se puede restablecer para un usuario si, por ejemplo, se le olvida.</span><span class="sxs-lookup"><span data-stu-id="28d6e-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="28d6e-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**</span><span class="sxs-lookup"><span data-stu-id="28d6e-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="28d6e-123">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="28d6e-123">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="28d6e-124">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="28d6e-124">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="28d6e-125">En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="28d6e-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="28d6e-126">En la ventana **Restablecer Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="28d6e-126">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="28d6e-127">El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo.</span><span class="sxs-lookup"><span data-stu-id="28d6e-127">In the Reset conference ID? window, click Yes. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>
  
<span data-ttu-id="28d6e-128">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="28d6e-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="28d6e-129">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="28d6e-129">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="28d6e-130">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="28d6e-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="28d6e-131">Una vez que se haya creado el Id. de conferencia nuevo o se haya restablecido el anterior, los autores de llamada no podrán usar el Id. anterior.</span><span class="sxs-lookup"><span data-stu-id="28d6e-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="28d6e-132">Tendrá que notificar a los usuarios que deben volver a programar las invitaciones de reunión que ya tienen y comprobar que se haya añadido el nuevo Id. de conferencia a las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="28d6e-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="28d6e-133">El Id. de conferencia tiene que cumplir con el requisito de longitud en dígitos que se haya configurado en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="28d6e-133">The conference ID must meet the length in digits set on the dial-in conferencing bridge. You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span> <span data-ttu-id="28d6e-134">No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.</span><span class="sxs-lookup"><span data-stu-id="28d6e-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="28d6e-135">El Id. de conferencia de todos los usuarios de audioconferencias será de siete dígitos de manera predeterminada. Además, el número de dígitos no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="28d6e-135">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="28d6e-136">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="28d6e-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="28d6e-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="28d6e-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="28d6e-140">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="28d6e-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="28d6e-141">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28d6e-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="28d6e-142">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="28d6e-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="28d6e-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="28d6e-143">Related topics</span></span>

[<span data-ttu-id="28d6e-144">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="28d6e-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)


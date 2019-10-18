---
title: Consultar, cambiar y restablecer un Id. de conferencia asignado a un usuario en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a asignar un Id. de conferencia a un usuario en Microsoft Teams y cuáles deben ser los parámetros del Id. de conferencia. '
ms.openlocfilehash: d134a3664a6cee588d08f3d1a33bc6018d97a1fa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571342"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="4d4f3-103">Ver y restablecer un Id. de conferencia asignado a un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d4f3-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="4d4f3-104">Un Id. de conferencia se asigna automáticamente a un usuario de Microsoft Teams cuando está configurado para la Audioconferencia en Office 365 y usa Microsoft como proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="4d4f3-105">El Id. de conferencia asignado se envía en la invitación de la reunión cuando esta se programa.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="4d4f3-106">Se asignará un Id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="4d4f3-107">Aunque el Id. de conferencia se crea y se asigna automáticamente a un usuario, puede suceder que un usuario no quiera usar este Id. y quiera configurar un número concreto, o que los usuarios no lo recuerden o lo hayan perdido.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="4d4f3-108">En esos casos, puede usar el Centro de administración de Microsoft Teams o Windows PowerShell para ver, modificar y restablecer el Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="4d4f3-109">Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="4d4f3-110">Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4d4f3-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="4d4f3-111">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="4d4f3-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="4d4f3-112">Para ver el Id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="4d4f3-112">To view the conference ID</span></span>

<span data-ttu-id="4d4f3-113">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4d4f3-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4d4f3-114">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4d4f3-115">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4d4f3-116">En **Audioconferencia**, mire en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4d4f3-117">Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de audioconferencia haciendo clic en el vínculo **Enviar información de conferencia por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="4d4f3-118">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4d4f3-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4d4f3-119">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="4d4f3-120">Para restablecer el Id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="4d4f3-120">To reset the conference ID</span></span>

<span data-ttu-id="4d4f3-121">El Id. de conferencia se puede restablecer para un usuario si, por ejemplo, se le olvida.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="4d4f3-122">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4d4f3-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4d4f3-123">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4d4f3-124">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4d4f3-125">En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="4d4f3-126">En la ventana **Restablecer Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="4d4f3-127">El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="4d4f3-128">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4d4f3-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4d4f3-129">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="4d4f3-130">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="4d4f3-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="4d4f3-131">Una vez que se haya creado el Id. de conferencia nuevo o se haya restablecido el anterior, los autores de llamada no podrán usar el Id. anterior.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4d4f3-132">Tendrá que notificar a los usuarios que deben volver a programar las invitaciones de reunión que ya tienen y comprobar que se haya añadido el nuevo Id. de conferencia a las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="4d4f3-133">El Id. de conferencia tiene que cumplir con el requisito de longitud en dígitos que se haya configurado en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="4d4f3-134">No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4d4f3-135">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4d4f3-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4d4f3-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="4d4f3-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4d4f3-139">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="4d4f3-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4d4f3-140">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d4f3-140">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4d4f3-141">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4d4f3-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4d4f3-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4d4f3-142">Related topics</span></span>

[<span data-ttu-id="4d4f3-143">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="4d4f3-143">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)


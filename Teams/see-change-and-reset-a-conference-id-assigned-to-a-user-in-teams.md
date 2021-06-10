---
title: Ver, cambiar y restablecer el id. de conferencia de un usuario
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Obtenga información sobre cómo asignar un id. de conferencia a un usuario en Microsoft Teams y cuáles deben ser los parámetros de id. de conferencia.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117213"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="9c7a2-103">Ver y restablecer un id. de conferencia asignado a un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c7a2-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="9c7a2-104">Un id. de conferencia se asigna automáticamente a un usuario de Microsoft Teams cuando se configura para conferencias de audio en Microsoft 365 o Office 365 y usa Microsoft como proveedor de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="9c7a2-105">El id. de conferencia asignado se envía en la invitación a la reunión cuando se programa la reunión.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="9c7a2-106">Se asignará un Id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="9c7a2-107">Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o cuando los usuarios no puedan recordar o haber perdido su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="9c7a2-108">Puede usar Microsoft Teams centro de administración o Windows PowerShell para ver, cambiar y restablecer su id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="9c7a2-109">Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="9c7a2-110">Vea [Restablecer un id. de](reset-a-conference-id-for-a-user-in-teams.md) conferencia para un usuario en Microsoft Teams para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="9c7a2-111">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="9c7a2-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="9c7a2-112">Para ver el id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="9c7a2-112">To view the conference ID</span></span>

<span data-ttu-id="9c7a2-113">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="9c7a2-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9c7a2-114">En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9c7a2-115">En la parte superior de la página, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="9c7a2-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9c7a2-116">En **Audioconferencia,** busque en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9c7a2-117">Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya el id. de conferencia y los números de teléfono de audio haciendo clic en el vínculo Enviar información de conferencia por **correo** electrónico.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="9c7a2-118">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9c7a2-119">Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="9c7a2-120">Para restablecer el id. de conferencia</span><span class="sxs-lookup"><span data-stu-id="9c7a2-120">To reset the conference ID</span></span>

<span data-ttu-id="9c7a2-121">Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="9c7a2-122">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="9c7a2-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9c7a2-123">En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9c7a2-124">En la parte superior de la página, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="9c7a2-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9c7a2-125">En **Audioconferencia, haga** clic **en Restablecer id. de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="9c7a2-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="9c7a2-126">En la ventana **Restablecer id. de** conferencia, haga clic en **Restablecer.**</span><span class="sxs-lookup"><span data-stu-id="9c7a2-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="9c7a2-127">Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="9c7a2-128">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9c7a2-129">Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="9c7a2-130">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="9c7a2-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="9c7a2-131">Después de crear un id. de conferencia nuevo o restablecer uno, los autores de la llamada no pueden usar el id. de conferencia antiguo.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="9c7a2-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="9c7a2-133">El id. de conferencia debe cumplir la longitud de los dígitos establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="9c7a2-134">No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9c7a2-135">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9c7a2-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9c7a2-136">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9c7a2-137">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="9c7a2-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9c7a2-138">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="9c7a2-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9c7a2-139">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="9c7a2-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="9c7a2-140">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9c7a2-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="9c7a2-141">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9c7a2-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9c7a2-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9c7a2-142">Related topics</span></span>

[<span data-ttu-id="9c7a2-143">Pruebe o compre Audioconferencia en Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="9c7a2-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
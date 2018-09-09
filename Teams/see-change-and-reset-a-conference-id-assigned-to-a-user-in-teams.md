---
title: Ver, cambiar y restablecer un identificador de conferencia asignado a un usuario en Microsoft Teams
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
description: 'Obtenga información sobre cómo asignar un identificador de conferencia a un usuario en Microsoft Teams y qué la conferencia ID deben ser parámetros. '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892036"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="9f945-103">Ver y restablecer un identificador de conferencia asignado a un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f945-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="9f945-104">Un identificador de conferencia se asigna automáticamente a un usuario de Microsoft Teams cuando se configuran para conferencias de Audio en Office 365 y usar Microsoft como el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="9f945-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="9f945-105">El identificador de conferencia asignado se envía en la invitación a la reunión cuando la reunión está programada.</span><span class="sxs-lookup"><span data-stu-id="9f945-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="9f945-106">Se asignará un Id. de conferencia único a cada reunión que programe un usuario.</span><span class="sxs-lookup"><span data-stu-id="9f945-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="9f945-107">Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea usar este uno y que desea establecer para un cierto número, o cuando los usuarios no pueden recordar o que han perdido su identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9f945-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="9f945-108">Puede usar el centro de administración de Microsoft Teams o Windows PowerShell para ver, cambiar y restablecer su identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9f945-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="9f945-109">Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="9f945-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="9f945-110">Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9f945-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="9f945-111">Ver y restablecer los identificadores de conferencia</span><span class="sxs-lookup"><span data-stu-id="9f945-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="9f945-112">Para ver el identificador de conferencia</span><span class="sxs-lookup"><span data-stu-id="9f945-112">To view the conference ID</span></span>

<span data-ttu-id="9f945-113">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="9f945-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9f945-114">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="9f945-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9f945-115">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9f945-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9f945-116">En las **Conferencias de Audio**, mire en el **Identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="9f945-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9f945-117">Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y los números de teléfono de audio, haga clic en el vínculo **Enviar información de conferencia en el correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="9f945-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="9f945-118">**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**</span><span class="sxs-lookup"><span data-stu-id="9f945-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9f945-119">Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f945-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="9f945-120">Para restablecer el identificador de conferencia</span><span class="sxs-lookup"><span data-stu-id="9f945-120">To reset the conference ID</span></span>

<span data-ttu-id="9f945-121">Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.</span><span class="sxs-lookup"><span data-stu-id="9f945-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="9f945-122">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="9f945-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9f945-123">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="9f945-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9f945-124">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9f945-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9f945-125">En **Conferencias de Audio**, haga clic en **Restablecer el identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="9f945-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="9f945-126">En la ventana **Restablecer Id. de conferencia** , haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="9f945-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="9f945-127">Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9f945-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="9f945-128">**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**</span><span class="sxs-lookup"><span data-stu-id="9f945-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9f945-129">Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f945-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="9f945-130">¿Qué más tengo que saber?</span><span class="sxs-lookup"><span data-stu-id="9f945-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="9f945-131">Una vez que se crea un nuevo identificador de conferencia o uno se restablece, no se puede usar el identificador de conferencia antigua por los autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9f945-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="9f945-132">Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9f945-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="9f945-133">El identificador de conferencia debe cumplir la longitud en dígitos establecer en el puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="9f945-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="9f945-134">No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.</span><span class="sxs-lookup"><span data-stu-id="9f945-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="9f945-135">El identificador de conferencia para todos los usuarios de conferencia de audio será 7 dígitos de forma predeterminada y no se puede cambiar el número de dígitos.</span><span class="sxs-lookup"><span data-stu-id="9f945-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9f945-136">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9f945-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9f945-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="9f945-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9f945-140">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="9f945-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9f945-141">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f945-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9f945-142">Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f945-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9f945-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9f945-143">Related topics</span></span>

[<span data-ttu-id="9f945-144">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="9f945-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)


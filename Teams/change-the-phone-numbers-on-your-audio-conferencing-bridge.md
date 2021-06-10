---
title: Cambiar los números de teléfono en el puente de audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Obtenga información sobre los pasos necesarios para asignar un nuevo número de teléfono de servicio al puente de conferencias para expandir la cobertura para los usuarios.
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102666"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="bcfe6-103">Cambiar los números de teléfono de su puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bcfe6-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="bcfe6-104">Al comprar licencias **de audioconferencia,** Microsoft hospeda el puente de audioconferencia para su organización.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="bcfe6-105">El puente de audioconferencia proporciona números de teléfono de acceso telefónico local de diferentes ubicaciones para que los organizadores y participantes de la reunión puedan usarlos para unirse Skype Empresarial o Microsoft Teams reuniones con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="bcfe6-106">Además de los números de teléfono ya asignados al puente de conferencias, puede obtener números de servicio adicionales [(números](./getting-service-phone-numbers.md) gratuitos y de pago usados para audioconferencias) de otras ubicaciones y, después, asignarlos al puente de conferencias para que pueda expandir la cobertura para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](./getting-service-phone-numbers.md) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bcfe6-107">Para poder asignar o desasignar un número de teléfono para un puente de conferencias, el número de teléfono debe ser un número *de "servicio".*</span><span class="sxs-lookup"><span data-stu-id="bcfe6-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="bcfe6-108">Para ver el tipo de número que es, vaya a Números de Teléfono en el centro de administración de Microsoft Teams y busque en la  >   columna **Tipo de** número.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="bcfe6-109">Microsoft 365 o Office 365 créditos de comunicaciones deben configurarse primero para que los usuarios puedan llamar al puente en un número gratuito.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="bcfe6-110">Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="bcfe6-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="bcfe6-111">Paso 1: Asignar el nuevo número de teléfono al puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bcfe6-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="bcfe6-112">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bcfe6-113">En el panel de navegación izquierdo, vaya **a Números** de  >  **Teléfono voz.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="bcfe6-114">Seleccione el número de teléfono de la lista y haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="bcfe6-115">En la **página Editar,** en **Asignado a**, expanda el menú desplegable y, a continuación, seleccione Aplicar **puente de**  >  **conferencia.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="bcfe6-116">Paso 2: cambiar el número de teléfono predeterminado del puente de conferencia (opcional)</span><span class="sxs-lookup"><span data-stu-id="bcfe6-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="bcfe6-117">El número de teléfono predeterminado del puente de conferencia define el identificador de llamada que se usará cuando un participante o el organizador coloquen una llamada saliente desde una reunión.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="bcfe6-118">Solo se puede establecer un número de pago de servicio como el número predeterminado para el puente de conferencias; los números gratuitos del servicio no se pueden establecer **como el número predeterminado del puente de conferencias.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="bcfe6-119">Si va a asignar un número de pago de servicio y desea establecerlo como el nuevo número predeterminado para el puente de audioconferencia, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="bcfe6-120">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bcfe6-121">En el panel de navegación izquierdo, vaya a **Puentes de conferencia**  >  **reuniones.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="bcfe6-122">Resalte el número de pago de servicio que desea configurar como predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="bcfe6-123">Haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="bcfe6-124">Paso 3: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)</span><span class="sxs-lookup"><span data-stu-id="bcfe6-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="bcfe6-125">Los números de teléfono predeterminados de un usuario son los que se incluyen en las invitaciones de reunión cuando programan una reunión.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="bcfe6-126">Para obtener más información, incluido cómo se asignan los números de teléfono predeterminados a los nuevos usuarios, vea Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las invitaciones [en Skype Empresarial Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="bcfe6-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="bcfe6-127">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bcfe6-128">En el panel de navegación izquierdo, vaya a **Usuarios** y haga clic en el nombre para mostrar del usuario deseado en la lista.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="bcfe6-129">Junto a **Audioconferencia,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="bcfe6-130">En **Número de pago** o Número **gratuito,** seleccione el número de la lista desplegable y haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="bcfe6-131">Una vez aplicados los cambios, los nuevos números de teléfono predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que programe una nueva reunión.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="bcfe6-132">Paso 4: Actualizar las invitaciones de reunión existentes de los usuarios con el servicio de migración de reuniones (opcional)</span><span class="sxs-lookup"><span data-stu-id="bcfe6-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="bcfe6-133">Para los dos pasos siguientes, tendrá que iniciar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="bcfe6-134">Si actualizó los números de teléfono predeterminados que se incluyen en las invitaciones de reunión para algunos o todos los usuarios, opcionalmente puede actualizar las invitaciones a reuniones que ya se enviaron a los usuarios de su organización antes de cambiar sus números de teléfono predeterminados con el Servicio de migración de reuniones.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="bcfe6-135">Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="bcfe6-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="bcfe6-136">Ejecute el Servicio de migración de reuniones (MMS) para los usuarios que cambiaron sus números de teléfono predeterminados en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="bcfe6-137">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="bcfe6-p107">También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .</span><span class="sxs-lookup"><span data-stu-id="bcfe6-p107">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="bcfe6-140">Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="bcfe6-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="bcfe6-141">Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="bcfe6-142">Dado que el número de teléfono está cambiando, es importante actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si existe) y actualizar las invitaciones a reuniones existentes antes de que el número de teléfono no esté desasignado del puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="bcfe6-143">Si el número de teléfono se quita sin actualizar los usuarios y sus reuniones, las invitaciones a reuniones existentes podrían contener un número de teléfono que no funcionará para unirse a sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="bcfe6-144">Para los primeros tres pasos, tendrá que iniciar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="bcfe6-145">Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="bcfe6-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="bcfe6-146">Paso 1: Actualizar los usuarios que tienen el número de teléfono para que no se les haya desasignado uno de sus números predeterminados</span><span class="sxs-lookup"><span data-stu-id="bcfe6-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="bcfe6-147">Reemplace el número de pago o gratuito predeterminado para todos los usuarios que tengan el número que se va a desasignar como un número predeterminado e inicie el proceso de reprogramación de sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="bcfe6-148">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="bcfe6-149">También puede cambiar el número de usuarios de pago o gratuito predeterminado en el centro Microsoft Teams administración.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="bcfe6-150">No obstante, en este modo no se volverán a programar las reuniones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="bcfe6-151">Para obtener información adicional, vea Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las [invitaciones en Skype Empresarial En línea.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="bcfe6-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="bcfe6-152">Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="bcfe6-153">Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcfe6-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="bcfe6-154">Todas las reuniones se reprogramarán una vez que no haya operaciones *en* estado Pendiente o *En* curso.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="bcfe6-155">Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="bcfe6-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="bcfe6-156">Paso 3: Desasignar el número de teléfono antiguo del puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bcfe6-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="bcfe6-157">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bcfe6-158">En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="bcfe6-159">Si el número de teléfono es un número gratuito, seleccione el número de teléfono de la lista y haga clic en **Liberar.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="bcfe6-160">Si el número de teléfono es un número de pago, ponte en contacto con el soporte técnico [de Microsoft](/microsoft-365/admin/contact-support-for-business-products) para que el número de teléfono no esté desasignado.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-160">If the phone number is a toll number, please contact [Microsoft support](/microsoft-365/admin/contact-support-for-business-products) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="bcfe6-161">Si el número de teléfono es un número gratuito, haga clic **en Sí** en la ventana de confirmación.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="bcfe6-162">Después de que un número de teléfono no se haya desasignado de un puente de audioconferencia, el número de teléfono ya no estará disponible para que los usuarios se unan a reuniones nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="bcfe6-163">Ahorrar tiempo y automatizar</span><span class="sxs-lookup"><span data-stu-id="bcfe6-163">Save time and automate</span></span>

<span data-ttu-id="bcfe6-164">Para ahorrar tiempo automatizando este proceso, puede usar los [cmdlets Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="bcfe6-165">Use el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-165">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="bcfe6-166">Para cambiar el número gratuito predeterminado de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="bcfe6-167">Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcfe6-168">Para buscar el BridgeID, use **get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="bcfe6-169">Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que no tengan un número, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="bcfe6-170">Para cambiar el número gratuito predeterminado de todos los usuarios que tienen el 8005551234 como su número gratuito predeterminado al 8005551239 y volver a programar automáticamente sus reuniones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="bcfe6-171">Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que se encuentren en EE. UU. y volver a programar automáticamente sus reuniones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="bcfe6-172">La ubicación que se usa anteriormente debe coincidir con la información de contacto de los usuarios que se establece en el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bcfe6-173">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="bcfe6-173">Troubleshooting</span></span>

<span data-ttu-id="bcfe6-174">**El botón Desasignación no está disponible**</span><span class="sxs-lookup"><span data-stu-id="bcfe6-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="bcfe6-175">Desea desasignar un número, pero el botón no está disponible y, si mientras mantiene el puntero sobre él, se le redirigirá para ponerse en contacto con el soporte técnico con el siguiente mensaje: "Los números predeterminados o compartidos no se pueden desasignar desde el _puente. Para desasignación de números de pago dedicados, póngase en contacto con el soporte técnico."._</span><span class="sxs-lookup"><span data-stu-id="bcfe6-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="bcfe6-176">Para obtener más información sobre los puentes, ejecute el siguiente Powershell:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="bcfe6-177">El resultado, aparte de otra información como Identidad, Nombre y Región, también debe contener defaultservicenumber.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="bcfe6-178">**Ejemplo**, para desasignar, defaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="bcfe6-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="bcfe6-179">Acerca de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcfe6-179">About Windows PowerShell</span></span>

<span data-ttu-id="bcfe6-180">Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="bcfe6-181">Windows PowerShell puede ayudarle a administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, especialmente cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="bcfe6-182">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="bcfe6-183">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bcfe6-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="bcfe6-184">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="bcfe6-184">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

<span data-ttu-id="bcfe6-185">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bcfe6-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bcfe6-186">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="bcfe6-186">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="bcfe6-187">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="bcfe6-187">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="bcfe6-188">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bcfe6-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="bcfe6-189">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bcfe6-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="bcfe6-190">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bcfe6-190">Related topics</span></span>
<span data-ttu-id="bcfe6-191">[Cambiar la configuración de un puente de Audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="bcfe6-191">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>
---
title: Cambiar los números de teléfono en el puente de Audioconferencia
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
description: Conozca los pasos necesarios para asignar un nuevo número de teléfono de servicio a su puente de conferencia para ampliar la cobertura para los usuarios.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918756"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="fd9de-103">Cambiar los números de teléfono de su puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="fd9de-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="fd9de-104">Cuando compra licencias **de Audioconferencia,** Microsoft hospeda el puente de audioconferencia para su organización.</span><span class="sxs-lookup"><span data-stu-id="fd9de-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="fd9de-105">El puente de audioconferencia proporciona números de teléfono de acceso telefónico local de diferentes ubicaciones para que los organizadores y participantes de la reunión puedan usarlos para unirse a las reuniones de Skype Empresarial o Microsoft Teams con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="fd9de-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="fd9de-106">Además de los números de teléfono ya asignados al puente de conferencia, puede obtener números de servicio adicionales [(números](/microsoftteams/getting-service-phone-numbers) de pago y gratuitos utilizados para audioconferencias) desde otras ubicaciones y asignarlos al puente de conferencia para que pueda ampliar la cobertura para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd9de-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd9de-107">Para poder asignar o desasignar un número de teléfono a un puente de conferencia, el número de teléfono debe ser un número *de* servicio '.</span><span class="sxs-lookup"><span data-stu-id="fd9de-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="fd9de-108">Para ver el tipo de número, vaya a Números de teléfono de voz en el Centro de administración de Microsoft Teams y busque en la  >   columna **Tipo de** número.</span><span class="sxs-lookup"><span data-stu-id="fd9de-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="fd9de-109">Los créditos de comunicaciones de Microsoft 365 u Office 365 deben configurarse primero para que los usuarios puedan llamar al puente desde un número gratuito.</span><span class="sxs-lookup"><span data-stu-id="fd9de-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="fd9de-110">Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="fd9de-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="fd9de-111">Paso 1: Asignar el nuevo número de teléfono al puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="fd9de-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="fd9de-112">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="fd9de-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="fd9de-113">En el panel de navegación izquierdo, vaya a Números **de teléfono de**  >  **voz.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="fd9de-114">Seleccione el número de teléfono de la lista y haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="fd9de-115">En la **página Editar,** en **Asignado a,** expanda la lista desplegable y, después, seleccione **Aplicar puente de**  >  **conferencia.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="fd9de-116">Paso 2: Cambiar el número de teléfono predeterminado del puente de conferencia (opcional)</span><span class="sxs-lookup"><span data-stu-id="fd9de-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="fd9de-117">El número de teléfono predeterminado del puente de conferencia define el identificador de llamada que se usará cuando un participante o el organizador realizará una llamada saliente desde dentro de una reunión.</span><span class="sxs-lookup"><span data-stu-id="fd9de-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="fd9de-118">Solo se puede establecer un número de servicio de pago como número predeterminado para el puente de conferencia; los números de servicio gratuitos no se pueden establecer **como el número predeterminado del puente de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="fd9de-119">Si asigna un número de servicio de pago y le gustaría establecerlo como el nuevo número predeterminado para el puente de audioconferencia, realice estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fd9de-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="fd9de-120">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="fd9de-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="fd9de-121">En el panel de navegación izquierdo, vaya **a Puentes de conferencia de**  >  **reuniones.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="fd9de-122">Resalte el número de servicio de pago que desea configurar como predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fd9de-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="fd9de-123">Haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="fd9de-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="fd9de-124">Paso 3: cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)</span><span class="sxs-lookup"><span data-stu-id="fd9de-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="fd9de-125">Cuando se programa una reunión, los números de teléfono predeterminados de un usuario son los que se incluyen en las invitaciones a la reunión.</span><span class="sxs-lookup"><span data-stu-id="fd9de-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="fd9de-126">Para obtener más información, incluido cómo se asignan los números de teléfono predeterminados a los nuevos usuarios, vea Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las invitaciones [en Skype Empresarial Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="fd9de-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="fd9de-127">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="fd9de-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="fd9de-128">En el panel de navegación izquierdo, vaya **a Usuarios** y haga clic en el nombre para mostrar del usuario deseado en la lista.</span><span class="sxs-lookup"><span data-stu-id="fd9de-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="fd9de-129">Junto a **Audioconferencia,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="fd9de-130">En **Número de pago** o Número **gratuito,** seleccione el número en la lista desplegable y haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="fd9de-131">Una vez que se hayan aplicado los cambios, los nuevos números de teléfono predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que se programe una nueva reunión.</span><span class="sxs-lookup"><span data-stu-id="fd9de-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="fd9de-132">Paso 4: Actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)</span><span class="sxs-lookup"><span data-stu-id="fd9de-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="fd9de-133">Para los dos pasos siguientes, deberá iniciar la Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd9de-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="fd9de-134">Si ha actualizado los números de teléfono predeterminados que se incluyen en las invitaciones de reunión para algunos o todos los usuarios, puede actualizar las invitaciones de reunión que ya se enviaron a los usuarios de su organización antes de que se cambiaran sus números de teléfono predeterminados con el servicio de migración de reuniones.</span><span class="sxs-lookup"><span data-stu-id="fd9de-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="fd9de-135">Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="fd9de-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="fd9de-136">Ejecute el Servicio de migración de reuniones (MMS) para los usuarios a los que se les cambiaron los números de teléfono predeterminados en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="fd9de-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="fd9de-137">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fd9de-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="fd9de-138">También puede ver el estado de migración de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="fd9de-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="fd9de-139">Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .</span><span class="sxs-lookup"><span data-stu-id="fd9de-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="fd9de-140">Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="fd9de-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="fd9de-141">Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número.</span><span class="sxs-lookup"><span data-stu-id="fd9de-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="fd9de-142">Como el número de teléfono va a cambiar, es importante actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si los hay) y actualizar las invitaciones de reunión existentes antes de que se desasigne el número de teléfono del puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="fd9de-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="fd9de-143">Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcionará para unirse a sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="fd9de-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="fd9de-144">Para los primeros tres pasos, tendrá que iniciar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd9de-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="fd9de-145">Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="fd9de-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="fd9de-146">Paso 1: Actualizar los usuarios que tienen el número de teléfono para que se les desasigne como uno de sus números predeterminados</span><span class="sxs-lookup"><span data-stu-id="fd9de-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="fd9de-147">Reemplace el número de teléfono gratuito o de pago predeterminado de todos los usuarios que tengan el número para el que se va a eliminar la firma como un número predeterminado e inicie el proceso de volver a programar sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="fd9de-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="fd9de-148">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fd9de-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="fd9de-149">También puede cambiar el número gratuito o de pago predeterminado de los usuarios en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd9de-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fd9de-150">No obstante, en este modo no se volverán a programar las reuniones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fd9de-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="fd9de-151">Para obtener información adicional, consulte Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las [invitaciones en Skype Empresarial Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="fd9de-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd9de-152">Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="fd9de-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="fd9de-153">Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd9de-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="fd9de-154">Todas las reuniones se volverán a programar cuando no haya ninguna operación con *estado* pendiente o *en* curso.</span><span class="sxs-lookup"><span data-stu-id="fd9de-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="fd9de-155">Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="fd9de-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="fd9de-156">Paso 3: Desasignar el número de teléfono anterior del puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="fd9de-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="fd9de-157">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="fd9de-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="fd9de-158">En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="fd9de-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="fd9de-159">Si el número de teléfono es gratuito, selecciónelo de la lista y haga clic en **Liberar.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="fd9de-160">Si el número de teléfono es un número de pago, ponte en contacto con el soporte técnico de [Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) para que se desasigne el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="fd9de-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="fd9de-161">Si el número de teléfono es gratuito, haga clic en **Sí en** la ventana de confirmación.</span><span class="sxs-lookup"><span data-stu-id="fd9de-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="fd9de-162">Una vez que se desasigne un número de teléfono a un puente de audioconferencia, el número de teléfono ya no estará disponible para los usuarios que se unan a reuniones nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="fd9de-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fd9de-163">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="fd9de-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="fd9de-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9de-164"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="fd9de-165">Para verificar que Windows PowerShell está listo</span><span class="sxs-lookup"><span data-stu-id="fd9de-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="fd9de-166">Estos pasos comprueban que está ejecutando Windows PowerShell versión 3.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="fd9de-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="fd9de-167">Escriba **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fd9de-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="fd9de-168">Escriba _Get-Host_ en la ventana de **Windows PowerShell** para comprobar la versión.</span><span class="sxs-lookup"><span data-stu-id="fd9de-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="fd9de-169">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd9de-169">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="fd9de-170">Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="fd9de-170">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="fd9de-171">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="fd9de-171">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="fd9de-172">También debe instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="fd9de-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="fd9de-173">Este módulo solo es compatible con equipos de 64 bits y se puede descargar desde el Centro de descarga de Microsoft en [Windows PowerShell Module para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="fd9de-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="fd9de-174">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="fd9de-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="fd9de-175">Si necesita más información, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.</span><span class="sxs-lookup"><span data-stu-id="fd9de-175">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="fd9de-176">Para iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd9de-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="fd9de-177">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fd9de-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="fd9de-178">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fd9de-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="fd9de-179">En la **Windows PowerShell** de correo electrónico, conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="fd9de-179">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>

> [!NOTE]
> <span data-ttu-id="fd9de-180">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="fd9de-180">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="fd9de-181">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="fd9de-181">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="fd9de-182">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="fd9de-182">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="fd9de-183">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Conectarse a Skype Empresarial [Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)mediante el Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd9de-183">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="fd9de-184">Ahorre tiempo y automatice</span><span class="sxs-lookup"><span data-stu-id="fd9de-184">Save time and automate</span></span>

<span data-ttu-id="fd9de-185">Para ahorrar tiempo mediante la automatización de este proceso, puede usar [los cmdlet Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-185">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="fd9de-186">Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="fd9de-186">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="fd9de-187">Para cambiar el número gratuito predeterminado de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="fd9de-187">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="fd9de-188">Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fd9de-188">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd9de-189">Para buscar el Id. de puente, use **Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="fd9de-189">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="fd9de-190">Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que no tengan un número, ejecute:</span><span class="sxs-lookup"><span data-stu-id="fd9de-190">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="fd9de-191">Para cambiar el número gratuito predeterminado de todos los usuarios que tienen el 8005551234 como su número gratuito predeterminado al 8005551239 y volver a programar automáticamente sus reuniones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="fd9de-191">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="fd9de-192">Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que se encuentren en EE. UU. y volver a programar automáticamente sus reuniones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="fd9de-192">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="fd9de-193">La ubicación que se usa arriba debe coincidir con la información de contacto de los usuarios establecidos en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd9de-193">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fd9de-194">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="fd9de-194">Troubleshooting</span></span>

<span data-ttu-id="fd9de-195">**El botón Desasignación no está disponible**</span><span class="sxs-lookup"><span data-stu-id="fd9de-195">**Unassign button isn't available**</span></span>

<span data-ttu-id="fd9de-196">Quiere cancelar lasignación de un número, pero el botón no está disponible y, si al mantener el puntero sobre él, se le redirige al soporte técnico con el siguiente mensaje: "No se puede cancelar la firma de los números predeterminados o compartidos del _puente. Para desasignir números de pago dedicados, póngase en contacto con el soporte técnico._".</span><span class="sxs-lookup"><span data-stu-id="fd9de-196">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="fd9de-197">Para obtener más información sobre los puentes, ejecute el siguiente PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fd9de-197">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="fd9de-198">El resultado, salvo otra información como Identidad, Nombre y Región, también debe contener el DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="fd9de-198">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="fd9de-199">**Ejemplo,** para desasignar, el valor DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="fd9de-199">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="fd9de-200">Acerca de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd9de-200">About Windows PowerShell</span></span>

<span data-ttu-id="fd9de-201">Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="fd9de-201">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="fd9de-202">Windows PowerShell puede ayudarle a administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, especialmente si tiene que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="fd9de-202">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="fd9de-203">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="fd9de-203">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="fd9de-204">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="fd9de-204">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="fd9de-205">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="fd9de-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="fd9de-206">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="fd9de-206">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="fd9de-207">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="fd9de-207">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="fd9de-208">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd9de-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="fd9de-209">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="fd9de-209">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="fd9de-210">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="fd9de-210">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="fd9de-211">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fd9de-211">Related topics</span></span>
<span data-ttu-id="fd9de-212">[Cambiar la configuración de un puente de Audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="fd9de-212">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

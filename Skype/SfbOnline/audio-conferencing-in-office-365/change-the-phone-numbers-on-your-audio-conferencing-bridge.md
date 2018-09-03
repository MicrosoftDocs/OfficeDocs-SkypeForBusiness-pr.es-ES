---
title: Cambiar los números de teléfono de su puente de Audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
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
description: Cuando adquiere licencias de Audioconferencia, Microsoft aloja el puente de audioconferencia de su organización. El puente de audioconferencia distribuye números de teléfono de acceso telefónico local de diferentes ubicaciones, de forma que los organizadores de la reunión y los participantes puedan utilizarlos para unirse a las reuniones de Skype for Business o Microsoft Teams mediante el teléfono.
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255715"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="b954a-104">Cambiar los números de teléfono de su puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b954a-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="b954a-105">Cuando adquiere **licencias de Audioconferencia**, Microsoft aloja el *puente de audioconferencia* de su organización.</span><span class="sxs-lookup"><span data-stu-id="b954a-105">When you buy **Skype for Business PSTN Conferencing** licenses, Microsoft is hosting a *conferencing bridge*  for your organization.</span></span> <span data-ttu-id="b954a-106">El puente de audioconferencia distribuye números de teléfono de acceso telefónico local de diferentes ubicaciones, de forma que los organizadores de la reunión y los participantes puedan utilizarlos para unirse a las reuniones de Skype for Business o Microsoft Teams mediante el teléfono.</span><span class="sxs-lookup"><span data-stu-id="b954a-106">The conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join meetings using a phone.</span></span>

<span data-ttu-id="b954a-107">Además de los números de teléfono que ya se hayan asignado al puente de conferencia, puede [Obtener números de servicio adicionales](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (números gratuitos y de pago utilizados para audioconferencias) desde otra ubicación y asignarlos al puente de conferencia, con el fin de ampliar la cobertura para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b954a-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [Getting Skype for Business service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (toll and toll-free numbers used for dial-in conferencing) from other locations and then assign them to the conferencing bridge so you can expand the area/country/region coverage for your users.</span></span>

> [!NOTE]
> <span data-ttu-id="b954a-108">Para poder asignar o quitar la asignación de un número de teléfono a un puente de conferencia, el número de teléfono debe ser un número "*de servicio*".</span><span class="sxs-lookup"><span data-stu-id="b954a-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a 'service' number.</span></span> <span data-ttu-id="b954a-109">Puede ver qué tipo de número de teléfono yendo a **Voz** > **Números de teléfono** y mirando en la columna **Tipo de número**.</span><span class="sxs-lookup"><span data-stu-id="b954a-109">You can see the type of number it is by using the **Voice** > **Phone numbers** tab and look under the **Number Type** column.</span></span> <span data-ttu-id="b954a-110">Los Créditos de comunicaciones de Office 365 deben configurarse primero para que los usuarios puedan marcar en el puente un número gratuito.</span><span class="sxs-lookup"><span data-stu-id="b954a-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="b954a-111">Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="b954a-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="b954a-112">Paso 1: Asignar el número de teléfono nuevo a su puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b954a-112">Step 1 - Assign the new phone number to your conferencing bridge</span></span>

1. <span data-ttu-id="b954a-113">Inicie sesión en Office 365 con su cuenta profesional.</span><span class="sxs-lookup"><span data-stu-id="b954a-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="b954a-114">Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Voz** > **Números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="b954a-114">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="b954a-115">Seleccione el número de teléfono en la lista y, en el panel de Acción, haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="b954a-115">Select the phone number from the list and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="b954a-116">En la página **Asignar**, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b954a-116">On the **Assign** page, click **Save**.</span></span>

    <span data-ttu-id="b954a-117">Solo puede establecerse un número de servicio de pago como número predeterminado para el puente de conferencia; **los números gratuitos de servicio no pueden establecerse como número predeterminado del puente de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="b954a-117">Only a service toll number can be set as the default number for your conferencing bridge, **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="b954a-118">Si asigna un número de servicio de pago y le gustaría establecer un nuevo número predeterminado para el puente de audioconferencia, seleccione **Utilizar este número como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="b954a-118">If you are assigning a service toll number and you would like to set it as the new default number for your conferencing bridge, check **Use this number as the default**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b954a-119">Tras asignar un nuevo número de teléfono, incluso si el número ha pasado a ser el nuevo número predeterminado, no cambiará el número predeterminado de los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="b954a-119">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="b954a-120">Para establecer el número de pago o gratuito predeterminado que se agrega a las invitaciones de reunión del organizador, consulte [Establecer los números de teléfono que se incluyen en invitaciones](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="b954a-120">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="b954a-121">Paso 2: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)</span><span class="sxs-lookup"><span data-stu-id="b954a-121">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="b954a-122">Cuando se programa una reunión, los números de teléfono que se incluyen en las invitaciones de reunión son los predeterminados del usuario.</span><span class="sxs-lookup"><span data-stu-id="b954a-122">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="b954a-123">Para obtener más información, vea [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="b954a-123">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

1. <span data-ttu-id="b954a-124">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="b954a-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="b954a-125">Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Audioconferencia** > **Usuarios** y seleccione los usuarios en la lista.</span><span class="sxs-lookup"><span data-stu-id="b954a-125">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Dial-in conferencing** > **Dial-in users** and find the users in the list.</span></span>

3. <span data-ttu-id="b954a-126">Haga clic en **Editar** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="b954a-126">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="b954a-127">En **Número de teléfono de pago predeterminado** o **Número de teléfono gratuito predeterminado**, seleccione el número en la lista y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b954a-127">Under ** Default toll number** or Default toll-free number, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="b954a-128">Cuando los cambios se hayan guardado, los números de teléfono nuevos predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que se programe una nueva reunión.</span><span class="sxs-lookup"><span data-stu-id="b954a-128">Once the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="b954a-129">Paso 3: Actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)</span><span class="sxs-lookup"><span data-stu-id="b954a-129">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="b954a-130">Para los siguientes dos pasos, tendrá que iniciar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b954a-130">For the first three steps, you will need to start Windows PowerShell.</span></span>

<span data-ttu-id="b954a-131">Al utilizar el servicio de migración de reuniones podrá decidir si quiere actualizar las invitaciones de reunión que se enviaron a los usuarios de su organización antes de cambiar los números de teléfono predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b954a-131">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers had been changed.</span></span> <span data-ttu-id="b954a-132">Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="b954a-132">For additional information, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

- <span data-ttu-id="b954a-133">Ejecute el servicio de migración de reuniones (MMS) para los usuarios a los que se les cambiaron los números de teléfono predeterminados en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b954a-133">Run the Meeting Migration Service for the users that had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="b954a-134">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b954a-134">To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="b954a-p109">También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .</span><span class="sxs-lookup"><span data-stu-id="b954a-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="b954a-137">Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="b954a-137">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="b954a-138">Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número.</span><span class="sxs-lookup"><span data-stu-id="b954a-138">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="b954a-139">Dado que el número de teléfono va a cambiar, es importante actualizar todos los usuarios que puedan tener un número de teléfono como su número predeterminado (en caso de tenerlo) y actualizar las invitaciones de reunión existentes antes de que se quite la asignación del número de teléfono del puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="b954a-139">Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the bridge.</span></span>

<span data-ttu-id="b954a-140">Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcione para unirse a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="b954a-140">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings anymore.</span></span>

<span data-ttu-id="b954a-141">Para los primeros tres pasos, tendrá que iniciar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b954a-141">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="b954a-142">Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="b954a-142">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="b954a-143">Paso 1: Actualizar usuarios que puedan tener el número de teléfono cuya asignación se va a cancelar como uno de sus números predeterminados</span><span class="sxs-lookup"><span data-stu-id="b954a-143">Step 1 - Update users that have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="b954a-p112">Reemplace el número de teléfono gratuito o de pago predeterminado de todos los usuarios que tengan el número cuya asignación se va a cancelar como número predeterminado e inicie el proceso de volver a programar las reuniones. Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b954a-p112">Replace the default toll or toll-free number for all users that have the number to be unassigned as a default number and start the process of rescheduling their meetings. To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 ><span data-ttu-id="b954a-146">También puede cambiar el número gratuito o de pago predeterminado de los usuarios en el centro de administración de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b954a-146">You can also change the default toll or toll-free number of users in the Skype for Business admin center, however, this won't automatically reschedule their meetings.</span></span> <span data-ttu-id="b954a-147">No obstante, en este modo no se volverán a programar las reuniones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b954a-147">However, this won't automatically reschedule their meetings.</span></span>

 <span data-ttu-id="b954a-148">Para obtener más información, vea [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="b954a-148">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b954a-149">Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="b954a-149">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="b954a-150">Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b954a-150">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="b954a-151">Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado *Pendiente* o *En curso*.</span><span class="sxs-lookup"><span data-stu-id="b954a-151">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="b954a-152">Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="b954a-152">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="b954a-153">Paso 3: Quitar la asignación del número de teléfono anterior del puente de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b954a-153">Step 3 - Unassign the old phone number from the dial-in conferencing bridge</span></span>

1. <span data-ttu-id="b954a-154">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="b954a-154">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="b954a-155">Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Voz** > **Números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="b954a-155">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="b954a-156">Seleccione el número de teléfono en la lista y, en el panel de Acción, haga clic en **Quitar asignación**.</span><span class="sxs-lookup"><span data-stu-id="b954a-156">Select the phone number from the list and in the Action pane, click **Unassign**.</span></span>

4. <span data-ttu-id="b954a-157">En la ventana confirmación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b954a-157">In the confirmation window, click **Yes**.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="b954a-158">Una vez quitada la asignación a un puente de audioconferencia de un número de teléfono, este dejará de estar disponible para los usuarios que se unan a reuniones nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="b954a-158">Once a phone number is unassigned from a conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b954a-159">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b954a-159">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="b954a-160"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="b954a-160"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="b954a-161">Para verificar que Windows PowerShell está listo</span><span class="sxs-lookup"><span data-stu-id="b954a-161">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="b954a-162">Con estos pasos podrá comprobar que está ejecutando Windows PowerShell versión 3.0 o superior</span><span class="sxs-lookup"><span data-stu-id="b954a-162">Check that you are running Windows PowerShell version 3.0 or higher</span></span>

1. <span data-ttu-id="b954a-163">Escriba **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b954a-163">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="b954a-164">Escriba _Get-Host_ en la ventana de **Windows PowerShell** para comprobar la versión.</span><span class="sxs-lookup"><span data-stu-id="b954a-164">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="b954a-p114">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="b954a-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="b954a-168">También debe instalar el módulo Windows PowerShell para Skype for Business Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="b954a-168">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="b954a-169">Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga Microsoft en el [Módulo de Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="b954a-169">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="b954a-170">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="b954a-170">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="b954a-171">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="b954a-171">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="b954a-172">Para iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b954a-172">To start Windows PowerShell</span></span>

 <span data-ttu-id="b954a-173">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b954a-173">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="b954a-174">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b954a-174">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="b954a-175">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="b954a-175">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b954a-176">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="b954a-176">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="b954a-177">Si desea obtener más información sobre cómo iniciar Windows PowerShell, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Conectarse a Skype for Business Online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b954a-177">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="b954a-178">Ahorrar tiempo y automatizar</span><span class="sxs-lookup"><span data-stu-id="b954a-178">Save time or automate</span></span>

<span data-ttu-id="b954a-179">Para ahorrar tiempo automatizando este proceso, puede utilizar los cmdlets [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber**.</span><span class="sxs-lookup"><span data-stu-id="b954a-179">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="b954a-180">Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="b954a-180">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="b954a-181">Para cambiar el número gratuito predeterminado de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b954a-181">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="b954a-182">Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.</span><span class="sxs-lookup"><span data-stu-id="b954a-182">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b954a-183">Para buscar el id. de puente, use **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="b954a-183">Note:To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="b954a-184">Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que no tengan un número, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b954a-184">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="b954a-185">Para cambiar el número gratuito predeterminado de todos los usuarios que tienen el 8005551234 como su número gratuito predeterminado al 8005551239 y volver a programar automáticamente sus reuniones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b954a-185">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="b954a-186">Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que se encuentren en EE. UU. y volver a programar automáticamente sus reuniones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b954a-186">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="b954a-187">La ubicación que se usa arriba debe coincidir con la información de contacto de los usuarios establecidos en el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b954a-187">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span>

## <a name="about-windows-powershell"></a><span data-ttu-id="b954a-188">Acerca de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b954a-188">About Windows PowerShell</span></span>

<span data-ttu-id="b954a-189">Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="b954a-189">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="b954a-190">Windows PowerShell puede ayudarlo a administrar Office 365 y Skype for Business Online mediante un único punto de administración que puede simplificar su trabajo diario, especialmente cuando deba realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="b954a-190">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b954a-191">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="b954a-191">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b954a-192">Una introducción a Windows PowerShell y Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b954a-192">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="b954a-193">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="b954a-193">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="b954a-p117">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="b954a-p117">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="b954a-196">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b954a-196">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="b954a-197">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b954a-197">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="b954a-198">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b954a-198">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="b954a-199">See also</span><span class="sxs-lookup"><span data-stu-id="b954a-199">Related topics</span></span>
[<span data-ttu-id="b954a-200">Cambiar la configuración de un puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b954a-200">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)

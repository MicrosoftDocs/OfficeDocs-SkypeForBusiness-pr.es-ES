---
title: Directivas de llamadas en Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Obtenga información acerca de la configuración de la directiva de llamada en Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 007bea10d8e452a2198c869ab545592b29c591c1
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632372"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="3f74c-103">Directivas de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f74c-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="3f74c-104">En Microsoft Teams, llamar al control de las directivas que la llamada a y las características de desvío de llamadas están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f74c-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="3f74c-105">Las directivas de la llamada a determinan si un usuario puede realizar llamadas privadas, use el desvío de llamadas o llamadas a otros usuarios o números de teléfono externos simultáneas, enrutar las llamadas al correo de voz, enviar las llamadas a grupos de llamadas, delegación para las llamadas entrantes y salientes, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3f74c-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="3f74c-106">Una directiva global predeterminada se crea automáticamente, pero los administradores también pueden crear y asignar directivas de llamada personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3f74c-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="3f74c-107">Crear una directiva llamada personalizada</span><span class="sxs-lookup"><span data-stu-id="3f74c-107">Create a custom calling policy</span></span>

<span data-ttu-id="3f74c-108">Siga estos pasos para crear una directiva llamada personalizada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="3f74c-109">En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="3f74c-110">Seleccione **nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-110">Select **New policy**.</span></span>
3. <span data-ttu-id="3f74c-111">Activar las características que desea usar en la directiva de llamada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="3f74c-112">Todas las selecciones están **desactivadas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="3f74c-113">Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="3f74c-114">Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="3f74c-115">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="3f74c-116">Modificar una directiva de llamada existente</span><span class="sxs-lookup"><span data-stu-id="3f74c-116">Modify an existing calling policy</span></span>

<span data-ttu-id="3f74c-117">Siga estos pasos para modificar una directiva de llamada existente.</span><span class="sxs-lookup"><span data-stu-id="3f74c-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="3f74c-118">En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="3f74c-119">Haga clic en junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="3f74c-120">Activar las características que desea usar en la directiva de llamada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="3f74c-121">Todas las selecciones están **desactivadas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="3f74c-122">Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="3f74c-123">Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="3f74c-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="3f74c-125">Asignar una directiva de llamada a un usuario</span><span class="sxs-lookup"><span data-stu-id="3f74c-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="3f74c-126">Siga estos pasos para asignar una directiva personalizada que llama a un usuario.</span><span class="sxs-lookup"><span data-stu-id="3f74c-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="3f74c-127">En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="3f74c-128">Haga clic en junto al nombre de directiva para seleccionarlo y, a continuación, seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="3f74c-129">En el panel **Administrar usuarios** , buscar el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="3f74c-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="3f74c-130">(Debe escribir al menos tres caracteres).</span><span class="sxs-lookup"><span data-stu-id="3f74c-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="3f74c-131">Seleccione el nombre del usuario y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="3f74c-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="3f74c-133">Configuración de la directiva de llamada</span><span class="sxs-lookup"><span data-stu-id="3f74c-133">Calling policy settings</span></span>

<span data-ttu-id="3f74c-134">Use la siguiente configuración para crear una directiva llamada personalizada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="3f74c-135">Usuario puede realizar llamadas privadas</span><span class="sxs-lookup"><span data-stu-id="3f74c-135">User can make private calls</span></span>

<span data-ttu-id="3f74c-136">Esta configuración controla todas las capacidades de llamada en los equipos.</span><span class="sxs-lookup"><span data-stu-id="3f74c-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="3f74c-137">Desactivar para desactivar la opción toda la funcionalidad de llamada en los equipos.</span><span class="sxs-lookup"><span data-stu-id="3f74c-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="3f74c-138">Desvío de llamadas y las llamadas simultáneas a otros usuarios</span><span class="sxs-lookup"><span data-stu-id="3f74c-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="3f74c-139">Esta configuración controla si las llamadas recibidas pueden transferirse a otros usuarios o pueden llamar a otra persona al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3f74c-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="3f74c-140">Desvío de llamadas y las llamadas simultáneas a números de teléfono externos</span><span class="sxs-lookup"><span data-stu-id="3f74c-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="3f74c-141">Esta configuración controla si las llamadas recibidas pueden transferirse a un número externo o pueden llamar a un número externo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3f74c-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="3f74c-142">Correo de voz está disponible para enrutar las llamadas entrantes a los usuarios</span><span class="sxs-lookup"><span data-stu-id="3f74c-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="3f74c-143">Esta configuración permite que las llamadas entrantes que se envíen al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="3f74c-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="3f74c-144">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="3f74c-144">Valid options are:</span></span>

   - <span data-ttu-id="3f74c-145">**Siempre habilitado** Correo de voz siempre está disponible para las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="3f74c-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="3f74c-146">**Siempre deshabilitado**  Correo de voz no está disponible para las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="3f74c-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="3f74c-147">**Controla el usuario**.</span><span class="sxs-lookup"><span data-stu-id="3f74c-147">**User controlled**.</span></span> <span data-ttu-id="3f74c-148">Los usuarios pueden determinar si desean enviar correo de voz para que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="3f74c-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="3f74c-149">Se pueden redirigir las llamadas entrantes para llamar a grupos</span><span class="sxs-lookup"><span data-stu-id="3f74c-149">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="3f74c-150">Esta configuración controla si se pueden reenviar las llamadas entrantes a un grupo de llamada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="3f74c-151">Permitir la delegación de las llamadas entrantes y salientes</span><span class="sxs-lookup"><span data-stu-id="3f74c-151">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="3f74c-152">Esta configuración permite que las llamadas entrantes se enrutan a los delegados, permitir que los delegados realizar llamadas salientes en nombre de los usuarios para quienes se delega permisos.</span><span class="sxs-lookup"><span data-stu-id="3f74c-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="3f74c-153">Para obtener más información, vea [compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="3f74c-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="3f74c-154">Evitar el desvío de pago y enviar las llamadas a través de la RTC</span><span class="sxs-lookup"><span data-stu-id="3f74c-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="3f74c-155">Si se establece en \*\*\*\* va a enviar las llamadas a través de la RTC e incurrir en los cargos en lugar de enviarlos a través de la red y omitir el cuotas.</span><span class="sxs-lookup"><span data-stu-id="3f74c-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="3f74c-156">No disponible en no disponible está disponible mientras se encuentre en una llamada</span><span class="sxs-lookup"><span data-stu-id="3f74c-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="3f74c-157">No disponible en no disponible (las opciones de disponibilidad)) es un nuevo valor en los equipos que se administran las directivas de llamada que le permite configurar las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada se pondrá en espera.</span><span class="sxs-lookup"><span data-stu-id="3f74c-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="3f74c-158">Se pueden rechazar las llamadas entrantes o nuevo con una señal de ocupado.</span><span class="sxs-lookup"><span data-stu-id="3f74c-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="3f74c-159">Puede habilitar las opciones de disponibilidad en el nivel de inquilino o en el nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="3f74c-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="3f74c-160">Independientemente de cómo se configuran las opciones de disponibilidad, los usuarios de una llamada o conferencia o aquellos con una llamada en espera no se les impide iniciar nuevas llamadas o conferencias.</span><span class="sxs-lookup"><span data-stu-id="3f74c-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="3f74c-161">Esta opción está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f74c-161">This setting is disabled by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f74c-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f74c-162">See also</span></span>

[<span data-ttu-id="3f74c-163">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="3f74c-163">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
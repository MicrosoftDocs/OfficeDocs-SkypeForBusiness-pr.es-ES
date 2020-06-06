---
title: Directivas de llamadas en Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo crear, modificar y agregar usuarios a directivas de llamadas personalizadas en Microsoft Teams, así como diversas configuraciones de la Directiva de llamadas.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "44592825"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="78612-103">Directivas de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="78612-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="78612-104">En Microsoft Teams, las directivas de llamadas controlan qué características de llamadas y desvío de llamadas están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="78612-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="78612-105">Las políticas de llamadas determinan si un usuario puede hacer llamadas privadas, usar el desvío de llamadas o llamar de forma simultánea a otros usuarios o números de teléfono externos, enrutar llamadas al buzón de voz, enviar llamadas a grupos de llamadas, usar la delegación para llamadas entrantes y salientes, etc.</span><span class="sxs-lookup"><span data-stu-id="78612-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="78612-106">Se crea automáticamente una directiva global predeterminada, pero los administradores también pueden crear y asignar directivas de llamadas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="78612-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="78612-107">Crear una directiva de llamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="78612-107">Create a custom calling policy</span></span>

<span data-ttu-id="78612-108">Siga estos pasos para crear una directiva de llamadas personalizada.</span><span class="sxs-lookup"><span data-stu-id="78612-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="78612-109">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="78612-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="78612-110">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="78612-110">Select **Add**.</span></span>
3. <span data-ttu-id="78612-111">Activa o desactiva las características que deseas usar en tu Directiva de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78612-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="78612-112">Para controlar si los usuarios pueden enrutar llamadas entrantes al buzón de voz, seleccione **habilitado** o controlado por el **usuario**.</span><span class="sxs-lookup"><span data-stu-id="78612-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="78612-113">Para evitar el enrutamiento al buzón de voz, seleccione **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="78612-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="78612-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78612-114">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="78612-115">Modificar una directiva de llamadas existente</span><span class="sxs-lookup"><span data-stu-id="78612-115">Modify an existing calling policy</span></span>

<span data-ttu-id="78612-116">Siga estos pasos para modificar una directiva de llamadas existente.</span><span class="sxs-lookup"><span data-stu-id="78612-116">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="78612-117">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="78612-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="78612-118">Haga clic en junto a la Directiva que desea modificar y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="78612-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="78612-119">Realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78612-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="78612-120">Asignar una directiva de llamadas personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="78612-120">Assign a custom calling policy to users</span></span>

<span data-ttu-id="78612-121">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="78612-121">To assign a policy to one user:</span></span>

1. <span data-ttu-id="78612-122">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="78612-122">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="78612-123">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="78612-123">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="78612-124">En **Directiva de llamada**, seleccione la Directiva de llamada que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="78612-124">Under **Calling policy**, select the calling policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="78612-125">Para asignar una directiva a varios usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="78612-125">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="78612-126">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.</span><span class="sxs-lookup"><span data-stu-id="78612-126">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="78612-127">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="78612-127">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="78612-128">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="78612-128">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="78612-129">Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="78612-129">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="78612-130">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78612-130">Or, you can also do the following:</span></span>

1. <span data-ttu-id="78612-131">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="78612-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="78612-132">Haga clic a la izquierda del nombre de la directiva para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="78612-132">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="78612-133">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="78612-133">Select **Manage users**.</span></span>
4. <span data-ttu-id="78612-134">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="78612-134">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="78612-135">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="78612-135">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="78612-136">Cuando termine de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78612-136">After you finish adding users, select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="78612-137">Configuración de la Directiva de llamadas</span><span class="sxs-lookup"><span data-stu-id="78612-137">Calling policy settings</span></span>

<span data-ttu-id="78612-138">Esta es la configuración que puede configurar para las directivas de llamada.</span><span class="sxs-lookup"><span data-stu-id="78612-138">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="78612-139">Realizar llamadas privadas</span><span class="sxs-lookup"><span data-stu-id="78612-139">Make private calls</span></span>

<span data-ttu-id="78612-140">Esta opción controla todas las capacidades de llamadas de Teams.</span><span class="sxs-lookup"><span data-stu-id="78612-140">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="78612-141">Desactive esta opción para desactivar toda la funcionalidad de llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="78612-141">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="78612-142">Desvío de llamadas y llamadas simultáneas a las personas de su organización</span><span class="sxs-lookup"><span data-stu-id="78612-142">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="78612-143">Esta configuración controla si las llamadas entrantes pueden desviarse a otros usuarios o pueden llamar a otra persona al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="78612-143">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="78612-144">Desvío de llamadas y llamadas simultáneas a números de teléfono externos</span><span class="sxs-lookup"><span data-stu-id="78612-144">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="78612-145">Esta configuración controla si las llamadas entrantes pueden desviarse a un número externo o pueden sonar un número externo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="78612-145">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="78612-146">El buzón de voz está disponible para enrutar llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="78612-146">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="78612-147">Esta configuración permite que las llamadas entrantes se envíen al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="78612-147">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="78612-148">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="78612-148">Valid options are:</span></span>

- <span data-ttu-id="78612-149">**Habilitado** El buzón de voz siempre está disponible para las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="78612-149">**Enabled** Voicemail is always available for inbound calls.</span></span> 
- <span data-ttu-id="78612-150">**Desactivado**  El buzón de voz no está disponible para llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="78612-150">**Disabled**  Voicemail is not available for inbound calls.</span></span> 
- <span data-ttu-id="78612-151">**Controlado** por el usuario Los usuarios pueden determinar si desean que el buzón de voz esté disponible.</span><span class="sxs-lookup"><span data-stu-id="78612-151">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="78612-152">Las llamadas entrantes se pueden enrutar a grupos de llamadas</span><span class="sxs-lookup"><span data-stu-id="78612-152">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="78612-153">Esta configuración controla si las llamadas entrantes se pueden desviar a un grupo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78612-153">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="78612-154">Permitir la delegación de llamadas entrantes y salientes</span><span class="sxs-lookup"><span data-stu-id="78612-154">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="78612-155">Esta configuración permite que las llamadas entrantes se enruten a delegados, lo que permite a los delegados hacer llamadas salientes en nombre de los usuarios para los que han delegado permisos.</span><span class="sxs-lookup"><span data-stu-id="78612-155">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="78612-156">Para obtener más información, consulte [compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="78612-156">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="78612-157">Evitar la omisión de peajes y enviar llamadas a través de la RTC</span><span class="sxs-lookup"><span data-stu-id="78612-157">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="78612-158">Si se establece **en activado** , se enviarán llamadas a través de la RTC y se provocarán cargos, en lugar de enviarlos por la red y omitir los peajes.</span><span class="sxs-lookup"><span data-stu-id="78612-158">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="78612-159">El uso ocupado está disponible mientras estás en una llamada</span><span class="sxs-lookup"><span data-stu-id="78612-159">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="78612-160">Ocupado en ocupado (opciones de ocupado) es una nueva opción que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o una conferencia o hace una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="78612-160">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="78612-161">Las llamadas nuevas o entrantes pueden rechazarse con una señal de ocupado.</span><span class="sxs-lookup"><span data-stu-id="78612-161">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="78612-162">Puede habilitar las opciones de ocupado en el nivel de espacio empresarial o en el nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="78612-162">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="78612-163">Independientemente de la configuración de las opciones de ocupado, los usuarios de una llamada o conferencia, o aquellos con una llamada en espera, no pueden iniciar nuevas llamadas o conferencias.</span><span class="sxs-lookup"><span data-stu-id="78612-163">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="78612-164">Esta opción está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="78612-164">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="78612-165">Permitir llamadas RTC en Web</span><span class="sxs-lookup"><span data-stu-id="78612-165">Allow web PSTN calling</span></span>

<span data-ttu-id="78612-166">Esta configuración permite a los usuarios llamar a números de RTC mediante el cliente web de Teams.</span><span class="sxs-lookup"><span data-stu-id="78612-166">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="78612-167">Permitir música en espera</span><span class="sxs-lookup"><span data-stu-id="78612-167">Allow music on hold</span></span>

<span data-ttu-id="78612-168">Esta configuración le permite activar o desactivar la música en espera cuando una persona que llama RTC se coloca en espera.</span><span class="sxs-lookup"><span data-stu-id="78612-168">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="78612-169">Está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="78612-169">It's turned on by default.</span></span> <span data-ttu-id="78612-170">Esta configuración no se aplica a las características del delegado llamar y el jefe, y actualmente solo está disponible a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78612-170">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="78612-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="78612-171">See also</span></span>

[<span data-ttu-id="78612-172">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="78612-172">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

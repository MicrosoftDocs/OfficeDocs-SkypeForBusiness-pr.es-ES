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
ms.openlocfilehash: 030be626574e7acd3aa2116595acaba757eaa5af
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44942028"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="82e08-103">Directivas de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82e08-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="82e08-104">En Microsoft Teams, las directivas de llamadas controlan qué características de llamadas y desvío de llamadas están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="82e08-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="82e08-105">Las políticas de llamadas determinan si un usuario puede hacer llamadas privadas, usar el desvío de llamadas o llamar de forma simultánea a otros usuarios o números de teléfono externos, enrutar llamadas al buzón de voz, enviar llamadas a grupos de llamadas, usar la delegación para llamadas entrantes y salientes, etc.</span><span class="sxs-lookup"><span data-stu-id="82e08-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="82e08-106">Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="82e08-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="82e08-107">Crear una directiva de llamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="82e08-107">Create a custom calling policy</span></span>

<span data-ttu-id="82e08-108">Siga estos pasos para crear una directiva de llamadas personalizada.</span><span class="sxs-lookup"><span data-stu-id="82e08-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="82e08-109">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="82e08-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="82e08-110">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="82e08-110">Select **Add**.</span></span>
3. <span data-ttu-id="82e08-111">Activa o desactiva las características que deseas usar en tu Directiva de llamadas.</span><span class="sxs-lookup"><span data-stu-id="82e08-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="82e08-112">Para controlar si los usuarios pueden enrutar llamadas entrantes al buzón de voz, seleccione **habilitado** o controlado por el **usuario**.</span><span class="sxs-lookup"><span data-stu-id="82e08-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="82e08-113">Para evitar el enrutamiento al buzón de voz, seleccione **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="82e08-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="82e08-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="82e08-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="82e08-115">Modificar una directiva de llamada</span><span class="sxs-lookup"><span data-stu-id="82e08-115">Edit a calling policy</span></span>

<span data-ttu-id="82e08-116">Siga estos pasos para editar una directiva de llamadas existente.</span><span class="sxs-lookup"><span data-stu-id="82e08-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="82e08-117">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="82e08-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="82e08-118">Haga clic en junto a la Directiva que desea modificar y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82e08-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="82e08-119">Realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="82e08-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="82e08-120">Asignar una directiva de llamadas personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="82e08-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="82e08-121">Configuración de la Directiva de llamadas</span><span class="sxs-lookup"><span data-stu-id="82e08-121">Calling policy settings</span></span>

<span data-ttu-id="82e08-122">Esta es la configuración que puede configurar para las directivas de llamada.</span><span class="sxs-lookup"><span data-stu-id="82e08-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="82e08-123">Realizar llamadas privadas</span><span class="sxs-lookup"><span data-stu-id="82e08-123">Make private calls</span></span>

<span data-ttu-id="82e08-124">Esta opción controla todas las capacidades de llamadas de Teams.</span><span class="sxs-lookup"><span data-stu-id="82e08-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="82e08-125">Desactive esta opción para desactivar toda la funcionalidad de llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="82e08-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="82e08-126">Desvío de llamadas y llamadas simultáneas a las personas de su organización</span><span class="sxs-lookup"><span data-stu-id="82e08-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="82e08-127">Esta configuración controla si las llamadas entrantes pueden desviarse a otros usuarios o pueden llamar a otra persona al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="82e08-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="82e08-128">Desvío de llamadas y llamadas simultáneas a números de teléfono externos</span><span class="sxs-lookup"><span data-stu-id="82e08-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="82e08-129">Esta configuración controla si las llamadas entrantes pueden desviarse a un número externo o pueden sonar un número externo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="82e08-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="82e08-130">El buzón de voz está disponible para enrutar llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="82e08-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="82e08-131">Esta configuración permite que las llamadas entrantes se envíen al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="82e08-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="82e08-132">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="82e08-132">Valid options are:</span></span>

- <span data-ttu-id="82e08-133">**Habilitado** El buzón de voz siempre está disponible para las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="82e08-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="82e08-134">**Desactivado**  El buzón de voz no está disponible para llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="82e08-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="82e08-135">**Controlado** por el usuario Los usuarios pueden determinar si desean que el buzón de voz esté disponible.</span><span class="sxs-lookup"><span data-stu-id="82e08-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="82e08-136">Las llamadas entrantes se pueden enrutar a grupos de llamadas</span><span class="sxs-lookup"><span data-stu-id="82e08-136">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="82e08-137">Esta configuración controla si las llamadas entrantes se pueden desviar a un grupo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="82e08-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="82e08-138">Permitir la delegación de llamadas entrantes y salientes</span><span class="sxs-lookup"><span data-stu-id="82e08-138">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="82e08-139">Esta configuración permite que las llamadas entrantes se enruten a delegados, lo que permite a los delegados hacer llamadas salientes en nombre de los usuarios para los que han delegado permisos.</span><span class="sxs-lookup"><span data-stu-id="82e08-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="82e08-140">Para obtener más información, consulte [compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="82e08-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="82e08-141">Evitar la omisión de peajes y enviar llamadas a través de la RTC</span><span class="sxs-lookup"><span data-stu-id="82e08-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="82e08-142">Si se establece **en activado** , se enviarán llamadas a través de la RTC y se provocarán cargos, en lugar de enviarlos por la red y omitir los peajes.</span><span class="sxs-lookup"><span data-stu-id="82e08-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="82e08-143">El uso ocupado está disponible mientras estás en una llamada</span><span class="sxs-lookup"><span data-stu-id="82e08-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="82e08-144">Ocupado en ocupado (opciones de ocupado) es una nueva opción que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o una conferencia o hace una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="82e08-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="82e08-145">Las llamadas nuevas o entrantes pueden rechazarse con una señal de ocupado.</span><span class="sxs-lookup"><span data-stu-id="82e08-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="82e08-146">Puede habilitar las opciones de ocupado en el nivel de espacio empresarial o en el nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="82e08-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="82e08-147">Independientemente de la configuración de las opciones de ocupado, los usuarios de una llamada o conferencia, o aquellos con una llamada en espera, no pueden iniciar nuevas llamadas o conferencias.</span><span class="sxs-lookup"><span data-stu-id="82e08-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="82e08-148">Esta opción está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="82e08-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="82e08-149">Permitir llamadas RTC en Web</span><span class="sxs-lookup"><span data-stu-id="82e08-149">Allow web PSTN calling</span></span>

<span data-ttu-id="82e08-150">Esta configuración permite a los usuarios llamar a números de RTC mediante el cliente web de Teams.</span><span class="sxs-lookup"><span data-stu-id="82e08-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="82e08-151">Permitir música en espera</span><span class="sxs-lookup"><span data-stu-id="82e08-151">Allow music on hold</span></span>

<span data-ttu-id="82e08-152">Esta configuración le permite activar o desactivar la música en espera cuando una persona que llama RTC se coloca en espera.</span><span class="sxs-lookup"><span data-stu-id="82e08-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="82e08-153">Está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="82e08-153">It's turned on by default.</span></span> <span data-ttu-id="82e08-154">Esta configuración no se aplica a las características del delegado llamar y el jefe, y actualmente solo está disponible a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82e08-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="82e08-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="82e08-155">Related topics</span></span>

[<span data-ttu-id="82e08-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="82e08-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="82e08-157">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="82e08-157">Assign policies to your users in Teams</span></span>](assign-policies.md)

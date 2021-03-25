---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo habilitar Location-Based enrutamiento directo, incluida la habilitación para usuarios, sitios de red, configuraciones de puerta de enlace y directivas de llamadas.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120581"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="d5f0a-103">Habilitar enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="d5f0a-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="d5f0a-104">Antes de seguir los pasos de este artículo, asegúrese de que ha leído [Plan de enrutamiento Location-Based](location-based-routing-plan.md) para enrutamiento directo y ha completado los pasos de Configurar la configuración de red para Location-Based [enrutamiento.](location-based-routing-configure-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="d5f0a-105">En este artículo se describe cómo habilitar Location-Based enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="d5f0a-106">Después de implementar enrutamiento directo del sistema telefónico y configurar regiones de red, sitios y subredes, ya está listo para habilitar el enrutamiento Location-Based teléfono.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="d5f0a-107">Para completar los pasos de este artículo, necesitará familiarizarse con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="d5f0a-108">Para obtener más información, vea [Información general de PowerShell de Teams.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="d5f0a-109">Debe habilitar Location-Based enrutamiento para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5f0a-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="d5f0a-110">Usuarios</span><span class="sxs-lookup"><span data-stu-id="d5f0a-110">Users</span></span>
- <span data-ttu-id="d5f0a-111">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="d5f0a-111">Network sites</span></span>
- <span data-ttu-id="d5f0a-112">Configuraciones de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="d5f0a-112">Gateway configurations</span></span>
- <span data-ttu-id="d5f0a-113">Directivas de llamada</span><span class="sxs-lookup"><span data-stu-id="d5f0a-113">Calling policies</span></span>

<span data-ttu-id="d5f0a-114">Puede usar el Centro [de administración de Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l para habilitar Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d5f0a-115">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d5f0a-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="d5f0a-116">Habilitar Location-Based enrutamiento para usuarios</span><span class="sxs-lookup"><span data-stu-id="d5f0a-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="d5f0a-117">Cree una directiva de enrutamiento de voz y asigne usos RTC a la directiva.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="d5f0a-118">Al asignar usos de RTC a una directiva, asegúrese de realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d5f0a-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="d5f0a-119">Use los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC local en el sitio.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="d5f0a-120">Use los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan Location-Based restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="d5f0a-121">Asigne la directiva de enrutamiento de voz a los usuarios que requieran que se exijan restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="d5f0a-122">Para obtener más información sobre cómo crear directivas de enrutamiento de voz y asignarlas a los usuarios, vea Administrar directivas de enrutamiento de voz [en Microsoft Teams.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="d5f0a-123">Habilitar Location-Based enrutamiento para sitios de red</span><span class="sxs-lookup"><span data-stu-id="d5f0a-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="d5f0a-124">Habilite Location-Based enrutamiento para los sitios que necesitan aplicar restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="d5f0a-125">Para ello, en la navegación izquierda del Centro de administración de Microsoft Teams, vaya a Topología de red de ubicaciones, seleccione un sitio de red, haga clic en Editar y, a continuación, active Enrutamiento basado en  >   **ubicación.** </span><span class="sxs-lookup"><span data-stu-id="d5f0a-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="d5f0a-126">Para obtener más información, vea [Administrar la topología de red.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="d5f0a-127">Habilitar Location-Based enrutamiento de puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="d5f0a-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="d5f0a-128">Habilite Location-Based enrutamiento a puertas de enlace que enrute llamadas a puertas de enlace RTC que enrute llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="d5f0a-129">En el panel de navegación izquierdo, vaya a **Enrutamiento** directo  >  **de** voz y, a continuación, haga clic en la pestaña **SBC.**</span><span class="sxs-lookup"><span data-stu-id="d5f0a-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="d5f0a-130">Seleccione el SBC y, a continuación, haga clic **en Editar.**</span><span class="sxs-lookup"><span data-stu-id="d5f0a-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="d5f0a-131">En **Enrutamiento basado en ubicación y optimización multimedia,** active Habilitar enrutamiento basado en **ubicación.**</span><span class="sxs-lookup"><span data-stu-id="d5f0a-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="d5f0a-132">Especifique el id. de sitio de la puerta de enlace y, después, establezca el modo de omisión.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="d5f0a-133">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="d5f0a-134">Habilitar Location-Based enrutamiento para directivas de llamadas</span><span class="sxs-lookup"><span data-stu-id="d5f0a-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="d5f0a-135">Para exigir Location-Based enrutamiento para usuarios específicos, configure la directiva de llamadas del usuario para evitar la omisión de pago RTC.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="d5f0a-136">Para ello, active la configuración Evitar la omisión **de** pago en la directiva de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="d5f0a-137">Para obtener más información, vea [Directivas de llamadas en Teams.](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="d5f0a-138">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5f0a-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="d5f0a-139">Habilitar Location-Based enrutamiento para usuarios</span><span class="sxs-lookup"><span data-stu-id="d5f0a-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="d5f0a-140">Use el cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer los usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="d5f0a-141">Para varios usos, separe cada uso con una coma.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="d5f0a-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5f0a-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="d5f0a-143">Use el cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz para asociar al usuario con los usos RTC adecuados.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="d5f0a-144">Al asignar usos rtc a una directiva de enrutamiento de voz, asegúrese de realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d5f0a-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="d5f0a-145">Usar los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC local en el sitio</span><span class="sxs-lookup"><span data-stu-id="d5f0a-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="d5f0a-146">Use los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan Location-Based restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="d5f0a-147">En este ejemplo, creamos dos nuevas directivas de enrutamiento de voz y les asignamos usos rtc.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="d5f0a-148">En la tabla siguiente se muestran las directivas de enrutamiento de voz definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="d5f0a-149">Directiva de enrutamiento de voz 1</span><span class="sxs-lookup"><span data-stu-id="d5f0a-149">Voice routing policy 1</span></span>|<span data-ttu-id="d5f0a-150">Directiva de enrutamiento de voz 2</span><span class="sxs-lookup"><span data-stu-id="d5f0a-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="d5f0a-151">Id. de directiva de voz en línea</span><span class="sxs-lookup"><span data-stu-id="d5f0a-151">Online voice policy ID</span></span>   |<span data-ttu-id="d5f0a-152">Directiva de enrutamiento de voz en línea de Delhi</span><span class="sxs-lookup"><span data-stu-id="d5f0a-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="d5f0a-153">Directiva de enrutamiento de voz en línea de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d5f0a-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="d5f0a-154">Usos de RTC en línea</span><span class="sxs-lookup"><span data-stu-id="d5f0a-154">Online PSTN usages</span></span>  |<span data-ttu-id="d5f0a-155">Larga distancia</span><span class="sxs-lookup"><span data-stu-id="d5f0a-155">Long Distance</span></span>  |<span data-ttu-id="d5f0a-156">Distancia larga, Local, Interno</span><span class="sxs-lookup"><span data-stu-id="d5f0a-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="d5f0a-157">Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar directivas de enrutamiento de voz en línea a los usuarios que requieren que se exijan restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="d5f0a-158">Habilitar Location-Based enrutamiento para sitios de red</span><span class="sxs-lookup"><span data-stu-id="d5f0a-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="d5f0a-159">Use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar Location-Based enrutamiento y asociar directivas de enrutamiento de voz a los sitios de red que necesitan aplicar restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="d5f0a-160">En este ejemplo, habilitamos Location-Based enrutamiento para el sitio de Delhi y el sitio de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="d5f0a-161">En la tabla siguiente se muestran los sitios habilitados para Location-Based enrutamiento en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="d5f0a-162">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="d5f0a-163">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="d5f0a-164">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="d5f0a-164">Site name</span></span>    |<span data-ttu-id="d5f0a-165">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="d5f0a-166">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="d5f0a-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="d5f0a-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="d5f0a-168">True</span><span class="sxs-lookup"><span data-stu-id="d5f0a-168">True</span></span>    |<span data-ttu-id="d5f0a-169">True</span><span class="sxs-lookup"><span data-stu-id="d5f0a-169">True</span></span>    |
    |<span data-ttu-id="d5f0a-170">Subredes</span><span class="sxs-lookup"><span data-stu-id="d5f0a-170">Subnets</span></span>     |<span data-ttu-id="d5f0a-171">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="d5f0a-172">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="d5f0a-173">Habilitar Location-Based enrutamiento de puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="d5f0a-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="d5f0a-174">Use el cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada puerta de enlace o sitio de red.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="d5f0a-175">Si varias puertas de enlace están asociadas a un sistema (por ejemplo, Puerta de enlace o PBX), modifique cada puerta de enlace para habilitar Location-Based de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="d5f0a-176">En este ejemplo, creamos una configuración de puerta de enlace para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="d5f0a-177">Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="d5f0a-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="d5f0a-178">Use el cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar Location-Based enrutamiento para las puertas de enlace que necesitan aplicar restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="d5f0a-179">Habilite Location-Based enrutamiento a puertas de enlace que enrute llamadas a puertas de enlace RTC que enrute llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="d5f0a-180">En este ejemplo, habilitamos Location-Based enrutamiento para cada puerta de enlace asociada a puertas de enlace RTC en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="d5f0a-181">No habilite el enrutamiento Location-Based las puertas de enlace que no enrutar llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="d5f0a-182">Sin embargo, aún tiene que asociar la puerta de enlace al sitio de red donde se encuentra el sistema.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="d5f0a-183">Esto se debe a Location-Based restricciones de enrutamiento deben aplicarse para las llamadas RTC que lleguen a los puntos de conexión conectados a través de esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="d5f0a-184">En este ejemplo, Location-Based enrutamiento no está habilitado para cada puerta de enlace asociada a sistemas PBX en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="d5f0a-185">Habilitar Location-Based enrutamiento para directivas de llamadas</span><span class="sxs-lookup"><span data-stu-id="d5f0a-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="d5f0a-186">Para exigir Location-Based enrutamiento para usuarios específicos, configure la directiva de voz de los usuarios para evitar la omisión de pago de PTSN.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="d5f0a-187">Use el cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el Location-Based mediante la prevención de la omisión de pago RTC.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="d5f0a-188">En este ejemplo, evitamos la omisión de pago RTC a las directivas de llamadas de Usuario1.</span><span class="sxs-lookup"><span data-stu-id="d5f0a-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="d5f0a-189">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d5f0a-189">Related topics</span></span>

- [<span data-ttu-id="d5f0a-190">Configuración de red para características de voz en la nube en Teams</span><span class="sxs-lookup"><span data-stu-id="d5f0a-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
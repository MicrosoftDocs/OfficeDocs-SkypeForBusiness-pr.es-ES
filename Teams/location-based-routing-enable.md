---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Aprenda a habilitar el enrutamiento basado en la ubicación para el enrutamiento directo, lo que incluye habilitarlo para los usuarios, los sitios de red, las configuraciones de puerta de enlace y las directivas de llamadas.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69f2ee37e63f83d6fc1d19ea733ff44ad23e7011
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158997"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="3caf1-103">Habilitar enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="3caf1-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="3caf1-104">Antes de seguir los pasos de este artículo, asegúrese de que ha leído [planear el enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md) y completado los pasos de [configurar la configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3caf1-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="3caf1-105">En este artículo se describe cómo habilitar el enrutamiento basado en la ubicación para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="3caf1-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="3caf1-106">Después de implementar el enrutamiento directo de un sistema telefónico y configurar regiones, sitios y subredes de la red, está listo para habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="3caf1-107">Para completar los pasos de este artículo, necesitará cierta familiaridad con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3caf1-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="3caf1-108">Para obtener más información, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3caf1-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="3caf1-109">Debe habilitar el enrutamiento basado en la ubicación para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3caf1-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="3caf1-110">Usuarios</span><span class="sxs-lookup"><span data-stu-id="3caf1-110">Users</span></span>
- <span data-ttu-id="3caf1-111">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="3caf1-111">Network sites</span></span>
- <span data-ttu-id="3caf1-112">Configuraciones de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="3caf1-112">Gateway configurations</span></span>
- <span data-ttu-id="3caf1-113">Directivas de llamadas</span><span class="sxs-lookup"><span data-stu-id="3caf1-113">Calling policies</span></span>

<span data-ttu-id="3caf1-114">Puede usar el [centro de administración de Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l para habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3caf1-115">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3caf1-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="3caf1-116">Habilitar el enrutamiento basado en la ubicación para los usuarios</span><span class="sxs-lookup"><span data-stu-id="3caf1-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="3caf1-117">Crear una directiva de enrutamiento de voz y asignar usos de RTC a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3caf1-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="3caf1-118">Cuando asigne usos de RTC a una directiva, asegúrese de realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3caf1-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="3caf1-119">Use usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC local para el sitio.</span><span class="sxs-lookup"><span data-stu-id="3caf1-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="3caf1-120">Use usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="3caf1-121">Asigne la Directiva de enrutamiento de voz a los usuarios que necesiten exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3caf1-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="3caf1-122">Para obtener más información sobre cómo crear directivas de enrutamiento de voz y asignarlas a usuarios, consulte [Administrar directivas de enrutamiento de voz en Microsoft Teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3caf1-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="3caf1-123">Habilitar el enrutamiento basado en la ubicación de los sitios de red</span><span class="sxs-lookup"><span data-stu-id="3caf1-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="3caf1-124">Habilite el enrutamiento basado en la ubicación para los sitios que necesitan exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3caf1-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="3caf1-125">Para ello, en el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones** > **de red**, seleccione un sitio de red, haga clic en **Editar**y, a continuación, active el **enrutamiento basado**en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="3caf1-126">Para obtener más información, consulte [administrar la topología de red](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="3caf1-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="3caf1-127">Habilitar enrutamiento basado en la ubicación para puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="3caf1-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="3caf1-128">Habilite el enrutamiento basado en la ubicación a las puertas de enlace que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3caf1-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="3caf1-129">En el navegación de la izquierda, vaya a enrutamiento de **voz** > **directo**y, a continuación, haga clic en la pestaña **SBCS** .</span><span class="sxs-lookup"><span data-stu-id="3caf1-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="3caf1-130">Seleccione el SBC y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3caf1-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="3caf1-131">En la **optimización de enrutamiento y multimedia basado**en la ubicación, Active **Habilitar enrutamiento basado en la ubicación**.</span><span class="sxs-lookup"><span data-stu-id="3caf1-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="3caf1-132">Especifique el identificador del sitio de la puerta de enlace y, a continuación, establezca el modo de omisión.</span><span class="sxs-lookup"><span data-stu-id="3caf1-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="3caf1-133">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="3caf1-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="3caf1-134">Habilitar el enrutamiento basado en la ubicación para las directivas de llamadas</span><span class="sxs-lookup"><span data-stu-id="3caf1-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="3caf1-135">Para aplicar el enrutamiento basado en la ubicación para usuarios específicos, configure la Directiva de llamadas del usuario para evitar la omisión de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="3caf1-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="3caf1-136">Para ello, active la opción **evitar omisión de pago** en la política de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3caf1-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="3caf1-137">Para obtener más información, consulte [directivas de llamadas en Teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3caf1-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="3caf1-138">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3caf1-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="3caf1-139">Habilitar el enrutamiento basado en la ubicación para los usuarios</span><span class="sxs-lookup"><span data-stu-id="3caf1-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="3caf1-140">Use el cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="3caf1-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="3caf1-141">Para varios usos, separe cada uso con una coma.</span><span class="sxs-lookup"><span data-stu-id="3caf1-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="3caf1-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3caf1-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="3caf1-143">Use el cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz y asociar al usuario los usos de RTC apropiados.</span><span class="sxs-lookup"><span data-stu-id="3caf1-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="3caf1-144">Cuando asigne usos de RTC a una directiva de enrutamiento de voz, asegúrese de realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3caf1-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="3caf1-145">Usar usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC local para el sitio</span><span class="sxs-lookup"><span data-stu-id="3caf1-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="3caf1-146">Use usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="3caf1-147">En este ejemplo, creamos dos nuevas directivas de enrutamiento de voz y se les asignan usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="3caf1-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="3caf1-148">En la tabla siguiente se muestran las directivas de enrutamiento de voz definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3caf1-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="3caf1-149">Directiva de enrutamiento de voz 1</span><span class="sxs-lookup"><span data-stu-id="3caf1-149">Voice routing policy 1</span></span>|<span data-ttu-id="3caf1-150">Directiva de enrutamiento de voz 2</span><span class="sxs-lookup"><span data-stu-id="3caf1-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="3caf1-151">IDENTIFICADOR de directiva de voz en línea</span><span class="sxs-lookup"><span data-stu-id="3caf1-151">Online voice policy ID</span></span>   |<span data-ttu-id="3caf1-152">Directiva de enrutamiento de voz en línea de Delhi</span><span class="sxs-lookup"><span data-stu-id="3caf1-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="3caf1-153">Directiva de enrutamiento de voz en línea de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3caf1-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="3caf1-154">Usos de RTC en línea</span><span class="sxs-lookup"><span data-stu-id="3caf1-154">Online PSTN usages</span></span>  |<span data-ttu-id="3caf1-155">Larga distancia</span><span class="sxs-lookup"><span data-stu-id="3caf1-155">Long Distance</span></span>  |<span data-ttu-id="3caf1-156">Larga distancia, local, interna</span><span class="sxs-lookup"><span data-stu-id="3caf1-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="3caf1-157">Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar directivas de enrutamiento de voz en línea a los usuarios que necesiten exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3caf1-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="3caf1-158">Habilitar el enrutamiento basado en la ubicación de los sitios de red</span><span class="sxs-lookup"><span data-stu-id="3caf1-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="3caf1-159">Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar el enrutamiento basado en la ubicación y para asociar directivas de enrutamiento de voz a los sitios de red que necesitan exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3caf1-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="3caf1-160">En este ejemplo, habilitamos el enrutamiento basado en la ubicación para el sitio de Delhi y el sitio de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="3caf1-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="3caf1-161">En la tabla siguiente se muestran los sitios habilitados para el enrutamiento basado en la ubicación en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3caf1-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="3caf1-162">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3caf1-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="3caf1-163">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3caf1-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="3caf1-164">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="3caf1-164">Site name</span></span>    |<span data-ttu-id="3caf1-165">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3caf1-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="3caf1-166">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3caf1-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="3caf1-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="3caf1-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="3caf1-168">True</span><span class="sxs-lookup"><span data-stu-id="3caf1-168">True</span></span>    |<span data-ttu-id="3caf1-169">True</span><span class="sxs-lookup"><span data-stu-id="3caf1-169">True</span></span>    |
    |<span data-ttu-id="3caf1-170">Subredes</span><span class="sxs-lookup"><span data-stu-id="3caf1-170">Subnets</span></span>     |<span data-ttu-id="3caf1-171">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3caf1-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="3caf1-172">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3caf1-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="3caf1-173">Habilitar enrutamiento basado en la ubicación para puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="3caf1-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="3caf1-174">Use el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada puerta de enlace o sitio de red.</span><span class="sxs-lookup"><span data-stu-id="3caf1-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="3caf1-175">Si hay varias puertas de enlace asociadas a un sistema (por ejemplo, puerta de enlace o PBX), modifique cada puerta de enlace para habilitar las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="3caf1-176">En este ejemplo, creamos una configuración de puerta de enlace para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3caf1-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="3caf1-177">Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="3caf1-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="3caf1-178">Use el cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar el enrutamiento basado en la ubicación para las puertas de enlace que necesitan exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3caf1-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="3caf1-179">Habilite el enrutamiento basado en la ubicación a las puertas de enlace que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3caf1-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="3caf1-180">En este ejemplo, habilitamos el enrutamiento basado en la ubicación para cada puerta de enlace que está asociada a las puertas de enlace RTC en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="3caf1-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="3caf1-181">No habilite el enrutamiento basado en la ubicación para puertas de enlace que no enruten llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="3caf1-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="3caf1-182">Sin embargo, aún tiene que asociar la puerta de enlace al sitio de red en el que se encuentra el sistema.</span><span class="sxs-lookup"><span data-stu-id="3caf1-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="3caf1-183">Esto se debe a que las restricciones de enrutamiento basadas en la ubicación deben exigirse para que las llamadas RTC lleguen a los puntos de conexión que se conectan a través de esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3caf1-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="3caf1-184">En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada puerta de enlace que está asociada a sistemas PBX de la Delhi y los sitios de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="3caf1-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="3caf1-185">Los puntos de conexión conectados a los sistemas que no enruten las llamadas a la RTC (por ejemplo, una PBX) tendrán restricciones similares a las de los usuarios de Teams habilitados para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-185">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="3caf1-186">Esto significa que estos usuarios pueden realizar y recibir llamadas a usuarios de Teams y desde ellos, independientemente de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="3caf1-186">This means that these users can place and receive calls to and from Teams users regardless of the user's location.</span></span> <span data-ttu-id="3caf1-187">También pueden realizar y recibir llamadas a y desde otros sistemas que no enruten las llamadas a la red PSTN (por ejemplo, un extremo conectado a otro sistema PBX), independientemente del sitio de red al que esté asociado el sistema.</span><span class="sxs-lookup"><span data-stu-id="3caf1-187">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="3caf1-188">Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas que implican puntos de conexión RTC estarán sujetas a las fuerzas de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3caf1-188">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="3caf1-189">Estas llamadas deben usar solo puertas de enlace RTC que estén definidas como locales para esos sistemas.</span><span class="sxs-lookup"><span data-stu-id="3caf1-189">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="3caf1-190">En la tabla siguiente se muestra la configuración de puerta de enlace de cuatro puertas de enlace en dos sitios de red diferentes: dos conectadas a puertas de enlace RTC y dos conectadas a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="3caf1-190">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="3caf1-191">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="3caf1-191">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="3caf1-192">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="3caf1-192">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="3caf1-193">PstnGateway: puerta de enlace 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3caf1-193">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="3caf1-194">Verdadero</span><span class="sxs-lookup"><span data-stu-id="3caf1-194">True</span></span>     |   <span data-ttu-id="3caf1-195">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3caf1-195">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="3caf1-196">PstnGateway: puerta de enlace 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="3caf1-196">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="3caf1-197">Verdadero</span><span class="sxs-lookup"><span data-stu-id="3caf1-197">True</span></span>      |      <span data-ttu-id="3caf1-198">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3caf1-198">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="3caf1-199">PstnGateway: puerta de enlace 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3caf1-199">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="3caf1-200">Falso</span><span class="sxs-lookup"><span data-stu-id="3caf1-200">False</span></span>     |     <span data-ttu-id="3caf1-201">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3caf1-201">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="3caf1-202">PstnGateway: puerta de enlace 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3caf1-202">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="3caf1-203">Falso</span><span class="sxs-lookup"><span data-stu-id="3caf1-203">False</span></span>     |    <span data-ttu-id="3caf1-204">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3caf1-204">Site 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="3caf1-205">Habilitar el enrutamiento basado en la ubicación para las directivas de llamadas</span><span class="sxs-lookup"><span data-stu-id="3caf1-205">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="3caf1-206">Para aplicar el enrutamiento basado en la ubicación para usuarios específicos, configure la Directiva de voz de los usuarios para evitar la omisión de RTC de pago.</span><span class="sxs-lookup"><span data-stu-id="3caf1-206">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="3caf1-207">Use el cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el enrutamiento basado en la ubicación evitando la omisión de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="3caf1-207">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="3caf1-208">En este ejemplo, evitamos la omisión de llamadas de RTC a directivas de llamadas de Usuario1.</span><span class="sxs-lookup"><span data-stu-id="3caf1-208">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="3caf1-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3caf1-209">Related topics</span></span>

- [<span data-ttu-id="3caf1-210">Configuración de red de las características de voz en la nube en Teams</span><span class="sxs-lookup"><span data-stu-id="3caf1-210">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)

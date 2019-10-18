---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo habilitar el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4acd03dfff78d5aae329492014b24e55b2f92ec9
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572027"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="1e0c8-103">Habilitar enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1e0c8-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="1e0c8-104">Antes de seguir los pasos de este artículo, asegúrese de que ha leído [planear el enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md) y completado los pasos de [configurar la configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1e0c8-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="1e0c8-105">En este artículo se describe cómo habilitar el enrutamiento basado en la ubicación para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="1e0c8-106">Después de implementar el enrutamiento directo de un sistema telefónico y configurar regiones, sitios y subredes de la red, está listo para habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="1e0c8-107">Para completar los pasos de este artículo, necesitará cierta familiaridad con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="1e0c8-108">Para obtener más información, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1e0c8-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="1e0c8-109">Debe habilitar el enrutamiento basado en la ubicación para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e0c8-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="1e0c8-110">Usuarios</span><span class="sxs-lookup"><span data-stu-id="1e0c8-110">Users</span></span>
- <span data-ttu-id="1e0c8-111">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="1e0c8-111">Network sites</span></span>
- <span data-ttu-id="1e0c8-112">Configuraciones de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="1e0c8-112">Gateway configurations</span></span>
- <span data-ttu-id="1e0c8-113">Directivas de llamadas</span><span class="sxs-lookup"><span data-stu-id="1e0c8-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="1e0c8-114">Habilitar el enrutamiento basado en la ubicación para los usuarios</span><span class="sxs-lookup"><span data-stu-id="1e0c8-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="1e0c8-115">Use el cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="1e0c8-116">Para varios usos, separe cada uso con una coma.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="1e0c8-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1e0c8-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="1e0c8-118">Use el cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz y asociar al usuario los usos de RTC apropiados.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="1e0c8-119">Cuando asigne usos de RTC a una directiva de enrutamiento de voz, asegúrese de realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1e0c8-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="1e0c8-120">Usar usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC local para el sitio</span><span class="sxs-lookup"><span data-stu-id="1e0c8-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="1e0c8-121">Use usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="1e0c8-122">En este ejemplo, creamos dos nuevas directivas de enrutamiento de voz y se les asignan usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="1e0c8-123">En la tabla siguiente se muestran las directivas de enrutamiento de voz definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="1e0c8-124">Directiva de enrutamiento de voz 1</span><span class="sxs-lookup"><span data-stu-id="1e0c8-124">Voice routing policy 1</span></span>|<span data-ttu-id="1e0c8-125">Directiva de enrutamiento de voz 2</span><span class="sxs-lookup"><span data-stu-id="1e0c8-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="1e0c8-126">IDENTIFICADOR de directiva de voz en línea</span><span class="sxs-lookup"><span data-stu-id="1e0c8-126">Online voice policy ID</span></span>   |<span data-ttu-id="1e0c8-127">Directiva de enrutamiento de voz en línea de Delhi</span><span class="sxs-lookup"><span data-stu-id="1e0c8-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="1e0c8-128">Directiva de enrutamiento de voz en línea de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1e0c8-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="1e0c8-129">Usos de RTC en línea</span><span class="sxs-lookup"><span data-stu-id="1e0c8-129">Online PSTN usages</span></span>  |<span data-ttu-id="1e0c8-130">Larga distancia</span><span class="sxs-lookup"><span data-stu-id="1e0c8-130">Long Distance</span></span>  |<span data-ttu-id="1e0c8-131">Larga distancia, local, interna</span><span class="sxs-lookup"><span data-stu-id="1e0c8-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="1e0c8-132">Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar directivas de enrutamiento de voz en línea a los usuarios que necesiten exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="1e0c8-133">Habilitar el enrutamiento basado en la ubicación de los sitios de red</span><span class="sxs-lookup"><span data-stu-id="1e0c8-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="1e0c8-134">Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar el enrutamiento basado en la ubicación y para asociar directivas de enrutamiento de voz a los sitios de red que necesitan exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="1e0c8-135">En este ejemplo, habilitamos el enrutamiento basado en la ubicación para el sitio de Delhi y el sitio de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="1e0c8-136">En la tabla siguiente se muestran los sitios habilitados para el enrutamiento basado en la ubicación en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="1e0c8-137">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="1e0c8-138">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="1e0c8-139">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="1e0c8-139">Site name</span></span>    |<span data-ttu-id="1e0c8-140">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="1e0c8-141">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="1e0c8-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="1e0c8-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="1e0c8-143">True</span><span class="sxs-lookup"><span data-stu-id="1e0c8-143">True</span></span>    |<span data-ttu-id="1e0c8-144">True</span><span class="sxs-lookup"><span data-stu-id="1e0c8-144">True</span></span>    |
    |<span data-ttu-id="1e0c8-145">Subredes</span><span class="sxs-lookup"><span data-stu-id="1e0c8-145">Subnets</span></span>     |<span data-ttu-id="1e0c8-146">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="1e0c8-147">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="1e0c8-148">Habilitar enrutamiento basado en la ubicación para puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="1e0c8-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="1e0c8-149">Use el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada puerta de enlace o sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="1e0c8-150">Si hay varias puertas de enlace asociadas a un sistema (por ejemplo, puerta de enlace o PBX), modifique cada puerta de enlace para habilitar las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="1e0c8-151">En este ejemplo, creamos una configuración de puerta de enlace para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="1e0c8-152">Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="1e0c8-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="1e0c8-153">Use el cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar el enrutamiento basado en la ubicación para las puertas de enlace que necesitan exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="1e0c8-154">Habilite el enrutamiento basado en la ubicación a las puertas de enlace que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="1e0c8-155">En este ejemplo, habilitamos el enrutamiento basado en la ubicación para cada puerta de enlace que está asociada a las puertas de enlace RTC en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="1e0c8-156">No habilite el enrutamiento basado en la ubicación para puertas de enlace que no enruten llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="1e0c8-157">Sin embargo, aún tiene que asociar la puerta de enlace al sitio de red en el que se encuentra el sistema.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="1e0c8-158">Esto se debe a que las restricciones de enrutamiento basadas en la ubicación deben exigirse para que las llamadas RTC lleguen a los puntos de conexión que se conectan a través de esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="1e0c8-159">En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada puerta de enlace que está asociada a sistemas PBX de la Delhi y los sitios de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="1e0c8-160">Los puntos de conexión conectados a los sistemas que no enruten las llamadas a la RTC (por ejemplo, una PBX) tendrán restricciones similares a las de los usuarios de Teams habilitados para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="1e0c8-161">Esto significa que estos usuarios pueden realizar y recibir llamadas a usuarios de Teams y desde ellos, independientemente de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="1e0c8-162">También pueden realizar y recibir llamadas a y desde otros sistemas que no enruten las llamadas a la red PSTN (por ejemplo, un extremo conectado a otro sistema PBX), independientemente del sitio de red al que esté asociado el sistema.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="1e0c8-163">Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas que implican puntos de conexión RTC estarán sujetas a las fuerzas de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="1e0c8-164">Estas llamadas deben usar solo puertas de enlace RTC que estén definidas como locales para esos sistemas.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="1e0c8-165">En la tabla siguiente se muestra la configuración de puerta de enlace de cuatro puertas de enlace en dos sitios de red diferentes: dos conectadas a puertas de enlace RTC y dos conectadas a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="1e0c8-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="1e0c8-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="1e0c8-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="1e0c8-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="1e0c8-168">PstnGateway: puerta de enlace 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="1e0c8-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="1e0c8-169">True</span><span class="sxs-lookup"><span data-stu-id="1e0c8-169">True</span></span>     |   <span data-ttu-id="1e0c8-170">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="1e0c8-171">PstnGateway: puerta de enlace 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="1e0c8-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="1e0c8-172">True</span><span class="sxs-lookup"><span data-stu-id="1e0c8-172">True</span></span>      |      <span data-ttu-id="1e0c8-173">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="1e0c8-174">PstnGateway: puerta de enlace 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="1e0c8-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="1e0c8-175">False</span><span class="sxs-lookup"><span data-stu-id="1e0c8-175">False</span></span>     |     <span data-ttu-id="1e0c8-176">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="1e0c8-177">PstnGateway: puerta de enlace 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="1e0c8-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="1e0c8-178">False</span><span class="sxs-lookup"><span data-stu-id="1e0c8-178">False</span></span>     |    <span data-ttu-id="1e0c8-179">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1e0c8-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="1e0c8-180">Habilitar el enrutamiento basado en la ubicación para las directivas de llamadas</span><span class="sxs-lookup"><span data-stu-id="1e0c8-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="1e0c8-181">Para aplicar el enrutamiento basado en la ubicación para usuarios específicos, configure la Directiva de voz de los usuarios para evitar la omisión de RTC de pago.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="1e0c8-182">Use el cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el enrutamiento basado en la ubicación evitando la omisión de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="1e0c8-183">En este ejemplo, evitamos la omisión de llamadas de RTC a directivas de llamadas de Usuario1.</span><span class="sxs-lookup"><span data-stu-id="1e0c8-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="1e0c8-184">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1e0c8-184">Related topics</span></span>
- [<span data-ttu-id="1e0c8-185">Planear enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1e0c8-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="1e0c8-186">Configuración de red de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="1e0c8-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="1e0c8-187">Terminología de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="1e0c8-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)

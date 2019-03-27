---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo habilitar el enrutamiento basados en ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886035"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="ce746-103">Habilitar enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="ce746-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="ce746-104">Antes de seguir los pasos descritos en este artículo, asegúrese de que ha leído [Plan Location-Based enrutamiento para el enrutamiento directo](location-based-routing-plan.md) y completado los pasos de [configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ce746-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="ce746-105">Este artículo describe cómo habilitar el enrutamiento basados en ubicación para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="ce746-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="ce746-106">Después de implementar el enrutamiento directo de teléfono del sistema y configurar regiones de red, sitios y subredes, estará listo habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="ce746-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="ce746-107">Para completar los pasos descritos en este artículo, necesitará un poco familiarizado con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce746-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="ce746-108">Para obtener más información, vea [Introducción a los equipos de PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ce746-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="ce746-109">Tiene que habilitar el enrutamiento basado en la ubicación para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce746-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="ce746-110">Usuarios</span><span class="sxs-lookup"><span data-stu-id="ce746-110">Users</span></span>
- <span data-ttu-id="ce746-111">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="ce746-111">Network sites</span></span>
- <span data-ttu-id="ce746-112">Configuraciones de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="ce746-112">Gateway configurations</span></span>
- <span data-ttu-id="ce746-113">Llamar a las directivas</span><span class="sxs-lookup"><span data-stu-id="ce746-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="ce746-114">Habilitar el enrutamiento basado en la ubicación para los usuarios</span><span class="sxs-lookup"><span data-stu-id="ce746-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="ce746-115">Use el cmdlet [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer los usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="ce746-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="ce746-116">Para varios usos, separe cada uso con una coma.</span><span class="sxs-lookup"><span data-stu-id="ce746-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="ce746-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ce746-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="ce746-118">Use el cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz para asociar el usuario con los usos de RTC adecuados.</span><span class="sxs-lookup"><span data-stu-id="ce746-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="ce746-119">Al asignar los usos de RTC a una directiva de enrutamiento de voz, asegúrese de que se realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ce746-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="ce746-120">Use los usos de RTC asociados a las rutas de voz que usar una puerta de enlace de RTC local para el sitio</span><span class="sxs-lookup"><span data-stu-id="ce746-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="ce746-121">Use los usos de RTC asociados a las rutas de voz que usar una puerta de enlace de RTC que se encuentra en un área donde no son necesarias las restricciones de enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="ce746-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="ce746-122">En este ejemplo, creamos dos nuevas directivas enrutamiento de voz y asignar los usos de RTC a ellos.</span><span class="sxs-lookup"><span data-stu-id="ce746-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="ce746-123">En la siguiente tabla muestra las directivas de enrutamiento de voz definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ce746-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="ce746-124">Directiva de enrutamiento 1 de voz</span><span class="sxs-lookup"><span data-stu-id="ce746-124">Voice routing policy 1</span></span>|<span data-ttu-id="ce746-125">Directiva de enrutamiento 2 de voz</span><span class="sxs-lookup"><span data-stu-id="ce746-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="ce746-126">Identificador de la directiva de voz en línea</span><span class="sxs-lookup"><span data-stu-id="ce746-126">Online voice policy ID</span></span>   |<span data-ttu-id="ce746-127">Directiva de enrutamiento de voz en línea de Delhi</span><span class="sxs-lookup"><span data-stu-id="ce746-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="ce746-128">Directiva de enrutamiento de voz en línea de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="ce746-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="ce746-129">Usos de RTC en línea</span><span class="sxs-lookup"><span data-stu-id="ce746-129">Online PSTN usages</span></span>  |<span data-ttu-id="ce746-130">Larga distancia</span><span class="sxs-lookup"><span data-stu-id="ce746-130">Long Distance</span></span>  |<span data-ttu-id="ce746-131">Larga distancia, Local, interno</span><span class="sxs-lookup"><span data-stu-id="ce746-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="ce746-132">Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar las directivas de enrutamiento de voz en línea a los usuarios que requieren que se deben cumplir las restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="ce746-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="ce746-133">Habilitar el enrutamiento basado en la ubicación de sitios de red</span><span class="sxs-lookup"><span data-stu-id="ce746-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="ce746-134">Use el cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar el enrutamiento basado en la ubicación y asociar las directivas de enrutamiento de voz a los sitios de red que se deben aplicar las restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="ce746-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="ce746-135">En este ejemplo, se habilita enrutamiento basado en la ubicación del sitio de Delhi y el sitio de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="ce746-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="ce746-136">En la siguiente tabla muestra los sitios habilitados para enrutamiento basado en la ubicación en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ce746-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="ce746-137">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ce746-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="ce746-138">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ce746-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="ce746-139">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="ce746-139">Site name</span></span>    |<span data-ttu-id="ce746-140">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ce746-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="ce746-141">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ce746-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="ce746-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="ce746-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="ce746-143">True</span><span class="sxs-lookup"><span data-stu-id="ce746-143">True</span></span>    |<span data-ttu-id="ce746-144">True</span><span class="sxs-lookup"><span data-stu-id="ce746-144">True</span></span>    |
    |<span data-ttu-id="ce746-145">Subredes</span><span class="sxs-lookup"><span data-stu-id="ce746-145">Subnets</span></span>     |<span data-ttu-id="ce746-146">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ce746-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="ce746-147">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ce746-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="ce746-148">Habilitar el enrutamiento basado en la ubicación de las puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="ce746-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="ce746-149">Use el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada sitio de red o la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce746-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="ce746-150">Si varias puertas de enlace están asociados con un sistema (por ejemplo, la puerta de enlace o PBX), modifique cada puerta de enlace para habilitar las restricciones de enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="ce746-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="ce746-151">En este ejemplo, se crea una configuración de puerta de enlace para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce746-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="ce746-152">Para obtener más información, vea [Configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="ce746-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="ce746-153">Use el cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar el enrutamiento basado en la ubicación de las puertas de enlace que se deben aplicar las restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="ce746-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="ce746-154">Habilitar el enrutamiento basado en la ubicación a puertas de enlace que enrutan las llamadas a las puertas de enlace de RTC que enrutan las llamadas a la RTC y asociación el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce746-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="ce746-155">En este ejemplo, se habilita enrutamiento basado en la ubicación para cada puerta de enlace que está asociado a las puertas de enlace RTC en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="ce746-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="ce746-156">No habilite el enrutamiento basado en la ubicación de las puertas de enlace que no enrutan las llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="ce746-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="ce746-157">Sin embargo, aún debe asociar la puerta de enlace para el sitio de red donde se encuentra el sistema.</span><span class="sxs-lookup"><span data-stu-id="ce746-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="ce746-158">Esto es debido a restricciones de enrutamiento basados en ubicación necesitan que se deben cumplir para alcanzar los extremos que están conectados a través de esta puerta de enlace de llamadas de RTC.</span><span class="sxs-lookup"><span data-stu-id="ce746-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="ce746-159">En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada puerta de enlace que está asociado a sistemas PBX en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="ce746-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="ce746-160">Los extremos conectados a los sistemas que no enrutan las llamadas a la RTC (por ejemplo, un sistema PBX) tendrán restricciones similares como extremos de los usuarios de los equipos habilitados para enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="ce746-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="ce746-161">Esto significa que estos usuarios pueden realizar y recibir llamadas a y desde los usuarios de los equipos, independientemente de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="ce746-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="ce746-162">También puede realizar y recibir llamadas a y desde otros sistemas que no enrutan las llamadas a la red RTC (por ejemplo, un extremo conectado a un sistema PBX diferente) independientemente del sitio de red al que está asociado el sistema.</span><span class="sxs-lookup"><span data-stu-id="ce746-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="ce746-163">Todas las llamadas entrantes, las llamadas salientes, transferencias de llamadas y el desvío de llamadas que implican los extremos de RTC estarán sujetas a las aplicaciones de enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="ce746-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="ce746-164">Estas llamadas deben usar sólo puertas de enlace RTC que se definen como locales para dichos sistemas.</span><span class="sxs-lookup"><span data-stu-id="ce746-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="ce746-165">En la siguiente tabla muestra la configuración de puerta de enlace de cuatro puertas de enlace en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="ce746-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="ce746-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="ce746-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="ce746-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="ce746-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="ce746-168">SUPR PstnGateway:Gateway 1-puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="ce746-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="ce746-169">True</span><span class="sxs-lookup"><span data-stu-id="ce746-169">True</span></span>     |   <span data-ttu-id="ce746-170">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ce746-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="ce746-171">PstnGateway:Gateway 2 Hidráulico-puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="ce746-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="ce746-172">True</span><span class="sxs-lookup"><span data-stu-id="ce746-172">True</span></span>      |      <span data-ttu-id="ce746-173">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ce746-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="ce746-174">PstnGateway:Gateway 3 SUPR-PBX</span><span class="sxs-lookup"><span data-stu-id="ce746-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="ce746-175">False</span><span class="sxs-lookup"><span data-stu-id="ce746-175">False</span></span>     |     <span data-ttu-id="ce746-176">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ce746-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="ce746-177">PstnGateway:Gateway 4 Hidráulico-PBX</span><span class="sxs-lookup"><span data-stu-id="ce746-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="ce746-178">False</span><span class="sxs-lookup"><span data-stu-id="ce746-178">False</span></span>     |    <span data-ttu-id="ce746-179">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ce746-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="ce746-180">Habilitar el enrutamiento basados en ubicación para llamar a las directivas</span><span class="sxs-lookup"><span data-stu-id="ce746-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="ce746-181">Para exigir la aplicación de enrutamiento basados en ubicación para usuarios específicos, el desvío de configurar la directiva de voz de los usuarios para evitar que el teléfono de pago PTSN.</span><span class="sxs-lookup"><span data-stu-id="ce746-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="ce746-182">Use el cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el enrutamiento basado en ubicación al evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="ce746-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="ce746-183">En este ejemplo, se evitar el desvío de pago de RTC del Usuario1 al llamar a las directivas de.</span><span class="sxs-lookup"><span data-stu-id="ce746-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="ce746-184">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ce746-184">Related topics</span></span>
- [<span data-ttu-id="ce746-185">Planear enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="ce746-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="ce746-186">Configuración de red de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="ce746-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="ce746-187">Terminología de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="ce746-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)

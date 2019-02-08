---
title: Habilitar el enrutamiento basado en ubicación para el enrutamiento directo
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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8437eba299cb42415d224017ca7d0e888fffa684
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "29771011"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="1efde-103">Habilitar el enrutamiento basado en ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1efde-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="1efde-104">Antes de seguir los pasos descritos en este artículo, asegúrese de que ha leído [Plan Location-Based enrutamiento para el enrutamiento directo](location-based-routing-plan.md) y completado los pasos de [configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1efde-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="1efde-105">Este artículo describe cómo habilitar el enrutamiento basados en ubicación para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="1efde-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="1efde-106">Después de implementar el enrutamiento directo de teléfono del sistema y configurar regiones de red, sitios y subredes, estará listo habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1efde-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="1efde-107">Para completar los pasos descritos en este artículo, necesitará un poco familiarizado con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1efde-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="1efde-108">Para obtener más información, vea [Introducción a los equipos de PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1efde-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="1efde-109">Tiene que habilitar el enrutamiento basado en la ubicación para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1efde-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="1efde-110">Usuarios</span><span class="sxs-lookup"><span data-stu-id="1efde-110">Users</span></span>
- <span data-ttu-id="1efde-111">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="1efde-111">Network sites</span></span>
- <span data-ttu-id="1efde-112">Configuraciones de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="1efde-112">Gateway configurations</span></span>
- <span data-ttu-id="1efde-113">Llamar a las directivas</span><span class="sxs-lookup"><span data-stu-id="1efde-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="1efde-114">Habilitar el enrutamiento basado en la ubicación para los usuarios</span><span class="sxs-lookup"><span data-stu-id="1efde-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="1efde-115">Usar el ``Set-CsOnlinePstnUsages`` cmdlet para establecer usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="1efde-115">Use the ``Set-CsOnlinePstnUsages`` cmdlet to set PSTN usages.</span></span> <span data-ttu-id="1efde-116">Para varios usos, separe cada uso con una coma.</span><span class="sxs-lookup"><span data-stu-id="1efde-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="1efde-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1efde-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="1efde-118">Usar el ``New-CsOnlineVoiceRoutingPolicy`` cmdlet para crear una directiva de enrutamiento de voz para asociar el usuario con los usos de RTC adecuados.</span><span class="sxs-lookup"><span data-stu-id="1efde-118">Use the ``New-CsOnlineVoiceRoutingPolicy`` cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="1efde-119">Al asignar los usos de RTC a una directiva de enrutamiento de voz, asegúrese de que se realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1efde-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="1efde-120">Use los usos de RTC asociados a las rutas de voz que usar una puerta de enlace de RTC local para el sitio</span><span class="sxs-lookup"><span data-stu-id="1efde-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="1efde-121">Use los usos de RTC asociados a las rutas de voz que usar una puerta de enlace de RTC que se encuentra en un área donde no son necesarias las restricciones de enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1efde-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="1efde-122">En este ejemplo, creamos dos nuevas directivas enrutamiento de voz y asignar los usos de RTC a ellos.</span><span class="sxs-lookup"><span data-stu-id="1efde-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="1efde-123">En la siguiente tabla muestra las directivas de enrutamiento de voz definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1efde-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="1efde-124">Directiva de enrutamiento 1 de voz</span><span class="sxs-lookup"><span data-stu-id="1efde-124">Voice routing policy 1</span></span>|<span data-ttu-id="1efde-125">Directiva de enrutamiento 2 de voz</span><span class="sxs-lookup"><span data-stu-id="1efde-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="1efde-126">Identificador de la directiva de voz</span><span class="sxs-lookup"><span data-stu-id="1efde-126">Voice policy ID</span></span>   |<span data-ttu-id="1efde-127">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="1efde-127">Delhi voice routing policy</span></span>   |<span data-ttu-id="1efde-128">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efde-128">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="1efde-129">Usos de RTC en línea</span><span class="sxs-lookup"><span data-stu-id="1efde-129">Online PSTN usages</span></span>  |<span data-ttu-id="1efde-130">Larga distancia</span><span class="sxs-lookup"><span data-stu-id="1efde-130">Long Distance</span></span>  |<span data-ttu-id="1efde-131">Larga distancia, Local, interno</span><span class="sxs-lookup"><span data-stu-id="1efde-131">Long Distance, Local, Internal</span></span>  |

    <span data-ttu-id="1efde-132">Para obtener más información, vea [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="1efde-132">For more information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>
3. <span data-ttu-id="1efde-133">Usar el ``Grant-CsOnlineVoiceRoutingPolicy`` las directivas de enrutamiento para los usuarios que requieren que se deben cumplir las restricciones de enrutamiento de voz de cmdlet para asociar en línea.</span><span class="sxs-lookup"><span data-stu-id="1efde-133">Use the ``Grant-CsOnlineVoiceRoutingPolicy`` cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="1efde-134">Habilitar el enrutamiento basado en la ubicación de sitios de red</span><span class="sxs-lookup"><span data-stu-id="1efde-134">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="1efde-135">Usar el ``Set-CsTenantNetworkSite`` cmdlet para habilitar el enrutamiento basado en la ubicación y asociar las directivas de enrutamiento a los sitios de red que se deben aplicar las restricciones de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="1efde-135">Use the ``Set-CsTenantNetworkSite`` cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -OnlineVoiceRoutingPolicy <voice routing policy ID> 
    ```

    <span data-ttu-id="1efde-136">En este ejemplo, se habilita enrutamiento basado en la ubicación del sitio de Delhi y el sitio de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1efde-136">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "DelhiVoiceRoutingPolicy" 
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "HyderabadVoiceRoutingPolicy" 
    ```
    <span data-ttu-id="1efde-137">En la siguiente tabla muestra los sitios habilitados para enrutamiento basado en la ubicación en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1efde-137">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="1efde-138">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1efde-138">Site 1 (Delhi)</span></span>  |<span data-ttu-id="1efde-139">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1efde-139">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="1efde-140">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="1efde-140">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="1efde-141">True</span><span class="sxs-lookup"><span data-stu-id="1efde-141">True</span></span>    |<span data-ttu-id="1efde-142">True</span><span class="sxs-lookup"><span data-stu-id="1efde-142">True</span></span>    |
    |<span data-ttu-id="1efde-143">Directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="1efde-143">Voice routing policy</span></span>    | <span data-ttu-id="1efde-144">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="1efde-144">Delhi voice routing policy</span></span>       |<span data-ttu-id="1efde-145">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efde-145">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="1efde-146">Subredes</span><span class="sxs-lookup"><span data-stu-id="1efde-146">Subnets</span></span>     |<span data-ttu-id="1efde-147">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1efde-147">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="1efde-148">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1efde-148">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="1efde-149">Habilitar el enrutamiento basado en la ubicación de las puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="1efde-149">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="1efde-150">Usar el ``New-CsOnlinePstnGateway`` cmdlet para crear una configuración de puerta de enlace para cada sitio de red o la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1efde-150">Use the ``New-CsOnlinePstnGateway`` cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="1efde-151">Si varias puertas de enlace están asociados con un sistema (por ejemplo, la puerta de enlace o PBX), modifique cada puerta de enlace para habilitar las restricciones de enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1efde-151">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="1efde-152">En este ejemplo, se crea una configuración de puerta de enlace para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1efde-152">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="1efde-153">Para obtener más información, vea [Configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="1efde-153">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="1efde-154">Usar el ``Set-CSOnlinePSTNGateway`` cmdlet para habilitar el enrutamiento basado en la ubicación de las puertas de enlace que se deben aplicar las restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1efde-154">Use the ``Set-CSOnlinePSTNGateway`` cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="1efde-155">Habilitar el enrutamiento basado en la ubicación a puertas de enlace que enrutan las llamadas a las puertas de enlace de RTC que enrutan las llamadas a la RTC y asociación el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1efde-155">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="1efde-156">En este ejemplo, se habilita enrutamiento basado en la ubicación para cada puerta de enlace que está asociado a las puertas de enlace RTC en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1efde-156">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="1efde-157">No habilite el enrutamiento basado en la ubicación de las puertas de enlace que no enrutan las llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="1efde-157">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="1efde-158">Sin embargo, aún debe asociar la puerta de enlace para el sitio de red donde se encuentra el sistema.</span><span class="sxs-lookup"><span data-stu-id="1efde-158">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="1efde-159">Esto es debido a restricciones de enrutamiento basados en ubicación necesitan que se deben cumplir para alcanzar los extremos que están conectados a través de esta puerta de enlace de llamadas de RTC.</span><span class="sxs-lookup"><span data-stu-id="1efde-159">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="1efde-160">En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada puerta de enlace que está asociado a sistemas PBX en los sitios de Delhi y Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1efde-160">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="1efde-161">Los extremos conectados a los sistemas que no enrutan las llamadas a la RTC (por ejemplo, un sistema PBX) tendrán restricciones similares como extremos de los usuarios de los equipos habilitados para enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1efde-161">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="1efde-162">Esto significa que estos usuarios pueden realizar y recibir llamadas a y desde los usuarios de los equipos, independientemente de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="1efde-162">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="1efde-163">También puede realizar y recibir llamadas a y desde otros sistemas que no enrutan las llamadas a la red RTC (por ejemplo, un extremo conectado a un sistema PBX diferente) independientemente del sitio de red al que está asociado el sistema.</span><span class="sxs-lookup"><span data-stu-id="1efde-163">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="1efde-164">Todas las llamadas entrantes, las llamadas salientes, transferencias de llamadas y el desvío de llamadas que implican los extremos de RTC estarán sujetas a las aplicaciones de enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1efde-164">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="1efde-165">Estas llamadas deben usar sólo puertas de enlace RTC que se definen como locales para dichos sistemas.</span><span class="sxs-lookup"><span data-stu-id="1efde-165">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="1efde-166">En la siguiente tabla muestra la configuración de puerta de enlace de cuatro puertas de enlace en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="1efde-166">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="1efde-167">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="1efde-167">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="1efde-168">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="1efde-168">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="1efde-169">SUPR PstnGateway:Gateway 1-puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="1efde-169">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="1efde-170">True</span><span class="sxs-lookup"><span data-stu-id="1efde-170">True</span></span>     |   <span data-ttu-id="1efde-171">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1efde-171">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="1efde-172">PstnGateway:Gateway 2 Hidráulico-puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="1efde-172">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="1efde-173">True</span><span class="sxs-lookup"><span data-stu-id="1efde-173">True</span></span>      |      <span data-ttu-id="1efde-174">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1efde-174">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="1efde-175">PstnGateway:Gateway 3 SUPR-PBX</span><span class="sxs-lookup"><span data-stu-id="1efde-175">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="1efde-176">True</span><span class="sxs-lookup"><span data-stu-id="1efde-176">True</span></span>     |     <span data-ttu-id="1efde-177">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1efde-177">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="1efde-178">PstnGateway:Gateway 4 Hidráulico-PBX</span><span class="sxs-lookup"><span data-stu-id="1efde-178">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="1efde-179">True</span><span class="sxs-lookup"><span data-stu-id="1efde-179">True</span></span>     |    <span data-ttu-id="1efde-180">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1efde-180">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="1efde-181">Habilitar el enrutamiento basados en ubicación para llamar a las directivas</span><span class="sxs-lookup"><span data-stu-id="1efde-181">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="1efde-182">Para exigir la aplicación de enrutamiento basados en ubicación para usuarios específicos, el desvío de configurar la directiva de voz de los usuarios para evitar que el teléfono de pago PTSN.</span><span class="sxs-lookup"><span data-stu-id="1efde-182">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="1efde-183">Usar el ``Grant-TeamsCallingPolicy`` el desvío de cmdlet para habilitar el enrutamiento basado en ubicación impidiendo que los números de pago de RTC.</span><span class="sxs-lookup"><span data-stu-id="1efde-183">Use the ``Grant-TeamsCallingPolicy`` cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-TeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="1efde-184">En este ejemplo, se evitar el desvío de pago de RTC del Usuario1 al llamar a las directivas de.</span><span class="sxs-lookup"><span data-stu-id="1efde-184">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-TeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="1efde-185">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1efde-185">Related topics</span></span>
- [<span data-ttu-id="1efde-186">Planeación de enrutamiento basado en ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1efde-186">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="1efde-187">Establecer la configuración de red para el enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="1efde-187">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="1efde-188">Terminología de enrutamiento basados en ubicación</span><span class="sxs-lookup"><span data-stu-id="1efde-188">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)

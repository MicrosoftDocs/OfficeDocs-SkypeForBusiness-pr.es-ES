---
title: 'Lync Server 2013: habilitar el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f36d28ca41bb12aa98bab5add471e102ed282b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0bb3a-102">Habilitación del enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bb3a-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bb3a-103">_**Última modificación del tema:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="0bb3a-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="0bb3a-104">Una vez que se haya implementado la telefonía IP empresarial y se hayan definido las regiones de red, sitios y subredes, puede habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="0bb3a-105">El enrutamiento basado en ubicación debe estar habilitado para los siguientes elementos de Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="0bb3a-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="0bb3a-106">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="0bb3a-106">Network sites</span></span>

  - <span data-ttu-id="0bb3a-107">Configuraciones de tronco</span><span class="sxs-lookup"><span data-stu-id="0bb3a-107">Trunk configurations</span></span>

  - <span data-ttu-id="0bb3a-108">Directivas de voz</span><span class="sxs-lookup"><span data-stu-id="0bb3a-108">Voice policies</span></span>

  - <span data-ttu-id="0bb3a-109">Configuración de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="0bb3a-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="0bb3a-110">Habilitar el enrutamiento basado en ubicación a sitios de red</span><span class="sxs-lookup"><span data-stu-id="0bb3a-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="0bb3a-111">Una vez que haya implementado Enterprise Voice y los sitios de red configurados, estará preparado para configurar el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="0bb3a-112">En primer lugar, cree una directiva de enrutamiento de voz para asociar el sitio de red con los usos de RTC apropiados.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="0bb3a-113">Al asignar usos de RTC a una directiva de enrutamiento de voz, asegúrese de usar solo los usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC local al sitio o a una puerta de enlace RTC que se encuentra en una región en la que no se necesitan restricciones de enrutamiento basadas en la ubicación. Use el comando de Windows PowerShell de Lync Server, New-CsVoiceRoutingPolicy o el panel de control de Lync Server para crear directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="0bb3a-114">Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="0bb3a-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="0bb3a-115">En este ejemplo, los siguientes comandos de Windows PowerShell y tabla muestran dos directivas de enrutamiento de voz y sus usos de RTC asociados definidos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="0bb3a-116">Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0bb3a-117">Directiva de enrutamiento de voz 1</span><span class="sxs-lookup"><span data-stu-id="0bb3a-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="0bb3a-118">Directiva 2 de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="0bb3a-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bb3a-119">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="0bb3a-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-120">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="0bb3a-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-121">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0bb3a-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb3a-122">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="0bb3a-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-123">Uso de Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="0bb3a-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-124">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="0bb3a-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="0bb3a-125">A continuación, configure el enrutamiento basado en ubicación para los sitios de red aplicables y asocie sus directivas de enrutamiento de voz a ellos.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="0bb3a-126">Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite, para habilitar el enrutamiento basado en ubicación y asociar directivas de enrutamiento de voz a los sitios de red que deban exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="0bb3a-127">En este ejemplo, la tabla siguiente ilustra el enrutamiento basado en ubicación para dos sitios de red diferentes, Delhi y Hyderabad, definidos en este escenario con Windows PowerShell de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="0bb3a-128">Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0bb3a-129">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="0bb3a-130">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bb3a-131">Nombre del sitio </span><span class="sxs-lookup"><span data-stu-id="0bb3a-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-132">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-133">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb3a-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="0bb3a-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-135">True</span><span class="sxs-lookup"><span data-stu-id="0bb3a-135">True</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-136">True</span><span class="sxs-lookup"><span data-stu-id="0bb3a-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bb3a-137">Directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="0bb3a-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-138">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="0bb3a-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-139">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0bb3a-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb3a-140">Subredes</span><span class="sxs-lookup"><span data-stu-id="0bb3a-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-141">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-142">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="0bb3a-143">Habilitar el enrutamiento basado en ubicación a troncos</span><span class="sxs-lookup"><span data-stu-id="0bb3a-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="0bb3a-144">Antes de poder habilitar una configuración de tronco para el enrutamiento basado en ubicación, debe crear una configuración de tronco para cada tronco o cada sitio de red.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="0bb3a-145">Use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration, para crear una configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="0bb3a-146">Si hay varios troncos asociados a un sistema determinado (por ejemplo, a una puerta de enlace o PBX), se debe modificar cada configuración de tronco para habilitar las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="0bb3a-147">Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0bb3a-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0bb3a-148">En este ejemplo, los siguientes comandos de Windows PowerShell ilustran la creación de una configuración de tronco para cada tronco en la implementación definida en este escenario.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="0bb3a-149">Una vez configurada la configuración del tronco por tronco, puede usar el comando de Windows PowerShell de Lync Server, Set-CsTrunkConfiguration, para habilitar el enrutamiento basado en ubicación a los troncos que deben exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="0bb3a-150">Habilite el enrutamiento basado en ubicación a los troncos que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocien el sitio de red en el que se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="0bb3a-151">Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0bb3a-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0bb3a-152">En este ejemplo, el enrutamiento basado en ubicación está habilitado para todos los tronco asociados a puertas de enlace RTC en Delhi y Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="0bb3a-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="0bb3a-153">No habilite el enrutamiento basado en ubicación para troncos que no enruten llamadas a la RTC; sin embargo, debe asociar el tronco al sitio de red donde se encuentra el sistema, ya que las restricciones de enrutamiento basadas en ubicación deben aplicarse para las llamadas RTC que alcanzan los extremos conectados a través de este tronco.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="0bb3a-154">Para este ejemplo, el enrutamiento basado en ubicación no está habilitado para todos los tronco asociados a sistemas PBX en Delhi y Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="0bb3a-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="0bb3a-155">Los extremos que están conectados a sistemas que no enrutan las llamadas a la RTC (es decir, una PBX) tendrán restricciones similares a las de los extremos de Lync de los usuarios habilitados para el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="0bb3a-156">Esto significa que estos usuarios podrán realizar y recibir llamadas a y desde el usuario de Lync, independientemente de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="0bb3a-157">También podrán realizar llamadas de recepción a y desde otros sistemas que no enruten las llamadas a la red RTC (es decir, un extremo conectado a otra PBX), independientemente del sitio de red al que esté asociado el sistema.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="0bb3a-158">Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas con extremos RTC estarán sujetos a las fuerzas de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="0bb3a-159">Estas llamadas deben usar solo puertas de enlace RTC definidas como locales para dichos sistemas.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="0bb3a-160">En la tabla siguiente se muestra la configuración de tronco de cuatro troncos en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bb3a-161">Nombre</span><span class="sxs-lookup"><span data-stu-id="0bb3a-161">Name</span></span></th>
<th><span data-ttu-id="0bb3a-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="0bb3a-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="0bb3a-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="0bb3a-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bb3a-164">PstnGateway: tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="0bb3a-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-165">True</span><span class="sxs-lookup"><span data-stu-id="0bb3a-165">True</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-166">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb3a-167">PstnGateway: tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="0bb3a-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-168">True</span><span class="sxs-lookup"><span data-stu-id="0bb3a-168">True</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-169">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bb3a-170">PstnGateway: tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="0bb3a-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-171">False</span><span class="sxs-lookup"><span data-stu-id="0bb3a-171">False</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-172">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb3a-173">PstnGateway: tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="0bb3a-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-174">False</span><span class="sxs-lookup"><span data-stu-id="0bb3a-174">False</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-175">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0bb3a-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="0bb3a-176">Habilitar el enrutamiento basado en ubicación a directivas de voz</span><span class="sxs-lookup"><span data-stu-id="0bb3a-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="0bb3a-177">Para aplicar el enrutamiento basado en ubicación a usuarios específicos, configure la Directiva de voz de los usuarios para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="0bb3a-178">Use el comando de Windows PowerShell de Lync Server, New-CsVoicePolicy, para crear una nueva Directiva de voz o set-CsVoicePolicy, si usa una directiva existente, para habilitar el enrutamiento basado en ubicación evitando el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="0bb3a-179">Para obtener más información, vea [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="0bb3a-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="0bb3a-180">En este ejemplo, los siguientes comandos de Windows PowerShell y tabla muestran cómo evitar la omisión de peajes RTC en las directivas de voz de Delhi y Hyderabad definidas en este escenario.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="0bb3a-181">Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0bb3a-182">Directiva de voz 1</span><span class="sxs-lookup"><span data-stu-id="0bb3a-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="0bb3a-183">Directiva de voz 2</span><span class="sxs-lookup"><span data-stu-id="0bb3a-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bb3a-184">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="0bb3a-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-185">Directiva de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="0bb3a-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-186">Directiva de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0bb3a-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb3a-187">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="0bb3a-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-188">Uso de Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="0bb3a-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-189">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="0bb3a-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bb3a-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="0bb3a-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-191">True</span><span class="sxs-lookup"><span data-stu-id="0bb3a-191">True</span></span></p></td>
<td><p><span data-ttu-id="0bb3a-192">True</span><span class="sxs-lookup"><span data-stu-id="0bb3a-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="0bb3a-193">Habilitar el enrutamiento basado en ubicación en la configuración de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="0bb3a-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="0bb3a-194">Por último, habilite globalmente el enrutamiento basado en ubicación a la configuración de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="0bb3a-195">Use el comando de Windows PowerShell de Lync Server, New-CsRoutingConfiguration, para habilitar el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="0bb3a-196">Para obtener más información, vea [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0bb3a-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bb3a-197">Aunque el enrutamiento basado en ubicación debe habilitarse a través de una configuración global, el conjunto de reglas que se aplicará solo se aplicará a los sitios, usuarios y troncos para los que se haya configurado tal y como se especifica en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="0bb3a-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0bb3a-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bb3a-198">See Also</span></span>


[<span data-ttu-id="0bb3a-199">Configuración del enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bb3a-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: habilitar el enrutamiento basado en la ubicación'
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
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f9038-102">Habilitar el enrutamiento basado en la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9038-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9038-103">_**Última modificación del tema:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="f9038-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="f9038-104">Una vez que se implementa la telefonía IP empresarial y se definen las regiones, sitios y subredes de la red, puede habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f9038-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="f9038-105">El enrutamiento basado en la ubicación debe estar habilitado para los siguientes elementos de Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="f9038-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="f9038-106">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="f9038-106">Network sites</span></span>

  - <span data-ttu-id="f9038-107">Configuraciones troncales</span><span class="sxs-lookup"><span data-stu-id="f9038-107">Trunk configurations</span></span>

  - <span data-ttu-id="f9038-108">Directivas de voz</span><span class="sxs-lookup"><span data-stu-id="f9038-108">Voice policies</span></span>

  - <span data-ttu-id="f9038-109">Configuración de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="f9038-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="f9038-110">Habilitar el enrutamiento basado en ubicación a sitios de red</span><span class="sxs-lookup"><span data-stu-id="f9038-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="f9038-111">Una vez que haya implementado Enterprise Voice y los sitios de red configurados, estará listo para configurar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f9038-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="f9038-112">En primer lugar, cree una directiva de enrutamiento de voz para asociar el sitio de red a los usos de RTC apropiados.</span><span class="sxs-lookup"><span data-stu-id="f9038-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="f9038-113">Al asignar usos de RTC a una directiva de enrutamiento de voz, asegúrese de usar solo usos de RTC asociados a rutas de voz que usen una puerta de enlace PSTN local para el sitio o una puerta de enlace RTC que se encuentre en una región donde no se necesiten restricciones de enrutamiento basado en la ubicación. Use el comando de Windows PowerShell de Lync Server, New-CsVoiceRoutingPolicy o panel de control de Lync Server para crear directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="f9038-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="f9038-114">Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="f9038-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="f9038-115">En este ejemplo, los siguientes comandos de tabla y Windows PowerShell ilustran dos directivas de enrutamiento de voz y sus usos de RTC asociados definidos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="f9038-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="f9038-116">En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="f9038-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="f9038-117">Directiva de enrutamiento de voz 1</span><span class="sxs-lookup"><span data-stu-id="f9038-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="f9038-118">Directiva de enrutamiento de voz 2</span><span class="sxs-lookup"><span data-stu-id="f9038-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9038-119">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="f9038-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f9038-120">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="f9038-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f9038-121">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f9038-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9038-122">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="f9038-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f9038-123">Uso de la Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="f9038-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f9038-124">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="f9038-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="f9038-125">A continuación, configure el enrutamiento basado en la ubicación para los sitios de red aplicables y asocie sus directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="f9038-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="f9038-126">Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite, para habilitar el enrutamiento basado en la ubicación y asociar directivas de enrutamiento de voz a los sitios de red que deban exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f9038-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="f9038-127">En este ejemplo, la tabla siguiente muestra el enrutamiento basado en la ubicación de dos sitios de red diferentes, Delhi y Hyderabad, definidos en este escenario con Windows PowerShell de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9038-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="f9038-128">En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="f9038-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="f9038-129">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f9038-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="f9038-130">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f9038-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9038-131">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="f9038-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="f9038-132">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f9038-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="f9038-133">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f9038-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9038-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="f9038-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="f9038-135">True</span><span class="sxs-lookup"><span data-stu-id="f9038-135">True</span></span></p></td>
<td><p><span data-ttu-id="f9038-136">True</span><span class="sxs-lookup"><span data-stu-id="f9038-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9038-137">Directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="f9038-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f9038-138">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="f9038-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f9038-139">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f9038-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9038-140">Subredes</span><span class="sxs-lookup"><span data-stu-id="f9038-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="f9038-141">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f9038-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="f9038-142">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f9038-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="f9038-143">Habilitar el enrutamiento basado en la ubicación a los troncos</span><span class="sxs-lookup"><span data-stu-id="f9038-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="f9038-144">Antes de poder habilitar una configuración de tronco para el enrutamiento basado en la ubicación, debe crear una configuración troncal para cada troncal o cada sitio de red.</span><span class="sxs-lookup"><span data-stu-id="f9038-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="f9038-145">Use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration, para crear una configuración troncal.</span><span class="sxs-lookup"><span data-stu-id="f9038-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="f9038-146">Si hay varios troncos asociados con un sistema determinado (por ejemplo, puerta de enlace o PBX), cada configuración de troncal debe modificarse para habilitar las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f9038-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="f9038-147">Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f9038-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="f9038-148">En este ejemplo, los siguientes comandos de Windows PowerShell ilustran la creación de una configuración de tronco para cada tronco de la implementación definida en este escenario.</span><span class="sxs-lookup"><span data-stu-id="f9038-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="f9038-149">Una vez configurada la configuración del tronco por tronco, puede usar el comando de Windows PowerShell de Lync Server, Set-CsTrunkConfiguration, para habilitar el enrutamiento basado en la ubicación a sus troncos que deben exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f9038-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="f9038-150">Habilite el enrutamiento basado en la ubicación a los troncos que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="f9038-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="f9038-151">Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f9038-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="f9038-152">En este ejemplo, el enrutamiento basado en la ubicación está habilitado para cada tronco asociado a las puertas de enlace RTC de Delhi y Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="f9038-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="f9038-153">No habilite el enrutamiento basado en la ubicación para los troncos que no enruten las llamadas a la RTC; sin embargo, todavía debe asociar el tronco al sitio de red donde se encuentra el sistema, ya que es necesario exigir restricciones de enrutamiento basado en la ubicación para las llamadas RTC que llegan a los puntos de conexión conectados a través de este tronco.</span><span class="sxs-lookup"><span data-stu-id="f9038-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="f9038-154">En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada tronco asociado a sistemas PBX en Delhi y Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="f9038-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="f9038-155">Los puntos de conexión que estén conectados a sistemas que no enruten llamadas a la RTC (es decir, una PBX) tendrán restricciones similares a las de los extremos de Lync de los usuarios habilitados para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f9038-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="f9038-156">Esto significa que estos usuarios podrán realizar y recibir llamadas a y desde el usuario de Lync independientemente de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9038-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="f9038-157">También podrán realizar llamadas recibidas a otros sistemas y desde otros sistemas que no enruten las llamadas a la red RTC (es decir, un extremo conectado a otro PBX), independientemente del sitio de red al que esté asociado el sistema.</span><span class="sxs-lookup"><span data-stu-id="f9038-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="f9038-158">Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas con puntos de conexión RTC estarán sujetos a las fuerzas de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f9038-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="f9038-159">Dichas llamadas deben usar solo puertas de enlace RTC que estén definidas como locales para esos sistemas.</span><span class="sxs-lookup"><span data-stu-id="f9038-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="f9038-160">En la tabla siguiente se muestra la configuración troncal de cuatro troncos en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="f9038-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9038-161">Nombre</span><span class="sxs-lookup"><span data-stu-id="f9038-161">Name</span></span></th>
<th><span data-ttu-id="f9038-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="f9038-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="f9038-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="f9038-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9038-164">PstnGateway: troncal 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f9038-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f9038-165">Verdadero</span><span class="sxs-lookup"><span data-stu-id="f9038-165">True</span></span></p></td>
<td><p><span data-ttu-id="f9038-166">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f9038-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9038-167">PstnGateway: Troncal 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="f9038-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f9038-168">Verdadero</span><span class="sxs-lookup"><span data-stu-id="f9038-168">True</span></span></p></td>
<td><p><span data-ttu-id="f9038-169">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f9038-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9038-170">PstnGateway: troncal 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="f9038-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f9038-171">Falso</span><span class="sxs-lookup"><span data-stu-id="f9038-171">False</span></span></p></td>
<td><p><span data-ttu-id="f9038-172">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f9038-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9038-173">PstnGateway: troncal 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="f9038-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="f9038-174">Falso</span><span class="sxs-lookup"><span data-stu-id="f9038-174">False</span></span></p></td>
<td><p><span data-ttu-id="f9038-175">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f9038-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="f9038-176">Habilitar el enrutamiento basado en la ubicación a directivas de voz</span><span class="sxs-lookup"><span data-stu-id="f9038-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="f9038-177">Para aplicar el enrutamiento basado en la ubicación a usuarios específicos, configure la Directiva de voz de los usuarios para evitar la omisión de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="f9038-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f9038-178">Use el comando de Windows PowerShell de Lync Server, New-CsVoicePolicy, para crear una nueva Directiva de voz o set-CsVoicePolicy, si usa una directiva existente, para habilitar el enrutamiento basado en la ubicación evitando la omisión de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="f9038-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="f9038-179">Para obtener más información, vea [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="f9038-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="f9038-180">En este ejemplo, los siguientes comandos de tabla y Windows PowerShell ilustran la prevención de la omisión de llamadas RTC en las directivas de voz de Delhi y Hyderabad definidas en este escenario.</span><span class="sxs-lookup"><span data-stu-id="f9038-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="f9038-181">En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="f9038-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="f9038-182">Política de voz 1</span><span class="sxs-lookup"><span data-stu-id="f9038-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="f9038-183">Política de voz 2</span><span class="sxs-lookup"><span data-stu-id="f9038-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9038-184">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="f9038-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f9038-185">Directiva de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="f9038-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="f9038-186">Política de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f9038-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9038-187">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="f9038-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f9038-188">Uso de la Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="f9038-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f9038-189">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="f9038-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9038-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="f9038-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="f9038-191">True</span><span class="sxs-lookup"><span data-stu-id="f9038-191">True</span></span></p></td>
<td><p><span data-ttu-id="f9038-192">True</span><span class="sxs-lookup"><span data-stu-id="f9038-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="f9038-193">Habilitar el enrutamiento basado en la ubicación en la configuración de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="f9038-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="f9038-194">Por último, habilite globalmente el enrutamiento basado en la ubicación a la configuración de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f9038-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="f9038-195">Use el comando de Windows PowerShell de Lync Server, New-CsRoutingConfiguration, para habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f9038-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="f9038-196">Para obtener más información, consulte [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f9038-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9038-197">Si bien el enrutamiento basado en la ubicación debe habilitarse a través de una configuración global, el conjunto de reglas que se aplicará solo se aplicará a los sitios, usuarios y troncos para los que se haya configurado tal como se especifica en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="f9038-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9038-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9038-198">See Also</span></span>


[<span data-ttu-id="f9038-199">Configurar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9038-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


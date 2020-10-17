---
title: 'Lync Server 2013: habilitar el enrutamiento de Location-Based'
description: 'Lync Server 2013: habilitar el enrutamiento de Location-Based.'
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
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557626"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f7885-103">Habilitación del enrutamiento Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7885-103">Enabling Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7885-104">_**Última modificación del tema:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="f7885-104">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="f7885-105">Una vez que se haya implementado la telefonía IP empresarial y se hayan definido las regiones de red, sitios y subredes, podrá habilitar el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f7885-105">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="f7885-106">El enrutamiento de Location-Based debe estar habilitado para los siguientes elementos de Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="f7885-106">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="f7885-107">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="f7885-107">Network sites</span></span>

  - <span data-ttu-id="f7885-108">Configuraciones de tronco</span><span class="sxs-lookup"><span data-stu-id="f7885-108">Trunk configurations</span></span>

  - <span data-ttu-id="f7885-109">Directivas de voz</span><span class="sxs-lookup"><span data-stu-id="f7885-109">Voice policies</span></span>

  - <span data-ttu-id="f7885-110">Configuración de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="f7885-110">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="f7885-111">Habilitar el enrutamiento Location-Based a sitios de red</span><span class="sxs-lookup"><span data-stu-id="f7885-111">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="f7885-112">Una vez que haya implementado Enterprise Voice y configurado los sitios de red, estará preparado para configurar el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f7885-112">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="f7885-113">En primer lugar, cree una directiva de enrutamiento de voz para asociar el sitio de red con los usos de RTC apropiados.</span><span class="sxs-lookup"><span data-stu-id="f7885-113">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="f7885-114">Al asignar los usos de RTC a una directiva de enrutamiento de voz, asegúrese de usar solo los usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC local al sitio o a una puerta de enlace RTC que se encuentra en una región en la que no se necesitan restricciones de enrutamiento de Location-Based. Use el comando de Windows PowerShell de Lync Server, New-CsVoiceRoutingPolicy o el panel de control de Lync Server para crear directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="f7885-114">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="f7885-115">Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="f7885-115">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="f7885-116">En este ejemplo, los siguientes comandos de Windows PowerShell y tabla muestran dos directivas de enrutamiento de voz y sus usos de RTC asociados definidos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="f7885-116">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="f7885-117">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="f7885-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="f7885-118">Directiva de enrutamiento de voz 1</span><span class="sxs-lookup"><span data-stu-id="f7885-118">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="f7885-119">Directiva 2 de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="f7885-119">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7885-120">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="f7885-120">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f7885-121">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="f7885-121">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f7885-122">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7885-122">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7885-123">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="f7885-123">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f7885-124">Uso de Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="f7885-124">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f7885-125">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="f7885-125">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="f7885-126">A continuación, configure Location-Based enrutamiento para los sitios de red aplicables y asocie sus directivas de enrutamiento de voz a ellos.</span><span class="sxs-lookup"><span data-stu-id="f7885-126">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="f7885-127">Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite, para habilitar el enrutamiento Location-Based y asociar directivas de enrutamiento de voz a los sitios de red que deban exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f7885-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="f7885-128">En este ejemplo, la tabla siguiente ilustra el enrutamiento de Location-Based para dos sitios de red diferentes, Delhi y Hyderabad, definidos en este escenario con Windows PowerShell de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7885-128">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="f7885-129">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="f7885-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="f7885-130">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f7885-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="f7885-131">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f7885-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7885-132">Nombre del sitio </span><span class="sxs-lookup"><span data-stu-id="f7885-132">Site Name</span></span></p></td>
<td><p><span data-ttu-id="f7885-133">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f7885-133">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="f7885-134">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f7885-134">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7885-135">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="f7885-135">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="f7885-136">True</span><span class="sxs-lookup"><span data-stu-id="f7885-136">True</span></span></p></td>
<td><p><span data-ttu-id="f7885-137">True</span><span class="sxs-lookup"><span data-stu-id="f7885-137">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7885-138">Directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="f7885-138">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f7885-139">Directiva de enrutamiento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="f7885-139">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f7885-140">Directiva de enrutamiento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7885-140">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7885-141">Subredes</span><span class="sxs-lookup"><span data-stu-id="f7885-141">Subnets</span></span></p></td>
<td><p><span data-ttu-id="f7885-142">Subred 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f7885-142">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="f7885-143">Subred 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f7885-143">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="f7885-144">Habilitar el enrutamiento Location-Based a troncos</span><span class="sxs-lookup"><span data-stu-id="f7885-144">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="f7885-145">Antes de poder habilitar una configuración de tronco para Location-Based el enrutamiento, debe crear una configuración de tronco para cada tronco o cada sitio de red.</span><span class="sxs-lookup"><span data-stu-id="f7885-145">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="f7885-146">Use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration, para crear una configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="f7885-146">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="f7885-147">Si hay varios troncos asociados a un sistema determinado (por ejemplo, a una puerta de enlace o PBX), se debe modificar cada configuración de tronco para habilitar Location-Based restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f7885-147">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="f7885-148">Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f7885-148">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="f7885-149">En este ejemplo, los siguientes comandos de Windows PowerShell ilustran la creación de una configuración de tronco para cada tronco en la implementación definida en este escenario.</span><span class="sxs-lookup"><span data-stu-id="f7885-149">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="f7885-150">Una vez configurada la configuración del tronco por tronco, puede usar el comando de Windows PowerShell de Lync Server, Set-CsTrunkConfiguration, para habilitar el enrutamiento Location-Based a los troncos que deben exigir restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f7885-150">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="f7885-151">Habilite el enrutamiento Location-Based a troncos que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocien el sitio de red en el que se encuentra la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="f7885-151">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="f7885-152">Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f7885-152">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="f7885-153">En este ejemplo, se habilita el enrutamiento de Location-Based para cada tronco asociado a puertas de enlace RTC en Delhi y Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="f7885-153">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="f7885-154">No habilite el enrutamiento Location-Based para troncos que no enruten llamadas a la RTC; sin embargo, debe asociar el tronco al sitio de red en el que se encuentra el sistema como Location-Based restricciones de enrutamiento se deben aplicar para las llamadas RTC que alcanzan los extremos conectados a través de este tronco.</span><span class="sxs-lookup"><span data-stu-id="f7885-154">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="f7885-155">En este ejemplo, el enrutamiento de Location-Based no está habilitado para cada tronco asociado a sistemas PBX en Delhi y Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="f7885-155">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="f7885-156">Los extremos que están conectados a sistemas que no enrutan las llamadas a la RTC (es decir, una PBX) tendrán restricciones similares a las de los extremos de Lync de los usuarios habilitados para el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f7885-156">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="f7885-157">Esto significa que estos usuarios podrán realizar y recibir llamadas a y desde el usuario de Lync, independientemente de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="f7885-157">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="f7885-158">También podrán realizar llamadas de recepción a y desde otros sistemas que no enruten las llamadas a la red RTC (es decir, un extremo conectado a otra PBX), independientemente del sitio de red al que esté asociado el sistema.</span><span class="sxs-lookup"><span data-stu-id="f7885-158">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="f7885-159">Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas con puntos de conexión RTC estarán sujetos a Location-Based las fuerzas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f7885-159">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="f7885-160">Estas llamadas deben usar solo puertas de enlace RTC definidas como locales para dichos sistemas.</span><span class="sxs-lookup"><span data-stu-id="f7885-160">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="f7885-161">En la tabla siguiente se muestra la configuración de tronco de cuatro troncos en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="f7885-161">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7885-162">Nombre</span><span class="sxs-lookup"><span data-stu-id="f7885-162">Name</span></span></th>
<th><span data-ttu-id="f7885-163">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="f7885-163">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="f7885-164">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="f7885-164">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7885-165">PstnGateway: tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f7885-165">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f7885-166">Verdadero</span><span class="sxs-lookup"><span data-stu-id="f7885-166">True</span></span></p></td>
<td><p><span data-ttu-id="f7885-167">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f7885-167">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7885-168">PstnGateway: tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="f7885-168">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f7885-169">Verdadero</span><span class="sxs-lookup"><span data-stu-id="f7885-169">True</span></span></p></td>
<td><p><span data-ttu-id="f7885-170">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f7885-170">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7885-171">PstnGateway: tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="f7885-171">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f7885-172">False</span><span class="sxs-lookup"><span data-stu-id="f7885-172">False</span></span></p></td>
<td><p><span data-ttu-id="f7885-173">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f7885-173">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7885-174">PstnGateway: tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="f7885-174">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="f7885-175">False</span><span class="sxs-lookup"><span data-stu-id="f7885-175">False</span></span></p></td>
<td><p><span data-ttu-id="f7885-176">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f7885-176">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="f7885-177">Habilitar el enrutamiento Location-Based a directivas de voz</span><span class="sxs-lookup"><span data-stu-id="f7885-177">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="f7885-178">Para aplicar Location-Based enrutamiento a usuarios específicos, configure la Directiva de voz de los usuarios para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="f7885-178">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f7885-179">Use el comando de Windows PowerShell de Lync Server, New-CsVoicePolicy, para crear una nueva Directiva de voz o set-CsVoicePolicy, si usa una directiva existente, para habilitar el enrutamiento Location-Based evitando el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="f7885-179">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="f7885-180">Para obtener más información, vea [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="f7885-180">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="f7885-181">En este ejemplo, los siguientes comandos de Windows PowerShell y tabla muestran cómo evitar la omisión de peajes RTC en las directivas de voz de Delhi y Hyderabad definidas en este escenario.</span><span class="sxs-lookup"><span data-stu-id="f7885-181">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="f7885-182">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="f7885-182">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="f7885-183">Directiva de voz 1</span><span class="sxs-lookup"><span data-stu-id="f7885-183">Voice policy 1</span></span></th>
<th><span data-ttu-id="f7885-184">Directiva de voz 2</span><span class="sxs-lookup"><span data-stu-id="f7885-184">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7885-185">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="f7885-185">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f7885-186">Directiva de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="f7885-186">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="f7885-187">Directiva de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7885-187">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7885-188">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="f7885-188">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f7885-189">Uso de Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="f7885-189">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f7885-190">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="f7885-190">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7885-191">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="f7885-191">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="f7885-192">True</span><span class="sxs-lookup"><span data-stu-id="f7885-192">True</span></span></p></td>
<td><p><span data-ttu-id="f7885-193">True</span><span class="sxs-lookup"><span data-stu-id="f7885-193">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="f7885-194">Habilitar el enrutamiento de Location-Based en la configuración de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="f7885-194">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="f7885-195">Por último, habilite globalmente Location-Based enrutamiento a la configuración de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f7885-195">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="f7885-196">Use el comando de Windows PowerShell de Lync Server, New-CsRoutingConfiguration, para habilitar el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f7885-196">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="f7885-197">Para obtener más información, vea [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f7885-197">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7885-198">Aunque el enrutamiento de Location-Based debe estar habilitado a través de una configuración global, el conjunto de reglas que se aplicará solo se aplicará a los sitios, usuarios y troncos para los que se haya configurado tal y como se especifica en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="f7885-198">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7885-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7885-199">See Also</span></span>


[<span data-ttu-id="f7885-200">Configuración del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7885-200">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


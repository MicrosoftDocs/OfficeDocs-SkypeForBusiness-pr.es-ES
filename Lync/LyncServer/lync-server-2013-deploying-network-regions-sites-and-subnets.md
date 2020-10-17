---
title: 'Lync Server 2013: implementación de regiones de red, sitios y subredes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95d9f7e38e3169474aee33a3004b388c0b13f14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531153"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="ed962-102">Implementar regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed962-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed962-103">_**Última modificación del tema:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="ed962-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="ed962-104">Una vez implementada la telefonía IP empresarial, debe configurar:</span><span class="sxs-lookup"><span data-stu-id="ed962-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="ed962-105">Regiones de red</span><span class="sxs-lookup"><span data-stu-id="ed962-105">Network regions</span></span>

  - <span data-ttu-id="ed962-106">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="ed962-106">Network sites</span></span>

  - <span data-ttu-id="ed962-107">Subredes de red</span><span class="sxs-lookup"><span data-stu-id="ed962-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="ed962-108">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="ed962-108">Define Network Regions</span></span>

<span data-ttu-id="ed962-109">Use el comando de Windows PowerShell de Lync Server, New-CsNetworkRegion o el panel de control de Lync Server para definir las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ed962-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="ed962-110">Para obtener más información, vea [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="ed962-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="ed962-111">Para este ejemplo, el siguiente comando de Windows PowerShell ilustra la región de red, región 1 (India), definida en este escenario.</span><span class="sxs-lookup"><span data-stu-id="ed962-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="ed962-112">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="ed962-112">Define Network Sites</span></span>

<span data-ttu-id="ed962-113">Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite o el panel de control de Lync Server para definir sitios de red.</span><span class="sxs-lookup"><span data-stu-id="ed962-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="ed962-114">Para obtener más información, vea [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="ed962-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="ed962-115">Para este ejemplo, la siguiente tabla y el comando de Lync Server Windows PowerShell ilustran los sitios de red definidos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="ed962-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="ed962-116">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="ed962-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ed962-117">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ed962-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="ed962-118">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ed962-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed962-119">IDENTIFICADOR de sitio</span><span class="sxs-lookup"><span data-stu-id="ed962-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="ed962-120">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ed962-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="ed962-121">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ed962-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed962-122">IDENTIFICADOR de región</span><span class="sxs-lookup"><span data-stu-id="ed962-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="ed962-123">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="ed962-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="ed962-124">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="ed962-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="ed962-125">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="ed962-125">Define Network Subnets</span></span>

<span data-ttu-id="ed962-126">Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSubnet o el panel de control de Lync Server para definir las subredes de red y asignarlas a los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="ed962-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="ed962-127">Para obtener más información, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="ed962-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="ed962-128">En este ejemplo, los siguientes comandos de Windows PowerShell y tabla ilustran la asignación de subredes de red a los sitios de red, Delhi y Hyderabad, definidos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="ed962-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="ed962-129">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="ed962-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ed962-130">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ed962-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="ed962-131">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ed962-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed962-132">IDENTIFICADOR de subred</span><span class="sxs-lookup"><span data-stu-id="ed962-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="ed962-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="ed962-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="ed962-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="ed962-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed962-135">Mask</span><span class="sxs-lookup"><span data-stu-id="ed962-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="ed962-136">apartado</span><span class="sxs-lookup"><span data-stu-id="ed962-136">24</span></span></p></td>
<td><p><span data-ttu-id="ed962-137">apartado</span><span class="sxs-lookup"><span data-stu-id="ed962-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed962-138">IDENTIFICADOR de sitio</span><span class="sxs-lookup"><span data-stu-id="ed962-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="ed962-139">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ed962-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="ed962-140">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ed962-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed962-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed962-141">See Also</span></span>


[<span data-ttu-id="ed962-142">Configuración del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed962-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


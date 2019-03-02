---
title: Configuración de red de enrutamiento basado en la ubicación
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y configurar regiones de red, sitios y subredes para enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60ed4b1c69f2b6495e21fe28653b19ca905dfc6c
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353445"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="d28dd-103">Configuración de red de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="d28dd-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="d28dd-104">Si ya lo ha hecho, lea [Plan Location-Based enrutamiento para el enrutamiento directo](location-based-routing-plan.md) para revisar otros pasos debe tomar antes de implementar la configuración de red para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="d28dd-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you deploy network settings for Location-Based Routing.</span></span>

<span data-ttu-id="d28dd-105">Este artículo describe cómo configurar las opciones de red para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="d28dd-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="d28dd-106">Después de implementar el enrutamiento directo teléfono del sistema en la organización, son los siguientes pasos crear y configurar regiones de red, sitios de red y subredes de la red.</span><span class="sxs-lookup"><span data-stu-id="d28dd-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="d28dd-107">Para completar los pasos descritos en este artículo, necesitará un poco familiarizado con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d28dd-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="d28dd-108">Para obtener más información, vea [Introducción a los equipos de PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d28dd-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="d28dd-109">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="d28dd-109">Define network regions</span></span>
 <span data-ttu-id="d28dd-110">Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="d28dd-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d28dd-111">Usar el ``New-CsTenantNetworkRegion`` cmdlet de PowerShell para definir regiones de red.</span><span class="sxs-lookup"><span data-stu-id="d28dd-111">Use the ``New-CsTenantNetworkRegion`` PowerShell cmdlet to define network regions.</span></span> <span data-ttu-id="d28dd-112">Tenga en cuenta que el ``RegionID`` parámetro es un nombre lógico que representa la región geográfica de la región y no tiene dependencias ni las restricciones y el ``CentralSite <site ID>`` parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="d28dd-112">Note that the ``RegionID`` parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the ``CentralSite <site ID>`` parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="d28dd-113">En este ejemplo, se crea una región de red denominada India.</span><span class="sxs-lookup"><span data-stu-id="d28dd-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="d28dd-114">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="d28dd-114">Define network sites</span></span>

<span data-ttu-id="d28dd-115">Usar el ``New-CsTenantNetworkSite`` cmdlet de PowerShell para definir sitios de red.</span><span class="sxs-lookup"><span data-stu-id="d28dd-115">Use the ``New-CsTenantNetworkSite`` PowerShell cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="d28dd-116">En este ejemplo, creamos dos nuevos sitios de red, Delhi y Hyderabad, en la región de India.</span><span class="sxs-lookup"><span data-stu-id="d28dd-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="d28dd-117">En la siguiente tabla muestra los sitios de red definidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d28dd-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="d28dd-118">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="d28dd-118">Site 1</span></span> |<span data-ttu-id="d28dd-119">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="d28dd-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d28dd-120">Identificador de sitio</span><span class="sxs-lookup"><span data-stu-id="d28dd-120">Site ID</span></span>    |    <span data-ttu-id="d28dd-121">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d28dd-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="d28dd-122">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d28dd-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="d28dd-123">Identificador de región</span><span class="sxs-lookup"><span data-stu-id="d28dd-123">Region ID</span></span>  |     <span data-ttu-id="d28dd-124">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="d28dd-124">Region 1 (India)</span></span>    |   <span data-ttu-id="d28dd-125">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="d28dd-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="d28dd-126">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="d28dd-126">Define network subnets</span></span>

<span data-ttu-id="d28dd-127">Usar el ``New-CsTenantNetworkSubnet`` cmdlet para definir subredes de red y asociarlos a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="d28dd-127">Use the ``New-CsTenantNetworkSubnet`` cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="d28dd-128">Sólo se puede asociar con un sitio cada subred interna.</span><span class="sxs-lookup"><span data-stu-id="d28dd-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="d28dd-129">En este ejemplo, se crea una asociación entre la subred 192.168.0.0 y el sitio de red de Delhi y entre la subred 192.168.1.0 y el sitio de red de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="d28dd-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="d28dd-130">En la siguiente tabla muestra las subredes definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d28dd-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="d28dd-131">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="d28dd-131">Site 1</span></span> |<span data-ttu-id="d28dd-132">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="d28dd-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d28dd-133">Identificador de subred</span><span class="sxs-lookup"><span data-stu-id="d28dd-133">Subnet ID</span></span>   |    <span data-ttu-id="d28dd-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="d28dd-134">192.168.0.0</span></span>     |  <span data-ttu-id="d28dd-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="d28dd-135">192.168.1.0</span></span>     |
|<span data-ttu-id="d28dd-136">Máscara</span><span class="sxs-lookup"><span data-stu-id="d28dd-136">Mask</span></span>  |     <span data-ttu-id="d28dd-137">24</span><span class="sxs-lookup"><span data-stu-id="d28dd-137">24</span></span>    |   <span data-ttu-id="d28dd-138">24</span><span class="sxs-lookup"><span data-stu-id="d28dd-138">24</span></span>      |
|<span data-ttu-id="d28dd-139">Identificador de sitio</span><span class="sxs-lookup"><span data-stu-id="d28dd-139">Site ID</span></span>  | <span data-ttu-id="d28dd-140">Sitio (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d28dd-140">Site (Delhi)</span></span> | <span data-ttu-id="d28dd-141">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d28dd-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="d28dd-142">Para varias subredes, puede importar un archivo CSV mediante el uso de una secuencia de comandos como la siguiente.</span><span class="sxs-lookup"><span data-stu-id="d28dd-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="d28dd-143">En este ejemplo, el archivo CSV tiene el aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d28dd-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="d28dd-144">Definir subredes externas</span><span class="sxs-lookup"><span data-stu-id="d28dd-144">Define external subnets</span></span>
<span data-ttu-id="d28dd-145">Usar el ``New-CsTenantTrustedIPAddress`` cmdlet para definir subredes externas y asignarlas a los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d28dd-145">Use the ``New-CsTenantTrustedIPAddress`` cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="d28dd-146">Puede definir un número ilimitado de subredes de un inquilino.</span><span class="sxs-lookup"><span data-stu-id="d28dd-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="d28dd-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d28dd-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="d28dd-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d28dd-148">Next steps</span></span>
<span data-ttu-id="d28dd-149">Vaya a [Habilitar el enrutamiento basado en ubicación para el enrutamiento directo](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="d28dd-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="d28dd-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d28dd-150">Related topics</span></span>
- [<span data-ttu-id="d28dd-151">Planear enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="d28dd-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="d28dd-152">Terminología de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="d28dd-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)

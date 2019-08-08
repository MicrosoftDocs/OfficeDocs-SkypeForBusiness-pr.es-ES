---
title: Configuración de red de enrutamiento basado en la ubicación
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a crear y configurar regiones, sitios y subredes de red para el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245111"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="78336-103">Configuración de red de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="78336-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="78336-104">Si aún no lo ha hecho, lea [planificar el enrutamiento basado en la ubicación para que el enrutamiento directo](location-based-routing-plan.md) Revise otros pasos que debe realizar antes de configurar la configuración de red para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="78336-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="78336-105">En este artículo se describe cómo configurar las opciones de red para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="78336-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="78336-106">Después de implementar el enrutamiento directo de un sistema telefónico en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red.</span><span class="sxs-lookup"><span data-stu-id="78336-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="78336-107">Para completar los pasos de este artículo, necesitará cierta familiaridad con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78336-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="78336-108">Para obtener más información, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78336-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="78336-109">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="78336-109">Define network regions</span></span>
 <span data-ttu-id="78336-110">Una región de red interconecta varias partes de una red en varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="78336-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="78336-111">Use el cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) para definir regiones de red.</span><span class="sxs-lookup"><span data-stu-id="78336-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="78336-112">Tenga en cuenta que el parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones, &lt;y el&gt; parámetro de identificador de sitio CentralSite es opcional.</span><span class="sxs-lookup"><span data-stu-id="78336-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="78336-113">En este ejemplo, creamos una región de red denominada India.</span><span class="sxs-lookup"><span data-stu-id="78336-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="78336-114">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="78336-114">Define network sites</span></span>

<span data-ttu-id="78336-115">Use el cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sitios de red.</span><span class="sxs-lookup"><span data-stu-id="78336-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="78336-116">En este ejemplo, creamos dos nuevos sitios de red, Delhi y Hyderabad, en la región de India.</span><span class="sxs-lookup"><span data-stu-id="78336-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="78336-117">En la tabla siguiente se muestran los sitios de red definidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78336-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="78336-118">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="78336-118">Site 1</span></span> |<span data-ttu-id="78336-119">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="78336-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="78336-120">IDENTIFICADOR de sitio</span><span class="sxs-lookup"><span data-stu-id="78336-120">Site ID</span></span>    |    <span data-ttu-id="78336-121">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="78336-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="78336-122">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="78336-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="78336-123">IDENTIFICADOR de región</span><span class="sxs-lookup"><span data-stu-id="78336-123">Region ID</span></span>  |     <span data-ttu-id="78336-124">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="78336-124">Region 1 (India)</span></span>    |   <span data-ttu-id="78336-125">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="78336-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="78336-126">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="78336-126">Define network subnets</span></span>

<span data-ttu-id="78336-127">Use el cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir subredes de red y asociarlas a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="78336-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="78336-128">Cada subred interna solo se puede asociar con un sitio.</span><span class="sxs-lookup"><span data-stu-id="78336-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="78336-129">En este ejemplo, creamos una asociación entre la subred 192.168.0.0 y el sitio de red de Delhi y entre la subred 2001:4898: E8:25:844e: 926f: 85ad: dd8e y el sitio de red de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="78336-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="78336-130">En la tabla siguiente se muestran las subredes definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78336-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="78336-131">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="78336-131">Site 1</span></span> |<span data-ttu-id="78336-132">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="78336-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="78336-133">IDENTIFICADOR de subred</span><span class="sxs-lookup"><span data-stu-id="78336-133">Subnet ID</span></span>   |    <span data-ttu-id="78336-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="78336-134">192.168.0.0</span></span>     |  <span data-ttu-id="78336-135">2001:4898: E8:25:844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="78336-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="78336-136">Sin</span><span class="sxs-lookup"><span data-stu-id="78336-136">Mask</span></span>  |     <span data-ttu-id="78336-137">veinticuatro</span><span class="sxs-lookup"><span data-stu-id="78336-137">24</span></span>    |   <span data-ttu-id="78336-138">120</span><span class="sxs-lookup"><span data-stu-id="78336-138">120</span></span>      |
|<span data-ttu-id="78336-139">IDENTIFICADOR de sitio</span><span class="sxs-lookup"><span data-stu-id="78336-139">Site ID</span></span>  | <span data-ttu-id="78336-140">Sitio (Delhi)</span><span class="sxs-lookup"><span data-stu-id="78336-140">Site (Delhi)</span></span> | <span data-ttu-id="78336-141">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="78336-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="78336-142">En el caso de varias subredes, puede importar un archivo CSV con una secuencia de comandos como la siguiente.</span><span class="sxs-lookup"><span data-stu-id="78336-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="78336-143">En este ejemplo, el archivo CSV tiene un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="78336-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="78336-144">Definir subredes externas</span><span class="sxs-lookup"><span data-stu-id="78336-144">Define external subnets</span></span>
<span data-ttu-id="78336-145">Use el cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir subredes externas y asignarlas al inquilino.</span><span class="sxs-lookup"><span data-stu-id="78336-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="78336-146">Puede definir un número ilimitado de subredes para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="78336-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="78336-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78336-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="78336-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="78336-148">Next steps</span></span>
<span data-ttu-id="78336-149">Vaya a [Habilitar el enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="78336-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="78336-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="78336-150">Related topics</span></span>
- [<span data-ttu-id="78336-151">Planear enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="78336-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="78336-152">Terminología de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="78336-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)

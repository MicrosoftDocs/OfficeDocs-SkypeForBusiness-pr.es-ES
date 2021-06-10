---
title: Optimización de medios locales de enrutamiento directo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurar la optimización de medios locales para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576992"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="f9b54-103">Configurar la optimización de medios locales para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="f9b54-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="f9b54-104">La configuración de optimización de medios locales se basa en la configuración de red que es común a otras características de voz en la nube, como el enrutamiento Location-Based y las llamadas de emergencia dinámicas.</span><span class="sxs-lookup"><span data-stu-id="f9b54-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="f9b54-105">Para obtener más información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza, vea Configuración de red para [características de voz en la nube.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f9b54-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="f9b54-106">Antes de configurar la optimización de medios locales, [vea Optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="f9b54-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="f9b54-107">Para configurar la optimización de medios locales, se necesitan los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9b54-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="f9b54-108">Puede usar el Centro Teams de administración o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9b54-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="f9b54-109">Para obtener más información, [vea Administrar la topología de red.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="f9b54-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="f9b54-110">Configure el usuario y los sitios de SBC (como se describe en este artículo).</span><span class="sxs-lookup"><span data-stu-id="f9b54-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="f9b54-111">Configure los SBC para la optimización de medios locales (según la especificación del proveedor de SBC).</span><span class="sxs-lookup"><span data-stu-id="f9b54-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="f9b54-112">En el siguiente diagrama se muestra la configuración de red usada en los ejemplos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="f9b54-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="f9b54-113">![Diagrama que muestra la configuración de red para ejemplos](media/direct-routing-media-op-9.png "Configuración de red para ejemplos")</span><span class="sxs-lookup"><span data-stu-id="f9b54-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="f9b54-114">Configurar el usuario y los sitios de SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="f9b54-115">Para configurar el usuario y los sitios de SBC, deberá:</span><span class="sxs-lookup"><span data-stu-id="f9b54-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="f9b54-116">[Administrar direcciones IP de confianza externa.](#manage-external-trusted-ip-addresses)</span><span class="sxs-lookup"><span data-stu-id="f9b54-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="f9b54-117">[Defina la topología de red](#define-the-network-topology) configurando las regiones de red, los sitios de red y las subredes de red.</span><span class="sxs-lookup"><span data-stu-id="f9b54-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="f9b54-118">[Defina la topología de red virtual](#define-the-virtual-network-topology) asignando SBC a sitios con modos relevantes y valores SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="f9b54-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="f9b54-119">Configurar SBC para optimización de medios locales según la especificación de proveedor de SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="f9b54-120">En este artículo se describe la configuración de los componentes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9b54-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="f9b54-121">Para obtener información sobre la configuración de SBC, consulte la documentación del proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="f9b54-122">La optimización de medios locales es compatible con los siguientes proveedores de SBC:</span><span class="sxs-lookup"><span data-stu-id="f9b54-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="f9b54-123">Proveedor</span><span class="sxs-lookup"><span data-stu-id="f9b54-123">Vendor</span></span> | <span data-ttu-id="f9b54-124">Producto</span><span class="sxs-lookup"><span data-stu-id="f9b54-124">Product</span></span> |    <span data-ttu-id="f9b54-125">Versión de software</span><span class="sxs-lookup"><span data-stu-id="f9b54-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="f9b54-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="f9b54-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="f9b54-127">SBC Mediant 500</span><span class="sxs-lookup"><span data-stu-id="f9b54-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="f9b54-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f9b54-129">SBC Mediant 800</span><span class="sxs-lookup"><span data-stu-id="f9b54-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="f9b54-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f9b54-131">SBC Mediant 2600</span><span class="sxs-lookup"><span data-stu-id="f9b54-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="f9b54-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f9b54-133">SBC Mediant 4000</span><span class="sxs-lookup"><span data-stu-id="f9b54-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="f9b54-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f9b54-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="f9b54-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f9b54-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="f9b54-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f9b54-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="f9b54-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f9b54-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="f9b54-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="f9b54-142">7.20A.256</span></span> |
| [<span data-ttu-id="f9b54-143">Cinta de SBC Core</span><span class="sxs-lookup"><span data-stu-id="f9b54-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="f9b54-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="f9b54-144">SBC 5110</span></span>         | <span data-ttu-id="f9b54-145">8.2</span><span class="sxs-lookup"><span data-stu-id="f9b54-145">8.2</span></span>  |
|            |  <span data-ttu-id="f9b54-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="f9b54-146">SBC 5210</span></span>         | <span data-ttu-id="f9b54-147">8.2</span><span class="sxs-lookup"><span data-stu-id="f9b54-147">8.2</span></span>  |
|            |  <span data-ttu-id="f9b54-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="f9b54-148">SBC 5400</span></span>         | <span data-ttu-id="f9b54-149">8.2</span><span class="sxs-lookup"><span data-stu-id="f9b54-149">8.2</span></span>  |
|            |  <span data-ttu-id="f9b54-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="f9b54-150">SBC 7000</span></span>         | <span data-ttu-id="f9b54-151">8.2</span><span class="sxs-lookup"><span data-stu-id="f9b54-151">8.2</span></span>  |
|            |  <span data-ttu-id="f9b54-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="f9b54-152">SBC SWe</span></span>          | <span data-ttu-id="f9b54-153">8.2</span><span class="sxs-lookup"><span data-stu-id="f9b54-153">8.2</span></span>  |
| [<span data-ttu-id="f9b54-154">Cinta de opciones SBC Edge</span><span class="sxs-lookup"><span data-stu-id="f9b54-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="f9b54-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="f9b54-155">SBC SWe Lite</span></span> | <span data-ttu-id="f9b54-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="f9b54-156">8.1.5</span></span> |
|               | <span data-ttu-id="f9b54-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="f9b54-157">SBC 1000</span></span> | <span data-ttu-id="f9b54-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="f9b54-158">8.1.5</span></span>  |
|               | <span data-ttu-id="f9b54-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="f9b54-159">SBC 2000</span></span> | <span data-ttu-id="f9b54-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="f9b54-160">8.1.5</span></span>  |
| [<span data-ttu-id="f9b54-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="f9b54-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="f9b54-162">anynode</span><span class="sxs-lookup"><span data-stu-id="f9b54-162">anynode</span></span>          | <span data-ttu-id="f9b54-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="f9b54-163">4.0.1+</span></span> |
| [<span data-ttu-id="f9b54-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="f9b54-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="f9b54-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="f9b54-165">AP 1100</span></span> | <span data-ttu-id="f9b54-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f9b54-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="f9b54-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="f9b54-167">AP 3900</span></span> | <span data-ttu-id="f9b54-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f9b54-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="f9b54-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="f9b54-169">AP 4600</span></span> | <span data-ttu-id="f9b54-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f9b54-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="f9b54-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="f9b54-171">AP 6300</span></span> | <span data-ttu-id="f9b54-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f9b54-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="f9b54-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="f9b54-173">AP 6350</span></span> | <span data-ttu-id="f9b54-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f9b54-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="f9b54-175">VME</span><span class="sxs-lookup"><span data-stu-id="f9b54-175">VME</span></span>     | <span data-ttu-id="f9b54-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f9b54-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="f9b54-177">Administrar direcciones IP de confianza externa</span><span class="sxs-lookup"><span data-stu-id="f9b54-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="f9b54-178">Las IP de confianza externa son las IP externas de Internet de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="f9b54-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="f9b54-179">Estas DIRECCIONES IP son las direcciones IP que usan los Microsoft Teams cuando se conectan a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9b54-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="f9b54-180">Debe agregar estas IP externas para cada sitio en el que tenga usuarios con optimización de medios locales.</span><span class="sxs-lookup"><span data-stu-id="f9b54-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="f9b54-181">Para agregar las direcciones IP públicas de cada sitio, use el cmdlet New-CsTenantTrustedIPAddress sitio.</span><span class="sxs-lookup"><span data-stu-id="f9b54-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="f9b54-182">Puede definir un número ilimitado de direcciones IP de confianza para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="f9b54-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="f9b54-183">Si las direcciones IP externas que Microsoft 365 son direcciones IPv4 e IPv6, debe agregar ambos tipos de direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="f9b54-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="f9b54-184">Para IPv4, use la máscara 32.</span><span class="sxs-lookup"><span data-stu-id="f9b54-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="f9b54-185">Para IPv6, use la máscara 128.</span><span class="sxs-lookup"><span data-stu-id="f9b54-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="f9b54-186">Puede agregar direcciones IP externas individuales y subredes IP externas especificando diferentes MaskBits en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f9b54-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="f9b54-187">Ejemplo de agregar direcciones IP de confianza.</span><span class="sxs-lookup"><span data-stu-id="f9b54-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="f9b54-188">Definir la topología de red</span><span class="sxs-lookup"><span data-stu-id="f9b54-188">Define the network topology</span></span>

<span data-ttu-id="f9b54-189">En esta sección se describe cómo definir las regiones de red, los sitios de red y las subredes de red para la topología de red.</span><span class="sxs-lookup"><span data-stu-id="f9b54-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="f9b54-190">Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de usar el mismo caso que se usó durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="f9b54-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="f9b54-191">(Por ejemplo, los valores GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).</span><span class="sxs-lookup"><span data-stu-id="f9b54-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="f9b54-192">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="f9b54-192">Define network regions</span></span>

<span data-ttu-id="f9b54-193">Para definir regiones de red, use el cmdlet New-CsTenantNetworkRegion red.</span><span class="sxs-lookup"><span data-stu-id="f9b54-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="f9b54-194">El parámetro Id.región es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones.</span><span class="sxs-lookup"><span data-stu-id="f9b54-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="f9b54-195">El parámetro CentralSite <site ID> es opcional.</span><span class="sxs-lookup"><span data-stu-id="f9b54-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="f9b54-196">En el ejemplo siguiente se crea una región de red denominada APAC:</span><span class="sxs-lookup"><span data-stu-id="f9b54-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="f9b54-197">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="f9b54-197">Define network sites</span></span>

<span data-ttu-id="f9b54-198">Para definir sitios de red, use el cmdlet New-CsTenantNetworkSite red.</span><span class="sxs-lookup"><span data-stu-id="f9b54-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="f9b54-199">Cada sitio de red debe estar asociado a una región de red.</span><span class="sxs-lookup"><span data-stu-id="f9b54-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="f9b54-200">En el ejemplo siguiente se crean tres nuevos sitios de red, Vietnam, Indonesia y Singapur en la región de APAC:</span><span class="sxs-lookup"><span data-stu-id="f9b54-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="f9b54-201">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="f9b54-201">Define network subnets</span></span>

<span data-ttu-id="f9b54-202">Para definir subredes de red y asociarlas a sitios de red, use el cmdlet New-CsTenantNetworkSubnet red.</span><span class="sxs-lookup"><span data-stu-id="f9b54-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="f9b54-203">Cada subred de red solo se puede asociar a un sitio.</span><span class="sxs-lookup"><span data-stu-id="f9b54-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="f9b54-204">En el ejemplo siguiente se definen tres subredes de red y se asocian a los tres sitios de red: Vietnam, Indonesia y Singapur:</span><span class="sxs-lookup"><span data-stu-id="f9b54-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="f9b54-205">Definir la topología de red virtual</span><span class="sxs-lookup"><span data-stu-id="f9b54-205">Define the virtual network topology</span></span> 

<span data-ttu-id="f9b54-206">En primer lugar, el administrador de inquilinos crea una nueva configuración de SBC para cada SBC relevante mediante el cmdlet New-CsOnlinePSTNGateway espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="f9b54-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="f9b54-207">El administrador de inquilinos define la topología de red virtual especificando los sitios de red para los objetos de puerta de enlace RTC con el cmdlet Set-CsOnlinePSTNGateway datos:</span><span class="sxs-lookup"><span data-stu-id="f9b54-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="f9b54-208">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9b54-208">Note the following:</span></span> 
   - <span data-ttu-id="f9b54-209">Si el cliente tiene un único SBC, el parámetro -ProxySBC debe ser obligatorio $null o fqdn de SBC (escenario de SBC central con troncos centralizados).</span><span class="sxs-lookup"><span data-stu-id="f9b54-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="f9b54-210">El parámetro -MediaBypass debe establecerse en $true para admitir la optimización de medios locales.</span><span class="sxs-lookup"><span data-stu-id="f9b54-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="f9b54-211">Si el SBC no tiene el conjunto de parámetros -BypassMode, los encabezados X-MS no se enviarán.</span><span class="sxs-lookup"><span data-stu-id="f9b54-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="f9b54-212">Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de que usa el mismo caso que se usó durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="f9b54-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="f9b54-213">(Por ejemplo, los valores GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).</span><span class="sxs-lookup"><span data-stu-id="f9b54-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="f9b54-214">En el ejemplo siguiente se agregan tres SBC a los sitios de red Vietnam, Indonesia y Singapur en la región de APAC con el modo Omitir siempre:</span><span class="sxs-lookup"><span data-stu-id="f9b54-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="f9b54-215">Nota: Para garantizar las operaciones sin interrupciones cuando la optimización de medios locales y el enrutamiento Location-Based (LBR) están configurados al mismo tiempo, los SBC descendentes deben habilitarse para LBR estableciendo el parámetro GatewaySiteLbrEnabled en $true para cada SBC descendente.</span><span class="sxs-lookup"><span data-stu-id="f9b54-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="f9b54-216">(Esta configuración no es obligatoria para el SBC proxy).</span><span class="sxs-lookup"><span data-stu-id="f9b54-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="f9b54-217">Según la información anterior, enrutamiento directo incluirá tres encabezados SIP propietarios a invitaciones SIP y re-invitaciones, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9b54-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="f9b54-218">Encabezados X-MS introducidos en Enrutamiento directo en invitaciones y Re-Invites si BypassMode está definido:</span><span class="sxs-lookup"><span data-stu-id="f9b54-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="f9b54-219">Nombre del encabezado</span><span class="sxs-lookup"><span data-stu-id="f9b54-219">Header name</span></span> | <span data-ttu-id="f9b54-220">Valores</span><span class="sxs-lookup"><span data-stu-id="f9b54-220">Values</span></span> | <span data-ttu-id="f9b54-221">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9b54-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="f9b54-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="f9b54-222">X-MS-UserLocation</span></span> | <span data-ttu-id="f9b54-223">interno/externo</span><span class="sxs-lookup"><span data-stu-id="f9b54-223">internal/external</span></span> | <span data-ttu-id="f9b54-224">Indica si el usuario es interno o externo</span><span class="sxs-lookup"><span data-stu-id="f9b54-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="f9b54-225">Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="f9b54-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="f9b54-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="f9b54-226">SBC FQDN</span></span> | <span data-ttu-id="f9b54-227">El FQDN que está dirigido a la llamada incluso si el SBC no está conectado directamente al enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="f9b54-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="f9b54-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="f9b54-228">X-MS-MediaPath</span></span> | <span data-ttu-id="f9b54-229">Ejemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="f9b54-230">Orden de SBC que debe usarse para la ruta de acceso multimedia entre el usuario y el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="f9b54-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="f9b54-231">El SBC final siempre es el último</span><span class="sxs-lookup"><span data-stu-id="f9b54-231">The final SBC is always last</span></span> |
| <span data-ttu-id="f9b54-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="f9b54-232">X-MS-UserSite</span></span> | <span data-ttu-id="f9b54-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="f9b54-233">usersiteID</span></span> | <span data-ttu-id="f9b54-234">Cadena definida por el administrador de inquilinos</span><span class="sxs-lookup"><span data-stu-id="f9b54-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="f9b54-235">Flujos de llamadas</span><span class="sxs-lookup"><span data-stu-id="f9b54-235">Call flows</span></span> 

<span data-ttu-id="f9b54-236">A continuación se muestran los flujos de llamadas para dos modos:</span><span class="sxs-lookup"><span data-stu-id="f9b54-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="f9b54-237">Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="f9b54-238">Solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="f9b54-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="f9b54-239">Modo Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-239">Always Bypass mode</span></span>

<span data-ttu-id="f9b54-240">El modo Omitir siempre es la opción más sencilla de configurar.</span><span class="sxs-lookup"><span data-stu-id="f9b54-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="f9b54-241">El administrador de inquilinos puede configurar un único sitio para todos los usuarios y SBC si todos los SBC son accesibles desde cualquier sitio.</span><span class="sxs-lookup"><span data-stu-id="f9b54-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="f9b54-242">Los ejemplos muestran el modo de omisión siempre para los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="f9b54-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="f9b54-243">Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="f9b54-244">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="f9b54-245">Llamadas salientes y el usuario es externo</span><span class="sxs-lookup"><span data-stu-id="f9b54-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="f9b54-246">Llamadas entrantes y el usuario es externo</span><span class="sxs-lookup"><span data-stu-id="f9b54-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="f9b54-247">En la tabla siguiente se muestran los FQDN y las direcciones IP que se usan en los ejemplos:</span><span class="sxs-lookup"><span data-stu-id="f9b54-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="f9b54-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="f9b54-248">FQDN</span></span> | <span data-ttu-id="f9b54-249">Dirección IP externa de SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-249">SBC external IP address</span></span> | <span data-ttu-id="f9b54-250">Dirección IP interna de SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-250">SBC internal IP Address</span></span> | <span data-ttu-id="f9b54-251">Subred interna</span><span class="sxs-lookup"><span data-stu-id="f9b54-251">Internal subnet</span></span> | <span data-ttu-id="f9b54-252">Ubicación</span><span class="sxs-lookup"><span data-stu-id="f9b54-252">Location</span></span> | <span data-ttu-id="f9b54-253">NAT externa (IP de confianza)</span><span class="sxs-lookup"><span data-stu-id="f9b54-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="f9b54-255">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f9b54-255">None</span></span> | <span data-ttu-id="f9b54-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="f9b54-256">192.168.1.5</span></span> | <span data-ttu-id="f9b54-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="f9b54-257">192.168.1.0/24</span></span> | <span data-ttu-id="f9b54-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="f9b54-258">Vietnam</span></span> | <span data-ttu-id="f9b54-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="f9b54-259">172.16.240.110</span></span> |
| <span data-ttu-id="f9b54-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="f9b54-261">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f9b54-261">None</span></span> | <span data-ttu-id="f9b54-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="f9b54-262">192.168.2.5</span></span> | <span data-ttu-id="f9b54-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="f9b54-263">192.168.2.0/24</span></span> | <span data-ttu-id="f9b54-264">Indonesia</span><span class="sxs-lookup"><span data-stu-id="f9b54-264">Indonesia</span></span> | <span data-ttu-id="f9b54-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="f9b54-265">172.16.240.120</span></span> |
| <span data-ttu-id="f9b54-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="f9b54-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="f9b54-267">172.16.240.133</span></span> | <span data-ttu-id="f9b54-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="f9b54-268">192.168.3.5</span></span> | <span data-ttu-id="f9b54-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="f9b54-269">192.168.3.0/24</span></span> | <span data-ttu-id="f9b54-270">Singapur</span><span class="sxs-lookup"><span data-stu-id="f9b54-270">Singapore</span></span> | <span data-ttu-id="f9b54-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="f9b54-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="f9b54-272">Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC con Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="f9b54-273">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-273">Mode</span></span> |    <span data-ttu-id="f9b54-274">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-274">User</span></span> |  <span data-ttu-id="f9b54-275">Ubicación</span><span class="sxs-lookup"><span data-stu-id="f9b54-275">Location</span></span> |  <span data-ttu-id="f9b54-276">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="f9b54-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f9b54-277">AlwaysBypass</span></span> |    <span data-ttu-id="f9b54-278">Interno</span><span class="sxs-lookup"><span data-stu-id="f9b54-278">Internal</span></span> |  <span data-ttu-id="f9b54-279">El mismo sitio que SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-279">The same site as SBC</span></span> |  <span data-ttu-id="f9b54-280">Saliente</span><span class="sxs-lookup"><span data-stu-id="f9b54-280">Outbound</span></span> |

<span data-ttu-id="f9b54-281">En la tabla siguiente se muestra la configuración y la acción del usuario final:</span><span class="sxs-lookup"><span data-stu-id="f9b54-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="f9b54-282">Ubicación física del usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-282">User physical location</span></span>| <span data-ttu-id="f9b54-283">El usuario realiza o recibe una llamada a/desde un número</span><span class="sxs-lookup"><span data-stu-id="f9b54-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="f9b54-284">Número de teléfono de usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-284">User phone number</span></span>  | <span data-ttu-id="f9b54-285">Directiva de enrutamiento de voz en línea</span><span class="sxs-lookup"><span data-stu-id="f9b54-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="f9b54-286">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="f9b54-287">Vietnam</span></span> | <span data-ttu-id="f9b54-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="f9b54-288">+84 4 3926 3000</span></span> | <span data-ttu-id="f9b54-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="f9b54-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="f9b54-290">Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="f9b54-291">Prioridad 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="f9b54-292">VNsbc.contoso.com: omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="f9b54-293">proxysbc.contoso.com: omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="f9b54-294">En el siguiente diagrama se muestra la escala SIP para una llamada saliente con el modo Desviado siempre y el usuario en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="f9b54-295">![Diagrama que muestra las llamadas salientes](media/direct-routing-media-op-10.png "Llamadas salientes")</span><span class="sxs-lookup"><span data-stu-id="f9b54-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="f9b54-296">En la tabla siguiente se muestran los encabezados X-MS enviados por Enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="f9b54-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="f9b54-297">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f9b54-297">Parameter</span></span> | <span data-ttu-id="f9b54-298">Explicación</span><span class="sxs-lookup"><span data-stu-id="f9b54-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="f9b54-299">Invitar +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="f9b54-300">El FQDN de destino del SBC definido en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud</span><span class="sxs-lookup"><span data-stu-id="f9b54-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="f9b54-301">X-MS-UserLocation: interno</span><span class="sxs-lookup"><span data-stu-id="f9b54-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="f9b54-302">El campo indicaba que el usuario se encuentra dentro de la red corporativa</span><span class="sxs-lookup"><span data-stu-id="f9b54-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="f9b54-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="f9b54-304">Especifica el SBC que el cliente debe atravesar hasta el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="f9b54-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="f9b54-305">En este caso, como siempre hemos omitdo, y el cliente es interno el nombre de destino enviado como el único nombre en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="f9b54-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="f9b54-306">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="f9b54-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="f9b54-307">El campo indicado dentro del sitio donde se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="f9b54-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="f9b54-308">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC con Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="f9b54-309">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-309">Mode</span></span> |    <span data-ttu-id="f9b54-310">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-310">User</span></span> |  <span data-ttu-id="f9b54-311">Ubicación</span><span class="sxs-lookup"><span data-stu-id="f9b54-311">Location</span></span> |  <span data-ttu-id="f9b54-312">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f9b54-313">AlwaysBypass</span></span> |    <span data-ttu-id="f9b54-314">Interno</span><span class="sxs-lookup"><span data-stu-id="f9b54-314">Internal</span></span> | <span data-ttu-id="f9b54-315">El mismo sitio que SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-315">The same site as SBC</span></span> | <span data-ttu-id="f9b54-316">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9b54-316">Inbound</span></span> |


<span data-ttu-id="f9b54-317">En una llamada entrante, se desconoce la ubicación del usuario y el SBC debe adivinar dónde está el usuario.</span><span class="sxs-lookup"><span data-stu-id="f9b54-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="f9b54-318">Si la conjetura no es correcta, se requiere una nueva invitación.</span><span class="sxs-lookup"><span data-stu-id="f9b54-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="f9b54-319">En este caso se supone que el usuario es interno, que los medios pueden fluir directamente y que no es necesario realizar más acciones (volver a invitar).</span><span class="sxs-lookup"><span data-stu-id="f9b54-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="f9b54-320">El SBC conectado al servicio de enrutamiento directo notifica la ubicación de SBC de origen proporcionando Record-Route y campos de contacto.</span><span class="sxs-lookup"><span data-stu-id="f9b54-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="f9b54-321">En función de estos campos, la ruta de acceso multimedia se calcula mediante enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="f9b54-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="f9b54-322">Nota: Dado que un usuario puede tener varios puntos de conexión, no es posible admitir 183.</span><span class="sxs-lookup"><span data-stu-id="f9b54-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="f9b54-323">El enrutamiento directo siempre usará 180 llamadas en este caso.</span><span class="sxs-lookup"><span data-stu-id="f9b54-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="f9b54-324">En el siguiente diagrama se muestra la escala SIP para las llamadas entrantes con el modo AlwaysBypass y el usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="f9b54-326">Llamadas salientes y el usuario es externo con Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="f9b54-327">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-327">Mode</span></span> |    <span data-ttu-id="f9b54-328">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-328">User</span></span> |  <span data-ttu-id="f9b54-329">Sitio</span><span class="sxs-lookup"><span data-stu-id="f9b54-329">Site</span></span> |  <span data-ttu-id="f9b54-330">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="f9b54-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f9b54-331">AlwaysBypass</span></span> |  <span data-ttu-id="f9b54-332">Externo</span><span class="sxs-lookup"><span data-stu-id="f9b54-332">External</span></span> |  <span data-ttu-id="f9b54-333">N/D</span><span class="sxs-lookup"><span data-stu-id="f9b54-333">N/A</span></span> | <span data-ttu-id="f9b54-334">Saliente</span><span class="sxs-lookup"><span data-stu-id="f9b54-334">Outbound</span></span> |


<span data-ttu-id="f9b54-335">En el siguiente diagrama se muestra la escala SIP para una llamada saliente con el modo AlwaysBypass y el usuario es externo:</span><span class="sxs-lookup"><span data-stu-id="f9b54-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="f9b54-337">En la tabla siguiente se muestran los encabezados X-MS enviados por el servicio de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="f9b54-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="f9b54-338">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f9b54-338">Parameter</span></span> |   <span data-ttu-id="f9b54-339">Explicación</span><span class="sxs-lookup"><span data-stu-id="f9b54-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="f9b54-340">Invitar +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="f9b54-341">El FQDN de destino del SBC definido en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud.</span><span class="sxs-lookup"><span data-stu-id="f9b54-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="f9b54-342">X-MS-UserLocation: externa</span><span class="sxs-lookup"><span data-stu-id="f9b54-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="f9b54-343">El campo indicaba que el usuario se encuentra fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="f9b54-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="f9b54-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="f9b54-345">Especifica el SBC que el cliente debe atravesar hasta el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="f9b54-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="f9b54-346">En este caso, como siempre hemos omitdo, y el cliente es externo.</span><span class="sxs-lookup"><span data-stu-id="f9b54-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="f9b54-347">Las llamadas entrantes y el usuario son externos con Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="f9b54-348">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-348">Mode</span></span> | <span data-ttu-id="f9b54-349">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-349">User</span></span> | <span data-ttu-id="f9b54-350">Sitio</span><span class="sxs-lookup"><span data-stu-id="f9b54-350">Site</span></span> |  <span data-ttu-id="f9b54-351">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="f9b54-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f9b54-352">AlwaysBypass</span></span> |  <span data-ttu-id="f9b54-353">Externo</span><span class="sxs-lookup"><span data-stu-id="f9b54-353">External</span></span> |  <span data-ttu-id="f9b54-354">N/D</span><span class="sxs-lookup"><span data-stu-id="f9b54-354">N/A</span></span> |   <span data-ttu-id="f9b54-355">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9b54-355">Inbound</span></span> |

<span data-ttu-id="f9b54-356">Para una llamada entrante, el SBC conectado a Enrutamiento directo debe enviar una nueva invitación (de forma predeterminada, siempre se ofrecen candidatos de medios locales) si la ubicación del usuario es externa.</span><span class="sxs-lookup"><span data-stu-id="f9b54-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="f9b54-357">X-MediaPath se calcula en función Record-Route usuario de SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="f9b54-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="f9b54-358">En el siguiente diagrama se muestra la escala SIP de una llamada entrante con el modo AlwaysBypass y el usuario es externo.</span><span class="sxs-lookup"><span data-stu-id="f9b54-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="f9b54-360">Solo para el modo de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="f9b54-360">Only for local users mode</span></span>

<span data-ttu-id="f9b54-361">Los candidatos de medios locales del SBC de destino solo se ofrecerán si un usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="f9b54-362">En todos los demás casos, los medios fluirán a través de una IP interna o externa del SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="f9b54-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="f9b54-363">Se describen los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="f9b54-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="f9b54-364">Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="f9b54-365">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="f9b54-366">El usuario no está en la misma ubicación que el SBC, pero está en la red corporativa</span><span class="sxs-lookup"><span data-stu-id="f9b54-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="f9b54-367">Las llamadas entrantes y el usuario son internos, pero no se encuentra en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="f9b54-368">En la tabla siguiente se muestra la configuración y la acción del usuario final:</span><span class="sxs-lookup"><span data-stu-id="f9b54-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="f9b54-369">Ubicación física del usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-369">User physical location</span></span> |  <span data-ttu-id="f9b54-370">El usuario realiza o recibe una llamada a/desde un número</span><span class="sxs-lookup"><span data-stu-id="f9b54-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="f9b54-371">Número de teléfono de usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-371">User phone number</span></span> | <span data-ttu-id="f9b54-372">Directiva de enrutamiento de voz en línea</span><span class="sxs-lookup"><span data-stu-id="f9b54-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="f9b54-373">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="f9b54-374">Vietnam</span></span> | <span data-ttu-id="f9b54-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="f9b54-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="f9b54-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="f9b54-376">+84 4 5555 5555</span></span> | <span data-ttu-id="f9b54-377">Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="f9b54-378">Prioridad 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9b54-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="f9b54-379">VNsbc.contoso.com: OnlyForLocalUsers Proxysbc.contoso.com– Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="f9b54-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="f9b54-380">Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC con solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="f9b54-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="f9b54-381">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-381">Mode</span></span> | <span data-ttu-id="f9b54-382">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-382">User</span></span> | <span data-ttu-id="f9b54-383">Sitio</span><span class="sxs-lookup"><span data-stu-id="f9b54-383">Site</span></span> | <span data-ttu-id="f9b54-384">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f9b54-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="f9b54-386">Interno</span><span class="sxs-lookup"><span data-stu-id="f9b54-386">Internal</span></span> |<span data-ttu-id="f9b54-387">Igual que SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-387">Same as SBC</span></span>   | <span data-ttu-id="f9b54-388">Saliente</span><span class="sxs-lookup"><span data-stu-id="f9b54-388">Outbound</span></span> |

<span data-ttu-id="f9b54-389">En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="f9b54-390">Este es el mismo flujo que se muestra en las llamadas salientes cuando el [usuario se encuentra en la misma ubicación que el SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="f9b54-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="f9b54-392">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC con solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="f9b54-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="f9b54-393">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-393">Mode</span></span> | <span data-ttu-id="f9b54-394">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-394">User</span></span> | <span data-ttu-id="f9b54-395">Sitio</span><span class="sxs-lookup"><span data-stu-id="f9b54-395">Site</span></span> | <span data-ttu-id="f9b54-396">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f9b54-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="f9b54-398">Interno</span><span class="sxs-lookup"><span data-stu-id="f9b54-398">Internal</span></span> | <span data-ttu-id="f9b54-399">Igual que SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-399">Same as SBC</span></span> | <span data-ttu-id="f9b54-400">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9b54-400">Inbound</span></span> |

<span data-ttu-id="f9b54-401">En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="f9b54-402">Este es el mismo flujo que se muestra en Las llamadas entrantes cuando el [usuario se encuentra en la misma ubicación que el SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="f9b54-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="f9b54-404">El usuario no está en la misma ubicación que el SBC, pero está en la red corporativa con Solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="f9b54-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="f9b54-405">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-405">Mode</span></span> | <span data-ttu-id="f9b54-406">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-406">User</span></span> | <span data-ttu-id="f9b54-407">Sitio</span><span class="sxs-lookup"><span data-stu-id="f9b54-407">Site</span></span> |<span data-ttu-id="f9b54-408">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f9b54-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="f9b54-410">Interno</span><span class="sxs-lookup"><span data-stu-id="f9b54-410">Internal</span></span> |   <span data-ttu-id="f9b54-411">Diferente de SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-411">Different from SBC</span></span> | <span data-ttu-id="f9b54-412">Saliente</span><span class="sxs-lookup"><span data-stu-id="f9b54-412">Outbound</span></span> |

<span data-ttu-id="f9b54-413">El enrutamiento directo calcula X-MediaPath en función de la ubicación notificada del usuario y el modo configurado en el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="f9b54-414">En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="f9b54-416">La llamada entrante y el usuario es interno, pero no se encuentra en la misma ubicación que el SBC con solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="f9b54-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="f9b54-417">Modo</span><span class="sxs-lookup"><span data-stu-id="f9b54-417">Mode</span></span> |    <span data-ttu-id="f9b54-418">Usuario</span><span class="sxs-lookup"><span data-stu-id="f9b54-418">User</span></span> |  <span data-ttu-id="f9b54-419">Sitio</span><span class="sxs-lookup"><span data-stu-id="f9b54-419">Site</span></span> |  <span data-ttu-id="f9b54-420">Dirección de llamada</span><span class="sxs-lookup"><span data-stu-id="f9b54-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f9b54-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f9b54-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="f9b54-422">Interno</span><span class="sxs-lookup"><span data-stu-id="f9b54-422">Internal</span></span> |    <span data-ttu-id="f9b54-423">Diferente de SBC</span><span class="sxs-lookup"><span data-stu-id="f9b54-423">Different from SBC</span></span> |    <span data-ttu-id="f9b54-424">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9b54-424">Inbound</span></span> |

<span data-ttu-id="f9b54-425">En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="f9b54-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-17.png)










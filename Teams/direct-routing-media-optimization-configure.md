---
title: Enrutamiento directo de multimedia local de enrutamiento
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
description: Configurar la optimización de medios locales para el enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 518445e10b757adc9a21c426fb885bb04b7a878b
ms.sourcegitcommit: b143611d14765af054a4f84cca52e2003d35af1a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44047859"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="da4c1-103">Configurar la optimización de medios locales para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="da4c1-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="da4c1-104">La configuración para la optimización de medios locales se basa en la configuración de red que es común a otras características de voz en la nube, como el enrutamiento basado en la ubicación y las llamadas de emergencia dinámicas.</span><span class="sxs-lookup"><span data-stu-id="da4c1-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="da4c1-105">Para obtener más información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza, consulte [configuración de red para características de voz en la nube](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="da4c1-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="da4c1-106">Antes de configurar la optimización de medios locales, consulte la [optimización local de medios para el enrutamiento directo](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="da4c1-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="da4c1-107">Para configurar la optimización local de medios, se requieren los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="da4c1-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="da4c1-108">Puede usar el centro de administración de Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da4c1-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="da4c1-109">Para obtener más información, consulte [administrar la topología de red](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="da4c1-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="da4c1-110">Configure el usuario y los sitios de SBC (como se describe en este artículo).</span><span class="sxs-lookup"><span data-stu-id="da4c1-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="da4c1-111">Configure el SBCs para la optimización de medios locales (según la especificación de proveedor de SBC).</span><span class="sxs-lookup"><span data-stu-id="da4c1-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="da4c1-112">En el siguiente diagrama se muestra la configuración de red usada en los ejemplos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="da4c1-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="da4c1-113">![Diagrama que muestra la configuración de red para ejemplos](media/direct-routing-media-op-9.png "Configuración de red para ejemplos")</span><span class="sxs-lookup"><span data-stu-id="da4c1-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="da4c1-114">Configurar el usuario y los sitios de SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="da4c1-115">Para configurar los sitios de usuario y SBC, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="da4c1-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="da4c1-116">[Administrar direcciones IP externas de confianza](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="da4c1-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="da4c1-117">[Defina la topología de red](#define-the-network-topology) configurando las regiones de red, los sitios de red y las subredes de red.</span><span class="sxs-lookup"><span data-stu-id="da4c1-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="da4c1-118">[Defina la topología de red virtual](#define-the-virtual-network-topology) asignando SBC (s) a los sitios con los modos y valores de SBC de proxy.</span><span class="sxs-lookup"><span data-stu-id="da4c1-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="da4c1-119">Configurar SBC (s) para la optimización de medios locales según la especificación de proveedor de SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="da4c1-120">En este artículo se describe la configuración de los componentes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da4c1-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="da4c1-121">Para obtener información sobre la configuración de SBC, consulte la documenation de proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="da4c1-122">La optimización local de medios es compatible con los siguientes proveedores de SBC:</span><span class="sxs-lookup"><span data-stu-id="da4c1-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="da4c1-123">Proveedor</span><span class="sxs-lookup"><span data-stu-id="da4c1-123">Vendor</span></span> | <span data-ttu-id="da4c1-124">Producto</span><span class="sxs-lookup"><span data-stu-id="da4c1-124">Product</span></span> |    <span data-ttu-id="da4c1-125">Versión del software</span><span class="sxs-lookup"><span data-stu-id="da4c1-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="da4c1-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="da4c1-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="da4c1-127">SBC Mediant 500</span><span class="sxs-lookup"><span data-stu-id="da4c1-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="da4c1-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="da4c1-129">SBC Mediant 800</span><span class="sxs-lookup"><span data-stu-id="da4c1-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="da4c1-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="da4c1-131">SBC Mediant 2600</span><span class="sxs-lookup"><span data-stu-id="da4c1-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="da4c1-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="da4c1-133">SBC Mediant 4000</span><span class="sxs-lookup"><span data-stu-id="da4c1-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="da4c1-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="da4c1-135">SBC 1000B</span><span class="sxs-lookup"><span data-stu-id="da4c1-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="da4c1-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="da4c1-137">SBC 9000</span><span class="sxs-lookup"><span data-stu-id="da4c1-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="da4c1-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="da4c1-139">SBC Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="da4c1-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="da4c1-141">La nube Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="da4c1-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="da4c1-142">7.20A.256</span></span> |
| [<span data-ttu-id="da4c1-143">Núcleo de SBC de cinta</span><span class="sxs-lookup"><span data-stu-id="da4c1-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="da4c1-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="da4c1-144">SBC 5110</span></span>         | <span data-ttu-id="da4c1-145">8,2</span><span class="sxs-lookup"><span data-stu-id="da4c1-145">8.2</span></span>  |
|            |  <span data-ttu-id="da4c1-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="da4c1-146">SBC 5210</span></span>         | <span data-ttu-id="da4c1-147">8,2</span><span class="sxs-lookup"><span data-stu-id="da4c1-147">8.2</span></span>  |
|            |  <span data-ttu-id="da4c1-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="da4c1-148">SBC 5400</span></span>         | <span data-ttu-id="da4c1-149">8,2</span><span class="sxs-lookup"><span data-stu-id="da4c1-149">8.2</span></span>  |
|            |  <span data-ttu-id="da4c1-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="da4c1-150">SBC 7000</span></span>         | <span data-ttu-id="da4c1-151">8,2</span><span class="sxs-lookup"><span data-stu-id="da4c1-151">8.2</span></span>  |
|            |  <span data-ttu-id="da4c1-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="da4c1-152">SBC SWe</span></span>          | <span data-ttu-id="da4c1-153">8,2</span><span class="sxs-lookup"><span data-stu-id="da4c1-153">8.2</span></span>  |
| [<span data-ttu-id="da4c1-154">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="da4c1-154">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="da4c1-155">anynode</span><span class="sxs-lookup"><span data-stu-id="da4c1-155">anynode</span></span>          | <span data-ttu-id="da4c1-156">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="da4c1-156">4.0.1+</span></span> |
| [<span data-ttu-id="da4c1-157">Oracle</span><span class="sxs-lookup"><span data-stu-id="da4c1-157">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="da4c1-158">AP 1100</span><span class="sxs-lookup"><span data-stu-id="da4c1-158">AP 1100</span></span> | <span data-ttu-id="da4c1-159">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="da4c1-159">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="da4c1-160">AP 3900</span><span class="sxs-lookup"><span data-stu-id="da4c1-160">AP 3900</span></span> | <span data-ttu-id="da4c1-161">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="da4c1-161">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="da4c1-162">AP 4600</span><span class="sxs-lookup"><span data-stu-id="da4c1-162">AP 4600</span></span> | <span data-ttu-id="da4c1-163">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="da4c1-163">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="da4c1-164">AP 6300</span><span class="sxs-lookup"><span data-stu-id="da4c1-164">AP 6300</span></span> | <span data-ttu-id="da4c1-165">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="da4c1-165">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="da4c1-166">AP 6350</span><span class="sxs-lookup"><span data-stu-id="da4c1-166">AP 6350</span></span> | <span data-ttu-id="da4c1-167">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="da4c1-167">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="da4c1-168">VME</span><span class="sxs-lookup"><span data-stu-id="da4c1-168">VME</span></span>     | <span data-ttu-id="da4c1-169">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="da4c1-169">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="da4c1-170">Administrar direcciones IP de confianza externas</span><span class="sxs-lookup"><span data-stu-id="da4c1-170">Manage external trusted IP addresses</span></span>

<span data-ttu-id="da4c1-171">Las direcciones IP externas de confianza son direcciones IP externas de Internet de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="da4c1-171">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="da4c1-172">Estas son las direcciones IP que usan los clientes de Microsoft Teams cuando se conectan a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da4c1-172">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="da4c1-173">Debe agregar estas direcciones IP externas para cada sitio en el que tenga usuarios que usen la optimización local de medios.</span><span class="sxs-lookup"><span data-stu-id="da4c1-173">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="da4c1-174">Para agregar las direcciones IP públicas de cada sitio, use el cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="da4c1-174">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="da4c1-175">Puede definir un número ilimitado de direcciones IP de confianza para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="da4c1-175">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="da4c1-176">Si el IPs externo visto por Microsoft 365 son direcciones IPv4 e IPv6, tendrá que agregar ambos tipos de direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="da4c1-176">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="da4c1-177">Para IPv4, use la máscara 32.</span><span class="sxs-lookup"><span data-stu-id="da4c1-177">For IPv4, use mask 32.</span></span> <span data-ttu-id="da4c1-178">Para IPv6, use la máscara 128.</span><span class="sxs-lookup"><span data-stu-id="da4c1-178">For IPv6, use mask 128.</span></span> <span data-ttu-id="da4c1-179">Puede agregar direcciones IP externas individuales y subredes IP externas especificando diferentes MaskBits en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="da4c1-179">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="da4c1-180">Ejemplo de adición de direcciones IP fiables.</span><span class="sxs-lookup"><span data-stu-id="da4c1-180">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="da4c1-181">Definir la topología de red</span><span class="sxs-lookup"><span data-stu-id="da4c1-181">Define the network topology</span></span>

<span data-ttu-id="da4c1-182">En esta sección se describe cómo definir las regiones de red, los sitios de red y las subredes de red para su topología de red.</span><span class="sxs-lookup"><span data-stu-id="da4c1-182">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="da4c1-183">Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de usar el mismo caso que se usó durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="da4c1-183">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="da4c1-184">(Por ejemplo, los valores de GatewaySiteID "Vietnam" y "Vietnam" se tratarán como sitios diferentes).</span><span class="sxs-lookup"><span data-stu-id="da4c1-184">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="da4c1-185">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="da4c1-185">Define network regions</span></span>

<span data-ttu-id="da4c1-186">Para definir regiones de red, use el cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="da4c1-186">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="da4c1-187">El parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones.</span><span class="sxs-lookup"><span data-stu-id="da4c1-187">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="da4c1-188">El parámetro <site ID> CentralSite es opcional.</span><span class="sxs-lookup"><span data-stu-id="da4c1-188">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="da4c1-189">En el ejemplo siguiente se crea una región de red denominada APAC:</span><span class="sxs-lookup"><span data-stu-id="da4c1-189">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="da4c1-190">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="da4c1-190">Define network sites</span></span>

<span data-ttu-id="da4c1-191">Para definir sitios de red, use el cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="da4c1-191">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="da4c1-192">Cada sitio de red debe estar asociado a una región de red.</span><span class="sxs-lookup"><span data-stu-id="da4c1-192">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="da4c1-193">En el siguiente ejemplo se crean tres sitios de red nuevos, Vietnam, Indonesia y Singapur en la región APAC:</span><span class="sxs-lookup"><span data-stu-id="da4c1-193">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="da4c1-194">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="da4c1-194">Define network subnets</span></span>

<span data-ttu-id="da4c1-195">Para definir subredes de red y asociarlas a sitios de red, use el cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="da4c1-195">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="da4c1-196">Cada subred de red solo se puede asociar con un sitio.</span><span class="sxs-lookup"><span data-stu-id="da4c1-196">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="da4c1-197">En el ejemplo siguiente se definen tres subredes de red y se asocian con los tres sitios de red: Vietnam, Indonesia y Singapur:</span><span class="sxs-lookup"><span data-stu-id="da4c1-197">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="da4c1-198">Definir la topología de red virtual</span><span class="sxs-lookup"><span data-stu-id="da4c1-198">Define the virtual network topology</span></span> 

<span data-ttu-id="da4c1-199">En primer lugar, el administrador de inquilinos crea una nueva configuración de SBC para cada SBC relevante mediante el cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="da4c1-199">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="da4c1-200">El administrador de inquilinos define la topología de red virtual mediante la especificación de los sitios de red de los objetos de la puerta de enlace RTC con el cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="da4c1-200">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="da4c1-201">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da4c1-201">Note the following:</span></span> 
   - <span data-ttu-id="da4c1-202">Si el cliente tiene un único SBC, el parámetro-ProxySBC debe ser obligatorio $null o valor FQDN de SBC (SBC central con escenario de troncos centralizados).</span><span class="sxs-lookup"><span data-stu-id="da4c1-202">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="da4c1-203">El parámetro-MediaBypass debe establecerse en $true para admitir la optimización de medios locales.</span><span class="sxs-lookup"><span data-stu-id="da4c1-203">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="da4c1-204">Si el SBC no tiene establecido el parámetro-BypassMode, no se enviarán los encabezados X-MS.</span><span class="sxs-lookup"><span data-stu-id="da4c1-204">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="da4c1-205">Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de usar el mismo caso que el usado durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="da4c1-205">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="da4c1-206">(Por ejemplo, los valores de GatewaySiteID "Vietnam" y "Vietnam" se tratarán como sitios diferentes).</span><span class="sxs-lookup"><span data-stu-id="da4c1-206">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="da4c1-207">En el ejemplo siguiente se agrega tres SBCs a los sitios de red Vietnam, Indonesia y Singapur en la región de APACtion con MODE omite siempre:</span><span class="sxs-lookup"><span data-stu-id="da4c1-207">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="da4c1-208">Nota: para asegurarse de que las operaciones no interrumpidas se configuran al mismo tiempo con la optimización local de medios y el enrutamiento basado en ubicación (LBR), es necesario habilitar SBCs para LBR al configurar el $true parámetro GatewaySiteLbrEnabled para cada SBC de indirecto.</span><span class="sxs-lookup"><span data-stu-id="da4c1-208">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="da4c1-209">(Esta configuración no es obligatoria para el SBC proxy).</span><span class="sxs-lookup"><span data-stu-id="da4c1-209">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="da4c1-210">En función de la información anterior, el enrutamiento directo incluirá tres encabezados SIP de propiedad para las invitaciones SIP y las reinvitaciones, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="da4c1-210">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="da4c1-211">Encabezados X-MS introducidos en enrutamiento directo en invitaciones y reinvitaciones si se define BypassMode:</span><span class="sxs-lookup"><span data-stu-id="da4c1-211">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="da4c1-212">Nombre del encabezado</span><span class="sxs-lookup"><span data-stu-id="da4c1-212">Header name</span></span> | <span data-ttu-id="da4c1-213">Los</span><span class="sxs-lookup"><span data-stu-id="da4c1-213">Values</span></span> | <span data-ttu-id="da4c1-214">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da4c1-214">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="da4c1-215">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="da4c1-215">X-MS-UserLocation</span></span> | <span data-ttu-id="da4c1-216">interno/externo</span><span class="sxs-lookup"><span data-stu-id="da4c1-216">internal/external</span></span> | <span data-ttu-id="da4c1-217">Indica si el usuario es interno o externo</span><span class="sxs-lookup"><span data-stu-id="da4c1-217">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="da4c1-218">Solicitud: URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="da4c1-218">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="da4c1-219">FQDN DE SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-219">SBC FQDN</span></span> | <span data-ttu-id="da4c1-220">El FQDN que se destina a la llamada incluso si la SBC no está conectada directamente al enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="da4c1-220">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="da4c1-221">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="da4c1-221">X-MS-MediaPath</span></span> | <span data-ttu-id="da4c1-222">Ejemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-222">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="da4c1-223">Orden de SBCs que debe usarse para la ruta de medios entre el usuario y el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="da4c1-223">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="da4c1-224">El SBC final es siempre el último</span><span class="sxs-lookup"><span data-stu-id="da4c1-224">The final SBC is always last</span></span> |
| <span data-ttu-id="da4c1-225">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="da4c1-225">X-MS-UserSite</span></span> | <span data-ttu-id="da4c1-226">usersiteID</span><span class="sxs-lookup"><span data-stu-id="da4c1-226">usersiteID</span></span> | <span data-ttu-id="da4c1-227">Cadena definida por el administrador de inquilinos</span><span class="sxs-lookup"><span data-stu-id="da4c1-227">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="da4c1-228">Flujos de llamadas</span><span class="sxs-lookup"><span data-stu-id="da4c1-228">Call flows</span></span> 

<span data-ttu-id="da4c1-229">A continuación se muestran los flujos de llamadas para dos modos:</span><span class="sxs-lookup"><span data-stu-id="da4c1-229">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="da4c1-230">Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-230">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="da4c1-231">Solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="da4c1-231">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="da4c1-232">Modo de omisión de siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-232">Always Bypass mode</span></span>

<span data-ttu-id="da4c1-233">El modo de omisión de siempre es la opción más sencilla para configurar.</span><span class="sxs-lookup"><span data-stu-id="da4c1-233">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="da4c1-234">El administrador de inquilinos puede configurar un solo sitio para todos los usuarios y SBCs si todo SBCs es alcanzable desde cualquier sitio.</span><span class="sxs-lookup"><span data-stu-id="da4c1-234">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="da4c1-235">Los ejemplos muestran siempre el modo de omisión en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="da4c1-235">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="da4c1-236">Llamadas salientes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-236">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="da4c1-237">Llamadas entrantes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-237">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="da4c1-238">Llamadas salientes y el usuario es externo</span><span class="sxs-lookup"><span data-stu-id="da4c1-238">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="da4c1-239">Llamadas entrantes y el usuario es externo</span><span class="sxs-lookup"><span data-stu-id="da4c1-239">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="da4c1-240">En la siguiente tabla se muestran los FQDN y las direcciones IP que se usan en los ejemplos:</span><span class="sxs-lookup"><span data-stu-id="da4c1-240">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="da4c1-241">FQDN</span><span class="sxs-lookup"><span data-stu-id="da4c1-241">FQDN</span></span> | <span data-ttu-id="da4c1-242">Dirección IP externa de SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-242">SBC external IP address</span></span> | <span data-ttu-id="da4c1-243">Dirección IP interna de SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-243">SBC internal IP Address</span></span> | <span data-ttu-id="da4c1-244">Subred interna</span><span class="sxs-lookup"><span data-stu-id="da4c1-244">Internal subnet</span></span> | <span data-ttu-id="da4c1-245">Ubicación</span><span class="sxs-lookup"><span data-stu-id="da4c1-245">Location</span></span> | <span data-ttu-id="da4c1-246">NAT externa (IP de confianza)</span><span class="sxs-lookup"><span data-stu-id="da4c1-246">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-247">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-247">VNsbc.contoso.com</span></span> | <span data-ttu-id="da4c1-248">Ninguna</span><span class="sxs-lookup"><span data-stu-id="da4c1-248">None</span></span> | <span data-ttu-id="da4c1-249">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="da4c1-249">192.168.1.5</span></span> | <span data-ttu-id="da4c1-250">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="da4c1-250">192.168.1.0/24</span></span> | <span data-ttu-id="da4c1-251">Vietnam</span><span class="sxs-lookup"><span data-stu-id="da4c1-251">Vietnam</span></span> | <span data-ttu-id="da4c1-252">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="da4c1-252">172.16.240.110</span></span> |
| <span data-ttu-id="da4c1-253">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-253">IDsbc.contoso.com</span></span> | <span data-ttu-id="da4c1-254">Ninguna</span><span class="sxs-lookup"><span data-stu-id="da4c1-254">None</span></span> | <span data-ttu-id="da4c1-255">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="da4c1-255">192.168.2.5</span></span> | <span data-ttu-id="da4c1-256">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="da4c1-256">192.168.2.0/24</span></span> | <span data-ttu-id="da4c1-257">Indonesia</span><span class="sxs-lookup"><span data-stu-id="da4c1-257">Indonesia</span></span> | <span data-ttu-id="da4c1-258">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="da4c1-258">172.16.240.120</span></span> |
| <span data-ttu-id="da4c1-259">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-259">proxysbc.contoso.com</span></span> | <span data-ttu-id="da4c1-260">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="da4c1-260">172.16.240.133</span></span> | <span data-ttu-id="da4c1-261">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="da4c1-261">192.168.3.5</span></span> | <span data-ttu-id="da4c1-262">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="da4c1-262">192.168.3.0/24</span></span> | <span data-ttu-id="da4c1-263">Singapur</span><span class="sxs-lookup"><span data-stu-id="da4c1-263">Singapore</span></span> | <span data-ttu-id="da4c1-264">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="da4c1-264">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="da4c1-265">Llamadas salientes y el usuario está en la misma ubicación que el SBC con el método de omitir siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-265">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="da4c1-266">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-266">Mode</span></span> |    <span data-ttu-id="da4c1-267">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-267">User</span></span> |  <span data-ttu-id="da4c1-268">Ubicación</span><span class="sxs-lookup"><span data-stu-id="da4c1-268">Location</span></span> |  <span data-ttu-id="da4c1-269">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-269">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="da4c1-270">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="da4c1-270">AlwaysBypass</span></span> |    <span data-ttu-id="da4c1-271">Interno</span><span class="sxs-lookup"><span data-stu-id="da4c1-271">Internal</span></span> |  <span data-ttu-id="da4c1-272">El mismo sitio que el SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-272">The same site as SBC</span></span> |  <span data-ttu-id="da4c1-273">Saliente</span><span class="sxs-lookup"><span data-stu-id="da4c1-273">Outbound</span></span> |

<span data-ttu-id="da4c1-274">En la tabla siguiente se muestra la acción y la configuración de usuario final:</span><span class="sxs-lookup"><span data-stu-id="da4c1-274">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="da4c1-275">Ubicación física de usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-275">User physical location</span></span>| <span data-ttu-id="da4c1-276">El usuario realiza o recibe una llamada a o desde el número</span><span class="sxs-lookup"><span data-stu-id="da4c1-276">User makes or receives a call to/from number</span></span> | <span data-ttu-id="da4c1-277">Número de teléfono del usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-277">User phone number</span></span>  | <span data-ttu-id="da4c1-278">Directiva de enrutamiento de voz en línea</span><span class="sxs-lookup"><span data-stu-id="da4c1-278">Online Voice Routing Policy</span></span> | <span data-ttu-id="da4c1-279">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-279">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-280">Vietnam</span><span class="sxs-lookup"><span data-stu-id="da4c1-280">Vietnam</span></span> | <span data-ttu-id="da4c1-281">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="da4c1-281">+84 4 3926 3000</span></span> | <span data-ttu-id="da4c1-282">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="da4c1-282">+84 4 5555 5555</span></span>   | <span data-ttu-id="da4c1-283">Prioridad 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-283">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="da4c1-284">Prioridad 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-284">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="da4c1-285">VNsbc.contoso.com: omite siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-285">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="da4c1-286">proxysbc.contoso.com: omite siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-286">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="da4c1-287">En el siguiente diagrama se muestra la escalera SIP para una llamada saliente con el modo Omitir siempre y el usuario en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-287">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="da4c1-288">![Diagrama que muestra las llamadas salientes](media/direct-routing-media-op-10.png "Llamadas salientes")</span><span class="sxs-lookup"><span data-stu-id="da4c1-288">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="da4c1-289">En la tabla siguiente se muestran los encabezados X-MS enviados por enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="da4c1-289">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="da4c1-290">Parámetro</span><span class="sxs-lookup"><span data-stu-id="da4c1-290">Parameter</span></span> | <span data-ttu-id="da4c1-291">Explicación</span><span class="sxs-lookup"><span data-stu-id="da4c1-291">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="da4c1-292">Invitar a + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-292">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="da4c1-293">El nombre de destino de la SBC según se define en la Directiva de enrutamiento de voz en línea se envía en el URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="da4c1-293">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="da4c1-294">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="da4c1-294">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="da4c1-295">El campo indicó que el usuario se encuentra dentro de la red corporativa</span><span class="sxs-lookup"><span data-stu-id="da4c1-295">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="da4c1-296">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-296">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="da4c1-297">Especifica qué SBC debe atravesar el cliente hasta el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="da4c1-297">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="da4c1-298">En este caso, puesto que siempre hemos omitido y el cliente es interno, el nombre de destino enviado como el único nombre en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="da4c1-298">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="da4c1-299">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="da4c1-299">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="da4c1-300">El campo indicado dentro del sitio donde se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="da4c1-300">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="da4c1-301">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC con el método de omitir siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-301">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="da4c1-302">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-302">Mode</span></span> |    <span data-ttu-id="da4c1-303">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-303">User</span></span> |  <span data-ttu-id="da4c1-304">Ubicación</span><span class="sxs-lookup"><span data-stu-id="da4c1-304">Location</span></span> |  <span data-ttu-id="da4c1-305">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-305">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-306">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="da4c1-306">AlwaysBypass</span></span> |    <span data-ttu-id="da4c1-307">Interno</span><span class="sxs-lookup"><span data-stu-id="da4c1-307">Internal</span></span> | <span data-ttu-id="da4c1-308">El mismo sitio que el SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-308">The same site as SBC</span></span> | <span data-ttu-id="da4c1-309">Entrada</span><span class="sxs-lookup"><span data-stu-id="da4c1-309">Inbound</span></span> |


<span data-ttu-id="da4c1-310">En una llamada entrante, se desconoce la ubicación del usuario y la SBC debe adivinar dónde se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="da4c1-310">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="da4c1-311">Si la conjetura no es correcta, será necesario volver a invitar.</span><span class="sxs-lookup"><span data-stu-id="da4c1-311">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="da4c1-312">Este caso supone que el usuario es interno, los medios pueden fluir directamente y no se necesita ninguna otra acción (volver a invitar).</span><span class="sxs-lookup"><span data-stu-id="da4c1-312">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="da4c1-313">La SBC conectada al servicio de enrutamiento directo informa de la ubicación de la SBC de origen proporcionando los campos de ruta de registro y de contacto.</span><span class="sxs-lookup"><span data-stu-id="da4c1-313">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="da4c1-314">En función de estos campos, el enrutamiento directo calcula la ruta de medios.</span><span class="sxs-lookup"><span data-stu-id="da4c1-314">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="da4c1-315">Nota: dado que un usuario puede tener varios puntos de conexión, no es posible la compatibilidad con 183.</span><span class="sxs-lookup"><span data-stu-id="da4c1-315">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="da4c1-316">El enrutamiento directo siempre usará timbres de 180 en este caso.</span><span class="sxs-lookup"><span data-stu-id="da4c1-316">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="da4c1-317">En el siguiente diagrama se muestra la escalera de SIP para la llamada entrante con el modo AlwaysBypass, y el usuario está en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-317">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="da4c1-319">Las llamadas salientes y el usuario son externos con el método de omitir siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-319">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="da4c1-320">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-320">Mode</span></span> |    <span data-ttu-id="da4c1-321">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-321">User</span></span> |  <span data-ttu-id="da4c1-322">Sitio</span><span class="sxs-lookup"><span data-stu-id="da4c1-322">Site</span></span> |  <span data-ttu-id="da4c1-323">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-323">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="da4c1-324">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="da4c1-324">AlwaysBypass</span></span> |  <span data-ttu-id="da4c1-325">Externo</span><span class="sxs-lookup"><span data-stu-id="da4c1-325">External</span></span> |  <span data-ttu-id="da4c1-326">N/D</span><span class="sxs-lookup"><span data-stu-id="da4c1-326">N/A</span></span> | <span data-ttu-id="da4c1-327">Saliente</span><span class="sxs-lookup"><span data-stu-id="da4c1-327">Outbound</span></span> |


<span data-ttu-id="da4c1-328">En el siguiente diagrama se muestra la escalera SIP para una llamada saliente con el modo AlwaysBypass, y el usuario es externo:</span><span class="sxs-lookup"><span data-stu-id="da4c1-328">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="da4c1-330">En la tabla siguiente se muestran los encabezados X-MS enviados por el servicio de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="da4c1-330">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="da4c1-331">Parámetro</span><span class="sxs-lookup"><span data-stu-id="da4c1-331">Parameter</span></span> |   <span data-ttu-id="da4c1-332">Explicación</span><span class="sxs-lookup"><span data-stu-id="da4c1-332">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="da4c1-333">Invitar a + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-333">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="da4c1-334">El nombre de destino de la SBC, según se define en la Directiva de enrutamiento de voz en línea, se envía en el URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="da4c1-334">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="da4c1-335">X-MS-UserLocation: External</span><span class="sxs-lookup"><span data-stu-id="da4c1-335">X-MS-UserLocation: external</span></span> | <span data-ttu-id="da4c1-336">El campo indicó que el usuario se encuentra fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="da4c1-336">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="da4c1-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="da4c1-338">Especifica qué SBC debe atravesar el cliente hasta el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="da4c1-338">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="da4c1-339">En este caso, ya que siempre hemos omitido y el cliente es externo.</span><span class="sxs-lookup"><span data-stu-id="da4c1-339">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="da4c1-340">Las llamadas entrantes y las del usuario son externas Si omiten siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-340">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="da4c1-341">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-341">Mode</span></span> | <span data-ttu-id="da4c1-342">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-342">User</span></span> | <span data-ttu-id="da4c1-343">Sitio</span><span class="sxs-lookup"><span data-stu-id="da4c1-343">Site</span></span> |  <span data-ttu-id="da4c1-344">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-344">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="da4c1-345">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="da4c1-345">AlwaysBypass</span></span> |  <span data-ttu-id="da4c1-346">Externo</span><span class="sxs-lookup"><span data-stu-id="da4c1-346">External</span></span> |  <span data-ttu-id="da4c1-347">N/D</span><span class="sxs-lookup"><span data-stu-id="da4c1-347">N/A</span></span> |   <span data-ttu-id="da4c1-348">Entrada</span><span class="sxs-lookup"><span data-stu-id="da4c1-348">Inbound</span></span> |

<span data-ttu-id="da4c1-349">En el caso de una llamada entrante, la SBC conectada al enrutamiento directo necesita enviar una nueva invitación (de forma predeterminada, se ofrecen siempre los candidatos de medio local) si la ubicación del usuario es externa.</span><span class="sxs-lookup"><span data-stu-id="da4c1-349">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="da4c1-350">La X-MediaPath se calcula en función de la ruta de registro y el usuario de SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="da4c1-350">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="da4c1-351">En el siguiente diagrama se muestra la escalera SIP para una llamada entrante con el modo AlwaysBypass, y el usuario es externo.</span><span class="sxs-lookup"><span data-stu-id="da4c1-351">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="da4c1-353">Solo para el modo de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="da4c1-353">Only for local users mode</span></span>

<span data-ttu-id="da4c1-354">Los candidatos de medio local del SBC objetivo se ofrecerán solo si un usuario se encuentra en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-354">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="da4c1-355">En todos los demás casos, los medios se transmiten a través de una IP interna o externa del SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="da4c1-355">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="da4c1-356">Se describen los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="da4c1-356">The following scenarios are described:</span></span>

- [<span data-ttu-id="da4c1-357">Llamadas salientes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-357">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="da4c1-358">Llamadas entrantes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-358">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="da4c1-359">El usuario no está en la misma ubicación que la SBC pero está en la red corporativa</span><span class="sxs-lookup"><span data-stu-id="da4c1-359">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="da4c1-360">Las llamadas entrantes y el usuario son internas, pero no están en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-360">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="da4c1-361">La siguiente tabla muestra la configuración y la acción del usuario final:</span><span class="sxs-lookup"><span data-stu-id="da4c1-361">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="da4c1-362">Ubicación física de usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-362">User physical location</span></span> |  <span data-ttu-id="da4c1-363">El usuario realiza o recibe una llamada a o desde el número</span><span class="sxs-lookup"><span data-stu-id="da4c1-363">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="da4c1-364">Número de teléfono del usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-364">User phone number</span></span> | <span data-ttu-id="da4c1-365">Directiva de enrutamiento de voz en línea</span><span class="sxs-lookup"><span data-stu-id="da4c1-365">Online Voice Routing Policy</span></span> |   <span data-ttu-id="da4c1-366">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-366">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-367">Vietnam</span><span class="sxs-lookup"><span data-stu-id="da4c1-367">Vietnam</span></span> | <span data-ttu-id="da4c1-368">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="da4c1-368">+84 4 3926  3000</span></span> |  <span data-ttu-id="da4c1-369">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="da4c1-369">+84 4 5555 5555</span></span> | <span data-ttu-id="da4c1-370">Prioridad 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-370">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="da4c1-371">Prioridad 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da4c1-371">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="da4c1-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – omitir siempre</span><span class="sxs-lookup"><span data-stu-id="da4c1-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="da4c1-373">Llamadas salientes y el usuario está en la misma ubicación que la SBC solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="da4c1-373">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="da4c1-374">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-374">Mode</span></span> | <span data-ttu-id="da4c1-375">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-375">User</span></span> | <span data-ttu-id="da4c1-376">Sitio</span><span class="sxs-lookup"><span data-stu-id="da4c1-376">Site</span></span> | <span data-ttu-id="da4c1-377">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-377">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-378">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="da4c1-378">OnlyForLocalUsers</span></span> |   <span data-ttu-id="da4c1-379">Interno</span><span class="sxs-lookup"><span data-stu-id="da4c1-379">Internal</span></span> |<span data-ttu-id="da4c1-380">Igual que SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-380">Same as SBC</span></span>   | <span data-ttu-id="da4c1-381">Saliente</span><span class="sxs-lookup"><span data-stu-id="da4c1-381">Outbound</span></span> |

<span data-ttu-id="da4c1-382">En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-382">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="da4c1-383">Este es el mismo flujo que se muestra en las [llamadas salientes cuando el usuario está en la misma ubicación que la SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="da4c1-383">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="da4c1-385">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que la SBC solo para los usuarios locales</span><span class="sxs-lookup"><span data-stu-id="da4c1-385">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="da4c1-386">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-386">Mode</span></span> | <span data-ttu-id="da4c1-387">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-387">User</span></span> | <span data-ttu-id="da4c1-388">Sitio</span><span class="sxs-lookup"><span data-stu-id="da4c1-388">Site</span></span> | <span data-ttu-id="da4c1-389">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-389">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-390">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="da4c1-390">OnlyForLocalUsers</span></span> |   <span data-ttu-id="da4c1-391">Interno</span><span class="sxs-lookup"><span data-stu-id="da4c1-391">Internal</span></span> | <span data-ttu-id="da4c1-392">Igual que SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-392">Same as SBC</span></span> | <span data-ttu-id="da4c1-393">Entrada</span><span class="sxs-lookup"><span data-stu-id="da4c1-393">Inbound</span></span> |

<span data-ttu-id="da4c1-394">En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-394">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="da4c1-395">Este es el mismo flujo que se muestra en las [llamadas entrantes cuando el usuario está en la misma ubicación que la SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="da4c1-395">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="da4c1-397">El usuario no está en la misma ubicación que la SBC pero está en la red corporativa solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="da4c1-397">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="da4c1-398">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-398">Mode</span></span> | <span data-ttu-id="da4c1-399">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-399">User</span></span> | <span data-ttu-id="da4c1-400">Sitio</span><span class="sxs-lookup"><span data-stu-id="da4c1-400">Site</span></span> |<span data-ttu-id="da4c1-401">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-401">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-402">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="da4c1-402">OnlyForLocalUsers</span></span>  | <span data-ttu-id="da4c1-403">Interno</span><span class="sxs-lookup"><span data-stu-id="da4c1-403">Internal</span></span> |   <span data-ttu-id="da4c1-404">Diferente de SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-404">Different from SBC</span></span> | <span data-ttu-id="da4c1-405">Saliente</span><span class="sxs-lookup"><span data-stu-id="da4c1-405">Outbound</span></span> |

<span data-ttu-id="da4c1-406">El enrutamiento directo calcula la X-MediaPath en función de la ubicación de la que se informó del usuario y el modo configurado en la SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-406">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="da4c1-407">En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-407">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="da4c1-409">La llamada entrante y el usuario son internas, pero no están en la misma ubicación que el SBC solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="da4c1-409">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="da4c1-410">Modo</span><span class="sxs-lookup"><span data-stu-id="da4c1-410">Mode</span></span> |    <span data-ttu-id="da4c1-411">Usuario</span><span class="sxs-lookup"><span data-stu-id="da4c1-411">User</span></span> |  <span data-ttu-id="da4c1-412">Sitio</span><span class="sxs-lookup"><span data-stu-id="da4c1-412">Site</span></span> |  <span data-ttu-id="da4c1-413">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="da4c1-413">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="da4c1-414">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="da4c1-414">OnlyForLocalUsers</span></span> | <span data-ttu-id="da4c1-415">Interno</span><span class="sxs-lookup"><span data-stu-id="da4c1-415">Internal</span></span> |    <span data-ttu-id="da4c1-416">Diferente de SBC</span><span class="sxs-lookup"><span data-stu-id="da4c1-416">Different from SBC</span></span> |    <span data-ttu-id="da4c1-417">Entrada</span><span class="sxs-lookup"><span data-stu-id="da4c1-417">Inbound</span></span> |

<span data-ttu-id="da4c1-418">En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="da4c1-418">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-17.png)










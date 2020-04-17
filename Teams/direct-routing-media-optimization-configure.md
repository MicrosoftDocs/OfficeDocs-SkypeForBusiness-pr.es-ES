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
ms.openlocfilehash: 8a69a46d7620628c7afffb706354c0f6e7868f3d
ms.sourcegitcommit: 3dd6499416e9fbdcb48187c6322bd607290502ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541597"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="95697-103">Configurar la optimización de medios locales para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="95697-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="95697-104">La configuración para la optimización de medios locales se basa en la configuración de red que es común a otras características de voz en la nube, como el enrutamiento basado en la ubicación y las llamadas de emergencia dinámicas.</span><span class="sxs-lookup"><span data-stu-id="95697-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="95697-105">Para obtener más información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza, consulte [configuración de red para características de voz en la nube](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="95697-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="95697-106">Antes de configurar la optimización de medios locales, consulte la [optimización local de medios para el enrutamiento directo](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="95697-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="95697-107">Para configurar la optimización local de medios, se requieren los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="95697-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="95697-108">Puede usar el centro de administración de Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95697-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="95697-109">Para obtener más información, consulte [administrar la topología de red](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="95697-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="95697-110">Configure el usuario y los sitios de SBC (como se describe en este artículo).</span><span class="sxs-lookup"><span data-stu-id="95697-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="95697-111">Configure el SBCs para la optimización de medios locales (según la especificación de proveedor de SBC).</span><span class="sxs-lookup"><span data-stu-id="95697-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="95697-112">En el siguiente diagrama se muestra la configuración de red usada en los ejemplos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="95697-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="95697-113">![Diagrama que muestra la configuración de red para ejemplos](media/direct-routing-media-op-9.png "Configuración de red para ejemplos")</span><span class="sxs-lookup"><span data-stu-id="95697-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="95697-114">Configurar el usuario y los sitios de SBC</span><span class="sxs-lookup"><span data-stu-id="95697-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="95697-115">Para configurar los sitios de usuario y SBC, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="95697-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="95697-116">[Administrar direcciones IP externas de confianza](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="95697-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="95697-117">[Defina la topología de red](#define-the-network-topology) configurando las regiones de red, los sitios de red y las subredes de red.</span><span class="sxs-lookup"><span data-stu-id="95697-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="95697-118">[Defina la topología de red virtual](#define-the-virtual-network-topology) asignando SBC (s) a los sitios con los modos y valores de SBC de proxy.</span><span class="sxs-lookup"><span data-stu-id="95697-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="95697-119">Configurar SBC (s) para la optimización de medios locales según la especificación de proveedor de SBC</span><span class="sxs-lookup"><span data-stu-id="95697-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="95697-120">En este artículo se describe la configuración de los componentes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95697-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="95697-121">Para obtener información sobre la configuración de SBC, consulte la documenation de proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="95697-122">La optimización local de medios es compatible con los siguientes proveedores de SBC:</span><span class="sxs-lookup"><span data-stu-id="95697-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="95697-123">Proveedor</span><span class="sxs-lookup"><span data-stu-id="95697-123">Vendor</span></span> | <span data-ttu-id="95697-124">Producto</span><span class="sxs-lookup"><span data-stu-id="95697-124">Product</span></span> |    <span data-ttu-id="95697-125">Versión del software</span><span class="sxs-lookup"><span data-stu-id="95697-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="95697-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="95697-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="95697-127">SBC Mediant 500</span><span class="sxs-lookup"><span data-stu-id="95697-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="95697-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="95697-129">SBC Mediant 800</span><span class="sxs-lookup"><span data-stu-id="95697-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="95697-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="95697-131">SBC Mediant 2600</span><span class="sxs-lookup"><span data-stu-id="95697-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="95697-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="95697-133">SBC Mediant 4000</span><span class="sxs-lookup"><span data-stu-id="95697-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="95697-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="95697-135">SBC 1000B</span><span class="sxs-lookup"><span data-stu-id="95697-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="95697-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="95697-137">SBC 9000</span><span class="sxs-lookup"><span data-stu-id="95697-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="95697-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="95697-139">SBC Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="95697-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="95697-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="95697-141">La nube Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="95697-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="95697-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="95697-142">7.20A.256</span></span> |
| [<span data-ttu-id="95697-143">Núcleo de SBC de cinta</span><span class="sxs-lookup"><span data-stu-id="95697-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="95697-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="95697-144">SBC 5110</span></span>         | <span data-ttu-id="95697-145">8,2</span><span class="sxs-lookup"><span data-stu-id="95697-145">8.2</span></span>  |
|            |  <span data-ttu-id="95697-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="95697-146">SBC 5210</span></span>         | <span data-ttu-id="95697-147">8,2</span><span class="sxs-lookup"><span data-stu-id="95697-147">8.2</span></span>  |
|            |  <span data-ttu-id="95697-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="95697-148">SBC 5400</span></span>         | <span data-ttu-id="95697-149">8,2</span><span class="sxs-lookup"><span data-stu-id="95697-149">8.2</span></span>  |
|            |  <span data-ttu-id="95697-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="95697-150">SBC 7000</span></span>         | <span data-ttu-id="95697-151">8,2</span><span class="sxs-lookup"><span data-stu-id="95697-151">8.2</span></span>  |
|            |  <span data-ttu-id="95697-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="95697-152">SBC SWe</span></span>          | <span data-ttu-id="95697-153">8,2</span><span class="sxs-lookup"><span data-stu-id="95697-153">8.2</span></span>  |
| [<span data-ttu-id="95697-154">Borde de SBC de cinta</span><span class="sxs-lookup"><span data-stu-id="95697-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="95697-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="95697-155">SBC 1000</span></span>         | <span data-ttu-id="95697-156">8.1.1, compilación 527</span><span class="sxs-lookup"><span data-stu-id="95697-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="95697-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="95697-157">SBC 2000</span></span>         | <span data-ttu-id="95697-158">8.1.1, compilación 527</span><span class="sxs-lookup"><span data-stu-id="95697-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="95697-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="95697-159">SBC SWe Lite</span></span>     | <span data-ttu-id="95697-160">8.1.0, compilación 222</span><span class="sxs-lookup"><span data-stu-id="95697-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="95697-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="95697-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="95697-162">anynode</span><span class="sxs-lookup"><span data-stu-id="95697-162">anynode</span></span>          | <span data-ttu-id="95697-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="95697-163">4.0.1+</span></span> |
| [<span data-ttu-id="95697-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="95697-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="95697-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="95697-165">AP 1100</span></span> | <span data-ttu-id="95697-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="95697-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="95697-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="95697-167">AP 3900</span></span> | <span data-ttu-id="95697-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="95697-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="95697-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="95697-169">AP 4600</span></span> | <span data-ttu-id="95697-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="95697-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="95697-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="95697-171">AP 6300</span></span> | <span data-ttu-id="95697-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="95697-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="95697-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="95697-173">AP 6350</span></span> | <span data-ttu-id="95697-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="95697-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="95697-175">VME</span><span class="sxs-lookup"><span data-stu-id="95697-175">VME</span></span>     | <span data-ttu-id="95697-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="95697-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="95697-177">Administrar direcciones IP de confianza externas</span><span class="sxs-lookup"><span data-stu-id="95697-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="95697-178">Las direcciones IP externas de confianza son direcciones IP externas de Internet de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="95697-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="95697-179">Estas son las direcciones IP que usan los clientes de Microsoft Teams cuando se conectan a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95697-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="95697-180">Debe agregar estas direcciones IP externas para cada sitio en el que tenga usuarios que usen la optimización local de medios.</span><span class="sxs-lookup"><span data-stu-id="95697-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="95697-181">Para agregar las direcciones IP públicas de cada sitio, use el cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="95697-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="95697-182">Puede definir un número ilimitado de direcciones IP de confianza para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="95697-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="95697-183">Si el IPs externo visto por Microsoft 365 son direcciones IPv4 e IPv6, tendrá que agregar ambos tipos de direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="95697-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="95697-184">Para IPv4, use la máscara 32.</span><span class="sxs-lookup"><span data-stu-id="95697-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="95697-185">Para IPv6, use la máscara 128.</span><span class="sxs-lookup"><span data-stu-id="95697-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="95697-186">Puede agregar direcciones IP externas individuales y subredes IP externas especificando diferentes MaskBits en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="95697-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="95697-187">Ejemplo de adición de direcciones IP fiables.</span><span class="sxs-lookup"><span data-stu-id="95697-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="95697-188">Definir la topología de red</span><span class="sxs-lookup"><span data-stu-id="95697-188">Define the network topology</span></span>

<span data-ttu-id="95697-189">En esta sección se describe cómo definir las regiones de red, los sitios de red y las subredes de red para su topología de red.</span><span class="sxs-lookup"><span data-stu-id="95697-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="95697-190">Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de usar el mismo caso que se usó durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="95697-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="95697-191">(Por ejemplo, los valores de GatewaySiteID "Vietnam" y "Vietnam" se tratarán como sitios diferentes).</span><span class="sxs-lookup"><span data-stu-id="95697-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="95697-192">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="95697-192">Define network regions</span></span>

<span data-ttu-id="95697-193">Para definir regiones de red, use el cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="95697-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="95697-194">El parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones.</span><span class="sxs-lookup"><span data-stu-id="95697-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="95697-195">El parámetro <site ID> CentralSite es opcional.</span><span class="sxs-lookup"><span data-stu-id="95697-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="95697-196">En el ejemplo siguiente se crea una región de red denominada APAC:</span><span class="sxs-lookup"><span data-stu-id="95697-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="95697-197">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="95697-197">Define network sites</span></span>

<span data-ttu-id="95697-198">Para definir sitios de red, use el cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="95697-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="95697-199">Cada sitio de red debe estar asociado a una región de red.</span><span class="sxs-lookup"><span data-stu-id="95697-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="95697-200">En el siguiente ejemplo se crean tres sitios de red nuevos, Vietnam, Indonesia y Singapur en la región APAC:</span><span class="sxs-lookup"><span data-stu-id="95697-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="95697-201">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="95697-201">Define network subnets</span></span>

<span data-ttu-id="95697-202">Para definir subredes de red y asociarlas a sitios de red, use el cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="95697-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="95697-203">Cada subred de red solo se puede asociar con un sitio.</span><span class="sxs-lookup"><span data-stu-id="95697-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="95697-204">En el ejemplo siguiente se definen tres subredes de red y se asocian con los tres sitios de red: Vietnam, Indonesia y Singapur:</span><span class="sxs-lookup"><span data-stu-id="95697-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="95697-205">Definir la topología de red virtual</span><span class="sxs-lookup"><span data-stu-id="95697-205">Define the virtual network topology</span></span> 

<span data-ttu-id="95697-206">En primer lugar, el administrador de inquilinos crea una nueva configuración de SBC para cada SBC relevante mediante el cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="95697-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="95697-207">El administrador de inquilinos define la topología de red virtual mediante la especificación de los sitios de red de los objetos de la puerta de enlace RTC con el cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="95697-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="95697-208">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95697-208">Note the following:</span></span> 
   - <span data-ttu-id="95697-209">Si el cliente tiene un único SBC, el parámetro-ProxySBC debe ser obligatorio $null o valor FQDN de SBC (SBC central con escenario de troncos centralizados).</span><span class="sxs-lookup"><span data-stu-id="95697-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="95697-210">El parámetro-MediaBypass debe establecerse en $true para admitir la optimización de medios locales.</span><span class="sxs-lookup"><span data-stu-id="95697-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="95697-211">Si el SBC no tiene establecido el parámetro-BypassMode, no se enviarán los encabezados X-MS.</span><span class="sxs-lookup"><span data-stu-id="95697-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="95697-212">Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de usar el mismo caso que el usado durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="95697-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="95697-213">(Por ejemplo, los valores de GatewaySiteID "Vietnam" y "Vietnam" se tratarán como sitios diferentes).</span><span class="sxs-lookup"><span data-stu-id="95697-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="95697-214">En el ejemplo siguiente se agrega tres SBCs a los sitios de red Vietnam, Indonesia y Singapur en la región de APACtion con MODE omite siempre:</span><span class="sxs-lookup"><span data-stu-id="95697-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="95697-215">Nota: para asegurarse de que las operaciones no interrumpidas se configuran al mismo tiempo con la optimización local de medios y el enrutamiento basado en ubicación (LBR), es necesario habilitar SBCs para LBR al configurar el $true parámetro GatewaySiteLbrEnabled para cada SBC de indirecto.</span><span class="sxs-lookup"><span data-stu-id="95697-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="95697-216">(Esta configuración no es obligatoria para el SBC proxy).</span><span class="sxs-lookup"><span data-stu-id="95697-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="95697-217">En función de la información anterior, el enrutamiento directo incluirá tres encabezados SIP de propiedad para las invitaciones SIP y las reinvitaciones, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="95697-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="95697-218">Encabezados X-MS introducidos en enrutamiento directo en invitaciones y reinvitaciones si se define BypassMode:</span><span class="sxs-lookup"><span data-stu-id="95697-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="95697-219">Nombre del encabezado</span><span class="sxs-lookup"><span data-stu-id="95697-219">Header name</span></span> | <span data-ttu-id="95697-220">Los</span><span class="sxs-lookup"><span data-stu-id="95697-220">Values</span></span> | <span data-ttu-id="95697-221">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95697-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="95697-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="95697-222">X-MS-UserLocation</span></span> | <span data-ttu-id="95697-223">interno/externo</span><span class="sxs-lookup"><span data-stu-id="95697-223">internal/external</span></span> | <span data-ttu-id="95697-224">Indica si el usuario es interno o externo</span><span class="sxs-lookup"><span data-stu-id="95697-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="95697-225">Solicitud: URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="95697-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="95697-226">FQDN DE SBC</span><span class="sxs-lookup"><span data-stu-id="95697-226">SBC FQDN</span></span> | <span data-ttu-id="95697-227">El FQDN que se destina a la llamada incluso si la SBC no está conectada directamente al enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="95697-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="95697-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="95697-228">X-MS-MediaPath</span></span> | <span data-ttu-id="95697-229">Ejemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="95697-230">Orden de SBCs que debe usarse para la ruta de medios entre el usuario y el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="95697-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="95697-231">El SBC final es siempre el último</span><span class="sxs-lookup"><span data-stu-id="95697-231">The final SBC is always last</span></span> |
| <span data-ttu-id="95697-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="95697-232">X-MS-UserSite</span></span> | <span data-ttu-id="95697-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="95697-233">usersiteID</span></span> | <span data-ttu-id="95697-234">Cadena definida por el administrador de inquilinos</span><span class="sxs-lookup"><span data-stu-id="95697-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="95697-235">Flujos de llamadas</span><span class="sxs-lookup"><span data-stu-id="95697-235">Call flows</span></span> 

<span data-ttu-id="95697-236">A continuación se muestran los flujos de llamadas para dos modos:</span><span class="sxs-lookup"><span data-stu-id="95697-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="95697-237">Omitir siempre</span><span class="sxs-lookup"><span data-stu-id="95697-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="95697-238">Solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="95697-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="95697-239">Modo de omisión de siempre</span><span class="sxs-lookup"><span data-stu-id="95697-239">Always Bypass mode</span></span>

<span data-ttu-id="95697-240">El modo de omisión de siempre es la opción más sencilla para configurar.</span><span class="sxs-lookup"><span data-stu-id="95697-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="95697-241">El administrador de inquilinos puede configurar un solo sitio para todos los usuarios y SBCs si todo SBCs es alcanzable desde cualquier sitio.</span><span class="sxs-lookup"><span data-stu-id="95697-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="95697-242">Los ejemplos muestran siempre el modo de omisión en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="95697-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="95697-243">Llamadas salientes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="95697-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="95697-244">Llamadas entrantes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="95697-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="95697-245">Llamadas salientes y el usuario es externo</span><span class="sxs-lookup"><span data-stu-id="95697-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="95697-246">Llamadas entrantes y el usuario es externo</span><span class="sxs-lookup"><span data-stu-id="95697-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="95697-247">En la siguiente tabla se muestran los FQDN y las direcciones IP que se usan en los ejemplos:</span><span class="sxs-lookup"><span data-stu-id="95697-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="95697-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="95697-248">FQDN</span></span> | <span data-ttu-id="95697-249">Dirección IP externa de SBC</span><span class="sxs-lookup"><span data-stu-id="95697-249">SBC external IP address</span></span> | <span data-ttu-id="95697-250">Dirección IP interna de SBC</span><span class="sxs-lookup"><span data-stu-id="95697-250">SBC internal IP Address</span></span> | <span data-ttu-id="95697-251">Subred interna</span><span class="sxs-lookup"><span data-stu-id="95697-251">Internal subnet</span></span> | <span data-ttu-id="95697-252">Ubicación</span><span class="sxs-lookup"><span data-stu-id="95697-252">Location</span></span> | <span data-ttu-id="95697-253">NAT externa (IP de confianza)</span><span class="sxs-lookup"><span data-stu-id="95697-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="95697-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="95697-255">Ninguna</span><span class="sxs-lookup"><span data-stu-id="95697-255">None</span></span> | <span data-ttu-id="95697-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="95697-256">192.168.1.5</span></span> | <span data-ttu-id="95697-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="95697-257">192.168.1.0/24</span></span> | <span data-ttu-id="95697-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="95697-258">Vietnam</span></span> | <span data-ttu-id="95697-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="95697-259">172.16.240.110</span></span> |
| <span data-ttu-id="95697-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="95697-261">Ninguna</span><span class="sxs-lookup"><span data-stu-id="95697-261">None</span></span> | <span data-ttu-id="95697-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="95697-262">192.168.2.5</span></span> | <span data-ttu-id="95697-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="95697-263">192.168.2.0/24</span></span> | <span data-ttu-id="95697-264">Indonesia</span><span class="sxs-lookup"><span data-stu-id="95697-264">Indonesia</span></span> | <span data-ttu-id="95697-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="95697-265">172.16.240.120</span></span> |
| <span data-ttu-id="95697-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="95697-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="95697-267">172.16.240.133</span></span> | <span data-ttu-id="95697-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="95697-268">192.168.3.5</span></span> | <span data-ttu-id="95697-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="95697-269">192.168.3.0/24</span></span> | <span data-ttu-id="95697-270">Singapur</span><span class="sxs-lookup"><span data-stu-id="95697-270">Singapore</span></span> | <span data-ttu-id="95697-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="95697-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="95697-272">Llamadas salientes y el usuario está en la misma ubicación que el SBC con el método de omitir siempre</span><span class="sxs-lookup"><span data-stu-id="95697-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="95697-273">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-273">Mode</span></span> |    <span data-ttu-id="95697-274">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-274">User</span></span> |  <span data-ttu-id="95697-275">Ubicación</span><span class="sxs-lookup"><span data-stu-id="95697-275">Location</span></span> |  <span data-ttu-id="95697-276">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="95697-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="95697-277">AlwaysBypass</span></span> |    <span data-ttu-id="95697-278">Interno</span><span class="sxs-lookup"><span data-stu-id="95697-278">Internal</span></span> |  <span data-ttu-id="95697-279">El mismo sitio que el SBC</span><span class="sxs-lookup"><span data-stu-id="95697-279">The same site as SBC</span></span> |  <span data-ttu-id="95697-280">Saliente</span><span class="sxs-lookup"><span data-stu-id="95697-280">Outbound</span></span> |

<span data-ttu-id="95697-281">En la tabla siguiente se muestra la acción y la configuración de usuario final:</span><span class="sxs-lookup"><span data-stu-id="95697-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="95697-282">Ubicación física de usuario</span><span class="sxs-lookup"><span data-stu-id="95697-282">User physical location</span></span>| <span data-ttu-id="95697-283">El usuario realiza o recibe una llamada a o desde el número</span><span class="sxs-lookup"><span data-stu-id="95697-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="95697-284">Número de teléfono del usuario</span><span class="sxs-lookup"><span data-stu-id="95697-284">User phone number</span></span>  | <span data-ttu-id="95697-285">Directiva de enrutamiento de voz en línea</span><span class="sxs-lookup"><span data-stu-id="95697-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="95697-286">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="95697-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="95697-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="95697-287">Vietnam</span></span> | <span data-ttu-id="95697-288">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="95697-288">+84 4 3926 3000</span></span> | <span data-ttu-id="95697-289">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="95697-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="95697-290">Prioridad 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="95697-291">Prioridad 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="95697-292">VNsbc.contoso.com: omite siempre</span><span class="sxs-lookup"><span data-stu-id="95697-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="95697-293">proxysbc.contoso.com: omite siempre</span><span class="sxs-lookup"><span data-stu-id="95697-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="95697-294">En el siguiente diagrama se muestra la escalera SIP para una llamada saliente con el modo Omitir siempre y el usuario en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="95697-295">![Diagrama que muestra las llamadas salientes](media/direct-routing-media-op-10.png "Llamadas salientes")</span><span class="sxs-lookup"><span data-stu-id="95697-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="95697-296">En la tabla siguiente se muestran los encabezados X-MS enviados por enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="95697-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="95697-297">Parámetro</span><span class="sxs-lookup"><span data-stu-id="95697-297">Parameter</span></span> | <span data-ttu-id="95697-298">Explicación</span><span class="sxs-lookup"><span data-stu-id="95697-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="95697-299">Invitar a + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="95697-300">El nombre de destino de la SBC según se define en la Directiva de enrutamiento de voz en línea se envía en el URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="95697-300">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="95697-301">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="95697-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="95697-302">El campo indicó que el usuario se encuentra dentro de la red corporativa</span><span class="sxs-lookup"><span data-stu-id="95697-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="95697-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="95697-304">Especifica qué SBC debe atravesar el cliente hasta el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="95697-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="95697-305">En este caso, puesto que siempre hemos omitido y el cliente es interno, el nombre de destino enviado como el único nombre en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="95697-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="95697-306">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="95697-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="95697-307">El campo indicado dentro del sitio donde se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="95697-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="95697-308">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC con el método de omitir siempre</span><span class="sxs-lookup"><span data-stu-id="95697-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="95697-309">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-309">Mode</span></span> |    <span data-ttu-id="95697-310">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-310">User</span></span> |  <span data-ttu-id="95697-311">Ubicación</span><span class="sxs-lookup"><span data-stu-id="95697-311">Location</span></span> |  <span data-ttu-id="95697-312">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="95697-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="95697-313">AlwaysBypass</span></span> |    <span data-ttu-id="95697-314">Interno</span><span class="sxs-lookup"><span data-stu-id="95697-314">Internal</span></span> | <span data-ttu-id="95697-315">El mismo sitio que el SBC</span><span class="sxs-lookup"><span data-stu-id="95697-315">The same site as SBC</span></span> | <span data-ttu-id="95697-316">Entrada</span><span class="sxs-lookup"><span data-stu-id="95697-316">Inbound</span></span> |


<span data-ttu-id="95697-317">En una llamada entrante, se desconoce la ubicación del usuario y la SBC debe adivinar dónde se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="95697-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="95697-318">Si la conjetura no es correcta, será necesario volver a invitar.</span><span class="sxs-lookup"><span data-stu-id="95697-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="95697-319">Este caso supone que el usuario es interno, los medios pueden fluir directamente y no se necesita ninguna otra acción (volver a invitar).</span><span class="sxs-lookup"><span data-stu-id="95697-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="95697-320">La SBC conectada al servicio de enrutamiento directo informa de la ubicación de la SBC de origen proporcionando los campos de ruta de registro y de contacto.</span><span class="sxs-lookup"><span data-stu-id="95697-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="95697-321">En función de estos campos, el enrutamiento directo calcula la ruta de medios.</span><span class="sxs-lookup"><span data-stu-id="95697-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="95697-322">Nota: dado que un usuario puede tener varios puntos de conexión, no es posible la compatibilidad con 183.</span><span class="sxs-lookup"><span data-stu-id="95697-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="95697-323">El enrutamiento directo siempre usará timbres de 180 en este caso.</span><span class="sxs-lookup"><span data-stu-id="95697-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="95697-324">En el siguiente diagrama se muestra la escalera de SIP para la llamada entrante con el modo AlwaysBypass, y el usuario está en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="95697-326">Las llamadas salientes y el usuario son externos con el método de omitir siempre</span><span class="sxs-lookup"><span data-stu-id="95697-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="95697-327">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-327">Mode</span></span> |    <span data-ttu-id="95697-328">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-328">User</span></span> |  <span data-ttu-id="95697-329">Sitio</span><span class="sxs-lookup"><span data-stu-id="95697-329">Site</span></span> |  <span data-ttu-id="95697-330">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="95697-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="95697-331">AlwaysBypass</span></span> |  <span data-ttu-id="95697-332">Externo</span><span class="sxs-lookup"><span data-stu-id="95697-332">External</span></span> |  <span data-ttu-id="95697-333">N/D</span><span class="sxs-lookup"><span data-stu-id="95697-333">N/A</span></span> | <span data-ttu-id="95697-334">Saliente</span><span class="sxs-lookup"><span data-stu-id="95697-334">Outbound</span></span> |


<span data-ttu-id="95697-335">En el siguiente diagrama se muestra la escalera SIP para una llamada saliente con el modo AlwaysBypass, y el usuario es externo:</span><span class="sxs-lookup"><span data-stu-id="95697-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="95697-337">En la tabla siguiente se muestran los encabezados X-MS enviados por el servicio de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="95697-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="95697-338">Parámetro</span><span class="sxs-lookup"><span data-stu-id="95697-338">Parameter</span></span> |   <span data-ttu-id="95697-339">Explicación</span><span class="sxs-lookup"><span data-stu-id="95697-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="95697-340">Invitar a + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="95697-341">El nombre de destino de la SBC, según se define en la Directiva de enrutamiento de voz en línea, se envía en el URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="95697-341">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="95697-342">X-MS-UserLocation: External</span><span class="sxs-lookup"><span data-stu-id="95697-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="95697-343">El campo indicó que el usuario se encuentra fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="95697-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="95697-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="95697-345">Especifica qué SBC debe atravesar el cliente hasta el SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="95697-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="95697-346">En este caso, ya que siempre hemos omitido y el cliente es externo.</span><span class="sxs-lookup"><span data-stu-id="95697-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="95697-347">Las llamadas entrantes y las del usuario son externas Si omiten siempre</span><span class="sxs-lookup"><span data-stu-id="95697-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="95697-348">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-348">Mode</span></span> | <span data-ttu-id="95697-349">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-349">User</span></span> | <span data-ttu-id="95697-350">Sitio</span><span class="sxs-lookup"><span data-stu-id="95697-350">Site</span></span> |  <span data-ttu-id="95697-351">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="95697-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="95697-352">AlwaysBypass</span></span> |  <span data-ttu-id="95697-353">Externo</span><span class="sxs-lookup"><span data-stu-id="95697-353">External</span></span> |  <span data-ttu-id="95697-354">N/D</span><span class="sxs-lookup"><span data-stu-id="95697-354">N/A</span></span> |   <span data-ttu-id="95697-355">Entrada</span><span class="sxs-lookup"><span data-stu-id="95697-355">Inbound</span></span> |

<span data-ttu-id="95697-356">En el caso de una llamada entrante, la SBC conectada al enrutamiento directo necesita enviar una nueva invitación (de forma predeterminada, se ofrecen siempre los candidatos de medio local) si la ubicación del usuario es externa.</span><span class="sxs-lookup"><span data-stu-id="95697-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="95697-357">La X-MediaPath se calcula en función de la ruta de registro y el usuario de SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="95697-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="95697-358">En el siguiente diagrama se muestra la escalera SIP para una llamada entrante con el modo AlwaysBypass, y el usuario es externo.</span><span class="sxs-lookup"><span data-stu-id="95697-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="95697-360">Solo para el modo de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="95697-360">Only for local users mode</span></span>

<span data-ttu-id="95697-361">Los candidatos de medio local del SBC objetivo se ofrecerán solo si un usuario se encuentra en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="95697-362">En todos los demás casos, los medios se transmiten a través de una IP interna o externa del SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="95697-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="95697-363">Se describen los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="95697-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="95697-364">Llamadas salientes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="95697-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="95697-365">Llamadas entrantes y el usuario está en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="95697-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="95697-366">El usuario no está en la misma ubicación que la SBC pero está en la red corporativa</span><span class="sxs-lookup"><span data-stu-id="95697-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="95697-367">Las llamadas entrantes y el usuario son internas, pero no están en la misma ubicación que el SBC</span><span class="sxs-lookup"><span data-stu-id="95697-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="95697-368">La siguiente tabla muestra la configuración y la acción del usuario final:</span><span class="sxs-lookup"><span data-stu-id="95697-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="95697-369">Ubicación física de usuario</span><span class="sxs-lookup"><span data-stu-id="95697-369">User physical location</span></span> |  <span data-ttu-id="95697-370">El usuario realiza o recibe una llamada a o desde el número</span><span class="sxs-lookup"><span data-stu-id="95697-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="95697-371">Número de teléfono del usuario</span><span class="sxs-lookup"><span data-stu-id="95697-371">User phone number</span></span> | <span data-ttu-id="95697-372">Directiva de enrutamiento de voz en línea</span><span class="sxs-lookup"><span data-stu-id="95697-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="95697-373">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="95697-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="95697-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="95697-374">Vietnam</span></span> | <span data-ttu-id="95697-375">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="95697-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="95697-376">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="95697-376">+84 4 5555 5555</span></span> | <span data-ttu-id="95697-377">Prioridad 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="95697-378">Prioridad 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95697-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="95697-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – omitir siempre</span><span class="sxs-lookup"><span data-stu-id="95697-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="95697-380">Llamadas salientes y el usuario está en la misma ubicación que la SBC solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="95697-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="95697-381">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-381">Mode</span></span> | <span data-ttu-id="95697-382">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-382">User</span></span> | <span data-ttu-id="95697-383">Sitio</span><span class="sxs-lookup"><span data-stu-id="95697-383">Site</span></span> | <span data-ttu-id="95697-384">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="95697-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="95697-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="95697-386">Interno</span><span class="sxs-lookup"><span data-stu-id="95697-386">Internal</span></span> |<span data-ttu-id="95697-387">Igual que SBC</span><span class="sxs-lookup"><span data-stu-id="95697-387">Same as SBC</span></span>   | <span data-ttu-id="95697-388">Saliente</span><span class="sxs-lookup"><span data-stu-id="95697-388">Outbound</span></span> |

<span data-ttu-id="95697-389">En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="95697-390">Este es el mismo flujo que se muestra en las [llamadas salientes cuando el usuario está en la misma ubicación que la SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="95697-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="95697-392">Las llamadas entrantes y el usuario se encuentra en la misma ubicación que la SBC solo para los usuarios locales</span><span class="sxs-lookup"><span data-stu-id="95697-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="95697-393">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-393">Mode</span></span> | <span data-ttu-id="95697-394">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-394">User</span></span> | <span data-ttu-id="95697-395">Sitio</span><span class="sxs-lookup"><span data-stu-id="95697-395">Site</span></span> | <span data-ttu-id="95697-396">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="95697-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="95697-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="95697-398">Interno</span><span class="sxs-lookup"><span data-stu-id="95697-398">Internal</span></span> | <span data-ttu-id="95697-399">Igual que SBC</span><span class="sxs-lookup"><span data-stu-id="95697-399">Same as SBC</span></span> | <span data-ttu-id="95697-400">Entrada</span><span class="sxs-lookup"><span data-stu-id="95697-400">Inbound</span></span> |

<span data-ttu-id="95697-401">En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="95697-402">Este es el mismo flujo que se muestra en las [llamadas entrantes cuando el usuario está en la misma ubicación que la SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="95697-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="95697-404">El usuario no está en la misma ubicación que la SBC pero está en la red corporativa solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="95697-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="95697-405">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-405">Mode</span></span> | <span data-ttu-id="95697-406">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-406">User</span></span> | <span data-ttu-id="95697-407">Sitio</span><span class="sxs-lookup"><span data-stu-id="95697-407">Site</span></span> |<span data-ttu-id="95697-408">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="95697-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="95697-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="95697-410">Interno</span><span class="sxs-lookup"><span data-stu-id="95697-410">Internal</span></span> |   <span data-ttu-id="95697-411">Diferente de SBC</span><span class="sxs-lookup"><span data-stu-id="95697-411">Different from SBC</span></span> | <span data-ttu-id="95697-412">Saliente</span><span class="sxs-lookup"><span data-stu-id="95697-412">Outbound</span></span> |

<span data-ttu-id="95697-413">El enrutamiento directo calcula la X-MediaPath en función de la ubicación de la que se informó del usuario y el modo configurado en la SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="95697-414">En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="95697-416">La llamada entrante y el usuario son internas, pero no están en la misma ubicación que el SBC solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="95697-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="95697-417">Modo</span><span class="sxs-lookup"><span data-stu-id="95697-417">Mode</span></span> |    <span data-ttu-id="95697-418">Usuario</span><span class="sxs-lookup"><span data-stu-id="95697-418">User</span></span> |  <span data-ttu-id="95697-419">Sitio</span><span class="sxs-lookup"><span data-stu-id="95697-419">Site</span></span> |  <span data-ttu-id="95697-420">Dirección de la llamada</span><span class="sxs-lookup"><span data-stu-id="95697-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="95697-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="95697-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="95697-422">Interno</span><span class="sxs-lookup"><span data-stu-id="95697-422">Internal</span></span> |    <span data-ttu-id="95697-423">Diferente de SBC</span><span class="sxs-lookup"><span data-stu-id="95697-423">Different from SBC</span></span> |    <span data-ttu-id="95697-424">Entrada</span><span class="sxs-lookup"><span data-stu-id="95697-424">Inbound</span></span> |

<span data-ttu-id="95697-425">En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que la SBC.</span><span class="sxs-lookup"><span data-stu-id="95697-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama que muestra la escalera de SIP](media/direct-routing-media-op-17.png)










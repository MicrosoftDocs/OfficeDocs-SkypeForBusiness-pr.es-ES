---
title: Administrar la topología de red para las características de voz en la nube en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo configurar la configuración de red para las características de voz en la nube en Microsoft Teams.
ms.openlocfilehash: 7d8bc7f06934134538fca59a3f19285d97756e2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802580"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="90188-103">Administrar la topología de red para las características de voz en la nube en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90188-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="90188-104">Si su organización [](location-based-routing-plan.md) implementa enrutamiento basado en la ubicación para enrutamiento directo o llamadas de emergencia dinámicas, [](configure-dynamic-emergency-calling.md)debe configurar las opciones de red para usarlas con estas características de voz en la nube en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90188-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="90188-105">La configuración de red se usa para determinar la ubicación de un cliente de Teams e incluye regiones de red, sitios de red, subredes y direcciones IP de confianza.</span><span class="sxs-lookup"><span data-stu-id="90188-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="90188-106">En función de la característica y la funcionalidad de voz en la nube que está implementando, configure algunas o todas estas opciones.</span><span class="sxs-lookup"><span data-stu-id="90188-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="90188-107">Para obtener más información sobre estos términos, consulte [Configuración de red para las características de voz en la nube.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="90188-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="90188-108">Configure las opciones de red en **la página topología de** red del Centro de administración de Microsoft Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90188-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="90188-109">Configurar la configuración de red en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90188-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="90188-110">Las regiones de red, los sitios de red y las subredes se definen en la **pestaña Sitios** de red de la página Topología **de** red.</span><span class="sxs-lookup"><span data-stu-id="90188-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="90188-111">Aquí puede crear o modificar un sitio de red, asociar un sitio a una región de red, asociar una subred al sitio, activar el enrutamiento basado en la ubicación y asignar directivas de emergencia al sitio.</span><span class="sxs-lookup"><span data-stu-id="90188-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="90188-112">También puede agregar regiones de red que se puedan usar de forma global en todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="90188-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="90188-113">Agregar y configurar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="90188-113">Add and configure a network site</span></span>

1. <span data-ttu-id="90188-114">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la topología de red de ubicaciones y, a continuación, haga clic en  >  la pestaña **Sitios de** red.</span><span class="sxs-lookup"><span data-stu-id="90188-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="90188-115">Haga **clic en** Agregar y, a continuación, escriba un nombre y una descripción para el sitio.</span><span class="sxs-lookup"><span data-stu-id="90188-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![Captura de pantalla de la página Agregar sitio de red](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="90188-117">Para asociar el sitio a una región de red, haga  clic en Agregar región de **red,** seleccione una región existente o haga clic en Agregar para agregar una región y, a continuación, haga clic en **Vínculo.**</span><span class="sxs-lookup"><span data-stu-id="90188-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="90188-118">Para habilitar el Location-Based de destino para el sitio, active el **enrutamiento basado en la ubicación.**</span><span class="sxs-lookup"><span data-stu-id="90188-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="90188-119">Para asignar directivas de servicios de emergencia al sitio, realice uno de los siguientes procedimientos o ambos:</span><span class="sxs-lookup"><span data-stu-id="90188-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="90188-120">Si su organización usa planes de llamadas o enrutamiento directo de sistema telefónico implementado, en la directiva de llamadas de **emergencia,** seleccione la directiva que desee.</span><span class="sxs-lookup"><span data-stu-id="90188-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="90188-121">Si su organización implementó El enrutamiento directo de sistema telefónico, en la **directiva de enrutamiento** de llamadas de emergencia, seleccione la directiva que desee.</span><span class="sxs-lookup"><span data-stu-id="90188-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="90188-122">Para asociar una subred al sitio, **en** Subred, haga clic en **Agregar subredes.**</span><span class="sxs-lookup"><span data-stu-id="90188-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="90188-123">Especifique la versión IP, la dirección IP, el intervalo de red, agregue una descripción y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="90188-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="90188-124">Cada subred debe estar asociada a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="90188-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="90188-125">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="90188-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="90188-126">Modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="90188-126">Modify a network site</span></span>

1. <span data-ttu-id="90188-127">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la topología de red de ubicaciones y, a continuación, haga clic en  >  la pestaña **Sitios de** red.</span><span class="sxs-lookup"><span data-stu-id="90188-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="90188-128">Seleccione el sitio haciendo clic a la izquierda del nombre del sitio y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="90188-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="90188-129">Realice los cambios que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="90188-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="90188-130">Administrar direcciones IP de confianza externas</span><span class="sxs-lookup"><span data-stu-id="90188-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="90188-131">Puede administrar direcciones IP  de confianza externas en la pestaña Direcciones IP de confianza en la **página** Topología de red del Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90188-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="90188-132">Puede agregar un número ilimitado de direcciones IP externas de confianza.</span><span class="sxs-lookup"><span data-stu-id="90188-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="90188-133">Agregar una dirección IP de confianza</span><span class="sxs-lookup"><span data-stu-id="90188-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="90188-134">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la topología de red de ubicaciones y, a continuación, haga clic en la  >  pestaña Direcciones **IP de** confianza.</span><span class="sxs-lookup"><span data-stu-id="90188-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="90188-135">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="90188-135">Click **New**.</span></span>
3. <span data-ttu-id="90188-136">En el **panel Agregar dirección IP** de confianza, especifique la versión IP, la dirección IP, el intervalo de red, agregue una descripción y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="90188-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Captura de pantalla del panel Agregar dirección IP de confianza](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="90188-138">Editar una dirección IP de confianza</span><span class="sxs-lookup"><span data-stu-id="90188-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="90188-139">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la topología de red de ubicaciones y, a continuación, haga clic en la  >  pestaña Direcciones **IP de** confianza.</span><span class="sxs-lookup"><span data-stu-id="90188-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="90188-140">Seleccione la dirección IP haciendo clic a la izquierda de la misma y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="90188-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="90188-141">En el **panel Editar dirección IP de** confianza, realice los cambios que desee y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="90188-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="90188-142">Configurar las opciones de red con PowerShell</span><span class="sxs-lookup"><span data-stu-id="90188-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="90188-143">Para completar los pasos de esta sección, necesitará estar familiarizado con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90188-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="90188-144">Para obtener más información, consulte [Información general de PowerShell de Teams.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="90188-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="90188-145">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="90188-145">Define network regions</span></span>

 <span data-ttu-id="90188-146">Use el [cmdlet New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) para definir regiones de red.</span><span class="sxs-lookup"><span data-stu-id="90188-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="90188-147">Tenga en cuenta que el parámetro RegionID es un nombre lógico que representa la ubicación geográfica de la región y no tiene dependencias ni restricciones y el parámetro Id. de sitio de CentralSite &lt; &gt; es opcional.</span><span class="sxs-lookup"><span data-stu-id="90188-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="90188-148">En este ejemplo, creamos una región de red denominada India.</span><span class="sxs-lookup"><span data-stu-id="90188-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="90188-149">Vea también [Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)</span><span class="sxs-lookup"><span data-stu-id="90188-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="90188-150">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="90188-150">Define network sites</span></span>

<span data-ttu-id="90188-151">Use el [cmdlet New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sitios de red.</span><span class="sxs-lookup"><span data-stu-id="90188-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="90188-152">Cada sitio de red debe estar asociado a una región de red.</span><span class="sxs-lookup"><span data-stu-id="90188-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="90188-153">En este ejemplo, se crean dos nuevos sitios de red, Ada y Querabad, en la región de la India.</span><span class="sxs-lookup"><span data-stu-id="90188-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="90188-154">En la tabla siguiente se muestran los sitios de red definidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="90188-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="90188-155">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="90188-155">Site 1</span></span> |<span data-ttu-id="90188-156">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="90188-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="90188-157">Id. de sitio</span><span class="sxs-lookup"><span data-stu-id="90188-157">Site ID</span></span>    |    <span data-ttu-id="90188-158">Sitio 1 (Cca)</span><span class="sxs-lookup"><span data-stu-id="90188-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="90188-159">Sitio 2 (Jordaniarabad)</span><span class="sxs-lookup"><span data-stu-id="90188-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="90188-160">Id. de región</span><span class="sxs-lookup"><span data-stu-id="90188-160">Region ID</span></span>  |     <span data-ttu-id="90188-161">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="90188-161">Region 1 (India)</span></span>    |   <span data-ttu-id="90188-162">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="90188-162">Region 1 (India)</span></span>      |

<span data-ttu-id="90188-163">Vea también [Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)</span><span class="sxs-lookup"><span data-stu-id="90188-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="90188-164">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="90188-164">Define network subnets</span></span>

<span data-ttu-id="90188-165">Use el [cmdlet New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir subredes de red y asociarlas a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="90188-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="90188-166">Cada subred de red solo puede estar asociada a un sitio.</span><span class="sxs-lookup"><span data-stu-id="90188-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="90188-167">En este ejemplo, se crea una asociación entre la subred 192.168.0.0 y el sitio de red deGina, y entre la subred 2001:4898:e8:25:844e:926f:85ad:dd8e y el sitio de red de Rgpd.</span><span class="sxs-lookup"><span data-stu-id="90188-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="90188-168">En la tabla siguiente se muestran las subredes definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="90188-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="90188-169">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="90188-169">Site 1</span></span> |<span data-ttu-id="90188-170">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="90188-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="90188-171">Id. de subred</span><span class="sxs-lookup"><span data-stu-id="90188-171">Subnet ID</span></span>   |    <span data-ttu-id="90188-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="90188-172">192.168.0.0</span></span>     |  <span data-ttu-id="90188-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span><span class="sxs-lookup"><span data-stu-id="90188-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="90188-174">Máscara</span><span class="sxs-lookup"><span data-stu-id="90188-174">Mask</span></span>  |     <span data-ttu-id="90188-175">24</span><span class="sxs-lookup"><span data-stu-id="90188-175">24</span></span>    |   <span data-ttu-id="90188-176">120</span><span class="sxs-lookup"><span data-stu-id="90188-176">120</span></span>      |
|<span data-ttu-id="90188-177">Id. de sitio</span><span class="sxs-lookup"><span data-stu-id="90188-177">Site ID</span></span>  | <span data-ttu-id="90188-178">Sitio (Quédá)</span><span class="sxs-lookup"><span data-stu-id="90188-178">Site (Delhi)</span></span> | <span data-ttu-id="90188-179">Sitio 2 (Jordaniarabad)</span><span class="sxs-lookup"><span data-stu-id="90188-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="90188-180">Para varias subredes, puede importar un archivo CSV mediante un script como el siguiente.</span><span class="sxs-lookup"><span data-stu-id="90188-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="90188-181">En este ejemplo, el archivo CSV tiene un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="90188-181">In this example, the CSV file looks something like this:</span></span> 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="90188-182">Vea también [Set-CsTenantNetworkSubnet.](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)</span><span class="sxs-lookup"><span data-stu-id="90188-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="90188-183">Definir subredes externas (direcciones IP de confianza externas)</span><span class="sxs-lookup"><span data-stu-id="90188-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="90188-184">Use el [cmdlet New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir subredes externas y asignarlas al inquilino.</span><span class="sxs-lookup"><span data-stu-id="90188-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="90188-185">Puede definir un número ilimitado de subredes externas para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="90188-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="90188-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="90188-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="90188-187">Vea también [Set-CsTenantTrustedIPAddress.](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)</span><span class="sxs-lookup"><span data-stu-id="90188-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="90188-188">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="90188-188">Related topics</span></span>

- [<span data-ttu-id="90188-189">Configuración de red para las características de voz en la nube en Teams</span><span class="sxs-lookup"><span data-stu-id="90188-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)

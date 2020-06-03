---
title: Administrar la topología de red para las características de voz en la nube en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo configurar las opciones de red para las características de voz en la nube en Microsoft Teams.
ms.openlocfilehash: 03eaeac1bce07cffa7dc000f964f080361a37d40
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539630"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="0c8e3-103">Administrar la topología de red para las características de voz en la nube en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c8e3-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="0c8e3-104">Si su organización está implementando [enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md) o las [llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md), debe configurar las opciones de red para usarlas con estas características de voz de nube en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="0c8e3-105">La configuración de red se usa para determinar la ubicación de un cliente de equipo e incluir regiones de red, sitios de red, subredes y direcciones IP de confianza.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="0c8e3-106">En función de la característica de voz de nube y de la capacidad de implementación, debe configurar algunas o todas estas opciones.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="0c8e3-107">Para obtener más información sobre estos términos, consulte [configuración de red para características de voz en la nube](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0c8e3-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="0c8e3-108">La configuración de red se establece en la página **topología de red** del centro de administración de Microsoft Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0c8e3-109">Configurar las opciones de red en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c8e3-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="0c8e3-110">Defina regiones de red, sitios de red y subredes en la ficha **sitios de red** de la página topología de **red** .</span><span class="sxs-lookup"><span data-stu-id="0c8e3-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="0c8e3-111">Aquí puede crear o modificar un sitio de red, asociar un sitio con una región de red, asociar una subred al sitio, activar el enrutamiento basado en la ubicación y asignar directivas de emergencia al sitio.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="0c8e3-112">También puede Agregar regiones de red que se pueden usar globalmente para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="0c8e3-113">Agregar y configurar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="0c8e3-113">Add and configure a network site</span></span>

1. <span data-ttu-id="0c8e3-114">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **sitios de red** .</span><span class="sxs-lookup"><span data-stu-id="0c8e3-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="0c8e3-115">Haga clic en **Agregar**y, a continuación, escriba un nombre y una descripción para el sitio.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![Captura de pantalla de la página Agregar sitio de red](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="0c8e3-117">Para asociar el sitio con una región de red, haga clic en **Agregar región de red**, seleccione una región existente o haga clic en **Agregar** para agregar una región y, a continuación, haga clic en **vincular**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="0c8e3-118">Para habilitar el enrutamiento basado en la ubicación del sitio, active el **enrutamiento basado**en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="0c8e3-119">Para asignar directivas de servicios de emergencia al sitio, realice una de las siguientes acciones o ambas:</span><span class="sxs-lookup"><span data-stu-id="0c8e3-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="0c8e3-120">Si su organización usa planes de llamadas o enrutamiento directo de sistema telefónico implementado, en **Directiva de llamadas de emergencia**, seleccione la Directiva que desee.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="0c8e3-121">Si su organización ha implementado el enrutamiento de un sistema telefónico directo, en **Directiva de enrutamiento de llamadas de emergencia**, seleccione la Directiva que quiera.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="0c8e3-122">Para asociar una subred al sitio, en **subredes**, haga clic en **Agregar subredes**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="0c8e3-123">Especifique la versión IP, la dirección IP, el intervalo de red, agregue una descripción y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="0c8e3-124">Cada subred debe estar asociada a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="0c8e3-125">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="0c8e3-126">Modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="0c8e3-126">Modify a network site</span></span>

1. <span data-ttu-id="0c8e3-127">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **sitios de red** .</span><span class="sxs-lookup"><span data-stu-id="0c8e3-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="0c8e3-128">Seleccione el sitio haciendo clic a la izquierda del nombre del sitio y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0c8e3-129">Realice los cambios que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="0c8e3-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="0c8e3-130">Administrar direcciones IP de confianza externas</span><span class="sxs-lookup"><span data-stu-id="0c8e3-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="0c8e3-131">Las direcciones IP de confianza externas se administran en la ficha **IP fiables** de la página **topología de red** del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="0c8e3-132">Puedes añadir un número ilimitado de direcciones IP de confianza externas.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="0c8e3-133">Agregar una dirección IP fiable</span><span class="sxs-lookup"><span data-stu-id="0c8e3-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="0c8e3-134">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **IP fiables** .</span><span class="sxs-lookup"><span data-stu-id="0c8e3-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="0c8e3-135">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-135">Click **New**.</span></span>
3. <span data-ttu-id="0c8e3-136">En el panel **Agregar una dirección IP de confianza** , especifique la versión IP, la dirección IP, el intervalo de red, agregue una descripción y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Captura de pantalla del panel agregar dirección IP fiable](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="0c8e3-138">Modificar una dirección IP fiable</span><span class="sxs-lookup"><span data-stu-id="0c8e3-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="0c8e3-139">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **IP fiables** .</span><span class="sxs-lookup"><span data-stu-id="0c8e3-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="0c8e3-140">Seleccione la dirección IP haciendo clic a la izquierda y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="0c8e3-141">En el panel **Editar direcciones IP fiables** , realice los cambios que desee y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="0c8e3-142">Configurar las opciones de red con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c8e3-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="0c8e3-143">Para completar los pasos de esta sección, necesitará cierta familiaridad con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="0c8e3-144">Para obtener más información, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c8e3-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="0c8e3-145">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="0c8e3-145">Define network regions</span></span>

 <span data-ttu-id="0c8e3-146">Use el cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) para definir regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="0c8e3-147">Tenga en cuenta que el parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones, y el &lt; parámetro de identificador de sitio CentralSite &gt; es opcional.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="0c8e3-148">En este ejemplo, creamos una región de red denominada India.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="0c8e3-149">Consulte también [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span><span class="sxs-lookup"><span data-stu-id="0c8e3-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="0c8e3-150">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="0c8e3-150">Define network sites</span></span>

<span data-ttu-id="0c8e3-151">Use el cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sitios de red.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="0c8e3-152">Cada sitio de red debe estar asociado a una región de red.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="0c8e3-153">En este ejemplo, creamos dos nuevos sitios de red, Delhi y Hyderabad, en la región de India.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="0c8e3-154">En la tabla siguiente se muestran los sitios de red definidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="0c8e3-155">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="0c8e3-155">Site 1</span></span> |<span data-ttu-id="0c8e3-156">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="0c8e3-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0c8e3-157">IDENTIFICADOR de sitio</span><span class="sxs-lookup"><span data-stu-id="0c8e3-157">Site ID</span></span>    |    <span data-ttu-id="0c8e3-158">Sitio 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0c8e3-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="0c8e3-159">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0c8e3-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="0c8e3-160">IDENTIFICADOR de región</span><span class="sxs-lookup"><span data-stu-id="0c8e3-160">Region ID</span></span>  |     <span data-ttu-id="0c8e3-161">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="0c8e3-161">Region 1 (India)</span></span>    |   <span data-ttu-id="0c8e3-162">Región 1 (India)</span><span class="sxs-lookup"><span data-stu-id="0c8e3-162">Region 1 (India)</span></span>      |

<span data-ttu-id="0c8e3-163">Consulte también [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span><span class="sxs-lookup"><span data-stu-id="0c8e3-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="0c8e3-164">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="0c8e3-164">Define network subnets</span></span>

<span data-ttu-id="0c8e3-165">Use el cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir subredes de red y asociarlas a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="0c8e3-166">Cada subred de red solo se puede asociar con un sitio.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="0c8e3-167">En este ejemplo, creamos una asociación entre la subred 192.168.0.0 y el sitio de red de Delhi y entre la subred 2001:4898: E8:25:844e: 926f: 85ad: dd8e y el sitio de red de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="0c8e3-168">En la tabla siguiente se muestran las subredes definidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="0c8e3-169">Sitio 1</span><span class="sxs-lookup"><span data-stu-id="0c8e3-169">Site 1</span></span> |<span data-ttu-id="0c8e3-170">Sitio 2</span><span class="sxs-lookup"><span data-stu-id="0c8e3-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0c8e3-171">IDENTIFICADOR de subred</span><span class="sxs-lookup"><span data-stu-id="0c8e3-171">Subnet ID</span></span>   |    <span data-ttu-id="0c8e3-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="0c8e3-172">192.168.0.0</span></span>     |  <span data-ttu-id="0c8e3-173">2001:4898: E8:25:844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="0c8e3-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="0c8e3-174">Sin</span><span class="sxs-lookup"><span data-stu-id="0c8e3-174">Mask</span></span>  |     <span data-ttu-id="0c8e3-175">veinticuatro</span><span class="sxs-lookup"><span data-stu-id="0c8e3-175">24</span></span>    |   <span data-ttu-id="0c8e3-176">120</span><span class="sxs-lookup"><span data-stu-id="0c8e3-176">120</span></span>      |
|<span data-ttu-id="0c8e3-177">IDENTIFICADOR de sitio</span><span class="sxs-lookup"><span data-stu-id="0c8e3-177">Site ID</span></span>  | <span data-ttu-id="0c8e3-178">Sitio (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0c8e3-178">Site (Delhi)</span></span> | <span data-ttu-id="0c8e3-179">Sitio 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0c8e3-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="0c8e3-180">En el caso de varias subredes, puede importar un archivo CSV con una secuencia de comandos como la siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="0c8e3-181">En este ejemplo, el archivo CSV tiene un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="0c8e3-181">In this example, the CSV file looks something like this:</span></span>

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="0c8e3-182">Consulte también [set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span><span class="sxs-lookup"><span data-stu-id="0c8e3-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="0c8e3-183">Definir subredes externas (direcciones IP externas de confianza)</span><span class="sxs-lookup"><span data-stu-id="0c8e3-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="0c8e3-184">Use el cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir subredes externas y asignarlas al inquilino.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="0c8e3-185">Puede definir un número ilimitado de subredes externas para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="0c8e3-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="0c8e3-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c8e3-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="0c8e3-187">Consulte también [set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span><span class="sxs-lookup"><span data-stu-id="0c8e3-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c8e3-188">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0c8e3-188">Related topics</span></span>

- [<span data-ttu-id="0c8e3-189">Configuración de red de las características de voz en la nube en Teams</span><span class="sxs-lookup"><span data-stu-id="0c8e3-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)

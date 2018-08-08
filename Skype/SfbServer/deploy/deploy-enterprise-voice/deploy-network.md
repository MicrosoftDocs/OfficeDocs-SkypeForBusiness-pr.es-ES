---
title: Implementar regiones de red, sitios y las subredes de Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Crear o modificar regiones de red, sitios de red y asociar subredes de red en Skype para Business Server. Todas estas se usan para las características avanzadas de Enterprise Voice: desvío de medios, el control de admisión y enrutamiento basado en la ubicación de llamadas.'
ms.openlocfilehash: 427ab9102fe7a840aee68e0dbc2c372b908930e8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20980777"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="8287a-104">Implementar regiones de red, sitios y las subredes de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="8287a-104">Deploy network regions, sites and subnets in Skype for Business</span></span>
 
<span data-ttu-id="8287a-105">Crear o modificar regiones de red, sitios de red y asociar subredes de red en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8287a-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="8287a-106">Todas estas se usan para las características avanzadas de Enterprise Voice: desvío de medios, el control de admisión y enrutamiento basado en la ubicación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8287a-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>
  
<span data-ttu-id="8287a-107">Las características avanzadas de Telefonía IP empresarial son [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md) y [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="8287a-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="8287a-108">Para todas estas características, es necesario crear regiones de red, sitios de red y subredes.</span><span class="sxs-lookup"><span data-stu-id="8287a-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="8287a-109">Por ejemplo, todas estas características requieren que cada una de las subredes de la topología estén asociadas a un sitio de red específico, y cada uno de los sitios de red debe estar asociado a una región de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="8287a-110">Para obtener más información acerca de estos términos, vea [configuración de red para las características avanzadas de Enterprise Voice en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="8287a-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span></span>
  
<span data-ttu-id="8287a-111">El control de admisión de llamadas y E9-1-1 tienen requisitos de configuración adicionales para los sitios de red:</span><span class="sxs-lookup"><span data-stu-id="8287a-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>
  
- <span data-ttu-id="8287a-112">El control de admisión de llamadas requiere que se especifique un   perfil de directiva de ancho de banda para cada uno de los sitios restringidos con limitaciones de ancho de banda WAN.</span><span class="sxs-lookup"><span data-stu-id="8287a-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="8287a-113">Si tiene previsto implementar el control de admisión de llamadas, debe [crear perfiles de directiva de ancho de banda en Skype para Business Server](create-bandwidth-policy-profiles.md) antes de configurar los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>
    
- <span data-ttu-id="8287a-114">E9-1-1 requiere que se especifique una directiva de ubicación para cada uno de los sitios.</span><span class="sxs-lookup"><span data-stu-id="8287a-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="8287a-115">Si planea implementar E9-1-1, debe [crear las directivas de ubicación en Skype para Business Server](create-location-policies.md) antes de configurar los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>
    
## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="8287a-116">Crear o modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="8287a-116">Create or modify a Network Region</span></span>

<span data-ttu-id="8287a-117">Si ya ha creado las regiones de red para una de estas características, no es necesario crear nuevas regiones de red; otras características avanzadas de Enterprise Voice utilizará esas mismos regiones de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> 
  
<span data-ttu-id="8287a-p106">Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="8287a-p106">You may, however, need to modify an existing network region definition to apply feature-specific settings. For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 
  
### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8287a-120">Para crear una región de red mediante Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8287a-121">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8287a-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8287a-122">Ejecute el cmdlet New-CsNetworkRegion para crear regiones de red:</span><span class="sxs-lookup"><span data-stu-id="8287a-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="8287a-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8287a-123">For example:</span></span>
    
   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="8287a-124">En este ejemplo, ha creado una región de red denominada "NorthAmerica" que está asociado a un sitio central con identificador de sitio CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="8287a-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>
    
3. <span data-ttu-id="8287a-125">Para terminar de crear regiones de red para la topología, repita el paso 2 con parámetros para cada región de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>
    
### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8287a-126">Para crear una región de red mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8287a-127">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8287a-127">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="8287a-128">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="8287a-128">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="8287a-129">Haga clic en **Región**</span><span class="sxs-lookup"><span data-stu-id="8287a-129">Click **Region**.</span></span>
    
4. <span data-ttu-id="8287a-130">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8287a-130">Click **New**.</span></span>
    
5. <span data-ttu-id="8287a-131">En la página **Región nueva**, haga clic en **Nombre** y escriba un nombre para la región de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>
    
6. <span data-ttu-id="8287a-132">Haga clic en **Sitio central** y, a continuación, haga clic en un sitio central de la lista.</span><span class="sxs-lookup"><span data-stu-id="8287a-132">Click **Central site**, and then click a central site in the list.</span></span>
    
7. <span data-ttu-id="8287a-133">Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>
    
8. <span data-ttu-id="8287a-134">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8287a-134">Click **Commit**.</span></span>
    
9. <span data-ttu-id="8287a-135">Para terminar de crear regiones de red para la topología, repita los pasos del 4 al 8 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="8287a-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>
    
### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8287a-136">Para modificar una región de red mediante Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8287a-137">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8287a-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8287a-138">Ejecute el cmdlet Set-CsNetworkRegion para modificar una región de red existente:</span><span class="sxs-lookup"><span data-stu-id="8287a-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="8287a-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8287a-139">For example:</span></span>
    
   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="8287a-140">En este ejemplo, se modifica una región de red existente denominada "NorthAmerica" (creada mediante los procedimientos descritos anteriormente en este tema) cambiando la descripción.</span><span class="sxs-lookup"><span data-stu-id="8287a-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="8287a-141">Si existía una descripción para el área de "NorthAmerica", este comando sobrescribe con este valor; Si no se establecieron ninguna descripción, a continuación, este comando establece.</span><span class="sxs-lookup"><span data-stu-id="8287a-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>
    
3. <span data-ttu-id="8287a-142">Para modificar otras regiones de red, repita el paso 2 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="8287a-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>
    
### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8287a-143">Para modificar una región de red mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8287a-144">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8287a-144">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="8287a-145">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="8287a-145">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="8287a-146">Haga clic en el botón de navegación **Región**.</span><span class="sxs-lookup"><span data-stu-id="8287a-146">Click the **Region** navigation button.</span></span>
    
4. <span data-ttu-id="8287a-147">En la tabla, haga clic en la región de red que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="8287a-147">In the table, click the network region that you want to modify.</span></span>
    
5. <span data-ttu-id="8287a-148">Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.</span><span class="sxs-lookup"><span data-stu-id="8287a-148">Click **Edit**, and then click **Show details…**.</span></span>
    
6. <span data-ttu-id="8287a-149">En la página **Editar región** , cambie los valores de configuración de la región de red según corresponda.</span><span class="sxs-lookup"><span data-stu-id="8287a-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>
    
7. <span data-ttu-id="8287a-150">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8287a-150">Click **Commit**.</span></span>
    
8. <span data-ttu-id="8287a-151">Para terminar de modificar regiones de red, repita los pasos del 4 al 7 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="8287a-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>
    
## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="8287a-152">Crear o modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="8287a-152">Create or modify a network site</span></span>

<span data-ttu-id="8287a-153">Si ya ha creado los sitios de red para una de estas características, no es necesario crear nuevos sitios de red; otras características avanzadas de Enterprise Voice usarán los mismos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="8287a-154">Con todo, puede que sea necesario modificar una definición de sitio de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="8287a-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="8287a-155">Así, si ha creado un sitio de red para E9-1-1, deberá modificar el sitio de red durante la implementación de un control de admisión de llamadas con objeto de aplicar un perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="8287a-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span> 
  
### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8287a-156">Para crear un sitio de red mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8287a-157">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8287a-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8287a-158">Ejecute el cmdlet New-CsNetworkSite para crear sitios de red:</span><span class="sxs-lookup"><span data-stu-id="8287a-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="8287a-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8287a-159">For example:</span></span>
    
   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="8287a-160">En este ejemplo, ha creado un sitio de red denominado "Chicago" que se encuentra en la región de red "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="8287a-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8287a-161">Esta región de red ya debe existir para que este comando se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="8287a-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span> 
  
3. <span data-ttu-id="8287a-162">Para terminar de crear sitios de red en su topología, repita el paso 2 con la configuración pertinente del resto de sitios.</span><span class="sxs-lookup"><span data-stu-id="8287a-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>
    
### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8287a-163">Para crear un sitio de red mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8287a-164">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8287a-164">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="8287a-165">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="8287a-165">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="8287a-166">Haga clic en el botón de navegación **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="8287a-166">Click the **Site** navigation button.</span></span>
    
4. <span data-ttu-id="8287a-167">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8287a-167">Click **New**.</span></span>
    
5. <span data-ttu-id="8287a-168">En la página **Nuevo sitio**, haga clic en **Nombre** y, a continuación, escriba un nombre para el sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>
    
6. <span data-ttu-id="8287a-169">Haga clic en **Región**y, a continuación, en una región de la lista.</span><span class="sxs-lookup"><span data-stu-id="8287a-169">Click **Region**, and then click a region in the list.</span></span>
    
7. <span data-ttu-id="8287a-170">Si lo desea, también puede hacer clic en **Directiva de ancho de banda** y hacer clic en una directiva de ancho de banda de la lista.</span><span class="sxs-lookup"><span data-stu-id="8287a-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8287a-171">Las directivas de ancho de banda solo son necesarias cuando se implementa el control de admisión de llamadas en el sitio.</span><span class="sxs-lookup"><span data-stu-id="8287a-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span> 
  
8. <span data-ttu-id="8287a-172">Si lo desea, también puede hacer clic en **Directiva de ubicación** y hacer clic en una directiva de ubicación de la lista.</span><span class="sxs-lookup"><span data-stu-id="8287a-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8287a-173">Las directivas de ubicación solo son necesarias cuando se implementa E9-1-1 en el sitio.</span><span class="sxs-lookup"><span data-stu-id="8287a-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span> 
  
9. <span data-ttu-id="8287a-174">Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>
    
10. <span data-ttu-id="8287a-175">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8287a-175">Click **Commit**.</span></span>
    
11. <span data-ttu-id="8287a-176">Para terminar de crear sitios de red en su topología, repita los pasos 4 a 10 con la configuración pertinente del resto de sitios.</span><span class="sxs-lookup"><span data-stu-id="8287a-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>
    
### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8287a-177">Para modificar un sitio de red mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8287a-178">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8287a-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8287a-179">Ejecute el cmdlet Set-CsNetworkSite para modificar sitios de red:</span><span class="sxs-lookup"><span data-stu-id="8287a-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="8287a-180">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8287a-180">For example:</span></span>
    
   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="8287a-181">En este ejemplo, se mueve el sitio denominado a "Albuquerque" a la región de red "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="8287a-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="8287a-182">Para modificar la configuración de sitio de red a fin de implementar el control de admisión de llamadas, E9-1-1 o el desvío de medios, cambie la configuración del sitio de red ejecutando el cmdlet Set-CsNetworkSite con los parámetros BWPolicyProfileID o LocationPolicy respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8287a-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8287a-p110">En el caso del desvío de medios, existe un parámetro BypassID, si bien se recomienda encarecidamente no invalidar automáticamente los identificadores de desvío generados. No es necesario especificar más parámetros para configurar un sitio de red para el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="8287a-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span> 
  
3. <span data-ttu-id="8287a-185">Para terminar de modificar sitios de red en su topología, repita el paso 2 con la configuración pertinente del resto de sitios.</span><span class="sxs-lookup"><span data-stu-id="8287a-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>
    
### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8287a-186">Para modificar un sitio de red mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8287a-187">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8287a-187">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="8287a-188">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="8287a-188">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="8287a-189">Haga clic en el botón de navegación **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="8287a-189">Click the **Site** navigation button.</span></span>
    
4. <span data-ttu-id="8287a-190">En la tabla, haga clic en el sitio de red que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="8287a-190">In the table, click the network site that you want to modify.</span></span>
    
5. <span data-ttu-id="8287a-191">Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.</span><span class="sxs-lookup"><span data-stu-id="8287a-191">Click **Edit**, and then click **Show details…**.</span></span>
    
6. <span data-ttu-id="8287a-192">En la página **Modificar sitio** , cambie los valores de configuración de este sitio de red según corresponda.</span><span class="sxs-lookup"><span data-stu-id="8287a-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>
    
7. <span data-ttu-id="8287a-193">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8287a-193">Click **Commit**.</span></span>
    
8. <span data-ttu-id="8287a-194">Para terminar de modificar sitios de red, repita los pasos 4 a 7 con la configuración pertinente del resto de sitios.</span><span class="sxs-lookup"><span data-stu-id="8287a-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>
    
## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="8287a-195">Asociar una subred a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="8287a-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="8287a-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="8287a-196"></span></span>

<span data-ttu-id="8287a-197">Cada subred de la red debe estar asociado a un sitio de red específico, debido a que la información de la subred se utiliza para determinar el sitio de red en el que se encuentra un extremo mientras se inicia una nueva sesión.</span><span class="sxs-lookup"><span data-stu-id="8287a-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="8287a-198">Cuando se conoce la ubicación de cada parte en una sesión, pueden aplicar las características de Enterprise Voice esa información avanzada para determinar cómo controlar la configuración de llamadas o enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="8287a-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>
  
<span data-ttu-id="8287a-199">Todas las direcciones IP públicas de los servidores perimetrales de audio y vídeo en la implementación deben incluirse en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="8287a-200">Estas direcciones IP se agregan como subredes con una máscara de 32.</span><span class="sxs-lookup"><span data-stu-id="8287a-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="8287a-201">El sitio de red asociado debe corresponder con el sitio de red configurado adecuado.</span><span class="sxs-lookup"><span data-stu-id="8287a-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="8287a-202">Por ejemplo, en la dirección IP pública que se corresponde con el servicio perimetral A/v en el sitio central Chicago debería ser NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="8287a-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>
  
### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8287a-203">Para asociar una subred a un sitio de red mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8287a-204">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8287a-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8287a-205">Ejecute el cmdlet **New-CsNetworkSubnet** para asociar una subred a un sitio de red:</span><span class="sxs-lookup"><span data-stu-id="8287a-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="8287a-206">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8287a-206">For example:</span></span>
     
   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="8287a-207">En este ejemplo, ha creado una asociación entre la subred 172.11.12.13 y el sitio de red "Chicago".</span><span class="sxs-lookup"><span data-stu-id="8287a-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>
    
3. <span data-ttu-id="8287a-208">Repita el paso 2 para todas las subredes de la topología.</span><span class="sxs-lookup"><span data-stu-id="8287a-208">Repeat step 2 for all subnets in your topology.</span></span>
    
### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="8287a-209">Para asociar subredes a sitios de red mediante la importación de un archivo CSV</span><span class="sxs-lookup"><span data-stu-id="8287a-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="8287a-p113">Cree un archivo CSV que incluya todas las subredes que quiera agregar. Por ejemplo, cree un archivo denominado   **subnet.csv** con el contenido siguiente:</span><span class="sxs-lookup"><span data-stu-id="8287a-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
     `IPAddress, mask, description, NetworkSiteID`
    
     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`
    
2. <span data-ttu-id="8287a-212">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8287a-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8287a-213">Ejecute el siguiente cmdlet para importar **subnet.csv**y, a continuación, almacenar su contenido en el almacén de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8287a-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8287a-214">Para asociar una subred a un sitio de red mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8287a-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8287a-215">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8287a-215">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="8287a-216">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="8287a-216">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="8287a-217">Haga clic en el botón de navegación **Subred**.</span><span class="sxs-lookup"><span data-stu-id="8287a-217">Click the **Subnet** navigation button.</span></span>
    
4. <span data-ttu-id="8287a-218">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8287a-218">Click **New**.</span></span>
    
5. <span data-ttu-id="8287a-219">En la página **Nueva subred**, haga clic en **Id. de subred** y escriba la primera dirección en el intervalo de direcciones IP definido mediante la subred que quiere asociar al sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>
    
6. <span data-ttu-id="8287a-220">Haga clic en **Máscara** y escriba la máscara de bits que quiere aplicar a la subred.</span><span class="sxs-lookup"><span data-stu-id="8287a-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>
    
7. <span data-ttu-id="8287a-221">Haga clic en **Id. de sitio de red** y seleccione el identificador de sitio del sitio al que agrega esta subred.</span><span class="sxs-lookup"><span data-stu-id="8287a-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8287a-222">Si todavía no ha creado sitios de red, esta lista estará vacía.</span><span class="sxs-lookup"><span data-stu-id="8287a-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="8287a-223">Para obtener información detallada sobre el procedimiento, vea [creación o modificación de un sitio de red](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="8287a-223">For details about the procedure, see [Create or Modify a Network Site](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="8287a-224">También puede recuperar los identificadores de sitio para la implementación mediante la ejecución del cmdlet **Get-CsNetworkSite** .</span><span class="sxs-lookup"><span data-stu-id="8287a-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="8287a-225">Para obtener información detallada, vea el Skype para la documentación del Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8287a-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>
  
8. <span data-ttu-id="8287a-226">Si lo desea, haga clic en **Descripción** y escriba información adicional para describir esta subred.</span><span class="sxs-lookup"><span data-stu-id="8287a-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>
    
9. <span data-ttu-id="8287a-227">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8287a-227">Click **Commit**.</span></span>
    
<span data-ttu-id="8287a-228">Repita estos pasos para agregar otras subredes a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="8287a-229">Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="8287a-230">Esta alerta no aparecerá más que una vez en un período de ocho horas.</span><span class="sxs-lookup"><span data-stu-id="8287a-230">This alert will not be raised more than once within an 8-hour period.</span></span> 
  
<span data-ttu-id="8287a-231">A continuación se ofrece la información de alerta relevante y un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8287a-231">The relevant alert information and an example are as follows:</span></span>
  
 <span data-ttu-id="8287a-232">**Origen**: servicio de directivas de ancho de banda CS (principal)</span><span class="sxs-lookup"><span data-stu-id="8287a-232">**Source**: CS Bandwidth Policy Service (Core)</span></span> 
  
 <span data-ttu-id="8287a-233">**Número de evento**: 36034</span><span class="sxs-lookup"><span data-stu-id="8287a-233">**Event number**: 36034</span></span>
  
 <span data-ttu-id="8287a-234">**Nivel**: 2</span><span class="sxs-lookup"><span data-stu-id="8287a-234">**Level**: 2</span></span>
  
 <span data-ttu-id="8287a-235">**Descripción**: las subredes de las siguientes direcciones IP: \<lista de direcciones IP\> no son está configurada o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span> 
  
 <span data-ttu-id="8287a-236">**Causa**: las subredes de las correspondientes direcciones IP faltan en las opciones de configuración de la red o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span> 
  
 <span data-ttu-id="8287a-237">**Solución**: agregue subredes correspondientes a la lista de direcciones IP en los parámetros de configuración de red y asocie todas las subredes a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>
  
<span data-ttu-id="8287a-p116">Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8287a-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>
  
1. <span data-ttu-id="8287a-240">Asegúrese de que la dirección IP 10.121.248.226 esté asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 esté asociada a la subred 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="8287a-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>
    
2. <span data-ttu-id="8287a-241">Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 esté asociada a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8287a-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8287a-242">Vea también</span><span class="sxs-lookup"><span data-stu-id="8287a-242">See also</span></span>
<span data-ttu-id="8287a-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="8287a-243"></span></span>


[<span data-ttu-id="8287a-244">Nueva CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8287a-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="8287a-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8287a-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="8287a-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8287a-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="8287a-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8287a-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="8287a-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8287a-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)
  
[<span data-ttu-id="8287a-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8287a-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)
  
[<span data-ttu-id="8287a-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8287a-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)
  
[<span data-ttu-id="8287a-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8287a-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)


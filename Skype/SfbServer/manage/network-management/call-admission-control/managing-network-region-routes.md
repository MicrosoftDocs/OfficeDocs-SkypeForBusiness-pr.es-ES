---
title: Administrar rutas de regiones de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Una ruta de región de red define la ruta entre un par de regiones de red. Cada pareja de regiones de red en la implementación de control de admisión de llamadas requiere una ruta de región de red.
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817499"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="8f138-104">Administrar rutas de regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8f138-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="8f138-105">Una *ruta de región de red* define la ruta entre un par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="8f138-106">Cada pareja de regiones de red en la implementación de control de admisión de llamadas requiere una ruta de región de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="8f138-107">Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.</span><span class="sxs-lookup"><span data-stu-id="8f138-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="8f138-108">Use los procedimientos de este artilce para ver, crear, modificar o eliminar rutas de región de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="8f138-109">Ver información de ruta de la región de red</span><span class="sxs-lookup"><span data-stu-id="8f138-109">View network region route information</span></span> 

<span data-ttu-id="8f138-110">Cada región dentro de una configuración de control de admisión de llamadas (CAC) debe tener alguna forma de tener acceso a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="8f138-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="8f138-111">Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre las regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada pasará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="8f138-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="8f138-112">Use los procedimientos siguientes para ver las rutas de la región de red existente en el panel de control de Skype empresarial Server o en el shell de administración de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="8f138-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="8f138-113">Para ver la información de ruta de la región de red en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8f138-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="8f138-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8f138-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8f138-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8f138-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8f138-116">En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.</span><span class="sxs-lookup"><span data-stu-id="8f138-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="8f138-117">En la página Ruta de la **región** , haga clic en la ruta de la región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="8f138-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="8f138-118">Solo puedes ver una ruta de región a la vez.</span><span class="sxs-lookup"><span data-stu-id="8f138-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="8f138-119">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="8f138-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8f138-120">Ver la información de ruta de la región de red con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f138-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8f138-121">La información de ruta de la región de red se puede ver con Windows PowerShell y el cmdlet Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="8f138-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="8f138-122">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f138-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="8f138-123">Para ver la información de ruta de la región de red</span><span class="sxs-lookup"><span data-stu-id="8f138-123">To view network region route information</span></span>

  - <span data-ttu-id="8f138-124">Para ver información sobre todas las rutas de la región de red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8f138-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="8f138-125">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f138-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="8f138-126">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="8f138-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="8f138-127">Crear o modificar rutas de región de red</span><span class="sxs-lookup"><span data-stu-id="8f138-127">Create or modify network region routes</span></span>

<span data-ttu-id="8f138-128">Cada región dentro de una configuración de control de admisión de llamadas (CAC) debe tener alguna forma de tener acceso a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="8f138-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="8f138-129">Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre las regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada pasará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="8f138-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="8f138-130">Puede usar el panel de control de Skype empresarial Server para configurar las rutas de la región de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="8f138-131">Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una ruta de región de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="8f138-132">Use este tema para crear o modificar una ruta de región de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="8f138-133">Para crear una ruta de región de red</span><span class="sxs-lookup"><span data-stu-id="8f138-133">To create a network region route</span></span>

1.  <span data-ttu-id="8f138-134">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8f138-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8f138-135">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8f138-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8f138-136">En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.</span><span class="sxs-lookup"><span data-stu-id="8f138-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="8f138-137">En la página Ruta de la **región** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8f138-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="8f138-138">En **ruta de nueva región**, escriba un valor en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="8f138-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="8f138-139">Este valor debe ser único dentro de la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8f138-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="8f138-140">En la lista desplegable \*\* \#región de red 1\*\* , seleccione una de las dos regiones que se van a conectar mediante esta ruta.</span><span class="sxs-lookup"><span data-stu-id="8f138-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="8f138-141">En la lista desplegable \*\* \#región de red 2\*\* , seleccione la otra región de esta ruta.</span><span class="sxs-lookup"><span data-stu-id="8f138-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="8f138-142">Esta región debe ser diferente de la región seleccionada para la región \#de red 1.</span><span class="sxs-lookup"><span data-stu-id="8f138-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="8f138-143">Use el cuadro de lista **vínculos de región de red** para agregar vínculos de región a la ruta.</span><span class="sxs-lookup"><span data-stu-id="8f138-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="8f138-144">Haga clic en el botón **Agregar** para mostrar la página de vínculos de la **región** .</span><span class="sxs-lookup"><span data-stu-id="8f138-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="8f138-145">Haga clic en un vínculo de región para agregar a esta ruta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f138-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="8f138-146">Siga haciendo clic en el botón **Agregar** para agregar más vínculos o seleccione un vínculo y haga clic en **quitar** para quitar un vínculo.</span><span class="sxs-lookup"><span data-stu-id="8f138-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="8f138-147">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8f138-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="8f138-148">Para modificar una ruta de región de red</span><span class="sxs-lookup"><span data-stu-id="8f138-148">To modify a network region route</span></span>

1.  <span data-ttu-id="8f138-149">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8f138-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8f138-150">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8f138-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8f138-151">En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.</span><span class="sxs-lookup"><span data-stu-id="8f138-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="8f138-152">En la página Ruta de la **región** , haga clic en la ruta de la región que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8f138-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="8f138-153">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="8f138-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8f138-154">En la **ruta de edición región**, puede modificar las regiones Unidas por esta ruta y los vínculos de región asociados a la ruta.</span><span class="sxs-lookup"><span data-stu-id="8f138-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="8f138-155">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8f138-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="8f138-156">Eliminar las rutas de la región de red existentes</span><span class="sxs-lookup"><span data-stu-id="8f138-156">Delete existing network region routes</span></span>

<span data-ttu-id="8f138-157">Cada región dentro de una configuración de control de admisión de llamadas (CAC) debe tener alguna forma de tener acceso a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="8f138-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="8f138-158">Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre las regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada pasará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="8f138-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="8f138-159">Puede usar el panel de control de Skype empresarial Server para configurar las rutas de la región de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="8f138-160">Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una ruta de región de red.</span><span class="sxs-lookup"><span data-stu-id="8f138-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="8f138-161">Use este tema para eliminar las rutas de la región de red existentes.</span><span class="sxs-lookup"><span data-stu-id="8f138-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="8f138-162">Para eliminar una ruta de región de red</span><span class="sxs-lookup"><span data-stu-id="8f138-162">To delete a network region route</span></span>

1.  <span data-ttu-id="8f138-163">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8f138-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8f138-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8f138-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8f138-165">En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.</span><span class="sxs-lookup"><span data-stu-id="8f138-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="8f138-166">En la página Ruta de la **región** , haga clic en la ruta de la región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="8f138-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="8f138-167">Puede eliminar más de una ruta de región a la vez.</span><span class="sxs-lookup"><span data-stu-id="8f138-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="8f138-168">Para ello, presione CTRL y seleccione varias rutas de región mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="8f138-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="8f138-169">O bien, para seleccionar todas las rutas de la región, haga clic en **seleccionar todo** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="8f138-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="8f138-170">En el menú **Editar** , haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8f138-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="8f138-171">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f138-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="8f138-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f138-172">See Also</span></span>

[<span data-ttu-id="8f138-173">Administrar regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8f138-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="8f138-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8f138-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="8f138-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8f138-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="8f138-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8f138-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="8f138-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8f138-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  

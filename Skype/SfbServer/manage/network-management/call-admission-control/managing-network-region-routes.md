---
title: Administración de rutas de región de red
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Una ruta de región de red define la ruta entre un par de regiones de red. Cada par de regiones de red en su implementación de control de admisión de llamadas requiere una ruta de región de red.
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816440"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="9f816-104">Administrar rutas de regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9f816-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="9f816-105">Una *ruta de región de red* define la ruta entre un par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="9f816-106">Cada par de regiones de red en su implementación de control de admisión de llamadas requiere una ruta de región de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="9f816-107">Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.</span><span class="sxs-lookup"><span data-stu-id="9f816-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="9f816-108">Use los procedimientos de esta técnica para ver, crear, modificar o eliminar rutas de región de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="9f816-109">Ver información de ruta de región de red</span><span class="sxs-lookup"><span data-stu-id="9f816-109">View network region route information</span></span> 

<span data-ttu-id="9f816-110">Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="9f816-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9f816-111">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="9f816-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9f816-112">Use los siguientes procedimientos para ver las rutas de región de red existentes en el Panel de control de Skype Empresarial Server o en el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9f816-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="9f816-113">Para ver la información de ruta de región de red en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9f816-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9f816-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f816-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9f816-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9f816-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9f816-116">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**</span><span class="sxs-lookup"><span data-stu-id="9f816-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9f816-117">En la página **Ruta de región**, haga clic en la ruta regional que desea ver.</span><span class="sxs-lookup"><span data-stu-id="9f816-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="9f816-118">Solo puede ver una ruta regional cada vez.</span><span class="sxs-lookup"><span data-stu-id="9f816-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="9f816-119">En el menú  **Editar**, haga clic en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9f816-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9f816-120">Visualización de la información de ruta de región de red mediante cmdlets Windows PowerShell región</span><span class="sxs-lookup"><span data-stu-id="9f816-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9f816-121">La información de ruta de región de red se puede ver mediante Windows PowerShell y el cmdlet Get-CsNetworkInterRegionRoute región.</span><span class="sxs-lookup"><span data-stu-id="9f816-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="9f816-122">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f816-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="9f816-123">Para ver la información de ruta de región de red</span><span class="sxs-lookup"><span data-stu-id="9f816-123">To view network region route information</span></span>

  - <span data-ttu-id="9f816-124">Para ver información sobre todas las rutas de región de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="9f816-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="9f816-125">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f816-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="9f816-126">Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="9f816-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="9f816-127">Crear o modificar rutas de región de red</span><span class="sxs-lookup"><span data-stu-id="9f816-127">Create or modify network region routes</span></span>

<span data-ttu-id="9f816-128">Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="9f816-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9f816-129">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="9f816-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9f816-130">Puede usar el Panel de control de Skype Empresarial Server para configurar rutas regionales de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="9f816-131">Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una ruta regional de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="9f816-132">Consulte este tema para crear o modificar una ruta regional de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="9f816-133">Para crear una ruta regional de red</span><span class="sxs-lookup"><span data-stu-id="9f816-133">To create a network region route</span></span>

1.  <span data-ttu-id="9f816-134">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f816-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9f816-135">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9f816-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9f816-136">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**</span><span class="sxs-lookup"><span data-stu-id="9f816-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9f816-137">En la página **Ruta regional**, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9f816-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="9f816-138">En **Nueva ruta regional**, escriba un valor en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="9f816-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="9f816-139">Este valor debe ser único en la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9f816-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="9f816-140">En la lista desplegable Región de red **\# 1,** seleccione una de las dos regiones que se conectarán mediante esta ruta.</span><span class="sxs-lookup"><span data-stu-id="9f816-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="9f816-141">En la lista desplegable Región de red **\# 2,** seleccione la otra región para esta ruta.</span><span class="sxs-lookup"><span data-stu-id="9f816-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="9f816-142">Esta región debe ser diferente de la región seleccionada para la región de red \# 1.</span><span class="sxs-lookup"><span data-stu-id="9f816-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="9f816-p107">Use el cuadro de lista **Vínculos de región de red** para agregar vínculos de red a la ruta. Haga clic en el botón **Agregar** para mostrar la página **Vínculo regional**. Haga clic en un vínculo regional para agregarlo a esta ruta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9f816-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="9f816-146">Haga clic otra vez en el botón **Agregar** para añadir más vínculos, o seleccione un vínculo y haga clic en **Eliminar** para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="9f816-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="9f816-147">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9f816-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="9f816-148">Para modificar una ruta regional de red</span><span class="sxs-lookup"><span data-stu-id="9f816-148">To modify a network region route</span></span>

1.  <span data-ttu-id="9f816-149">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f816-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9f816-150">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9f816-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9f816-151">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**</span><span class="sxs-lookup"><span data-stu-id="9f816-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9f816-152">En la página **Ruta regional**, haga clic en la ruta regional que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="9f816-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="9f816-153">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9f816-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9f816-154">En **Editar ruta regional**, puede modificar las regiones agregadas a esta ruta y los vínculos regionales asociados a la misma.</span><span class="sxs-lookup"><span data-stu-id="9f816-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="9f816-155">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9f816-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="9f816-156">Eliminar rutas de región de red existentes</span><span class="sxs-lookup"><span data-stu-id="9f816-156">Delete existing network region routes</span></span>

<span data-ttu-id="9f816-157">Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="9f816-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9f816-158">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="9f816-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9f816-159">Puede usar el Panel de control de Skype Empresarial Server para configurar rutas regionales de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="9f816-160">Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una ruta regional de red.</span><span class="sxs-lookup"><span data-stu-id="9f816-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="9f816-161">Use este tema para eliminar las rutas de región de red existentes.</span><span class="sxs-lookup"><span data-stu-id="9f816-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="9f816-162">Para eliminar una ruta regional de red</span><span class="sxs-lookup"><span data-stu-id="9f816-162">To delete a network region route</span></span>

1.  <span data-ttu-id="9f816-163">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f816-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9f816-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9f816-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9f816-165">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**</span><span class="sxs-lookup"><span data-stu-id="9f816-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9f816-166">En la página **Ruta regional**, haga clic en la ruta regional que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="9f816-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="9f816-p109">Puede eliminar más de una ruta regional en la misma operación. Para hacerlo, presione la tecla CTRL y seleccione varias rutas regionales sin dejar de presionar CTRL. También puede seleccionar todas las rutas regionales haciendo clic en **Seleccionar todo** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9f816-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="9f816-170">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9f816-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="9f816-171">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9f816-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="9f816-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f816-172">See Also</span></span>

[<span data-ttu-id="9f816-173">Administrar regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9f816-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="9f816-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9f816-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="9f816-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9f816-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="9f816-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9f816-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="9f816-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9f816-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  

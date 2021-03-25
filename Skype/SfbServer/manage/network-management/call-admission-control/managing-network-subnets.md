---
title: Administración de subredes de red
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
description: En la mayoría de las implementaciones de Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes. Debido a esto, suele ser mejor configurar subredes desde el Shell de administración de Skype Empresarial Server.
ms.openlocfilehash: ef771ad78f00085374038203e1049790a9179e88
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122444"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="c68c6-104">Administrar subredes de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c68c6-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="c68c6-105">Puede usar el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server para administrar subredes de red.</span><span class="sxs-lookup"><span data-stu-id="c68c6-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="c68c6-106">En la mayoría de las implementaciones de Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="c68c6-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c68c6-107">Debido a esto, suele ser mejor configurar subredes desde el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c68c6-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="c68c6-108">Use las secciones de este artículo para ver información de subred de red o crear, modificar o eliminar subredes de red.</span><span class="sxs-lookup"><span data-stu-id="c68c6-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="c68c6-109">Ver información de subred de red</span><span class="sxs-lookup"><span data-stu-id="c68c6-109">View network subnet information</span></span> 

<span data-ttu-id="c68c6-110">Puede usar el siguiente procedimiento para ver una subred de la red.</span><span class="sxs-lookup"><span data-stu-id="c68c6-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="c68c6-111">Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="c68c6-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="c68c6-112">Para ver una subred de la red</span><span class="sxs-lookup"><span data-stu-id="c68c6-112">To view a network subnet</span></span>

1.  <span data-ttu-id="c68c6-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c68c6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c68c6-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c68c6-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c68c6-115">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c68c6-116">En la página **Subred**, haga clic en la subred que desea ver.</span><span class="sxs-lookup"><span data-stu-id="c68c6-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="c68c6-117">Solo puede ver una subred de cada vez.</span><span class="sxs-lookup"><span data-stu-id="c68c6-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="c68c6-118">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c68c6-119">Ver la información de configuración de subred de red mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="c68c6-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c68c6-120">La información de subred de red se puede ver mediante Windows PowerShell y el cmdlet Get-CsNetworkSubnet red.</span><span class="sxs-lookup"><span data-stu-id="c68c6-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="c68c6-121">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c68c6-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="c68c6-122">Para ver información de subred de red</span><span class="sxs-lookup"><span data-stu-id="c68c6-122">To view network subnet information</span></span>

  - <span data-ttu-id="c68c6-123">Para ver información sobre todas las subredes de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="c68c6-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="c68c6-124">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c68c6-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="c68c6-125">Para más información, vea el tema de ayuda del cmdlet [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="c68c6-125">For more information, see the help topic for the [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="c68c6-126">Crear o modificar subredes de red</span><span class="sxs-lookup"><span data-stu-id="c68c6-126">Create or modify network subnets</span></span> 

<span data-ttu-id="c68c6-127">Cada subred de red debe asociarse a un sitio de red para poder determinar la ubicación geográfica del host que pertenece a esta subred.</span><span class="sxs-lookup"><span data-stu-id="c68c6-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="c68c6-128">Puede usar el Panel de control de Skype Empresarial Server para configurar subredes.</span><span class="sxs-lookup"><span data-stu-id="c68c6-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="c68c6-129">Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="c68c6-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="c68c6-130">En la mayoría de las implementaciones de Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="c68c6-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c68c6-131">Debido a esto, suele ser mejor configurar subredes desde el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c68c6-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c68c6-132">Desde allí, puede llamar a **New-CsNetworkSubnet** junto con Windows PowerShell cmdlet **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="c68c6-133">Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c68c6-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="c68c6-134">Para consultar ejemplos sobre cómo crear subredes a partir de un archivo .csv, consulte [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="c68c6-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="c68c6-135">Para crear una subred de red</span><span class="sxs-lookup"><span data-stu-id="c68c6-135">To create a network subnet</span></span>

1.  <span data-ttu-id="c68c6-136">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c68c6-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c68c6-137">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c68c6-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c68c6-138">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c68c6-139">En la página **Subred**, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="c68c6-p107">En **Nueva subred**, especifique un valor en el campo **ID de subred**. Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe estar ubicada en primer lugar en el intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="c68c6-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="c68c6-142">En el campo **Máscara**, especifique un valor numérico del 1 al 32.</span><span class="sxs-lookup"><span data-stu-id="c68c6-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="c68c6-143">Este valor es la máscara de bits que se aplicará a la subred que se está creando.</span><span class="sxs-lookup"><span data-stu-id="c68c6-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="c68c6-144">En **Id. del sitio de red**, seleccione el sitio al que pertenece la subred.</span><span class="sxs-lookup"><span data-stu-id="c68c6-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="c68c6-145">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta subred más allá de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="c68c6-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="c68c6-146">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="c68c6-147">Para modificar una subred de red</span><span class="sxs-lookup"><span data-stu-id="c68c6-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="c68c6-148">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c68c6-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c68c6-149">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c68c6-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c68c6-150">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c68c6-151">En la página **Subred**, haga clic en la subred que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="c68c6-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="c68c6-152">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c68c6-p108">En la página **Editar subred**, puede modificar la máscara de bits, el sitio de red asociado o la descripción. Si modifica la máscara de bits, recuerde que el ID de subred debe seguir siendo la primera dirección del intervalo de dirección IP definido en la subred.</span><span class="sxs-lookup"><span data-stu-id="c68c6-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="c68c6-155">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="c68c6-156">Eliminar subredes de red</span><span class="sxs-lookup"><span data-stu-id="c68c6-156">Delete network subnets</span></span>

<span data-ttu-id="c68c6-157">Puede usar el procedimiento siguiente para eliminar una subred.</span><span class="sxs-lookup"><span data-stu-id="c68c6-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="c68c6-158">Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="c68c6-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="c68c6-159">En la mayoría de las implementaciones de Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="c68c6-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c68c6-160">Debido a esto, suele ser mejor configurar subredes desde el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c68c6-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c68c6-161">Desde allí, puede llamar a **New-CsNetworkSubnet** junto con Windows PowerShell cmdlet **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="c68c6-162">Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c68c6-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="c68c6-163">Para ver ejemplos de cómo crear subredes desde un archivo .csv, consulte [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="c68c6-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="c68c6-164">Para eliminar una subred de red:</span><span class="sxs-lookup"><span data-stu-id="c68c6-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="c68c6-165">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c68c6-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c68c6-166">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c68c6-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c68c6-167">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c68c6-168">En la página **Subred**, haga clic en la subred que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="c68c6-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="c68c6-p111">Puede eliminar simultáneamente varias subredes. Para ello, mantenga presionada la tecla Ctrl y seleccione varias subredes. O bien, para seleccionar todas las subredes, haga clic en **Seleccionar todo** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="c68c6-172">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c68c6-173">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c68c6-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="c68c6-174">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c68c6-174">See Also</span></span>

[<span data-ttu-id="c68c6-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c68c6-175">New-CsNetworkSubnet</span></span>](/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="c68c6-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c68c6-176">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="c68c6-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c68c6-177">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="c68c6-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c68c6-178">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/Get-CsNetworkSubnet)
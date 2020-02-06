---
title: Administración de subredes de red
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
description: En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817469"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="11ae5-104">Administrar subredes de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="11ae5-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="11ae5-105">Puede usar el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server para administrar subredes de red.</span><span class="sxs-lookup"><span data-stu-id="11ae5-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="11ae5-106">En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="11ae5-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="11ae5-107">Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="11ae5-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="11ae5-108">Use las secciones de este artículo para ver información de subred de red o crear, modificar o eliminar subredes de red.</span><span class="sxs-lookup"><span data-stu-id="11ae5-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="11ae5-109">Ver la información de subred de red</span><span class="sxs-lookup"><span data-stu-id="11ae5-109">View network subnet information</span></span> 

<span data-ttu-id="11ae5-110">Puede usar el procedimiento siguiente para ver una subred de red.</span><span class="sxs-lookup"><span data-stu-id="11ae5-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="11ae5-111">Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="11ae5-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="11ae5-112">Para ver una subred de red</span><span class="sxs-lookup"><span data-stu-id="11ae5-112">To view a network subnet</span></span>

1.  <span data-ttu-id="11ae5-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ae5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11ae5-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="11ae5-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="11ae5-115">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="11ae5-116">En la página **subred** , haga clic en la subred que desea ver.</span><span class="sxs-lookup"><span data-stu-id="11ae5-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="11ae5-117">Solo puedes ver una subred a la vez.</span><span class="sxs-lookup"><span data-stu-id="11ae5-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="11ae5-118">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="11ae5-119">Ver la información de configuración de subred de red con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11ae5-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="11ae5-120">La información de subred de red se puede ver con Windows PowerShell y el cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="11ae5-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="11ae5-121">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ae5-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="11ae5-122">Para ver la información de subred</span><span class="sxs-lookup"><span data-stu-id="11ae5-122">To view network subnet information</span></span>

  - <span data-ttu-id="11ae5-123">Para ver información sobre todas las subredes de la red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="11ae5-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="11ae5-124">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="11ae5-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="11ae5-125">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="11ae5-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="11ae5-126">Crear o modificar subredes de red</span><span class="sxs-lookup"><span data-stu-id="11ae5-126">Create or modify network subnets</span></span> 

<span data-ttu-id="11ae5-127">Una subred de red debe estar asociada a un sitio de red para determinar la ubicación geográfica del host que pertenece a esta subred.</span><span class="sxs-lookup"><span data-stu-id="11ae5-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="11ae5-128">Puede usar el panel de control de Skype empresarial Server para configurar subredes.</span><span class="sxs-lookup"><span data-stu-id="11ae5-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="11ae5-129">Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="11ae5-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="11ae5-130">En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="11ae5-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="11ae5-131">Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="11ae5-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="11ae5-132">Desde allí puedes llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ae5-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="11ae5-133">Al usar estos cmdlets juntos, puede leer la configuración de la subred de un archivo de valores separados por comas (. csv) y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="11ae5-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="11ae5-134">Para obtener ejemplos de cómo crear subredes a partir de un archivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="11ae5-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="11ae5-135">Para crear una subred de red</span><span class="sxs-lookup"><span data-stu-id="11ae5-135">To create a network subnet</span></span>

1.  <span data-ttu-id="11ae5-136">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ae5-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11ae5-137">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="11ae5-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="11ae5-138">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="11ae5-139">En la página **subred** , haga clic en **nueva**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="11ae5-140">En **nueva subred**, escriba un valor en el campo **ID de subred** .</span><span class="sxs-lookup"><span data-stu-id="11ae5-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="11ae5-141">Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe ser la primera dirección del intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="11ae5-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="11ae5-142">En el campo **máscara** , escriba un valor numérico comprendido entre 1 y 32.</span><span class="sxs-lookup"><span data-stu-id="11ae5-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="11ae5-143">Este valor es la máscara de red que se aplicará a la subred que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="11ae5-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="11ae5-144">En **identificador de sitio de red**, seleccione el sitio al que pertenece esta subred.</span><span class="sxs-lookup"><span data-stu-id="11ae5-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="11ae5-145">Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta subred que no puede expresarse solo por el nombre.</span><span class="sxs-lookup"><span data-stu-id="11ae5-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="11ae5-146">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="11ae5-147">Para modificar una subred de red</span><span class="sxs-lookup"><span data-stu-id="11ae5-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="11ae5-148">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ae5-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11ae5-149">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="11ae5-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="11ae5-150">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="11ae5-151">En la página **subred** , haga clic en la subred que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="11ae5-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="11ae5-152">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="11ae5-153">En la página **Editar subred** , puede modificar la máscara de máscara, el sitio de red asociado o la descripción.</span><span class="sxs-lookup"><span data-stu-id="11ae5-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="11ae5-154">Si modifica la máscara de subred, tenga en cuenta que el identificador de subred debe ser la primera dirección del intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="11ae5-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="11ae5-155">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="11ae5-156">Eliminar subredes de red</span><span class="sxs-lookup"><span data-stu-id="11ae5-156">Delete network subnets</span></span>

<span data-ttu-id="11ae5-157">Puede usar el procedimiento siguiente para eliminar una subred.</span><span class="sxs-lookup"><span data-stu-id="11ae5-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="11ae5-158">Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="11ae5-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="11ae5-159">En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="11ae5-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="11ae5-160">Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="11ae5-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="11ae5-161">Desde allí puedes llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ae5-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="11ae5-162">Al usar estos cmdlets juntos, puede leer la configuración de la subred de un archivo de valores separados por comas (. csv) y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="11ae5-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="11ae5-163">Para obtener ejemplos de cómo crear subredes a partir de un archivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="11ae5-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="11ae5-164">Para eliminar una subred de red</span><span class="sxs-lookup"><span data-stu-id="11ae5-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="11ae5-165">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ae5-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11ae5-166">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="11ae5-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="11ae5-167">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="11ae5-168">En la página **subred** , haga clic en la subred que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="11ae5-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="11ae5-169">Puede eliminar más de una subred a la vez.</span><span class="sxs-lookup"><span data-stu-id="11ae5-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="11ae5-170">Para ello, presione CTRL y seleccione varias subredes mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="11ae5-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="11ae5-171">O bien, para seleccionar todas las subredes, haga clic en **seleccionar todo** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="11ae5-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="11ae5-172">En el menú **Editar** , haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="11ae5-173">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11ae5-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="11ae5-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="11ae5-174">See Also</span></span>

[<span data-ttu-id="11ae5-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="11ae5-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="11ae5-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="11ae5-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="11ae5-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="11ae5-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="11ae5-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="11ae5-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  

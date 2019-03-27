---
title: Administración de subredes de red
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes. Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial.
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899753"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="8219c-104">Administrar subredes de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8219c-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="8219c-105">Puede usar cualquiera el Skype para Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial para administrar subredes de red.</span><span class="sxs-lookup"><span data-stu-id="8219c-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="8219c-106">En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="8219c-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="8219c-107">Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8219c-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="8219c-108">Use las secciones de este artículo para ver la información de la subred de red o crear, modificar o eliminar las subredes de la red.</span><span class="sxs-lookup"><span data-stu-id="8219c-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="8219c-109">Ver información de subred de red</span><span class="sxs-lookup"><span data-stu-id="8219c-109">View network subnet information</span></span> 

<span data-ttu-id="8219c-110">Puede usar el siguiente procedimiento para ver una subred de red.</span><span class="sxs-lookup"><span data-stu-id="8219c-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="8219c-111">De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="8219c-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="8219c-112">Para ver una subred de red</span><span class="sxs-lookup"><span data-stu-id="8219c-112">To view a network subnet</span></span>

1.  <span data-ttu-id="8219c-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8219c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8219c-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8219c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8219c-115">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.</span><span class="sxs-lookup"><span data-stu-id="8219c-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="8219c-116">En la página **subred** , haga clic en la subred que desea ver.</span><span class="sxs-lookup"><span data-stu-id="8219c-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="8219c-117">Sólo se puede ver una subred a la vez.</span><span class="sxs-lookup"><span data-stu-id="8219c-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="8219c-118">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="8219c-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8219c-119">Ver la información de configuración de subred de red mediante cmdlets de uso de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8219c-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8219c-120">Información de subred de red puede verse mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="8219c-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="8219c-121">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8219c-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="8219c-122">Para ver la información de la subred de red</span><span class="sxs-lookup"><span data-stu-id="8219c-122">To view network subnet information</span></span>

  - <span data-ttu-id="8219c-123">Para ver información acerca de todas las subredes de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8219c-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="8219c-124">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8219c-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="8219c-125">Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="8219c-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="8219c-126">Crear o modificar subredes de red</span><span class="sxs-lookup"><span data-stu-id="8219c-126">Create or modify network subnets</span></span> 

<span data-ttu-id="8219c-127">Una subred de red debe asociarse con un sitio de red con el fin de determinar la ubicación geográfica del host que pertenecen a esta subred.</span><span class="sxs-lookup"><span data-stu-id="8219c-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="8219c-128">Puede usar el Skype para el Panel de Control de servidor empresarial para configurar subredes.</span><span class="sxs-lookup"><span data-stu-id="8219c-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="8219c-129">De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="8219c-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="8219c-130">En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="8219c-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="8219c-131">Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8219c-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8219c-132">Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8219c-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="8219c-133">Mediante el uso de estos cmdlets juntos, puede leer en configuración de subred desde un archivo de valores separados por comas (.csv) y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8219c-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="8219c-134">Para obtener ejemplos de cómo crear subredes desde un archivo .csv, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="8219c-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="8219c-135">Para crear una subred de red</span><span class="sxs-lookup"><span data-stu-id="8219c-135">To create a network subnet</span></span>

1.  <span data-ttu-id="8219c-136">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8219c-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8219c-137">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8219c-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8219c-138">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.</span><span class="sxs-lookup"><span data-stu-id="8219c-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="8219c-139">En la página **subred** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8219c-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="8219c-140">En la **Nueva subred**, escriba un valor en el campo **ID de subred** .</span><span class="sxs-lookup"><span data-stu-id="8219c-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="8219c-141">Esto debe ser una dirección IP (por ejemplo, 174.11.12.0), y debe ser la primera dirección en el intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="8219c-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="8219c-142">En el campo **máscara** , escriba un valor numérico comprendido entre 1 y 32.</span><span class="sxs-lookup"><span data-stu-id="8219c-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="8219c-143">Este valor es la máscara de bits que se va a aplicar a la subred que se está creando.</span><span class="sxs-lookup"><span data-stu-id="8219c-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="8219c-144">En el **identificador de sitio de red**, seleccione el sitio al que pertenece esta subred.</span><span class="sxs-lookup"><span data-stu-id="8219c-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="8219c-145">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de esta subred que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="8219c-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="8219c-146">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8219c-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="8219c-147">Para modificar una subred de red</span><span class="sxs-lookup"><span data-stu-id="8219c-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="8219c-148">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8219c-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8219c-149">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8219c-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8219c-150">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.</span><span class="sxs-lookup"><span data-stu-id="8219c-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="8219c-151">En la página **subred** , haga clic en la subred que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8219c-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="8219c-152">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="8219c-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8219c-153">En la página **Editar subred** , puede modificar la máscara de bits, el sitio de red asociados o la descripción.</span><span class="sxs-lookup"><span data-stu-id="8219c-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="8219c-154">Si modifica la máscara de bits, tenga en cuenta que el ID de subred aún debe ser la primera dirección en el intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="8219c-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="8219c-155">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8219c-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="8219c-156">Eliminación de subredes de red</span><span class="sxs-lookup"><span data-stu-id="8219c-156">Delete network subnets</span></span>

<span data-ttu-id="8219c-157">Puede usar el siguiente procedimiento para eliminar una subred.</span><span class="sxs-lookup"><span data-stu-id="8219c-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="8219c-158">De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="8219c-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="8219c-159">En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="8219c-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="8219c-160">Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8219c-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8219c-161">Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8219c-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="8219c-162">Mediante el uso de estos cmdlets juntos, puede leer en configuración de subred desde un archivo de valores separados por comas (.csv) y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8219c-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="8219c-163">Para obtener ejemplos de cómo crear subredes desde un archivo .csv, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="8219c-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="8219c-164">Para eliminar una subred de red</span><span class="sxs-lookup"><span data-stu-id="8219c-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="8219c-165">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8219c-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8219c-166">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8219c-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8219c-167">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.</span><span class="sxs-lookup"><span data-stu-id="8219c-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="8219c-168">En la página **subred** , haga clic en la subred que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="8219c-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="8219c-169">Puede eliminar más de una subred a la vez.</span><span class="sxs-lookup"><span data-stu-id="8219c-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="8219c-170">Para ello, presione la tecla CTRL y seleccione varias subredes mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="8219c-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="8219c-171">O bien, para seleccionar todas las subredes, haga clic en **Seleccionar todo** en el menú **Edición** .</span><span class="sxs-lookup"><span data-stu-id="8219c-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="8219c-172">En el menú **Edición** , haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8219c-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="8219c-173">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8219c-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="8219c-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8219c-174">See Also</span></span>

[<span data-ttu-id="8219c-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8219c-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="8219c-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8219c-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="8219c-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8219c-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="8219c-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8219c-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  

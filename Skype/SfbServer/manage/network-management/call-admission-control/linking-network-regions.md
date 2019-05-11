---
title: Vinculación de regiones de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC). '
ms.openlocfilehash: 30d4a020826b24c3615ce059809645481466efc3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888355"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="163ca-103">Vincular regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="163ca-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="163ca-104">Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="163ca-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="163ca-105">Use las secciones de este artículo para ver la información del vínculo de región newtwork o configurar o eliminar vínculos de región de red.</span><span class="sxs-lookup"><span data-stu-id="163ca-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="163ca-106">Ver información de vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="163ca-106">View network region link information</span></span> 

<span data-ttu-id="163ca-107">Puede ver los vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="163ca-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="163ca-108">Las regiones dentro de una red están vinculadas a través de la conectividad de área extensa (WAN) de la red.</span><span class="sxs-lookup"><span data-stu-id="163ca-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="163ca-109">Puede usar el Skype para el Panel de Control de servidor empresarial para ver un vínculo existente entre dos regiones de red.</span><span class="sxs-lookup"><span data-stu-id="163ca-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="163ca-110">Para ver un vínculo de región de red en Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="163ca-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="163ca-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="163ca-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="163ca-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="163ca-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="163ca-113">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="163ca-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="163ca-114">En la página **Vínculo de región** , haga clic en el vínculo de región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="163ca-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="163ca-115">Sólo se puede ver información acerca de un vínculo de región a la vez.</span><span class="sxs-lookup"><span data-stu-id="163ca-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="163ca-116">En el menú **Editar** , seleccione **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="163ca-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="163ca-117">Ver la información de vínculo de región de red mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="163ca-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="163ca-118">Puede ver los vínculos de región de red mediante el uso de Windows PowerShell y el cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="163ca-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="163ca-119">Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="163ca-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="163ca-120">Para ver la información del vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="163ca-120">To view network region link information</span></span>

  - <span data-ttu-id="163ca-121">Para ver información acerca de todos los vínculos de región de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="163ca-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="163ca-122">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="163ca-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="163ca-123">Para obtener información detallada, vea [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="163ca-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="163ca-124">Configurar vínculos de región de red</span><span class="sxs-lookup"><span data-stu-id="163ca-124">Configure network region links</span></span> 

<span data-ttu-id="163ca-125">Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="163ca-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="163ca-126">Las regiones dentro de una red están vinculadas a través de la conectividad de área extensa (WAN) de la red.</span><span class="sxs-lookup"><span data-stu-id="163ca-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="163ca-127">Puede usar el Skype para el Panel de Control de servidor empresarial para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en las conexiones de audio y vídeos entre estas regiones.</span><span class="sxs-lookup"><span data-stu-id="163ca-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="163ca-128">Para crear un vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="163ca-128">To create a network region link</span></span>

1.  <span data-ttu-id="163ca-129">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="163ca-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="163ca-130">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="163ca-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="163ca-131">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="163ca-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="163ca-132">En la página **Vínculo de región** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="163ca-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="163ca-133">En el **Vínculo de región de nuevo**, escriba un valor en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="163ca-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="163ca-134">Este valor debe ser único dentro de su Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="163ca-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="163ca-135">Desde el **región de red \#1** lista desplegable, seleccione una de las dos regiones que se vincularán.</span><span class="sxs-lookup"><span data-stu-id="163ca-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="163ca-136">Desde el **región de red \#2** lista desplegable, seleccione la región de otra que se vincularán.</span><span class="sxs-lookup"><span data-stu-id="163ca-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="163ca-137">Esta región debe ser diferente de la región seleccionada para la región de red \#1.</span><span class="sxs-lookup"><span data-stu-id="163ca-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="163ca-138">(Opcional) Si desea poner limitaciones de ancho de banda en llamadas de audio o vídeos entre estas regiones, seleccione un perfil de directiva de ancho de banda de la lista desplegable **Directiva de ancho de banda** .</span><span class="sxs-lookup"><span data-stu-id="163ca-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="163ca-139">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="163ca-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="163ca-140">Para modificar un vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="163ca-140">To modify a network region link</span></span>

1.  <span data-ttu-id="163ca-141">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="163ca-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="163ca-142">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="163ca-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="163ca-143">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="163ca-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="163ca-144">En la página **Vínculo de región** , haga clic en el vínculo de región que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="163ca-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="163ca-145">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="163ca-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="163ca-146">En **Editar vínculo de región**, puede modificar las regiones que están vinculadas o el perfil de directiva de ancho de banda para este vínculo.</span><span class="sxs-lookup"><span data-stu-id="163ca-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="163ca-147">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="163ca-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="163ca-148">Eliminar vínculos de región de red</span><span class="sxs-lookup"><span data-stu-id="163ca-148">Delete network region links</span></span>

<span data-ttu-id="163ca-149">Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="163ca-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="163ca-150">Las regiones dentro de una red están vinculadas a través de la conectividad de área extensa (WAN) de la red.</span><span class="sxs-lookup"><span data-stu-id="163ca-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="163ca-151">Puede usar el Skype para el Panel de Control de servidor empresarial para eliminar un vínculo entre dos regiones de red existente.</span><span class="sxs-lookup"><span data-stu-id="163ca-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="163ca-152">Para eliminar un vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="163ca-152">To delete a network region link</span></span>

1.  <span data-ttu-id="163ca-153">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="163ca-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="163ca-154">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="163ca-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="163ca-155">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="163ca-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="163ca-156">En la página **Vínculo de región** , haga clic en el vínculo de región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="163ca-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="163ca-157">Puede eliminar más de un vínculo de región a la vez.</span><span class="sxs-lookup"><span data-stu-id="163ca-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="163ca-158">Para ello, presione la tecla CTRL y seleccione varios vínculos de región mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="163ca-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="163ca-159">O bien, para seleccionar todos los vínculos de región, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Edición</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="163ca-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="163ca-160">En el menú **Editar** , seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="163ca-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="163ca-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="163ca-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="163ca-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="163ca-162">See Also</span></span>

[<span data-ttu-id="163ca-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="163ca-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="163ca-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="163ca-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="163ca-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="163ca-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="163ca-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="163ca-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  

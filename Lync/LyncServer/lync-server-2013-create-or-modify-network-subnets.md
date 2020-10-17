---
title: 'Lync Server 2013: crear o modificar subredes de red'
description: 'Lync Server 2013: crear o modificar subredes de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546926"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="1eff5-103">Crear o modificar subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eff5-103">Create or modify network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eff5-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1eff5-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1eff5-105">Cada subred de red debe asociarse a un sitio de red para poder determinar la ubicación geográfica del host que pertenece a esta subred.</span><span class="sxs-lookup"><span data-stu-id="1eff5-105">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="1eff5-106">Puede usar el panel de control de Lync Server para configurar subredes.</span><span class="sxs-lookup"><span data-stu-id="1eff5-106">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="1eff5-107">Desde el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="1eff5-107">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="1eff5-108">Para obtener más información sobre cómo eliminar subredes de red, consulte [eliminar subredes de red en Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="1eff5-108">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="1eff5-109">En la mayoría de las implementaciones de Microsoft Lync Server 2013 donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="1eff5-109">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="1eff5-110">Por ello, suele ser mejor configurar subredes desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1eff5-110">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="1eff5-111">Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1eff5-111">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="1eff5-112">Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="1eff5-112">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="1eff5-113">Para consultar ejemplos sobre cómo crear subredes a partir de un archivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="1eff5-113">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="1eff5-114">Para crear una subred de red</span><span class="sxs-lookup"><span data-stu-id="1eff5-114">To create a network subnet</span></span>

1.  <span data-ttu-id="1eff5-115">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1eff5-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1eff5-116">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1eff5-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1eff5-117">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1eff5-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1eff5-118">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Subred**.</span><span class="sxs-lookup"><span data-stu-id="1eff5-118">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="1eff5-119">En la página **Subred**, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="1eff5-119">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="1eff5-p104">En **Nueva subred**, especifique un valor en el campo **ID de subred**. Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe estar ubicada en primer lugar en el intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="1eff5-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="1eff5-122">En el campo **Máscara**, especifique un valor numérico del 1 al 32.</span><span class="sxs-lookup"><span data-stu-id="1eff5-122">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1eff5-123">Este valor es la máscara de bits que se aplicará a la subred que se está creando.</span><span class="sxs-lookup"><span data-stu-id="1eff5-123">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="1eff5-124">En **Id. del sitio de red**, seleccione el sitio al que pertenece la subred.</span><span class="sxs-lookup"><span data-stu-id="1eff5-124">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="1eff5-125">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta subred más allá de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="1eff5-125">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="1eff5-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1eff5-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="1eff5-127">Para modificar una subred de red</span><span class="sxs-lookup"><span data-stu-id="1eff5-127">To modify a network subnet</span></span>

1.  <span data-ttu-id="1eff5-128">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1eff5-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1eff5-129">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1eff5-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1eff5-130">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1eff5-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1eff5-131">En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Subred**.</span><span class="sxs-lookup"><span data-stu-id="1eff5-131">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="1eff5-132">En la página **Subred**, haga clic en la subred que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="1eff5-132">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="1eff5-133">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1eff5-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1eff5-p106">En la página **Editar subred**, puede modificar la máscara de bits, el sitio de red asociado o la descripción. Si modifica la máscara de bits, recuerde que el ID de subred debe seguir siendo la primera dirección del intervalo de dirección IP definido en la subred.</span><span class="sxs-lookup"><span data-stu-id="1eff5-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="1eff5-136">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1eff5-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1eff5-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1eff5-137">See Also</span></span>


[<span data-ttu-id="1eff5-138">Eliminación de subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eff5-138">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="1eff5-139">Acerca de las regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eff5-139">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="1eff5-140">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1eff5-140">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="1eff5-141">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1eff5-141">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="1eff5-142">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1eff5-142">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="1eff5-143">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1eff5-143">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


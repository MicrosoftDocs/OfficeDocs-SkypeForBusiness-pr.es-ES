---
title: 'Lync Server 2013: crear o modificar subredes de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="50b3c-102">Crear o modificar subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50b3c-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50b3c-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="50b3c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="50b3c-104">Una subred de red debe estar asociada a un sitio de red para determinar la ubicación geográfica del host que pertenece a esta subred.</span><span class="sxs-lookup"><span data-stu-id="50b3c-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="50b3c-105">Puede usar el panel de control de Lync Server para configurar subredes.</span><span class="sxs-lookup"><span data-stu-id="50b3c-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="50b3c-106">En el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="50b3c-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="50b3c-107">Para más información sobre cómo eliminar subredes de red, vea [eliminar subredes de red en Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="50b3c-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="50b3c-108">En la mayoría de las implementaciones de Microsoft Lync Server 2013 donde se implementa control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="50b3c-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="50b3c-109">Por ello, suele ser mejor configurar las subredes desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50b3c-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="50b3c-110">Desde allí puedes llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50b3c-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="50b3c-111">Al usar estos cmdlets juntos, puede leer la configuración de la subred de un archivo de valores separados por comas (. csv) y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="50b3c-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="50b3c-112">Para obtener ejemplos de cómo crear subredes a partir de un archivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="50b3c-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="50b3c-113">Para crear una subred de red</span><span class="sxs-lookup"><span data-stu-id="50b3c-113">To create a network subnet</span></span>

1.  <span data-ttu-id="50b3c-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="50b3c-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50b3c-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50b3c-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50b3c-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="50b3c-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50b3c-117">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **subred**.</span><span class="sxs-lookup"><span data-stu-id="50b3c-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="50b3c-118">En la página **subred** , haga clic en **nueva**.</span><span class="sxs-lookup"><span data-stu-id="50b3c-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="50b3c-119">En **nueva subred**, escriba un valor en el campo **ID de subred** .</span><span class="sxs-lookup"><span data-stu-id="50b3c-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="50b3c-120">Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe ser la primera dirección del intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="50b3c-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="50b3c-121">En el campo **máscara** , escriba un valor numérico comprendido entre 1 y 32.</span><span class="sxs-lookup"><span data-stu-id="50b3c-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50b3c-122">Este valor es la máscara de red que se aplicará a la subred que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="50b3c-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="50b3c-123">En **identificador de sitio de red**, seleccione el sitio al que pertenece esta subred.</span><span class="sxs-lookup"><span data-stu-id="50b3c-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="50b3c-124">Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta subred que no puede expresarse solo por el nombre.</span><span class="sxs-lookup"><span data-stu-id="50b3c-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="50b3c-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="50b3c-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="50b3c-126">Para modificar una subred de red</span><span class="sxs-lookup"><span data-stu-id="50b3c-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="50b3c-127">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="50b3c-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50b3c-128">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50b3c-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50b3c-129">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="50b3c-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50b3c-130">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **subred**.</span><span class="sxs-lookup"><span data-stu-id="50b3c-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="50b3c-131">En la página **subred** , haga clic en la subred que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="50b3c-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="50b3c-132">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="50b3c-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="50b3c-133">En la página **Editar subred** , puede modificar la máscara de máscara, el sitio de red asociado o la descripción.</span><span class="sxs-lookup"><span data-stu-id="50b3c-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="50b3c-134">Si modifica la máscara de subred, tenga en cuenta que el identificador de subred debe ser la primera dirección del intervalo de direcciones IP definido por la subred.</span><span class="sxs-lookup"><span data-stu-id="50b3c-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="50b3c-135">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="50b3c-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50b3c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="50b3c-136">See Also</span></span>


[<span data-ttu-id="50b3c-137">Eliminar subredes de la red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50b3c-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="50b3c-138">Acerca de las regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50b3c-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="50b3c-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50b3c-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="50b3c-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50b3c-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="50b3c-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50b3c-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="50b3c-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50b3c-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


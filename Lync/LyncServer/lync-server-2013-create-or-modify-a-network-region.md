---
title: 'Lync Server 2013: crear o modificar una región de red'
description: 'Lync Server 2013: crear o modificar una región de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a149a668f64df804d2631243d9bb63401bd8a284
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562236"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="6712c-103">Crear o modificar una región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6712c-103">Create or modify a network region in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6712c-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6712c-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6712c-105">Las \*regiones de red \* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="6712c-105">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="6712c-106">Use los siguientes procedimientos para crear o modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6712c-106">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="6712c-107">Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario que cree nuevas regiones de red; otras características avanzadas de Enterprise Voice usarán las mismas regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6712c-107">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="6712c-108">Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="6712c-108">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="6712c-109">Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="6712c-109">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="6712c-110">Para obtener más información, consulte [Configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="6712c-110">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6712c-111">Cualquier requisito específico de la característica para las definiciones de región de red está documentado en los temas sobre implementación para la característica.</span><span class="sxs-lookup"><span data-stu-id="6712c-111">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="6712c-112">Para obtener información detallada sobre cómo trabajar con regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6712c-112">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="6712c-113">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6712c-113">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="6712c-114">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6712c-114">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="6712c-115">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6712c-115">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="6712c-116">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6712c-116">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="6712c-117">Crear una región de red</span><span class="sxs-lookup"><span data-stu-id="6712c-117">Create a Network Region</span></span>

<span data-ttu-id="6712c-118">Cree una región de red que sirva para el control de admisión de llamadas, E9-1-1 o el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="6712c-118">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="6712c-119">Para crear una región de red mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6712c-119">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="6712c-120">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6712c-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6712c-121">Ejecute el cmdlet New-CsNetworkRegion para crear regiones de red:</span><span class="sxs-lookup"><span data-stu-id="6712c-121">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="6712c-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6712c-122">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="6712c-123">En este ejemplo, ha creado una región de red denominada "NorthAmerica" que está asociada a un sitio central con el identificador de sitio CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="6712c-123">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="6712c-124">Para terminar de crear regiones de red para la topología, repita el paso 2 con la configuración de cada región de red.</span><span class="sxs-lookup"><span data-stu-id="6712c-124">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="6712c-125">Para crear una región de red mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6712c-125">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6712c-126">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6712c-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6712c-127">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6712c-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="6712c-128">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="6712c-128">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="6712c-129">Haga clic en **región**.</span><span class="sxs-lookup"><span data-stu-id="6712c-129">Click **Region**.</span></span>

4.  <span data-ttu-id="6712c-130">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6712c-130">Click **New**.</span></span>

5.  <span data-ttu-id="6712c-131">En la página **región nueva** , haga clic en **nombre** y, a continuación, escriba un nombre para la región de red.</span><span class="sxs-lookup"><span data-stu-id="6712c-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="6712c-132">Haga clic en **sitio central**y, a continuación, haga clic en un sitio central de la lista.</span><span class="sxs-lookup"><span data-stu-id="6712c-132">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="6712c-133">Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.</span><span class="sxs-lookup"><span data-stu-id="6712c-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="6712c-134">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6712c-134">Click **Commit**.</span></span>

9.  <span data-ttu-id="6712c-135">Para terminar de crear regiones de red para la topología, repita los pasos 4 a 8 con la configuración para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="6712c-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="6712c-136">Modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="6712c-136">Modify a Network Region</span></span>

<span data-ttu-id="6712c-137">Modifique la configuración de una región de red existente para dar cabida a los cambios en la información de región básica o los cambios necesarios para una nueva característica.</span><span class="sxs-lookup"><span data-stu-id="6712c-137">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="6712c-138">Para modificar una región de red mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6712c-138">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="6712c-139">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6712c-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6712c-140">Ejecute el cmdlet Set-CsNetworkRegion para modificar una región de red existente:</span><span class="sxs-lookup"><span data-stu-id="6712c-140">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="6712c-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6712c-141">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="6712c-142">En este ejemplo, ha modificado una región de red existente denominada "Norteamérica" (creada con los procedimientos anteriormente en este tema) al cambiar la descripción.</span><span class="sxs-lookup"><span data-stu-id="6712c-142">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="6712c-143">Si existía una descripción para la región "NorthAmerica", este comando la sobrescribe con este valor; Si no se ha definido ninguna descripción, este comando la establece.</span><span class="sxs-lookup"><span data-stu-id="6712c-143">If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="6712c-144">Para modificar otras regiones de red, repita el paso 2 con opciones de configuración para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="6712c-144">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="6712c-145">Para modificar una región de red mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6712c-145">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6712c-146">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6712c-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6712c-147">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6712c-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="6712c-148">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="6712c-148">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="6712c-149">Haga clic en el botón de navegación **región** .</span><span class="sxs-lookup"><span data-stu-id="6712c-149">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="6712c-150">En la tabla, haga clic en la región de red que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="6712c-150">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="6712c-151">Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.</span><span class="sxs-lookup"><span data-stu-id="6712c-151">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="6712c-152">En la página **Editar región** , cambie los valores de la configuración de esta región de red según corresponda.</span><span class="sxs-lookup"><span data-stu-id="6712c-152">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="6712c-153">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6712c-153">Click **Commit**.</span></span>

8.  <span data-ttu-id="6712c-154">Para terminar de modificar regiones de red, repita los pasos 4 a 7 con la configuración para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="6712c-154">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


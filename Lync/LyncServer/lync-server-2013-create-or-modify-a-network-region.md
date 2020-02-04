---
title: 'Lync Server 2013: crear o modificar una región de red'
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
ms.openlocfilehash: 75011a28567da8a6e386c42f272ee1510b8ceddc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="828e3-102">Crear o modificar una región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="828e3-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="828e3-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="828e3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="828e3-104">Las *regiones de red* son los concentradores de red o las redes troncales que se usan en la configuración de control de admisión de llamadas, E9-1-1 y omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="828e3-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="828e3-105">Use los procedimientos siguientes para crear o modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="828e3-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="828e3-106">Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario crear regiones de red nuevas; otras características avanzadas de telefonía empresarial usarán esas mismas regiones de red.</span><span class="sxs-lookup"><span data-stu-id="828e3-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="828e3-107">Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="828e3-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="828e3-108">Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="828e3-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="828e3-109">Para obtener más información, vea [configurar regiones de red para CAC en Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="828e3-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="828e3-110">En los temas de implementación de la característica se documentan los requisitos específicos de las características de las definiciones de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="828e3-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="828e3-111">Para obtener más información sobre cómo trabajar con regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="828e3-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="828e3-112">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="828e3-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="828e3-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="828e3-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="828e3-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="828e3-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="828e3-115">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="828e3-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="828e3-116">Crear una región de red</span><span class="sxs-lookup"><span data-stu-id="828e3-116">Create a Network Region</span></span>

<span data-ttu-id="828e3-117">Cree una región de red que pueda usar el control de admisión de llamadas, el E9-1-1 o la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="828e3-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="828e3-118">Para crear una región de red con el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="828e3-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="828e3-119">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="828e3-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="828e3-120">Ejecute el cmdlet New-CsNetworkRegion para crear regiones de red:</span><span class="sxs-lookup"><span data-stu-id="828e3-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="828e3-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="828e3-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="828e3-122">En este ejemplo, ha creado una región de red denominada “NorthAmerica” que está asociada a un sitio central con identificador de sitio CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="828e3-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="828e3-123">Para terminar de crear regiones de red para la topología, repita el paso 2 con parámetros para cada región de red.</span><span class="sxs-lookup"><span data-stu-id="828e3-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="828e3-124">Para crear una región de red con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="828e3-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="828e3-125">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="828e3-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="828e3-126">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="828e3-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="828e3-127">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="828e3-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="828e3-128">Haga clic en **Región**</span><span class="sxs-lookup"><span data-stu-id="828e3-128">Click **Region**.</span></span>

4.  <span data-ttu-id="828e3-129">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="828e3-129">Click **New**.</span></span>

5.  <span data-ttu-id="828e3-130">En la página **Región nueva**, haga clic en **Nombre** y escriba un nombre para la región de red.</span><span class="sxs-lookup"><span data-stu-id="828e3-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="828e3-131">Haga clic en **Sitio central** y, a continuación, haga clic en un sitio central de la lista.</span><span class="sxs-lookup"><span data-stu-id="828e3-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="828e3-132">Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.</span><span class="sxs-lookup"><span data-stu-id="828e3-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="828e3-133">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="828e3-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="828e3-134">Para terminar de crear regiones de red para la topología, repita los pasos del 4 al 8 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="828e3-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="828e3-135">Modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="828e3-135">Modify a Network Region</span></span>

<span data-ttu-id="828e3-136">Modificar la configuración de una región de red existente para acomodar los cambios en la información de la región básica o los cambios necesarios para una nueva característica.</span><span class="sxs-lookup"><span data-stu-id="828e3-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="828e3-137">Para modificar una región de red mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="828e3-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="828e3-138">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="828e3-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="828e3-139">Ejecute el cmdlet Set-CsNetworkRegion para modificar una región de red existente:</span><span class="sxs-lookup"><span data-stu-id="828e3-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="828e3-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="828e3-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="828e3-p103">En este ejemplo, ha modificado una región de red existente denominada “NorthAmerica” (creada mediante los procedimientos descritos anteriormente en este tema) cambiando la descripción. Si ya existía una descripción para la región “NorthAmerica”, este comando la sobrescribirá con este valor; si no se había definido ninguna descripción, el comando la definirá.</span><span class="sxs-lookup"><span data-stu-id="828e3-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="828e3-143">Para modificar otras regiones de red, repita el paso 2 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="828e3-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="828e3-144">Para modificar una región de red con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="828e3-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="828e3-145">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="828e3-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="828e3-146">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="828e3-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="828e3-147">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="828e3-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="828e3-148">Haga clic en el botón de navegación **Región**.</span><span class="sxs-lookup"><span data-stu-id="828e3-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="828e3-149">En la tabla, haga clic en la región de red que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="828e3-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="828e3-150">Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.</span><span class="sxs-lookup"><span data-stu-id="828e3-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="828e3-151">En la página **Editar región**, modifique los valores de la configuración de esta región de red, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="828e3-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="828e3-152">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="828e3-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="828e3-153">Para terminar de modificar regiones de red, repita los pasos del 4 al 7 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="828e3-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


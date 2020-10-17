---
title: Lync Server 2013; Crear rutas entre regiones de red
description: Lync Server 2013; Crear rutas entre regiones de red.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 44c8c62a86f7cfb6ca5b1148dc097c1d7786ad29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546056"
---
# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="c65e4-103">Crear rutas entre regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c65e4-103">Create network interregion routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c65e4-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c65e4-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c65e4-p101">Una *ruta entre regiones de red* define la ruta entre un par de regiones de red. Cada par de regiones de red de la implementación del servicio de control de admisión de llamadas precisa una ruta entre regiones de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.</span><span class="sxs-lookup"><span data-stu-id="c65e4-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="c65e4-108">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones, una ruta entre regiones determina la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="c65e4-108">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="c65e4-109">Para obtener información detallada sobre cómo trabajar con rutas entre regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c65e4-109">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="c65e4-110">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c65e4-110">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="c65e4-111">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c65e4-111">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="c65e4-112">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c65e4-112">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="c65e4-113">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c65e4-113">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="c65e4-114">En el ejemplo de topología, hay que definir rutas entre regiones de red para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC.</span><span class="sxs-lookup"><span data-stu-id="c65e4-114">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="c65e4-115">Para crear rutas entre regiones de red mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c65e4-115">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="c65e4-116">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c65e4-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c65e4-117">Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias.</span><span class="sxs-lookup"><span data-stu-id="c65e4-117">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="c65e4-118">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c65e4-118">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="c65e4-119">La ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red debido a que no hay un vínculo de región de red directo entre ellas.</span><span class="sxs-lookup"><span data-stu-id="c65e4-119">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="c65e4-120">Para crear rutas entre regiones de red mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c65e4-120">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c65e4-121">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c65e4-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c65e4-122">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c65e4-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c65e4-123">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="c65e4-123">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="c65e4-124">Haga clic en el botón de navegación **Ruta regional**.</span><span class="sxs-lookup"><span data-stu-id="c65e4-124">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="c65e4-125">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c65e4-125">Click **New**.</span></span>

5.  <span data-ttu-id="c65e4-126">En la página **Nueva ruta regional**, haga clic en **Nombre** y escriba un nombre para la ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="c65e4-126">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="c65e4-127">Haga clic en **región de red \# 1**y, a continuación, haga clic en una región de red de la lista que desee enrutar a la región de red \# 2.</span><span class="sxs-lookup"><span data-stu-id="c65e4-127">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="c65e4-128">Haga clic en **región de red \# 2**y, a continuación, haga clic en una región de red de la lista que desee enrutar a la región de red \# 1.</span><span class="sxs-lookup"><span data-stu-id="c65e4-128">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="c65e4-129">Haga clic en **Agregar** junto al campo **Vínculos de región de red** y luego agregue un vínculo de región de red que se usará en la ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="c65e4-129">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="c65e4-p104">Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta. Por ejemplo, la ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red, debido a que no hay un vínculo de región de red directo entre ellas.</span><span class="sxs-lookup"><span data-stu-id="c65e4-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="c65e4-132">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c65e4-132">Click **Commit**.</span></span>

10. <span data-ttu-id="c65e4-133">Para finalizar la creación de rutas entre regiones de red de la topología, repita los pasos del 4 al 9 con la configuración para otras rutas entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="c65e4-133">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


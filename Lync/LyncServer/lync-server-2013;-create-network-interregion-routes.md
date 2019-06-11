---
title: Lync Server 2013; Crear rutas interregional de red
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: be1c28450708660e2322144802c81d5458ded6da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "34821820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="a9051-102">Crear rutas interregional de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9051-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9051-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a9051-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a9051-104">Una *ruta interregión de red* define la ruta entre un par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="a9051-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="a9051-105">Cada pareja de regiones de red en la implementación de control de admisión de llamadas requiere una ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="a9051-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="a9051-106">Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.</span><span class="sxs-lookup"><span data-stu-id="a9051-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="a9051-107">Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre regiones, una ruta interregion determina qué ruta de acceso vinculada atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="a9051-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="a9051-108">Para obtener más información sobre cómo trabajar con rutas entre regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a9051-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a9051-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a9051-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a9051-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a9051-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a9051-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a9051-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a9051-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a9051-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="a9051-113">En la topología de ejemplo, las rutas interregións de red deben definirse para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC.</span><span class="sxs-lookup"><span data-stu-id="a9051-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="a9051-114">Para crear rutas interregional de red con el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9051-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a9051-115">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a9051-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a9051-116">Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias.</span><span class="sxs-lookup"><span data-stu-id="a9051-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="a9051-117">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9051-117">For example, run:</span></span>
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a9051-118">La ruta interregional de la red de Norteamérica/APAC requiere dos vínculos de región de red porque no hay un vínculo de región de red directa entre ellos.</span><span class="sxs-lookup"><span data-stu-id="a9051-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="a9051-119">Para crear rutas interregional de red con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9051-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a9051-120">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9051-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a9051-121">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9051-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a9051-122">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="a9051-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a9051-123">Haga clic en el botón de navegación **Ruta regional**.</span><span class="sxs-lookup"><span data-stu-id="a9051-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="a9051-124">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a9051-124">Click **New**.</span></span>

5.  <span data-ttu-id="a9051-125">En la página **nueva ruta** de la región, haga clic en **nombre** y, a continuación, escriba un nombre para la ruta interregión de red.</span><span class="sxs-lookup"><span data-stu-id="a9051-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="a9051-126">Haga clic en **región \#de red 1**y, a continuación, haga clic en una región de red de la lista \#que quiera enrutar a la región de red 2.</span><span class="sxs-lookup"><span data-stu-id="a9051-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="a9051-127">Haga clic en **región \#de red 2**y, a continuación, haga clic en una región de red en la lista \#que quiera enrutar a la región de red 1.</span><span class="sxs-lookup"><span data-stu-id="a9051-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="a9051-128">Haga clic en **Agregar** junto al campo **vínculos de región de red** y, a continuación, agregue un vínculo región de red que se usará en la ruta interregión de red.</span><span class="sxs-lookup"><span data-stu-id="a9051-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a9051-129">Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta.</span><span class="sxs-lookup"><span data-stu-id="a9051-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="a9051-130">Por ejemplo, la ruta interregional de red de Norteamérica/APAC requiere dos vínculos de región de red porque no hay ningún vínculo de región de red directa entre ellos.</span><span class="sxs-lookup"><span data-stu-id="a9051-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="a9051-131">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a9051-131">Click **Commit**.</span></span>

10. <span data-ttu-id="a9051-132">Para terminar de crear rutas interregional de red para su topología, repita los pasos 4 a 9 con la configuración de otras rutas interregional de red.</span><span class="sxs-lookup"><span data-stu-id="a9051-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Crear rutas interregionales de red en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Cree o modifique las rutas interregional de red, que se usan por el control de admisión de llamadas de Enterprise Voice en Skype para Business Server.
ms.openlocfilehash: 5b792a9d1471e8925a44bcc5c0a1026e79aa0a0c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223542"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="22fdf-103">Crear rutas interregionales de red en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="22fdf-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="22fdf-104">Cree o modifique las rutas interregional de red, que se usan por el control de admisión de llamadas de Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="22fdf-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="22fdf-105">Una ruta entre regiones de red define la ruta entre un par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="22fdf-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="22fdf-106">Cada par de regiones de red de la implementación del servicio de control de admisión de llamadas precisa una ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="22fdf-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="22fdf-107">Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.</span><span class="sxs-lookup"><span data-stu-id="22fdf-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="22fdf-108">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones, una ruta entre regiones determina la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="22fdf-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="22fdf-109">En el ejemplo de topología, hay que definir rutas entre regiones de red para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC.</span><span class="sxs-lookup"><span data-stu-id="22fdf-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="22fdf-110">Para crear rutas interregionales de red mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="22fdf-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="22fdf-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="22fdf-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="22fdf-112">Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias.</span><span class="sxs-lookup"><span data-stu-id="22fdf-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="22fdf-113">Por ejemplo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="22fdf-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="22fdf-114">La ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red debido a que no hay un vínculo de región de red directo entre ellas.</span><span class="sxs-lookup"><span data-stu-id="22fdf-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="22fdf-115">Para crear rutas interregionales de red mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="22fdf-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="22fdf-116">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="22fdf-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="22fdf-117">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="22fdf-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="22fdf-118">Haga clic en el botón de navegación **Ruta regional**.</span><span class="sxs-lookup"><span data-stu-id="22fdf-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="22fdf-119">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="22fdf-119">Click **New**.</span></span>
    
5. <span data-ttu-id="22fdf-120">En la página **Nueva ruta regional**, haga clic en **Nombre** y escriba un nombre para la ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="22fdf-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="22fdf-121">Haga clic en **Región de red #1** y, a continuación, haga clic en una región de red de la lista que desee enrutar a la Región de red #2.</span><span class="sxs-lookup"><span data-stu-id="22fdf-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="22fdf-122">Haga clic en **Región de red #2** y, en la lista, seleccione la región de red que desea enrutar a la Región de red #1.</span><span class="sxs-lookup"><span data-stu-id="22fdf-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="22fdf-123">Haga clic en **Agregar** junto al campo **Vínculos de región de red** y luego agregue un vínculo de región de red que se usará en la ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="22fdf-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22fdf-p103">Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta. Por ejemplo, la ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red, debido a que no hay un vínculo de región de red directo entre ellas.</span><span class="sxs-lookup"><span data-stu-id="22fdf-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="22fdf-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22fdf-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="22fdf-127">Para finalizar la creación de rutas entre regiones de red de la topología, repita los pasos del 4 al 9 con la configuración para otras rutas entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="22fdf-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="22fdf-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="22fdf-128">See also</span></span>

[<span data-ttu-id="22fdf-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22fdf-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="22fdf-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22fdf-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="22fdf-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22fdf-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="22fdf-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22fdf-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

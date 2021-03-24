---
title: Crear rutas interregionales de red en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Cree o modifique rutas interregionales de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093128"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="c1b18-103">Crear rutas interregionales de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c1b18-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="c1b18-104">Cree o modifique rutas interregionales de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c1b18-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="c1b18-105">Una ruta interregional de red define la ruta entre un par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="c1b18-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="c1b18-106">Cada par de regiones de red de la implementación del control de admisión de llamadas requiere una ruta interregional de red.</span><span class="sxs-lookup"><span data-stu-id="c1b18-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="c1b18-107">Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.</span><span class="sxs-lookup"><span data-stu-id="c1b18-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="c1b18-108">Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre regiones, una ruta interregional determina qué ruta vinculada recorrerá la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="c1b18-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="c1b18-109">En la topología de ejemplo, las rutas interregionales de red deben definirse para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC.</span><span class="sxs-lookup"><span data-stu-id="c1b18-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c1b18-110">Para crear rutas interregionales de red mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c1b18-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c1b18-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="c1b18-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c1b18-112">Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias.</span><span class="sxs-lookup"><span data-stu-id="c1b18-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="c1b18-113">Por ejemplo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c1b18-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="c1b18-114">La ruta interregional de red de Norteamérica/APAC requiere dos vínculos de región de red porque no hay ningún vínculo de región de red directo entre ellos.</span><span class="sxs-lookup"><span data-stu-id="c1b18-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c1b18-115">Para crear rutas interregionales de red mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c1b18-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c1b18-116">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c1b18-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="c1b18-117">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="c1b18-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="c1b18-118">Haga clic en el botón de navegación **Ruta regional**.</span><span class="sxs-lookup"><span data-stu-id="c1b18-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="c1b18-119">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c1b18-119">Click **New**.</span></span>
    
5. <span data-ttu-id="c1b18-120">En la **página Nueva ruta de** región, haga clic en **Nombre** y, a continuación, escriba un nombre para la ruta interregional de red.</span><span class="sxs-lookup"><span data-stu-id="c1b18-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="c1b18-121">Haga clic en **Región de red #1** y, a continuación, haga clic en una región de red de la lista que desee enrutar a la Región de red #2.</span><span class="sxs-lookup"><span data-stu-id="c1b18-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="c1b18-122">Haga clic en **Región de red #2** y, a continuación, haga clic en una región de red de la lista que desee enrutar a la Región de red #1.</span><span class="sxs-lookup"><span data-stu-id="c1b18-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="c1b18-123">Haga **clic en** Agregar junto al campo **Vínculos de región** de red y, a continuación, agregue un vínculo de región de red que se usará en la ruta interregional de red.</span><span class="sxs-lookup"><span data-stu-id="c1b18-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1b18-124">Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta.</span><span class="sxs-lookup"><span data-stu-id="c1b18-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="c1b18-125">Por ejemplo, la ruta interregional de red Norteamérica/APAC requiere dos vínculos de región de red porque no hay un vínculo de región de red directo entre ellos.</span><span class="sxs-lookup"><span data-stu-id="c1b18-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="c1b18-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c1b18-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="c1b18-127">Para terminar de crear rutas interregionales de red para la topología, repita los pasos del 4 al 9 con la configuración de otras rutas interregionales de red.</span><span class="sxs-lookup"><span data-stu-id="c1b18-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c1b18-128">Ver también</span><span class="sxs-lookup"><span data-stu-id="c1b18-128">See also</span></span>

[<span data-ttu-id="c1b18-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c1b18-129">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="c1b18-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c1b18-130">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="c1b18-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c1b18-131">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="c1b18-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c1b18-132">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
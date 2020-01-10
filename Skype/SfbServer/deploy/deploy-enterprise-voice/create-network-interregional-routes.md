---
title: Crear rutas interregional de red en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Crear o modificar rutas interregional de red que usan el control de admisión de llamadas de telefonía de empresa en Skype empresarial Server.
ms.openlocfilehash: 6d9517796b2f418c39873850ee596a5effdba4e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001760"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="6ea70-103">Crear rutas interregional de red en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6ea70-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="6ea70-104">Crear o modificar rutas interregional de red que usan el control de admisión de llamadas de telefonía de empresa en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6ea70-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="6ea70-105">Una ruta entre regiones de red define la ruta entre un par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6ea70-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="6ea70-106">Cada par de regiones de red de la implementación del servicio de control de admisión de llamadas precisa una ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6ea70-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="6ea70-107">Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.</span><span class="sxs-lookup"><span data-stu-id="6ea70-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="6ea70-108">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones, una ruta entre regiones determina la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="6ea70-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="6ea70-109">En el ejemplo de topología, hay que definir rutas entre regiones de red para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC.</span><span class="sxs-lookup"><span data-stu-id="6ea70-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6ea70-110">Para crear rutas interregional de red con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6ea70-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6ea70-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="6ea70-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6ea70-112">Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias.</span><span class="sxs-lookup"><span data-stu-id="6ea70-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="6ea70-113">Por ejemplo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6ea70-113">For example, run:</span></span>
    
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
    > <span data-ttu-id="6ea70-114">La ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red debido a que no hay un vínculo de región de red directo entre ellas.</span><span class="sxs-lookup"><span data-stu-id="6ea70-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ea70-115">Para crear rutas interregional de red con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6ea70-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6ea70-116">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6ea70-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6ea70-117">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="6ea70-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6ea70-118">Haga clic en el botón de navegación **Ruta regional**.</span><span class="sxs-lookup"><span data-stu-id="6ea70-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="6ea70-119">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6ea70-119">Click **New**.</span></span>
    
5. <span data-ttu-id="6ea70-120">En la página **Nueva ruta regional**, haga clic en **Nombre** y escriba un nombre para la ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6ea70-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="6ea70-121">Haga clic en **Región de red #1** y, a continuación, haga clic en una región de red de la lista que desee enrutar a la Región de red #2.</span><span class="sxs-lookup"><span data-stu-id="6ea70-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="6ea70-122">Haga clic en **Región de red #2** y, en la lista, seleccione la región de red que desea enrutar a la Región de red #1.</span><span class="sxs-lookup"><span data-stu-id="6ea70-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="6ea70-123">Haga clic en **Agregar** junto al campo **Vínculos de región de red** y luego agregue un vínculo de región de red que se usará en la ruta entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6ea70-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6ea70-p103">Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta. Por ejemplo, la ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red, debido a que no hay un vínculo de región de red directo entre ellas.</span><span class="sxs-lookup"><span data-stu-id="6ea70-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="6ea70-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6ea70-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="6ea70-127">Para finalizar la creación de rutas entre regiones de red de la topología, repita los pasos del 4 al 9 con la configuración para otras rutas entre regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6ea70-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6ea70-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ea70-128">See also</span></span>

[<span data-ttu-id="6ea70-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="6ea70-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="6ea70-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="6ea70-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="6ea70-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="6ea70-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="6ea70-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="6ea70-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

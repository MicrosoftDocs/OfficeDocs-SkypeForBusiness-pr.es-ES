---
title: 'Lync Server 2013: visualización de información de ruta de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f509735cf3a43e6539305fcad31db17cfd52a11
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="3fda8-102">Ver información de ruta de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fda8-102">Viewing network region route information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fda8-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3fda8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3fda8-104">Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="3fda8-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="3fda8-105">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="3fda8-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="3fda8-106">Use los siguientes procedimientos para ver las rutas de región de red existentes en el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3fda8-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="3fda8-107">Para obtener información detallada sobre cómo crear o modificar rutas de región de red, vea [crear o modificar rutas de regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="3fda8-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="3fda8-108">Para ver la información de ruta de región de red en el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="3fda8-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3fda8-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3fda8-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3fda8-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3fda8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3fda8-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3fda8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3fda8-112">En la barra de navegación izquierda, haga clic en  \*\*Configuración de red \*\* y, a continuación, en \*\*Ruta de región \*\*.</span><span class="sxs-lookup"><span data-stu-id="3fda8-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="3fda8-113">En la página **Ruta de región**, haga clic en la ruta regional que desea ver.</span><span class="sxs-lookup"><span data-stu-id="3fda8-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3fda8-114">Solo puede ver una ruta regional cada vez.</span><span class="sxs-lookup"><span data-stu-id="3fda8-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="3fda8-115">En el menú  \*\*Editar \*\*, haga clic en  \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="3fda8-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3fda8-116">Visualización de información de rutas de región de red mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fda8-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3fda8-117">La información de ruta de región de red se puede ver con Windows PowerShell y el cmdlet Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="3fda8-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="3fda8-118">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fda8-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3fda8-119">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="3fda8-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="3fda8-120">Para ver la información de ruta de región de red</span><span class="sxs-lookup"><span data-stu-id="3fda8-120">To view network region route information</span></span>

  - <span data-ttu-id="3fda8-121">Para ver información sobre todas las rutas de región de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="3fda8-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="3fda8-122">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3fda8-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="3fda8-123">Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="3fda8-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3fda8-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3fda8-124">See Also</span></span>


[<span data-ttu-id="3fda8-125">Creación o modificación de rutas de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fda8-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="3fda8-126">Eliminación de rutas de región de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fda8-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


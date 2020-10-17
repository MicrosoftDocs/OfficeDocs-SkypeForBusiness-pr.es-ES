---
title: 'Lync Server 2013: eliminar rutas de región de red existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07a0331563c4d78c4e8fc3391b7f8423a2ecc21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525397"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="10dbe-102">Eliminación de rutas de región de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dbe-102">Deleting existing network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10dbe-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="10dbe-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="10dbe-104">Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="10dbe-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="10dbe-105">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="10dbe-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="10dbe-106">Puede usar el panel de control de Lync Server para configurar rutas de región de red.</span><span class="sxs-lookup"><span data-stu-id="10dbe-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="10dbe-107">En el panel de control de Lync Server, puede crear, modificar o eliminar una ruta de región de red.</span><span class="sxs-lookup"><span data-stu-id="10dbe-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="10dbe-108">Use este tema para eliminar las rutas de región de red existentes.</span><span class="sxs-lookup"><span data-stu-id="10dbe-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="10dbe-109">Para obtener información detallada sobre cómo crear o modificar rutas de región de red, vea [crear o modificar rutas de regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="10dbe-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="10dbe-110">Para eliminar una ruta regional de red</span><span class="sxs-lookup"><span data-stu-id="10dbe-110">To delete a network region route</span></span>

1.  <span data-ttu-id="10dbe-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="10dbe-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10dbe-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10dbe-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10dbe-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="10dbe-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10dbe-114">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.</span><span class="sxs-lookup"><span data-stu-id="10dbe-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="10dbe-115">En la página **Ruta regional**, haga clic en la ruta regional que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="10dbe-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10dbe-p103">Puede eliminar más de una ruta regional en la misma operación. Para hacerlo, presione la tecla CTRL y seleccione varias rutas regionales sin dejar de presionar CTRL. También puede seleccionar todas las rutas regionales haciendo clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="10dbe-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="10dbe-119">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="10dbe-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="10dbe-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="10dbe-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10dbe-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10dbe-121">See Also</span></span>


[<span data-ttu-id="10dbe-122">Creación o modificación de rutas de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dbe-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="10dbe-123">[Configurar una ruta de región de red](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="10dbe-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="10dbe-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="10dbe-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="10dbe-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="10dbe-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="10dbe-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="10dbe-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="10dbe-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="10dbe-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


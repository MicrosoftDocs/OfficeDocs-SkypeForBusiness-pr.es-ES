---
title: 'Lync Server 2013: creación o modificación de rutas de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e10cfddaa0e99ee5e6dbab5d196803923bfef95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="f1566-102">Creación o modificación de rutas de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1566-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1566-103">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="f1566-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="f1566-104">Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones.</span><span class="sxs-lookup"><span data-stu-id="f1566-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="f1566-105">Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra.</span><span class="sxs-lookup"><span data-stu-id="f1566-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="f1566-106">Puede usar el panel de control de Lync Server para configurar rutas de región de red.</span><span class="sxs-lookup"><span data-stu-id="f1566-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="f1566-107">En el panel de control de Lync Server, puede crear, modificar o eliminar una ruta de región de red.</span><span class="sxs-lookup"><span data-stu-id="f1566-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="f1566-108">Consulte este tema para crear o modificar una ruta regional de red.</span><span class="sxs-lookup"><span data-stu-id="f1566-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="f1566-109">Para obtener más información sobre cómo eliminar rutas de regiones de red existentes, consulte [eliminar rutas de regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="f1566-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="f1566-110">Para crear una ruta regional de red</span><span class="sxs-lookup"><span data-stu-id="f1566-110">To create a network region route</span></span>

1.  <span data-ttu-id="f1566-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f1566-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1566-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1566-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1566-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1566-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1566-114">En la barra de navegación izquierda, haga clic en  \*\*Configuración de red \*\* y, a continuación, en \*\*Ruta de región \*\*.</span><span class="sxs-lookup"><span data-stu-id="f1566-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f1566-115">En la página **Ruta regional**, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="f1566-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="f1566-116">En **Nueva ruta regional**, escriba un valor en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f1566-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1566-117">Este valor debe ser único dentro de la implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1566-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="f1566-118">En la lista desplegable \*\* \#región de red 1\*\* , seleccione una de las dos regiones que se conectarán mediante esta ruta.</span><span class="sxs-lookup"><span data-stu-id="f1566-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="f1566-119">En la lista desplegable \*\* \#región de red 2\*\* , seleccione la otra región de esta ruta.</span><span class="sxs-lookup"><span data-stu-id="f1566-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="f1566-120">Esta región debe ser diferente de la región seleccionada para la región \#de red 1.</span><span class="sxs-lookup"><span data-stu-id="f1566-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="f1566-p104">Use el cuadro de lista **Vínculos de región de red** para agregar vínculos de red a la ruta. Haga clic en el botón **Agregar** para mostrar la página **Vínculo regional**. Haga clic en un vínculo regional para agregarlo a esta ruta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1566-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1566-124">Haga clic otra vez en el botón <STRONG>Agregar</STRONG> para añadir más vínculos, o seleccione un vínculo y haga clic en <STRONG>Eliminar</STRONG> para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="f1566-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="f1566-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f1566-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="f1566-126">Para modificar una ruta regional de red</span><span class="sxs-lookup"><span data-stu-id="f1566-126">To modify a network region route</span></span>

1.  <span data-ttu-id="f1566-127">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f1566-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1566-128">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1566-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1566-129">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1566-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1566-130">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.</span><span class="sxs-lookup"><span data-stu-id="f1566-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f1566-131">En la página **Ruta regional**, haga clic en la ruta regional que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="f1566-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="f1566-132">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="f1566-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f1566-133">En **Editar ruta regional**, puede modificar las regiones agregadas a esta ruta y los vínculos regionales asociados a la misma.</span><span class="sxs-lookup"><span data-stu-id="f1566-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="f1566-134">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f1566-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1566-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1566-135">See Also</span></span>


[<span data-ttu-id="f1566-136">Eliminación de rutas de región de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1566-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


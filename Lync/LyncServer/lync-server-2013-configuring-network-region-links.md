---
title: 'Lync Server 2013: configuración de vínculos de región de red'
description: 'Lync Server 2013: configuración de vínculos de región de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92593f3b8fcd5fe3307a9c193ed7cddcf6dfce0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547016"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="5a64d-103">Configuración de vínculos de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a64d-103">Configuring network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a64d-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5a64d-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5a64d-105">Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5a64d-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="5a64d-106">Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN).</span><span class="sxs-lookup"><span data-stu-id="5a64d-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="5a64d-107">Puede usar el panel de control de Lync Server para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en las conexiones de audio y vídeo entre estas regiones.</span><span class="sxs-lookup"><span data-stu-id="5a64d-107">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="5a64d-108">Para obtener más información sobre cómo eliminar un vínculo de región de red existente, consulte [eliminar vínculos de región de red en Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="5a64d-108">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="5a64d-109">Para crear un vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="5a64d-109">To create a network region link</span></span>

1.  <span data-ttu-id="5a64d-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5a64d-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5a64d-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a64d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5a64d-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5a64d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5a64d-113">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Vínculo regional**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="5a64d-114">En la página **Vínculo regional**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-114">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="5a64d-115">En **Vínculo regional nuevo**, escriba un valor en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-115">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a64d-116">Este valor debe ser único dentro de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a64d-116">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="5a64d-117">En la lista desplegable **región de red \# 1** , seleccione una de las dos regiones que se van a vincular.</span><span class="sxs-lookup"><span data-stu-id="5a64d-117">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="5a64d-118">En la lista desplegable **región de red \# 2** , seleccione la otra región que se va a vincular.</span><span class="sxs-lookup"><span data-stu-id="5a64d-118">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="5a64d-119">Esta región debe ser diferente de la región seleccionada para la región de red \# 1.</span><span class="sxs-lookup"><span data-stu-id="5a64d-119">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="5a64d-120">(Opcional) Si desea establecer limitaciones de ancho de banda en llamadas de audio o vídeo entre estas regiones, seleccione un perfil de directiva de ancho de banda en la lista desplegable **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-120">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="5a64d-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="5a64d-122">Para modificar un vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="5a64d-122">To modify a network region link</span></span>

1.  <span data-ttu-id="5a64d-123">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5a64d-123">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5a64d-124">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a64d-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5a64d-125">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5a64d-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5a64d-126">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Vínculo regional**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-126">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="5a64d-127">En la página **Vínculo regional**, haga clic en el vínculo regional que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="5a64d-127">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="5a64d-128">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-128">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5a64d-129">En **Editar vínculo regional** puede modificar las regiones que están vinculadas o el perfil de directiva de ancho de banda para este vínculo.</span><span class="sxs-lookup"><span data-stu-id="5a64d-129">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="5a64d-130">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5a64d-130">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a64d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a64d-131">See Also</span></span>


[<span data-ttu-id="5a64d-132">Eliminación de vínculos de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a64d-132">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="5a64d-133">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5a64d-133">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="5a64d-134">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5a64d-134">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="5a64d-135">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5a64d-135">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="5a64d-136">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5a64d-136">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

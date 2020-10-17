---
title: 'Lync Server 2013: visualización de información de vínculos de región de red'
description: 'Lync Server 2013: visualización de información de vínculos de región de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0134ded9942ebda91050c1f7b0bbcfef018451a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565366"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="db10f-103">Ver la información del vínculo de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db10f-103">Viewing network region link information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db10f-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="db10f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="db10f-105">Puede ver enlaces entre dos regiones de red como parte de un servicio de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="db10f-105">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="db10f-106">Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN).</span><span class="sxs-lookup"><span data-stu-id="db10f-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="db10f-107">Puede usar el panel de control de Lync Server para ver un vínculo existente entre dos regiones de red.</span><span class="sxs-lookup"><span data-stu-id="db10f-107">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="db10f-108">Para obtener información detallada sobre cómo crear o modificar el vínculo de región de red, vea [Configuring Network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="db10f-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="db10f-109">Para ver un vínculo de región de red en el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="db10f-109">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="db10f-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="db10f-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="db10f-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db10f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="db10f-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="db10f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="db10f-113">En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="db10f-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="db10f-114">En la página **Vínculo de región**, haga clic en el vínculo de región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="db10f-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db10f-115">Solo puede ver información acerca de un vínculo de región a la vez.</span><span class="sxs-lookup"><span data-stu-id="db10f-115">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="db10f-116">En el menú **Editar**, seleccione **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="db10f-116">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="db10f-117">Visualización de información de vínculos de región de red mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db10f-117">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="db10f-118">Puede ver los vínculos de región de red con Windows PowerShell y el cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="db10f-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="db10f-119">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db10f-119">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="db10f-120">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="db10f-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="db10f-121">Para ver la información de un vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="db10f-121">To view network region link information</span></span>

  - <span data-ttu-id="db10f-122">Para ver información sobre todos los vínculos de región de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="db10f-122">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="db10f-123">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="db10f-123">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="db10f-124">Para obtener información detallada, vea [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="db10f-124">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db10f-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db10f-125">See Also</span></span>


[<span data-ttu-id="db10f-126">Configuración de vínculos a sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db10f-126">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


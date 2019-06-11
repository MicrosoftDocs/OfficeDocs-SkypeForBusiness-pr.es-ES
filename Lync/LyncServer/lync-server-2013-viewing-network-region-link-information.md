---
title: 'Lync Server 2013: visualización de la información del vínculo región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5bec9bdc656a33a34727f29bfc56ad39b2476a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="a49a9-102">Visualización de la información del vínculo región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a49a9-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a49a9-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a49a9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a49a9-104">Puede ver los vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="a49a9-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="a49a9-105">Las regiones dentro de una red están vinculadas a través de la conectividad de red de área extensa (WAN).</span><span class="sxs-lookup"><span data-stu-id="a49a9-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="a49a9-106">Puede usar el panel de control de Lync Server para ver un vínculo existente entre dos regiones de red.</span><span class="sxs-lookup"><span data-stu-id="a49a9-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="a49a9-107">Para obtener detalles sobre cómo crear o modificar el vínculo región de red, vea [configuración de vínculos de regiones de red en Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="a49a9-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="a49a9-108">Para ver un vínculo de región de red en el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a49a9-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a49a9-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a49a9-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a49a9-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a49a9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a49a9-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a49a9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a49a9-112">En la barra de navegación izquierda, haga clic en **configuración de red** y, a continuación, en **vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="a49a9-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="a49a9-113">En la página vínculo de la **región** , haga clic en el vínculo de la región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="a49a9-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a49a9-114">Solo puedes ver información sobre un vínculo de región a la vez.</span><span class="sxs-lookup"><span data-stu-id="a49a9-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="a49a9-115">En el menú **Editar** , seleccione **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="a49a9-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a49a9-116">Visualización de la información del vínculo región de red con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a49a9-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a49a9-117">Puede ver los vínculos de la región de red con Windows PowerShell y el cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="a49a9-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="a49a9-118">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a49a9-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a49a9-119">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="a49a9-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="a49a9-120">Para ver información de vínculos de la región de red</span><span class="sxs-lookup"><span data-stu-id="a49a9-120">To view network region link information</span></span>

  - <span data-ttu-id="a49a9-121">Para ver información sobre todos los vínculos de la región de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a49a9-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="a49a9-122">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a49a9-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="a49a9-123">Para obtener más información, vea [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="a49a9-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a49a9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a49a9-124">See Also</span></span>


[<span data-ttu-id="a49a9-125">Configuración de vínculos a sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a49a9-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


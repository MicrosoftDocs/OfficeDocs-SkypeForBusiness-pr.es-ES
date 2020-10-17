---
title: 'Lync Server 2013: visualización de información del sitio de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a63f8abe0adb2f17a674474cbf91884bef5d389
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535627"
---
# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="b51f0-102">Ver la información del sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b51f0-102">Viewing network site information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b51f0-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b51f0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b51f0-104">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="b51f0-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="b51f0-105">Puede ver la información del sitio de red en el panel de control de Lync Server 2013 o en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b51f0-105">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="b51f0-106">Para obtener información detallada sobre cómo crear o modificar sitios de red, vea [crear o modificar sitios de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="b51f0-106">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="b51f0-107">Para ver la información del sitio de red en el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b51f0-107">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b51f0-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b51f0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b51f0-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b51f0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b51f0-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b51f0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b51f0-111">En la barra de navegación izquierda, haga clic en  \*\*Configuración de red \*\* y, a continuación, en  \*\*Sitio \*\*.</span><span class="sxs-lookup"><span data-stu-id="b51f0-111">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="b51f0-112">En la página **Sitio**, haga clic en el sitio que desea ver.</span><span class="sxs-lookup"><span data-stu-id="b51f0-112">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b51f0-113">Solo puede ver información para un sitio cada vez.</span><span class="sxs-lookup"><span data-stu-id="b51f0-113">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="b51f0-114">En el menú  \*\*Editar \*\*, haga clic en  \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="b51f0-114">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b51f0-115">Visualización de la información del sitio de red mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b51f0-115">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b51f0-116">Puede ver la información del sitio de red mediante Windows PowerShell y el cmdlet Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="b51f0-116">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="b51f0-117">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b51f0-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b51f0-118">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b51f0-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="b51f0-119">Para ver la información de sitio de red</span><span class="sxs-lookup"><span data-stu-id="b51f0-119">To view network site information</span></span>

  - <span data-ttu-id="b51f0-120">Para ver información sobre todos los sitios de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="b51f0-120">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="b51f0-121">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b51f0-121">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="b51f0-122">Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="b51f0-122">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b51f0-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b51f0-123">See Also</span></span>


[<span data-ttu-id="b51f0-124">Crear o modificar sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b51f0-124">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="b51f0-125">Eliminación de un sitio de red existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b51f0-125">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


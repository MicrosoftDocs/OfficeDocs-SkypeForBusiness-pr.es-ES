---
title: 'Lync Server 2013: visualización de la información de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7222afb226a211609423cb3c5ad1e40383de67e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535727"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="ae856-102">Ver la información de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae856-102">Viewing network region information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae856-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ae856-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ae856-104">Una región de red interconecta varias partes de una red a través de varias zonas geográficas.</span><span class="sxs-lookup"><span data-stu-id="ae856-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ae856-105">Cada región de red debe asociarse con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="ae856-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ae856-106">El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas).</span><span class="sxs-lookup"><span data-stu-id="ae856-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ae856-107">Puede usar el panel de control de Lync Server para ver las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ae856-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="ae856-108">Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="ae856-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ae856-109">Use este tema para ver las regiones de red existentes.</span><span class="sxs-lookup"><span data-stu-id="ae856-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="ae856-110">Para obtener información detallada acerca de la creación o modificación de regiones de red existentes, consulte [creación o modificación de regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="ae856-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="ae856-111">Para ver información sobre una región de red con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ae856-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ae856-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ae856-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae856-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ae856-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ae856-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ae856-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ae856-115">En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Región**.</span><span class="sxs-lookup"><span data-stu-id="ae856-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="ae856-116">En la página **región** , haga clic en la región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="ae856-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae856-117">Solo puede ver una región a la vez.</span><span class="sxs-lookup"><span data-stu-id="ae856-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="ae856-118">En el menú \*\*Editar \*\*, haga clic en \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="ae856-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ae856-119">Ver la información de región de red mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae856-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ae856-120">Puede ver la información de la región de red con Windows PowerShell y el cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="ae856-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="ae856-121">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae856-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ae856-122">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="ae856-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="ae856-123">Para ver la información de la región de red</span><span class="sxs-lookup"><span data-stu-id="ae856-123">To view network region information</span></span>

  - <span data-ttu-id="ae856-124">Para ver información sobre todas las regiones de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="ae856-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="ae856-125">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae856-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="ae856-126">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="ae856-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ae856-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae856-127">See Also</span></span>


[<span data-ttu-id="ae856-128">Creación o modificación de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae856-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="ae856-129">Eliminación de regiones de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae856-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


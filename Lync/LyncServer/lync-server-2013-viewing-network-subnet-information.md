---
title: 'Lync Server 2013: visualización de la información de subred de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453d66d35d02d6b0e91f0c6b82b1ccfe71f149b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535607"
---
# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="48e46-102">Ver la información de subred de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e46-102">Viewing network subnet information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48e46-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="48e46-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="48e46-104">Puede usar el siguiente procedimiento para ver una subred de la red.</span><span class="sxs-lookup"><span data-stu-id="48e46-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="48e46-105">Desde el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="48e46-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="48e46-106">Para obtener información detallada acerca de la creación o modificación de subredes de red, consulte [crear o modificar subredes de red en Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="48e46-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="48e46-107">Para ver una subred de la red</span><span class="sxs-lookup"><span data-stu-id="48e46-107">To view a network subnet</span></span>

1.  <span data-ttu-id="48e46-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="48e46-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="48e46-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48e46-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="48e46-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="48e46-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="48e46-111">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Subred**.</span><span class="sxs-lookup"><span data-stu-id="48e46-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="48e46-112">En la página \*\*Subred \*\*, haga clic en la subred que desea ver.</span><span class="sxs-lookup"><span data-stu-id="48e46-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48e46-113">Solo puede ver una subred de cada vez.</span><span class="sxs-lookup"><span data-stu-id="48e46-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="48e46-114">En el menú \*\*Editar \*\*, haga clic en **Mostrar detalles...**.</span><span class="sxs-lookup"><span data-stu-id="48e46-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="48e46-115">Visualización de la información de configuración de subred de red mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48e46-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="48e46-116">La información de la subred de red se puede ver con Windows PowerShell y el cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="48e46-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="48e46-117">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48e46-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="48e46-118">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="48e46-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="48e46-119">Para ver la información de subred de la red</span><span class="sxs-lookup"><span data-stu-id="48e46-119">To view network subnet information</span></span>

  - <span data-ttu-id="48e46-120">Para ver información sobre todas las subredes de la red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="48e46-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="48e46-121">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="48e46-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="48e46-122">Para más información, vea el tema de ayuda del cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="48e46-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48e46-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48e46-123">See Also</span></span>


[<span data-ttu-id="48e46-124">Crear o modificar subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e46-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="48e46-125">Eliminación de subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e46-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


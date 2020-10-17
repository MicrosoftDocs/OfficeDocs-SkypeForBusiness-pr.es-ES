---
title: 'Lync Server 2013: eliminación de subredes de red'
description: 'Lync Server 2013: eliminación de subredes de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6635ec99b68c4ceb10d1cda343fef35c951bf152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557886"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="b44f6-103">Eliminación de subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b44f6-103">Deleting network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b44f6-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b44f6-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b44f6-105">Puede usar el procedimiento siguiente para eliminar una subred.</span><span class="sxs-lookup"><span data-stu-id="b44f6-105">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="b44f6-106">Desde el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red.</span><span class="sxs-lookup"><span data-stu-id="b44f6-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="b44f6-107">Para obtener más información sobre cómo crear o modificar subredes de red, vea [crear o modificar subredes de red en Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="b44f6-107">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="b44f6-108">En la mayoría de las implementaciones de Microsoft Lync Server 2013 donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes.</span><span class="sxs-lookup"><span data-stu-id="b44f6-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="b44f6-109">Por ello, suele ser mejor configurar subredes desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b44f6-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="b44f6-110">Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b44f6-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="b44f6-111">Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b44f6-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="b44f6-112">Para ver ejemplos de cómo crear subredes desde un archivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="b44f6-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="b44f6-113">Para eliminar una subred de red:</span><span class="sxs-lookup"><span data-stu-id="b44f6-113">To delete a network subnet</span></span>

1.  <span data-ttu-id="b44f6-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b44f6-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b44f6-115">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b44f6-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b44f6-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b44f6-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b44f6-117">En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Subred**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b44f6-118">En la página **Subred**, haga clic en la subred que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="b44f6-118">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b44f6-p104">Puede eliminar simultáneamente varias subredes. Para ello, mantenga presionada la tecla Ctrl y seleccione varias subredes. O bien, para seleccionar todas las subredes, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b44f6-p104">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b44f6-122">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-122">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="b44f6-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-123">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b44f6-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b44f6-124">See Also</span></span>


[<span data-ttu-id="b44f6-125">Crear o modificar subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b44f6-125">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


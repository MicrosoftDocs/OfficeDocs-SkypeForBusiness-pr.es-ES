---
title: 'Lync Server 2013: eliminar un grupo de agentes'
description: 'Lync Server 2013: eliminar un grupo de agentes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dded2db0957e37a624d7e8bf3a06e102f8d35cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553686"
---
# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="6fb5a-103">Eliminar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb5a-103">Delete an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fb5a-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6fb5a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6fb5a-105">Use uno de los siguientes procedimientos para eliminar un grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-105">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="6fb5a-106">Para usar el panel de control de Lync Server para eliminar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="6fb5a-106">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="6fb5a-107">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="6fb5a-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6fb5a-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6fb5a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6fb5a-110">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-110">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="6fb5a-111">En la página **grupos de respuesta** , escriba todo o parte del nombre del grupo de agentes que desea eliminar en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-111">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="6fb5a-112">En la lista resultante, haga clic en el grupo que desea eliminar, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-112">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="6fb5a-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="6fb5a-114">Para usar Windows PowerShell para eliminar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="6fb5a-114">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="6fb5a-115">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-115">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="6fb5a-116">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6fb5a-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6fb5a-117">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6fb5a-117">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="6fb5a-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fb5a-118">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fb5a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fb5a-119">See Also</span></span>


[<span data-ttu-id="6fb5a-120">Crear o modificar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb5a-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="6fb5a-121">Remove-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="6fb5a-121">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="6fb5a-122">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="6fb5a-122">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


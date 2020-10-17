---
title: 'Lync Server 2013: eliminar un flujo de trabajo'
description: 'Lync Server 2013: eliminar un flujo de trabajo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a588a1dc0428660db95d4d492abbd1b157ca7a0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553706"
---
# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="75f53-103">Eliminar un flujo de trabajo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75f53-103">Delete a workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75f53-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="75f53-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="75f53-105">Utilice uno de los procedimientos siguientes para eliminar flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="75f53-105">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="75f53-106">Para usar el panel de control de Lync Server eliminar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="75f53-106">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="75f53-107">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="75f53-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="75f53-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75f53-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75f53-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75f53-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75f53-110">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="75f53-110">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="75f53-111">En la página **Flujo de trabajo**, haga clic en **Crear o editar flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="75f53-111">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="75f53-112">En el campo de búsqueda **Seleccionar un servicio**, escriba parte del nombre, o el nombre completo, del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="75f53-112">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="75f53-113">En la lista de servicios, haga clic en el servicio que desee y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75f53-113">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75f53-114">Se abre la página web herramienta de configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="75f53-114">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="75f53-115">También puede abrir la Página Web de la herramienta de configuración del grupo de respuesta directamente desde un explorador Web conectándose a <STRONG>https:// &lt; fqdngrupoweb &gt; /RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="75f53-115">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="75f53-116">En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea eliminar y, a continuación, en **Acción**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="75f53-116">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="75f53-117">Haga clic en **Yes** (Sí).</span><span class="sxs-lookup"><span data-stu-id="75f53-117">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="75f53-118">Para usar Windows PowerShell para eliminar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="75f53-118">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="75f53-119">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="75f53-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="75f53-120">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="75f53-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="75f53-121">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="75f53-121">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="75f53-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75f53-122">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>


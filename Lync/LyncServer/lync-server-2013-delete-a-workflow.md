---
title: 'Lync Server 2013: eliminar un flujo de trabajo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="5c8d8-102">Eliminar un flujo de trabajo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c8d8-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c8d8-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5c8d8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5c8d8-104">Use uno de los procedimientos siguientes para eliminar un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="5c8d8-105">Para usar el panel de control de Lync Server eliminar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5c8d8-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="5c8d8-106">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="5c8d8-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5c8d8-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5c8d8-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5c8d8-109">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="5c8d8-110">En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="5c8d8-111">En el campo **seleccionar una** búsqueda de servicio, escriba parte o todo el nombre del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="5c8d8-112">En la lista de servicios, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5c8d8-113">Se abre la Página Web de la herramienta de configuración de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="5c8d8-114">También puede abrir la Página Web de la herramienta de configuración de grupos de respuesta directamente desde un explorador Web conectándose a <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="5c8d8-115">En **administrar un flujo de trabajo existente**, busque el flujo de trabajo que desea eliminar y, a continuación, en **acción**, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="5c8d8-116">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="5c8d8-117">Para usar Windows PowerShell para eliminar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5c8d8-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="5c8d8-118">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="5c8d8-119">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5c8d8-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5c8d8-120">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5c8d8-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="5c8d8-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5c8d8-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>


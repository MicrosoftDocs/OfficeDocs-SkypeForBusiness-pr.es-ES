---
title: 'Lync Server 2013: crear o modificar un flujo de trabajo'
description: 'Lync Server 2013: crear o modificar un flujo de trabajo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a workflow
ms:assetid: 5ac1c0f3-e82f-40ca-b972-91950e38c05b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520997(v=OCS.15)
ms:contentKeyID: 48184225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 053b80e313e497313e613a5f8b16bd5beeabf7ac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574476"
---
# <a name="create-or-modify-a-workflow-in-lync-server-2013"></a><span data-ttu-id="8a4a8-103">Crear o modificar un flujo de trabajo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4a8-103">Create or modify a workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a4a8-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8a4a8-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8a4a8-105">Lync Server 2013 admite dos tipos de flujos de trabajo: Grupo de extensiones y respuesta de voz interactiva (IVR).</span><span class="sxs-lookup"><span data-stu-id="8a4a8-105">Lync Server 2013 supports two types of workflows: hunt group and interactive voice response (IVR).</span></span> <span data-ttu-id="8a4a8-106">Cuando se crea un flujo de trabajo, se usa la herramienta de configuración de grupo de respuesta para especificar la cola que se va a usar y otras opciones, como un mensaje de bienvenida, la música en espera, el horario comercial y las preguntas que la aplicación de grupo de respuesta solicita al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-106">When you create a workflow, you use the Response Group Configuration Tool to specify the queue to use and other settings, such as a welcome message, music on hold, business hours, and questions that the Response Group application asks the caller.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a4a8-107">Debe crear grupos de agentes y colas antes de crear un flujo de trabajo que use dichos elementos.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-107">You must create agent groups and queues before you create a workflow that uses them.</span></span> <span data-ttu-id="8a4a8-108">Si desea crear horario comercial y festivos predefinidos que puede usar para varios flujos de trabajo, también debe definir estas horas y festivos antes de crear un flujo de trabajo que las use.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-108">If you want to create predefined business hours and holidays that you can use for multiple workflows, you must also define these hours and holidays before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8a4a8-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8a4a8-109">In This Section</span></span>

  - [<span data-ttu-id="8a4a8-110">Crear o modificar un flujo de trabajo de grupo de búsqueda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4a8-110">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="8a4a8-111">Crear o modificar un flujo de trabajo interactivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4a8-111">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a4a8-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a4a8-112">See Also</span></span>


[<span data-ttu-id="8a4a8-113">Crear o modificar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4a8-113">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  
[<span data-ttu-id="8a4a8-114">Crear o modificar una cola en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4a8-114">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)  
[<span data-ttu-id="8a4a8-115">Opcional Definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4a8-115">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="8a4a8-116">Opcional Definir el horario comercial del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4a8-116">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


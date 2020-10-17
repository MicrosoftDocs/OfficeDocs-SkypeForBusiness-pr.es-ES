---
title: 'Lync Server 2013: crear flujos de trabajo de grupo de respuesta'
description: 'Lync Server 2013: crear flujos de trabajo de grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7082295eeca45c4dac76d68ef54b5c32fafb25d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548656"
---
# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="78b77-103">Crear flujos de trabajo de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78b77-103">Create Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78b77-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="78b77-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="78b77-p101">Un flujo de trabajo define el comportamiento de una llamada desde el momento en que suena el teléfono hasta que alguien la atiende. El flujo de trabajo especifica la cola que se va a usar para poner la llamada en espera, así como el método de enrutamiento que se va a usar en grupos de extensiones o las preguntas y respuestas que se van a utilizar en grupos de respuesta interactivos. Un flujo de trabajo también define configuraciones como el mensaje de bienvenida, la música en espera, horario laboral y los días festivos.</span><span class="sxs-lookup"><span data-stu-id="78b77-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="78b77-108">Use la herramienta de configuración de grupos de respuesta para crear flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78b77-108">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="78b77-109">Puede acceder a la herramienta Configuración del grupo de respuesta desde la página grupo de respuesta del panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78b77-109">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78b77-110">Debe crear grupos de agentes y colas antes de crear un flujo de trabajo que use dichos elementos.</span><span class="sxs-lookup"><span data-stu-id="78b77-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="78b77-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="78b77-111">In This Section</span></span>

  - [<span data-ttu-id="78b77-112">Crear o modificar un flujo de trabajo de grupo de búsqueda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78b77-112">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="78b77-113">Diseñar flujos de llamadas de respuesta de voz interactiva en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78b77-113">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="78b77-114">Crear o modificar un flujo de trabajo interactivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78b77-114">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="78b77-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="78b77-115">Related Sections</span></span>

  - [<span data-ttu-id="78b77-116">Crear grupos de agentes de grupo de respuesta Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78b77-116">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="78b77-117">Crear colas de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78b77-117">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


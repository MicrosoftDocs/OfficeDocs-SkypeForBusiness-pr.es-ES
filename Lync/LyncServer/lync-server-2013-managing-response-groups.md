---
title: 'Lync Server 2013: administración de grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210debb3c3879d6895b127b960139970bf73d020
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="d35d6-102">Administración de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35d6-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d35d6-103">_**Última modificación del tema:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="d35d6-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="d35d6-104">Los grupos de respuesta son una característica de administración de llamadas que le permite poner en cola las llamadas realizadas a un área específica, como un servicio de asistencia y, a continuación, enrutar las llamadas a un grupo designado de personas, denominado *agentes*.</span><span class="sxs-lookup"><span data-stu-id="d35d6-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="d35d6-105">Para administrar grupos de respuesta, puede configurar grupos de agentes, colas y flujos de trabajo, que determinan qué sucede con una llamada desde el momento en que se coloca hasta que un agente la responde.</span><span class="sxs-lookup"><span data-stu-id="d35d6-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d35d6-106">Si tiene más de 300 flujos de trabajo en un solo grupo de la implementación de grupos de respuesta, es mejor usar los cmdlets del shell de administración de Lync Server para crear los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d35d6-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="d35d6-107">Si usa la herramienta de configuración de grupos de respuesta para crear flujos de trabajo para un grupo que tiene más de 300 flujos de trabajo, la página web tarda mucho tiempo en cargarse.</span><span class="sxs-lookup"><span data-stu-id="d35d6-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="d35d6-108">El número de agentes que se asocian indirectamente a flujos de trabajo a través de las colas también tiene un efecto proporcional en la carga de páginas.</span><span class="sxs-lookup"><span data-stu-id="d35d6-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="d35d6-109">Los temas de esta sección proporcionan procedimientos paso a paso para las tareas que puede realizar para personalizar y mantener la aplicación de grupo de respuesta en su implementación.</span><span class="sxs-lookup"><span data-stu-id="d35d6-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d35d6-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d35d6-110">In This Section</span></span>

  - [<span data-ttu-id="d35d6-111">Administrar grupos de agentes de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35d6-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="d35d6-112">Administrar colas de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35d6-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="d35d6-113">Administración de flujos de trabajo de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35d6-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="d35d6-114">Administrar la configuración de grupo de respuesta de nivel de aplicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35d6-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="d35d6-115">Mover grupos de respuesta a un grupo nuevo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35d6-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="d35d6-116">Administrar grupos de respuesta durante un desastre en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35d6-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


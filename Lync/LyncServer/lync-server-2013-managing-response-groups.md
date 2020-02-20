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
ms.openlocfilehash: ee9ee5808263f1e10489a09a711c60f93a13429d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="579c0-102">Administración de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="579c0-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="579c0-103">_**Última modificación del tema:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="579c0-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="579c0-104">Los grupos de respuesta son una característica para la administración de llamadas que habilitan poner en cola las llamadas que se realizan a un área específica, como el servicio de asistencia técnica, y de ahí se enrutan a un grupo designado de personas, que se denominan *agentes*.</span><span class="sxs-lookup"><span data-stu-id="579c0-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="579c0-105">Para administrar grupos de respuesta, deberá configurar grupos de agentes, colas y flujos de trabajo, que definen lo que ocurre con una llamada desde el momento que se realiza hasta que es atendida por un agente.</span><span class="sxs-lookup"><span data-stu-id="579c0-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="579c0-106">Si tiene más de 300 flujos de trabajo en un único grupo de servidores de la implementación del grupo de respuesta, es mejor usar los cmdlets del shell de administración de Lync Server para crear los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="579c0-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="579c0-107">Si usa la herramienta de configuración de grupos de respuesta para crear flujos de trabajo para un grupo de servidores con más de 300 flujos de trabajo, la página web tardará mucho tiempo en cargarse.</span><span class="sxs-lookup"><span data-stu-id="579c0-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="579c0-108">El número de agentes que se asocian de forma indirecta con flujos de trabajo a través de las colas también tiene un efecto proporcional en la carga de la página.</span><span class="sxs-lookup"><span data-stu-id="579c0-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="579c0-109">Los temas de esta sección proporcionan procedimientos paso a paso para las tareas que puede realizar para personalizar y mantener la aplicación de grupo de respuesta en su implementación</span><span class="sxs-lookup"><span data-stu-id="579c0-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="579c0-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="579c0-110">In This Section</span></span>

  - [<span data-ttu-id="579c0-111">Administración de grupos de agentes de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="579c0-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="579c0-112">Administración de colas de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="579c0-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="579c0-113">Administración de flujos de trabajo de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="579c0-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="579c0-114">Administración de la configuración del grupo de respuesta de nivel de aplicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="579c0-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="579c0-115">Mover grupos de respuesta a un nuevo grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="579c0-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="579c0-116">Administración de grupos de respuesta en Lync Server 2013 durante un desastre</span><span class="sxs-lookup"><span data-stu-id="579c0-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


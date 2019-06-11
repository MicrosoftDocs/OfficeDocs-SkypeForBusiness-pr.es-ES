---
title: 'Lync Server 2013: Configurar grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4d12d1ee21cfa5e480dea52a0de9f89b250715c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="97d10-102">Configurar grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97d10-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="97d10-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="97d10-104">El grupo de respuesta es una característica de voz de empresa que enruta y pone en cola las llamadas entrantes a grupos de personas, denominados *agentes*, como un servicio de asistencia o un servicio de asistencia al cliente.</span><span class="sxs-lookup"><span data-stu-id="97d10-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="97d10-105">Los componentes que requiere el grupo de respuesta se instalan y se habilitan automáticamente en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="97d10-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="97d10-106">Para que los usuarios puedan disponer de un grupo de respuesta, debe configurar grupos de agentes, después colas y, por último, flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97d10-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="97d10-107">Además, un administrador de grupo de respuesta puede delegar la configuración de un flujo de trabajo existente a un administrador de grupo de respuesta, que podrá modificar y volver a configurar el flujo de trabajo y sus grupos de agentes y colas relacionados.</span><span class="sxs-lookup"><span data-stu-id="97d10-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="97d10-108">Esta sección le guiará a través de la configuración del grupo de respuesta 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97d10-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="97d10-109">Se supone que ya ha leído las secciones de planificación relacionadas con el grupo de respuesta y ha implementado un servidor Enterprise Edition o un servidor Standard Edition con telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="97d10-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="97d10-110">Para obtener detalles acerca de la creación de un grupo de respuesta mediante el shell de administración de Lync Server, incluido un script de ejemplo, consulte "crear su primer grupo <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>de respuesta con el shell de administración de Lync Server" en.</span><span class="sxs-lookup"><span data-stu-id="97d10-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97d10-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="97d10-111">In This Section</span></span>

  - [<span data-ttu-id="97d10-112">Permisos y requisitos previos de configuración de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="97d10-113">Proceso de implementación para un grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="97d10-114">Resumen de escenarios de creación de flujo de trabajo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="97d10-115">Crear grupos de agentes de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="97d10-116">Crear colas de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="97d10-117">Faculta Definir las horas de trabajo del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="97d10-118">Faculta Definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="97d10-119">Crear flujos de trabajo de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="97d10-120">Faculta Comprobar la implementación de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97d10-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="97d10-121">See Also</span></span>


[<span data-ttu-id="97d10-122">Planeamiento de las características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


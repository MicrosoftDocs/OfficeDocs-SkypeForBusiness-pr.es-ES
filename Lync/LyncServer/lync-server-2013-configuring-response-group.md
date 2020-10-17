---
title: 'Lync Server 2013: configuración del grupo de respuesta'
description: 'Lync Server 2013: configuración del grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547936"
---
# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="fde98-103">Configuración del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-103">Configuring Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fde98-104">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="fde98-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="fde98-105">El grupo de respuesta es una característica de Enterprise Voice que enruta y pone en cola las llamadas entrantes a grupos de personas, denominados *agentes*, como un servicio de asistencia o un servicio de atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="fde98-105">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="fde98-106">Los componentes que necesita el grupo de respuesta se instalan y se habilitan automáticamente en el servidor front-end o servidor Standard Edition al implementar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fde98-106">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fde98-107">Para que el grupo de respuesta esté disponible para los usuarios, debe configurar los grupos de agentes; a continuación, las colas y, por último, los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fde98-107">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="fde98-108">Además, un administrador de grupo de respuesta puede delegar la configuración de un flujo de trabajo existente a un administrador de grupo de respuesta, que puede modificar y volver a configurar el flujo de trabajo y sus grupos de agentes y colas asociados.</span><span class="sxs-lookup"><span data-stu-id="fde98-108">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="fde98-109">Esta sección le guiará a través de la configuración del grupo de respuesta 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fde98-109">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="fde98-110">Se da por hecho que ya ha leído las secciones de planeación relacionadas con el grupo de respuesta y que ha implementado un servidor Enterprise Edition o un servidor Standard Edition con telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fde98-110">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="fde98-111">Para obtener información detallada sobre cómo crear un grupo de respuesta mediante el shell de administración de Lync Server, incluido un script de ejemplo, consulte "creación del primer grupo de respuesta con el shell de administración de Lync Server" en <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> .</span><span class="sxs-lookup"><span data-stu-id="fde98-111">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fde98-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fde98-112">In This Section</span></span>

  - [<span data-ttu-id="fde98-113">Permisos y requisitos previos de configuración de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-113">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="fde98-114">Proceso de implementación del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-114">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="fde98-115">Información general sobre los escenarios de creación de flujos de trabajo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-115">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="fde98-116">Crear grupos de agentes de grupo de respuesta Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-116">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="fde98-117">Crear colas de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-117">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="fde98-118">Opcional Definir el horario comercial del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-118">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="fde98-119">Opcional Definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-119">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="fde98-120">Crear flujos de trabajo de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-120">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="fde98-121">Opcional Comprobar la implementación del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-121">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fde98-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fde98-122">See Also</span></span>


[<span data-ttu-id="fde98-123">Planeación de características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde98-123">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


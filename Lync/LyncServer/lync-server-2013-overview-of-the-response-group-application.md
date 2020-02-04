---
title: 'Lync Server 2013: información general sobre la aplicación de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b01181296a42f786a4739b5ec59d775212baaf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="75dc4-102">Información general de la aplicación de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75dc4-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75dc4-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="75dc4-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="75dc4-104">Cuando el autor de una llamada llama a un grupo de respuesta, la llamada se redirige a un agente de acuerdo con un grupo de extensiones o las respuestas del autor de la llamada frente a las preguntas de la respuesta interactiva de voz (IVR).</span><span class="sxs-lookup"><span data-stu-id="75dc4-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="75dc4-105">La aplicación de grupo de respuesta usa métodos de enrutamiento de grupo de respuesta estándar para dirigir la llamada al siguiente agente disponible.</span><span class="sxs-lookup"><span data-stu-id="75dc4-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="75dc4-106">Los métodos de enrutamiento de llamadas incluyen el enrutamiento en serie, más tiempo de inactividad, paralelo, Round Robin y operador (es decir, se llama a todos los agentes al mismo tiempo para todas las llamadas entrantes, independientemente de su presencia actual).</span><span class="sxs-lookup"><span data-stu-id="75dc4-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="75dc4-107">Si no hay ningún agente disponible, la llamada se mantiene en una cola hasta que haya alguno.</span><span class="sxs-lookup"><span data-stu-id="75dc4-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="75dc4-108">Mientras se encuentra en la cola, el autor de la llamada escucha música hasta que un agente disponible acepte la llamada.</span><span class="sxs-lookup"><span data-stu-id="75dc4-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="75dc4-109">Si la cola está llena o la llamada supera el tiempo de espera mientras está en la cola, es posible que la persona que llama oiga un mensaje y, después, se desconecte o se transfiera a un destino diferente.</span><span class="sxs-lookup"><span data-stu-id="75dc4-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="75dc4-110">Cuando un agente acepta la llamada, el autor de la llamada puede ver o no la identidad del agente, en función de cómo haya configurado el administrador el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="75dc4-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="75dc4-111">Los agentes pueden ser formales, lo que significa que necesitan iniciar sesión en el grupo para poder aceptar las llamadas redirigidas al grupo, o bien informales, lo que significa que no es necesario que inicien sesión y finalicen sesión en el grupo para aceptar llamadas.</span><span class="sxs-lookup"><span data-stu-id="75dc4-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75dc4-112">Solo los usuarios locales pueden ser agentes.</span><span class="sxs-lookup"><span data-stu-id="75dc4-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="75dc4-113">Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.</span><span class="sxs-lookup"><span data-stu-id="75dc4-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="75dc4-114">La aplicación de grupo de respuesta usa un servicio interno, denominado creación de coincidencias, para poner en cola las llamadas y buscar agentes disponibles.</span><span class="sxs-lookup"><span data-stu-id="75dc4-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="75dc4-115">Cada equipo que ejecuta la aplicación de grupo de respuesta ejecuta la función coincidir con el servicio, pero solo se activa una coincidencia con el servicio por grupo de servidores de Lync.</span><span class="sxs-lookup"><span data-stu-id="75dc4-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="75dc4-116">Si el servicio de contactos activo deja de estar disponible durante una interrupción no planificada, se activará uno de los servicios de contactos pasivos.</span><span class="sxs-lookup"><span data-stu-id="75dc4-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="75dc4-117">La aplicación de grupo de respuesta hace todo lo posible para asegurarse de que el enrutamiento de llamadas y la cola no se interrumpan.</span><span class="sxs-lookup"><span data-stu-id="75dc4-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="75dc4-118">Pero, cuando se produce la transición del servicio de contactos, todas las llamadas que se están transfiriendo en ese momento se pierden.</span><span class="sxs-lookup"><span data-stu-id="75dc4-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="75dc4-119">Por ejemplo, si la transición se debe a que el servidor de aplicaciones para el usuario se baja, también se perderán las llamadas que el servicio de coincidencia activo en ese servidor de Front-End está administrando actualmente.</span><span class="sxs-lookup"><span data-stu-id="75dc4-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="75dc4-120">En Lync Server 2013, hay dos roles de administración disponibles para administrar grupos de respuesta: administrador de grupos de respuesta y administrador de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="75dc4-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="75dc4-121">Los administradores de grupos de respuesta pueden administrar cualquier aspecto de cualquier grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="75dc4-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="75dc4-122">Los administradores de grupos de respuesta solo pueden administrar determinados aspectos, y solo para los grupos de respuesta de los que son propietarios.</span><span class="sxs-lookup"><span data-stu-id="75dc4-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="75dc4-123">La nueva función de administrador puede ayudar a reducir los costos de administración, ya que puede delegar responsabilidades limitadas para grupos de respuesta específicos a cualquier usuario que tenga habilitada la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="75dc4-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="75dc4-124">Para dar cabida a la nueva función de administrador, la aplicación de grupo de respuesta de Lync Server 2013 introduce un **tipo de flujo de trabajo** administrado o no administrado.</span><span class="sxs-lookup"><span data-stu-id="75dc4-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="75dc4-125">En la tabla siguiente se describen los grupos de respuesta administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="75dc4-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="75dc4-126">Grupos de respuesta administrados y no administrados</span><span class="sxs-lookup"><span data-stu-id="75dc4-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75dc4-127">Tipo de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="75dc4-127">Response group type</span></span></th>
<th><span data-ttu-id="75dc4-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="75dc4-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75dc4-129">No administrado</span><span class="sxs-lookup"><span data-stu-id="75dc4-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="75dc4-130">Los grupos de respuesta no administrados no tienen ningún director asignado.</span><span class="sxs-lookup"><span data-stu-id="75dc4-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="75dc4-131">Solo el administrador del grupo de respuesta puede configurar estos grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="75dc4-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="75dc4-132">Varios grupos de respuesta no administrados pueden compartir un grupo de agentes o una cola.</span><span class="sxs-lookup"><span data-stu-id="75dc4-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="75dc4-133">Al migrar grupos de respuesta de una versión anterior a Lync Server 2013, el tipo se establece en no administrado.</span><span class="sxs-lookup"><span data-stu-id="75dc4-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75dc4-134">Administrado</span><span class="sxs-lookup"><span data-stu-id="75dc4-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="75dc4-135">Los administradores de grupos de respuesta pueden configurar cualquier aspecto de los grupos de respuesta administrados.</span><span class="sxs-lookup"><span data-stu-id="75dc4-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="75dc4-136">Los administradores de grupos de respuesta no pueden ver ni modificar grupos de respuesta que no estén asignados de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="75dc4-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="75dc4-137">Los administradores de grupos de respuesta solo pueden configurar algunos valores para los grupos de respuesta que se les hayan asignado explícitamente.</span><span class="sxs-lookup"><span data-stu-id="75dc4-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="75dc4-138">Los grupos de respuesta administrados no pueden compartir grupos de agentes ni colas con otros grupos de respuesta, ya sean administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="75dc4-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75dc4-139">En la siguiente tabla se describen las acciones que los administradores de grupos de respuesta pueden o no pueden realizar para los grupos de respuesta que tengan asignados.</span><span class="sxs-lookup"><span data-stu-id="75dc4-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="75dc4-140">Capacidades del director del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="75dc4-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75dc4-141">Puede configurar:</span><span class="sxs-lookup"><span data-stu-id="75dc4-141">Can configure:</span></span></th>
<th><span data-ttu-id="75dc4-142">Puede crear, eliminar o configurar:</span><span class="sxs-lookup"><span data-stu-id="75dc4-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="75dc4-143">No puede:</span><span class="sxs-lookup"><span data-stu-id="75dc4-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="75dc4-144">Agentes</span><span class="sxs-lookup"><span data-stu-id="75dc4-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="75dc4-145">Mensajes de bienvenida</span><span class="sxs-lookup"><span data-stu-id="75dc4-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="75dc4-146">Nombre del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="75dc4-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="75dc4-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="75dc4-147">Description</span></span></p></li>
<li><p><span data-ttu-id="75dc4-148">Número para mostrar</span><span class="sxs-lookup"><span data-stu-id="75dc4-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="75dc4-149">Horario comercial</span><span class="sxs-lookup"><span data-stu-id="75dc4-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="75dc4-150">Música en espera</span><span class="sxs-lookup"><span data-stu-id="75dc4-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="75dc4-151">Estado (activo/inactivo)</span><span class="sxs-lookup"><span data-stu-id="75dc4-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="75dc4-152">Flujos de trabajo del grupo de extensiones o flujos de trabajo de la respuesta interactiva de voz (IVR)</span><span class="sxs-lookup"><span data-stu-id="75dc4-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="75dc4-153">Grupos de agentes</span><span class="sxs-lookup"><span data-stu-id="75dc4-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="75dc4-154">Colas</span><span class="sxs-lookup"><span data-stu-id="75dc4-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="75dc4-155">Conjuntos de vacaciones</span><span class="sxs-lookup"><span data-stu-id="75dc4-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="75dc4-156">Crear o eliminar ningún tipo de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="75dc4-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="75dc4-157">Modificar la configuración principal de los grupos de respuesta, como el <strong>URI de SIP</strong>, el <strong>número de teléfono</strong> o el <strong>tipo de flujo de trabajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="75dc4-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75dc4-158">Los administradores de grupos de respuesta pueden usar las siguientes herramientas para administrar los grupos de respuesta designados.</span><span class="sxs-lookup"><span data-stu-id="75dc4-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="75dc4-159">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="75dc4-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75dc4-160">Los administradores de grupos de respuesta solo pueden administrar la configuración del grupo de respuesta con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="75dc4-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="75dc4-161">Otras opciones de configuración de Lync Server no están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="75dc4-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="75dc4-162">Herramienta de configuración de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="75dc4-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="75dc4-163">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="75dc4-163">Lync Server Management Shell</span></span>

<span data-ttu-id="75dc4-164">El grupo de respuesta se adapta bien a entornos departamentales o de grupo de trabajo (para obtener información detallada, consulte [planear la capacidad de un grupo de respuesta en Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) y puede implementarse en instalaciones de telefonía completamente nuevas.</span><span class="sxs-lookup"><span data-stu-id="75dc4-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="75dc4-165">Es compatible con las llamadas entrantes desde la implementación de telefonía IP empresarial y desde la red del operador local.</span><span class="sxs-lookup"><span data-stu-id="75dc4-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="75dc4-166">Los agentes pueden usar Lync 2013, Lync 2010, operador de Lync 2010 o Lync Phone Edition para tomar las llamadas dirigidas a ellos.</span><span class="sxs-lookup"><span data-stu-id="75dc4-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="75dc4-167">La aplicación de grupo de respuesta es un componente de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="75dc4-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="75dc4-168">Al implementar la telefonía IP empresarial, la aplicación de grupo de respuesta se instala y activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="75dc4-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


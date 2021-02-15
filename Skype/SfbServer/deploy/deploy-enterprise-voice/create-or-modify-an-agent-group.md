---
title: Crear o modificar un grupo de agentes en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Cree o modifique un grupo de agentes en Grupo de respuesta, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: dfa09c3341ad47f2646939738cb67db7b7f27304
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837100"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="7608f-103">Crear o modificar un grupo de agentes en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="7608f-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="7608f-104">Cree o modifique un grupo de agentes en Grupo de respuesta, en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="7608f-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7608f-105">Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7608f-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="7608f-106">Un agente que debe iniciar y cerrar sesión en el grupo, que es diferente de iniciar o cerrar sesión en Skype Empresarial, se denomina agente formal.</span><span class="sxs-lookup"><span data-stu-id="7608f-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="7608f-107">Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo.</span><span class="sxs-lookup"><span data-stu-id="7608f-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="7608f-108">Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada.</span><span class="sxs-lookup"><span data-stu-id="7608f-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="7608f-109">Los agentes formales inician y cierran sesión en sus grupos haciendo clic en un elemento de menú en Skype Empresarial para abrir el explorador Internet Explorer de Windows y mostrar una consola de página web.</span><span class="sxs-lookup"><span data-stu-id="7608f-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="7608f-110">Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de agente informal.</span><span class="sxs-lookup"><span data-stu-id="7608f-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="7608f-111">Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Skype Empresarial y no pueden cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7608f-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="7608f-p103">Solo los usuarios locales pueden ser agentes. Si un agente deja de ser local para estar en línea, las llamadas al grupo de respuesta no se enrutarán a dicho agente.</span><span class="sxs-lookup"><span data-stu-id="7608f-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="7608f-114">Use uno de los siguientes procedimientos para crear o modificar un grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="7608f-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7608f-p104">Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="7608f-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="7608f-118">Para usar el Panel de control de Skype Empresarial Server para crear o modificar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="7608f-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="7608f-119">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7608f-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7608f-120">Si es uno de los administradores delegados de grupos de respuesta para un flujo de trabajo administrado, puede crear grupos y usarlos en los flujos de trabajo que administra.</span><span class="sxs-lookup"><span data-stu-id="7608f-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="7608f-121">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7608f-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7608f-122">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="7608f-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="7608f-123">En la **página** Grupo, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7608f-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="7608f-124">Para crear un nuevo grupo de agentes, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7608f-124">To create a new agent group, click **New**.</span></span> <span data-ttu-id="7608f-125">En el **campo Seleccionar un servicio** de búsqueda, escriba todo o parte del nombre del servicio **ApplicationServer** al que desea agregar el grupo.</span><span class="sxs-lookup"><span data-stu-id="7608f-125">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="7608f-126">En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7608f-126">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="7608f-127">Para modificar un grupo de agentes existente, escriba todo o parte del nombre del grupo de agentes en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7608f-127">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="7608f-128">En la lista resultante, haga clic en el grupo que desee, haga clic en **Editar** y, a continuación, en **Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="7608f-128">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7608f-129">En **Nombre,** escriba un nombre identificativo para el grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="7608f-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="7608f-130">En **Descripción**, escriba una descripción para el grupo.</span><span class="sxs-lookup"><span data-stu-id="7608f-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="7608f-131">En **Directiva de participación**, elija uno de estos procedimientos para configurar el comportamiento de conexión al grupo:</span><span class="sxs-lookup"><span data-stu-id="7608f-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="7608f-132">Seleccione **Informal** para especificar que los agentes del grupo no necesitan iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7608f-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="7608f-133">Los agentes inician sesión automáticamente en el grupo cuando inician sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="7608f-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="7608f-134">Para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo, haga clic en **Formal**.</span><span class="sxs-lookup"><span data-stu-id="7608f-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="7608f-135">Al seleccionar esta opción, los agentes hacen clic en un elemento de menú en Skype Empresarial para abrir Internet Explorer y mostrar una consola de página web para iniciar y salir del grupo.</span><span class="sxs-lookup"><span data-stu-id="7608f-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="7608f-136">En **Tiempo de alerta (segundos)**, especifique los segundos que va a sonar la llamada de un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es 20 segundos).</span><span class="sxs-lookup"><span data-stu-id="7608f-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7608f-137">La configuración del tiempo de alerta del agente no puede superar los 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="7608f-137">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="7608f-138">Si el tiempo de alerta del agente supera los 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de transacciones SIP alcanza su tiempo de espera máximo.</span><span class="sxs-lookup"><span data-stu-id="7608f-138">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="7608f-139">En **Método de enrutamiento**, seleccione un método para enrutar las llamadas a los agentes del grupo, según se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="7608f-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="7608f-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the **longest),** click Longest idle .</span><span class="sxs-lookup"><span data-stu-id="7608f-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="7608f-p110">Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **Enrutamiento en paralelo**. La llamada se envía al primer agente que la acepta.</span><span class="sxs-lookup"><span data-stu-id="7608f-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="7608f-143">Para ofrecer una nueva llamada a un agente cada vez, haga clic en **Round robin**.</span><span class="sxs-lookup"><span data-stu-id="7608f-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="7608f-144">Para ofrecer siempre una llamada a los agentes en el orden en que aparecen en la lista **Agente**, haga clic en **Enrutamiento en serie**.</span><span class="sxs-lookup"><span data-stu-id="7608f-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="7608f-145">Para ofrecer una nueva llamada a todos los agentes que han iniciado sesión en Skype Empresarial y en la aplicación grupo de respuesta al mismo tiempo, independientemente de su presencia actual, haga clic en **Operador**.</span><span class="sxs-lookup"><span data-stu-id="7608f-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="7608f-146">Los usuarios que están configurados como agentes pueden ver todas las llamadas que están en espera y responder llamadas en espera en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="7608f-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="7608f-147">La llamada se envía al primer agente que la acepta, tras lo cual los demás agentes ya no ven la llamada.</span><span class="sxs-lookup"><span data-stu-id="7608f-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="7608f-148">En la ficha **Agentes**, especifique el modo en que desea crear la lista de agentes:</span><span class="sxs-lookup"><span data-stu-id="7608f-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="7608f-149">Para usar una lista personalizada de agentes, haga clic en Definir **un grupo** personalizado de agentes y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7608f-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="7608f-150">Para agregar un usuario al grupo de agentes,  haga clic en Seleccionar y, a continuación, en el campo de búsqueda Seleccionar agentes, escriba todo o parte del nombre del usuario que desea agregar a este grupo y, a continuación, haga clic en Buscar **.**</span><span class="sxs-lookup"><span data-stu-id="7608f-150">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="7608f-151">En la lista de agentes resultante, haga clic en el usuario y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="7608f-151">In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="7608f-152">Para quitar un usuario del grupo de agentes, en la lista de agentes, haga clic en el usuario que desea quitar y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="7608f-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="7608f-153">Para cambiar el orden en que se ofrecen llamadas a los agentes en grupos que usan enrutamiento por turnos o enrutamiento en serie, en la lista de agentes, haga clic en un usuario y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="7608f-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="7608f-154">Para usar una lista de distribución de Microsoft Exchange Server como grupo de agentes, haga clic en Usar una lista de distribución de correo electrónico existente y, a continuación, en Dirección de lista de **distribución,** escriba la dirección de correo electrónico de la lista de distribución (por ejemplo, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7608f-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="7608f-155">Si usa una lista de distribución de correo electrónico, se aplican las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7608f-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="7608f-p113">No se pueden seleccionar varias listas de distribución para el grupo de agentes. Cada grupo solo admite una lista de distribución única.</span><span class="sxs-lookup"><span data-stu-id="7608f-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="7608f-158">Si la lista de distribución contiene una o varias listas de distribución, los miembros de las listas de distribución anidadas no se agregan a la lista de agentes.</span><span class="sxs-lookup"><span data-stu-id="7608f-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="7608f-159">Si se selecciona el enrutamiento en serie o round robin, el servidor ofrece una llamada entrante al agente adecuado de acuerdo con el método de enrutamiento y según el orden en que los agentes aparecen en la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="7608f-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="7608f-160">Si la lista de distribución contiene usuarios para los que Lync Server 2010 está habilitado pero Telefonía IP empresarial no está habilitado, se agregarán al grupo de agentes como agentes disfuncionales.</span><span class="sxs-lookup"><span data-stu-id="7608f-160">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="7608f-161">Asegúrese de que todos los miembros de la lista de distribución Telefonía IP empresarial habilitadas para sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="7608f-161">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7608f-162">Si usa una lista de distribución de correo electrónico, las pertenencias ocultas o las listas ocultas podrían ser visibles para el administrador o los usuarios del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7608f-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="7608f-163">Las pertenencias ocultas o las listas ocultas pueden quedar visibles en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7608f-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="7608f-164">Si se configuró una lista de distribución para que la pertenencia esté oculta y el administrador del grupo de respuesta asigne la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para averiguar quiénes son los miembros.</span><span class="sxs-lookup"><span data-stu-id="7608f-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="7608f-165">Si se configuró una lista de distribución para que esté oculta en la lista global de direcciones de Exchange, es posible que el administrador del grupo de respuesta pueda ver la lista de distribución y asignarla a la lista de agentes si el proceso de grupo de respuesta tiene los permisos y derechos de usuario adecuados, incluso si el administrador no tiene los permisos y derechos de usuario adecuados.</span><span class="sxs-lookup"><span data-stu-id="7608f-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="7608f-166">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7608f-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="7608f-167">Para usar el Shell de administración de Skype Empresarial Server para crear o modificar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="7608f-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="7608f-168">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7608f-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="7608f-169">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="7608f-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7608f-170">Use **New-CsRgsAgentGroup para** crear un nuevo grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="7608f-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="7608f-171">Use **Set-CsRgsAgentGroup para** modificar un grupo de agentes existente.</span><span class="sxs-lookup"><span data-stu-id="7608f-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="7608f-172">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="7608f-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="7608f-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7608f-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="7608f-174">La configuración del tiempo de alerta del agente no puede superar los 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="7608f-174">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="7608f-175">Si el tiempo de alerta del agente es superior a 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de transacciones SIP alcanza su tiempo de espera máximo.</span><span class="sxs-lookup"><span data-stu-id="7608f-175">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="7608f-176">Confirme que se ha creado el grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="7608f-176">Confirm that the agent group is created.</span></span> <span data-ttu-id="7608f-177">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="7608f-177">Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="7608f-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="7608f-178">See also</span></span>

[<span data-ttu-id="7608f-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="7608f-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="7608f-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7608f-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="7608f-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7608f-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="7608f-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7608f-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)

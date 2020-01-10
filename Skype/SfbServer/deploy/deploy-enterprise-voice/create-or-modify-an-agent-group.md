---
title: Crear o modificar un grupo de agentes en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Crear o modificar un grupo de agentes en el grupo respuesta de Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: a919c1a25f3f4aa5a2d8648d782ea329f1e70d60
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001690"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="7f7fe-103">Crear o modificar un grupo de agentes en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="7f7fe-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="7f7fe-104">Crear o modificar un grupo de agentes en el grupo respuesta de Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7f7fe-105">Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="7f7fe-106">Un agente que debe iniciar y cerrar sesión en el grupo, lo cual difiere de la sesión o de Skype empresarial, se denomina agente formal.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="7f7fe-107">Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="7f7fe-108">Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="7f7fe-109">Agentes formales inicie y cierre sesión en sus grupos haciendo clic en un elemento de menú de Skype empresarial para abrir el explorador de Internet de Windows Internet Explorer y mostrar una consola de página web.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="7f7fe-110">Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de  agente informal.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="7f7fe-111">Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Skype empresarial y no pueden cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="7f7fe-112">Solo los usuarios locales pueden ser agentes.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="7f7fe-113">Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="7f7fe-114">Use uno de los procedimientos siguientes para crear o modificar un grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7f7fe-p104">Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="7f7fe-118">Para usar el panel de control de Skype empresarial Server para crear o modificar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="7f7fe-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="7f7fe-119">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f7fe-120">Si es uno de los administradores del grupo de respuesta delegado de un flujo de trabajo administrado, podrá crear grupos y asignarlos a los flujos de trabajo que administre.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="7f7fe-121">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7f7fe-122">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, haga clic en **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="7f7fe-123">En la página **Grupo**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="7f7fe-p105">Para crear un grupo de agente nuevo, haga clic en **Nuevo**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre completo o una parte del servicio **ApplicationServer** para el que desea añadir el grupo. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="7f7fe-p106">Para modificar un grupo de agentes existentes, en el campo de búsqueda, escriba el nombre completo o una parte del grupo de agentes. En la lista de resultados, haga clic en el grupo que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7f7fe-129">En **Nombre**, escriba un nombre de identificación para el grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="7f7fe-130">En **Descripción**, escriba una descripción para el grupo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="7f7fe-131">En la **Directiva de participación**, seleccione una de las siguientes opciones para configurar el comportamiento de inicio de sesión en el grupo:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="7f7fe-132">Seleccione **Informal** para especificar que los agentes del grupo no tienen que iniciar ni cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="7f7fe-133">Los agentes inician sesión automáticamente en el grupo cuando inician sesión en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="7f7fe-134">Seleccione **Formal** para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="7f7fe-135">Al seleccionar esta opción, los agentes hace clic en un elemento de menú de Skype empresarial para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="7f7fe-136">En **Tiempo de alerta (segundos)**, especifique el número de segundos para llamar a un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es de 20 segundos).</span><span class="sxs-lookup"><span data-stu-id="7f7fe-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7f7fe-p109">La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo. Para evitarlo, defina el valor del tiempo de alerta en menos de 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="7f7fe-139">En **Método de enrutamiento**, seleccione el método para las llamadas de enrutamiento a los agentes en el grupo tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="7f7fe-140">Para ofrecer una nueva llamada primero al agente que haya estado inactivo el más largo ( **disponible** o **inactivo** en Skype para empresas), haga clic en **tiempo de inactividad más largo**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="7f7fe-p110">Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **En paralelo**. La llamada se envía al primer agente que la acepte.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="7f7fe-143">Para ofrecer una nueva llamada a cada agente por turnos, haga clic en **Por turnos**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="7f7fe-144">Para ofrecer una nueva llamada a los agentes según el orden en el que aparecen en la lista de **Agente**, haga clic en **En serie**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="7f7fe-145">Para ofrecer una nueva llamada a todos los agentes que han iniciado sesión en Skype empresarial y la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual, haga clic en **operador**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="7f7fe-146">Los usuarios configurados como agentes pueden ver todas las llamadas y responder a las llamadas en espera en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="7f7fe-147">La llamada se envía al primer agente que la acepta, y a partir de ese momento los demás agentes ya no pueden ver la llamada.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="7f7fe-148">En **Agentes**, especifique cómo desea crear su lista de agentes:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="7f7fe-149">Para usar una lista personalizada de agentes, haga clic en **Definir un grupo personalizado de agentes** y, a continuación, realice uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="7f7fe-p112">Para agregar un usuario al grupo de agentes, haga clic en **Seleccionar** y, a continuación, en el campo de búsqueda **Seleccionar agentes**, escriba el nombre completo o una parte del usuario que desea agregar a este grupo y haga clic en **Buscar**. En la lista de resultados, haga clic en el usuario y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="7f7fe-152">Para quitar a un usuario de un grupo de agentes, en la lista de agentes, seleccione el usuario que desea quitar y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="7f7fe-153">Para cambiar el orden en el que se ofrecen llamadas a los agentes de los grupos que usan el enrutamiento por turnos (round robin) o en serie, en la lista de agentes, haga clic en un usuario y, a continuación, seleccione la flecha hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="7f7fe-154">Para utilizar una lista de distribución de Microsoft Exchange Server, haga clic en **Usar una lista de distribución de correo electrónico existente** y, a continuación, en **Dirección de lista de distribución**, escriba la dirección de correo electrónico de la lista de distribución (por ejemplo, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7f7fe-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="7f7fe-155">Si usa una lista de distribución de correo electrónico, se aplican las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="7f7fe-p113">No puede seleccionar varias listas de distribución para el grupo de agentes. Cada grupo admite solo una única lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="7f7fe-158">Si la lista de distribución contiene una o más listas de distribución, los miembros de las listas de distribución anidadas no se agregan a la lista de agentes.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="7f7fe-159">Si se selecciona un enrutamiento en serie y por turnos o round robin, el servidor ofrece una llamada de entrada al agente apropiado de acuerdo con el método de enrutamiento y de acuerdo con el orden en el que los agentes aparecen en la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="7f7fe-p114">Si la lista de distribución contiene usuarios para los que Lync Server 2010 está habilitado, pero la telefonía IP empresarial no, se agregarán al grupo de agentes como agentes disfuncionales. Asegúrese de que todos los miembros de la lista de distribución tengan la Telefonía IP empresarial habilitada en sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7f7fe-162">Si usa una lista de distribución de correo electrónico, las suscripciones ocultas o las listas ocultas podrían hacerse visibles para el administrador del grupo de respuesta o los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="7f7fe-163">Los miembros ocultos o las listas ocultas se pueden convertir en visibles de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="7f7fe-164">Si una lista de distribución se configuró de modo que la pertenencia está oculta y el administrador del grupo de respuesta asigna la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para averiguar quiénes son los miembros.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="7f7fe-165">Si se ha configurado una lista de distribución de modo que se oculte en la lista global de direcciones de Exchange, es posible que el administrador del grupo de respuesta pueda ver la lista de distribución y asignarla a la lista de agentes si el proceso de grupo de respuesta tiene los derechos de usuario apropiados y permisos, incluso si el administrador no tiene los derechos de usuario y los permisos apropiados.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="7f7fe-166">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="7f7fe-167">Para usar el shell de administración de Skype empresarial para crear o modificar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="7f7fe-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="7f7fe-168">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="7f7fe-169">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7f7fe-170">Use **New-CsRgsAgentGroup** para crear un grupo de agentes nuevo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="7f7fe-171">Use **Set-CsRgsAgentGroup** para modificar un grupo de agentes existente.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="7f7fe-172">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="7f7fe-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="7f7fe-p116">La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo.</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="7f7fe-p117">Confirme que el grupo de agentes se ha creado. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="7f7fe-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="7f7fe-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f7fe-178">See also</span></span>

[<span data-ttu-id="7f7fe-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="7f7fe-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="7f7fe-180">Nuevo: CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7f7fe-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="7f7fe-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7f7fe-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="7f7fe-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7f7fe-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)

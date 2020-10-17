---
title: 'Lync Server 2013: crear o modificar un grupo de agentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 874b73af42869bc5cbe6a66b7efaf792d231b95d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525757"
---
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="0825f-102">Crear o modificar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0825f-102">Create or modify an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0825f-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="0825f-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="0825f-104">Use uno de los siguientes procedimientos para crear o modificar un grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="0825f-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0825f-105">Un administrador (por ejemplo, CsVoiceAdministrator) debe habilitar a los usuarios para telefonía IP empresarial y Lync Server antes de que los usuarios se puedan asignar a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="0825f-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="0825f-106">Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear grupos de agentes y usar los grupos de agentes en los flujos de trabajo que administre.</span><span class="sxs-lookup"><span data-stu-id="0825f-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0825f-p102">Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="0825f-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="0825f-110">Para usar el panel de control de Lync Server para crear o modificar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="0825f-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="0825f-111">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0825f-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0825f-112">Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear grupos y usarlos en los flujos de trabajo que administre.</span><span class="sxs-lookup"><span data-stu-id="0825f-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="0825f-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0825f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0825f-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0825f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0825f-115">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="0825f-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="0825f-116">En la página **Grupo** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0825f-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="0825f-117">Para crear un nuevo grupo de agentes, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0825f-117">To create a new agent group, click **New**.</span></span> <span data-ttu-id="0825f-118">En el campo de búsqueda **seleccionar un servicio** , escriba todo o parte del nombre del servicio **ApplicationServer** en el que desea agregar el grupo.</span><span class="sxs-lookup"><span data-stu-id="0825f-118">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="0825f-119">En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0825f-119">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="0825f-120">Para modificar un grupo de agentes existente, escriba todo o parte del nombre del grupo de agentes en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0825f-120">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="0825f-121">En la lista resultante, haga clic en el grupo que desee, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0825f-121">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0825f-122">En **nombre**, escriba un nombre de identificación para el grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="0825f-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="0825f-123">En **Descripción**, escriba una descripción para el grupo.</span><span class="sxs-lookup"><span data-stu-id="0825f-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="0825f-124">En **Directiva de participación**, elija uno de estos procedimientos para configurar el comportamiento de conexión al grupo:</span><span class="sxs-lookup"><span data-stu-id="0825f-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="0825f-125">Seleccione **Informal** para especificar que los agentes del grupo no necesitan iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="0825f-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="0825f-126">Los agentes inician sesión automáticamente en el grupo cuando inician sesión en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0825f-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="0825f-127">Para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo, haga clic en **Formal**.</span><span class="sxs-lookup"><span data-stu-id="0825f-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="0825f-128">Al seleccionar esta opción, los agentes hacen clic en un elemento de menú de Lync para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="0825f-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="0825f-129">En **Tiempo de alerta (segundos)**, especifique los segundos que va a sonar la llamada de un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es 20 segundos).</span><span class="sxs-lookup"><span data-stu-id="0825f-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0825f-130">La configuración del tiempo de alerta del agente no puede superar los 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="0825f-130">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="0825f-131">Si el tiempo de la alerta del agente supera los 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de la transacción SIP alcanza el tiempo de espera máximo.</span><span class="sxs-lookup"><span data-stu-id="0825f-131">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="0825f-132">En **Método de enrutamiento**, seleccione un método para enrutar las llamadas a los agentes del grupo, según se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="0825f-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="0825f-133">Para ofrecer una llamada nueva primero al agente que ha estado más tiempo inactivo (el más largo ha estado **disponible** o **inactivo** en Lync Server), haga clic en tiempo de **inactividad más largo**.</span><span class="sxs-lookup"><span data-stu-id="0825f-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="0825f-p109">Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **Enrutamiento en paralelo**. La llamada se envía al primer agente que la acepta.</span><span class="sxs-lookup"><span data-stu-id="0825f-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="0825f-136">Para ofrecer una nueva llamada a un agente cada vez, haga clic en **Round robin**.</span><span class="sxs-lookup"><span data-stu-id="0825f-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="0825f-137">Para ofrecer siempre una llamada a los agentes en el orden en que aparecen en la lista **Agente**, haga clic en **Enrutamiento en serie**.</span><span class="sxs-lookup"><span data-stu-id="0825f-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="0825f-138">Para ofrecer una nueva llamada a todos los agentes que hayan iniciado sesión en Lync Server 2013 y la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual, haga clic en **operador**.</span><span class="sxs-lookup"><span data-stu-id="0825f-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="0825f-139">Los usuarios del operador de Lync 2010 que están configurados como agentes pueden ver todas las llamadas en espera y responder a las llamadas en espera en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="0825f-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="0825f-140">La llamada se envía al primer agente que la acepta, tras lo cual los otros usuarios del operador de Lync 2010 ya no verán la llamada.</span><span class="sxs-lookup"><span data-stu-id="0825f-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="0825f-141">En la ficha **Agentes**, especifique el modo en que desea crear la lista de agentes:</span><span class="sxs-lookup"><span data-stu-id="0825f-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="0825f-142">Para usar una lista personalizada de agentes, haga clic en **definir un grupo personalizado de agentes**y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0825f-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="0825f-143">Para agregar un usuario al grupo de agentes, haga clic en **seleccionar**y, a continuación, en el campo de búsqueda **seleccionar agentes** , escriba todo o parte del nombre del usuario que desea agregar a este grupo y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0825f-143">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="0825f-144">En la lista de agentes resultante, haga clic en el usuario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0825f-144">In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="0825f-145">Para quitar un usuario del grupo de agentes, en la lista de agentes, haga clic en el usuario que desea quitar y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="0825f-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="0825f-146">Para cambiar el orden en el que se ofrecen las llamadas a los agentes en los grupos que usan el enrutamiento Round Robin o el enrutamiento en serie, en la lista de agentes, haga clic en un usuario y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="0825f-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="0825f-147">Para usar una lista de distribución de Microsoft Exchange Server como grupo de agentes, haga clic en **usar una lista de distribución de correo electrónico existente**y, a continuación, en dirección de la **lista de distribución**, escriba la dirección de correo electrónico de la lista de distribución (por ejemplo, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0825f-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="0825f-148">Si usa una lista de distribución de correo electrónico, se aplican las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0825f-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="0825f-p112">No se pueden seleccionar varias listas de distribución para el grupo de agentes. Cada grupo solo admite una lista de distribución única.</span><span class="sxs-lookup"><span data-stu-id="0825f-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="0825f-151">Si la lista de distribución contiene una o varias listas de distribución, los miembros de las listas de distribución anidadas no se agregan a la lista de agentes.</span><span class="sxs-lookup"><span data-stu-id="0825f-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="0825f-152">Si se selecciona el enrutamiento en serie o Round Robin, el servidor ofrece una llamada entrante al agente apropiado de acuerdo con el método de enrutamiento y según el orden en el que los agentes aparecen en la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="0825f-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="0825f-153">Si la lista de distribución contiene los usuarios para los que Lync Server 2010 está habilitado, pero Enterprise Voice no está habilitado, se agregará al grupo de agentes como agentes disfuncionales.</span><span class="sxs-lookup"><span data-stu-id="0825f-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="0825f-154">Asegúrese de que todos los miembros de la lista de distribución tienen habilitada la telefonía IP empresarial para sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="0825f-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="0825f-155">Si usa una lista de distribución de correo electrónico, las pertenencias ocultas o las listas ocultas pueden ser visibles para el administrador del grupo de respuesta o los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0825f-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="0825f-156">Las pertenencias ocultas o las listas ocultas pueden quedar visibles en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0825f-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="0825f-157">Si se ha configurado una lista de distribución para que la pertenencia esté oculta y el administrador del grupo de respuesta asigna la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para averiguar quiénes son los miembros.</span><span class="sxs-lookup"><span data-stu-id="0825f-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="0825f-158">Si se ha configurado una lista de distribución para que quede oculta en la lista global de direcciones de Exchange, es posible que el administrador del grupo de respuesta pueda ver la lista de distribución y asignarla a la lista de agentes si el proceso del grupo de respuesta tiene los derechos y permisos de usuario adecuados, incluso si el administrador no tiene los permisos y derechos de usuario adecuados.</span><span class="sxs-lookup"><span data-stu-id="0825f-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="0825f-159">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0825f-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="0825f-160">Para usar Windows PowerShell para crear o modificar un grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="0825f-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="0825f-161">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0825f-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="0825f-162">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0825f-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0825f-163">Use **New-CsRgsAgentGroup** para crear un nuevo grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="0825f-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="0825f-164">Use **set-CsRgsAgentGroup** para modificar un grupo de agentes existente.</span><span class="sxs-lookup"><span data-stu-id="0825f-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="0825f-165">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0825f-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="0825f-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0825f-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0825f-167">La configuración del tiempo de alerta del agente no puede superar los 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="0825f-167">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="0825f-168">Si la hora de la alerta del agente es superior a 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de la transacción SIP alcanza el tiempo de espera máximo.</span><span class="sxs-lookup"><span data-stu-id="0825f-168">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="0825f-169">Confirme que se ha creado el grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="0825f-169">Confirm that the agent group is created.</span></span> <span data-ttu-id="0825f-170">Realizar</span><span class="sxs-lookup"><span data-stu-id="0825f-170">Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0825f-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0825f-171">See Also</span></span>


[<span data-ttu-id="0825f-172">Eliminar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0825f-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="0825f-173">Administración de grupos de agentes de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0825f-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="0825f-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="0825f-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="0825f-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="0825f-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="0825f-176">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="0825f-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="0825f-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="0825f-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


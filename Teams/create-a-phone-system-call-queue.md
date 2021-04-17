---
title: Crear una cola de llamadas en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar Sistema telefónico para las colas de llamadas con Microsoft Teams, que proporciona un mensaje de saludo, música en espera, redirección de llamadas y otras características.
ms.openlocfilehash: 1202de31beddb8f70391d40d4e6218942c59cba1
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874456"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="b6eae-103">Crear una cola de llamada</span><span class="sxs-lookup"><span data-stu-id="b6eae-103">Create a call queue</span></span>

<span data-ttu-id="b6eae-104">Las colas de llamadas proporcionan un método para enrutamiento de autores de llamadas a personas de la organización que pueden ayudarle con un problema o pregunta en particular.</span><span class="sxs-lookup"><span data-stu-id="b6eae-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="b6eae-105">Las llamadas se distribuyen de una en una a las personas que están en la cola (que se denominan *agentes*).</span><span class="sxs-lookup"><span data-stu-id="b6eae-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="b6eae-106">Las colas de llamadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="b6eae-106">Call queues provide:</span></span>

- <span data-ttu-id="b6eae-107">Un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="b6eae-107">A greeting message.</span></span>

- <span data-ttu-id="b6eae-108">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="b6eae-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="b6eae-109">Enrutamiento de llamadas *Primera en llegar, primera en salir* (FIFO),en la orden para los agentes.</span><span class="sxs-lookup"><span data-stu-id="b6eae-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="b6eae-110">Opciones de gestión del desbordamiento de la cola y del tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b6eae-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="b6eae-111">Asegúrese de que ha leído Plan para operadores [automáticos](plan-auto-attendant-call-queue.md) de Teams y colas de llamadas y ha seguido los pasos de introducción antes de seguir los procedimientos de este artículo. [](plan-auto-attendant-call-queue.md#getting-started)</span><span class="sxs-lookup"><span data-stu-id="b6eae-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="b6eae-112">Para configurar una cola de llamadas, en el centro de administración de Teams, expanda **Voz**, haga clic en **Llamar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b6eae-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="b6eae-113">Cuenta de recursos e idioma</span><span class="sxs-lookup"><span data-stu-id="b6eae-113">Resource account and language</span></span>

![Captura de pantalla de la configuración de la cuenta de recursos y de idioma](media/call-queue-name-language.png)

1. <span data-ttu-id="b6eae-115">Escriba un nombre descriptivo para la cola.</span><span class="sxs-lookup"><span data-stu-id="b6eae-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="b6eae-116">Haga clic en **Agregar cuentas**, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b6eae-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="b6eae-117">(Los agentes verán el nombre de la cuenta de recurso cuando reciban una llamada entrante).</span><span class="sxs-lookup"><span data-stu-id="b6eae-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="b6eae-118">Elija un [idioma compatible.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="b6eae-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="b6eae-119">Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción de correo de voz (si las habilita).</span><span class="sxs-lookup"><span data-stu-id="b6eae-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="b6eae-120">Saludos y música en espera en cola</span><span class="sxs-lookup"><span data-stu-id="b6eae-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="b6eae-121">Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola.</span><span class="sxs-lookup"><span data-stu-id="b6eae-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="b6eae-122">Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="b6eae-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="b6eae-123">Los equipos proporcionan música predeterminada a los autores de llamadas mientras están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="b6eae-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="b6eae-124">Si desea reproducir un archivo de audio específico, elija **Reproducir un archivo de audio en** y cargar un archivo MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="b6eae-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="b6eae-125">La grabación cargada no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="b6eae-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="b6eae-126">La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar ningún pago de la organización.</span><span class="sxs-lookup"><span data-stu-id="b6eae-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="b6eae-127">Llamar a agentes</span><span class="sxs-lookup"><span data-stu-id="b6eae-127">Call agents</span></span>

<span data-ttu-id="b6eae-128">Revise los [requisitos previos para agregar agentes a una cola de llamadas.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="b6eae-128">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Captura de pantalla de la configuración de usuarios y grupos para las colas de llamadas](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="b6eae-130">Canal de Teams</span><span class="sxs-lookup"><span data-stu-id="b6eae-130">Teams channel</span></span>

<span data-ttu-id="b6eae-131">Puede agregar hasta 200 agentes a través de un canal de Teams.</span><span class="sxs-lookup"><span data-stu-id="b6eae-131">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="b6eae-132">Si desea usar un [canal de Teams para](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)administrar la cola, seleccione la opción Elegir **un** equipo y haga clic en Agregar **un canal.**</span><span class="sxs-lookup"><span data-stu-id="b6eae-132">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="b6eae-133">Busque el equipo que desea usar, selecciónelo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b6eae-133">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="b6eae-134">Seleccione el canal que desea usar y haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="b6eae-134">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="b6eae-135">Los clientes siguientes son compatibles al usar un canal de Teams para las colas de llamadas:</span><span class="sxs-lookup"><span data-stu-id="b6eae-135">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="b6eae-136">Cliente de Windows de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6eae-136">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="b6eae-137">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="b6eae-137">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="b6eae-138">Usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="b6eae-138">Users and groups</span></span>

<span data-ttu-id="b6eae-139">Puede agregar hasta 20 agentes individualmente y hasta 200 agentes a través de grupos.</span><span class="sxs-lookup"><span data-stu-id="b6eae-139">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="b6eae-140">Si desea agregar usuarios o grupos individuales a la cola, seleccione la **opción Elegir usuarios y** grupos.</span><span class="sxs-lookup"><span data-stu-id="b6eae-140">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="b6eae-141">Para agregar un usuario a la cola, haga clic en **Agregar usuarios**, busque el usuario, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b6eae-141">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="b6eae-142">Para agregar un grupo a la cola, haga clic en **Agregar grupos**, busque el grupo, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b6eae-142">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="b6eae-143">Puede usar listas de distribución, grupos de seguridad, grupos de seguridad, grupos de Microsoft 365 o equipos de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6eae-143">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="b6eae-144">Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.</span><span class="sxs-lookup"><span data-stu-id="b6eae-144">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="b6eae-145">Enrutamiento de llamada</span><span class="sxs-lookup"><span data-stu-id="b6eae-145">Call routing</span></span>

![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="b6eae-147">**El modo de conferencia** reduce de forma significativa la cantidad de tiempo que tarda un autor de llamada en estar conectado con un agente, después de que el agente acepte la llamada.</span><span class="sxs-lookup"><span data-stu-id="b6eae-147">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="b6eae-148">Para que el modo de conferencia funcione, los agentes en la cola de llamadas deben usar uno de los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="b6eae-148">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="b6eae-149">Última versión del cliente de escritorio de Microsoft Teams, la aplicación de Android o la aplicación de iOS</span><span class="sxs-lookup"><span data-stu-id="b6eae-149">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="b6eae-150">Versión de teléfono 1449/1.0.94.2020051601 o posterior de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6eae-150">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="b6eae-151">Las cuentas de Teams de los agentes deben establecerse en modo solo Teams.</span><span class="sxs-lookup"><span data-stu-id="b6eae-151">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="b6eae-152">Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b6eae-152">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="b6eae-153">Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.</span><span class="sxs-lookup"><span data-stu-id="b6eae-153">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="b6eae-154">El modo de conferencia no es compatible si las llamadas telefónicas se enruta a la cola desde una puerta de enlace de enrutamiento directo habilitada para enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="b6eae-154">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="b6eae-155">**El método de enrutamiento** determina el orden en que los agentes reciben llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="b6eae-155">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="b6eae-156">Elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="b6eae-156">Choose from these options:</span></span>

- <span data-ttu-id="b6eae-157">**El enrutamiento de operador** hace una llamada a todos los agentes en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b6eae-157">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="b6eae-158">El primer agente de llamada que tome la llamada la recibe.</span><span class="sxs-lookup"><span data-stu-id="b6eae-158">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="b6eae-159">**El enrutamiento de serie** a todos los agentes de llamada uno por uno en el orden especificado en la **Llamar a** lista.</span><span class="sxs-lookup"><span data-stu-id="b6eae-159">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="b6eae-160">Si un agente desestima o no contesta una llamada, se realizará una llamada al siguiente agente y se intentará con todos los agentes hasta que la llamada sea contestada o se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b6eae-160">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="b6eae-161">**Distribución equilibrada** equilibra el enrutamiento de llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="b6eae-161">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="b6eae-162">Esto puede ser deseable en un entorno de ventas de entrada para asegurar la misma oportunidad entre todos los agentes de llamada.</span><span class="sxs-lookup"><span data-stu-id="b6eae-162">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="b6eae-163">**Inactividad mayor** dirige cada llamada al agente que ha estado inactivo por más tiempo.</span><span class="sxs-lookup"><span data-stu-id="b6eae-163">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="b6eae-164">Un agente se considera inactivo si su estado de presencia está disponible o si su estado de presencia ha estado inactivo durante menos de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="b6eae-164">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="b6eae-165">Los agentes cuyo estado de presencia ha estado inactivo durante más de 10 minutos no se consideran inactivos y no podrán recibir llamadas hasta que cambien su presencia a Disponible.</span><span class="sxs-lookup"><span data-stu-id="b6eae-165">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Captura de pantalla de configuración de enrutamiento, de baja y de hora de alerta](media/call-queue-presence-agents-time.png)


<span data-ttu-id="b6eae-167">**La red de enrutamiento basada en** usa el estado de disponibilidad de los agentes de llamada para determinar si un agente debe incluirse en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b6eae-167">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="b6eae-168">Los agentes de llamadas cuyo estado de disponibilidad está establecido en **Disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="b6eae-168">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="b6eae-169">Los agentes cuyo estado de disponibilidad se establezca en cualquier otro estado se excluyen de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que el estado de disponibilidad vuelva a cambiar a **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="b6eae-169">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="b6eae-170">Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b6eae-170">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="b6eae-171">Si un agente opta por no recibir llamadas, no se incluirán en la lista de enrutamiento de llamadas independientemente de cómo esté configurado su estado de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b6eae-171">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="b6eae-172">Los agentes que usan el cliente de Skype Empresarial no se incluyen en la lista de enrutamiento de llamadas cuando está habilitado el enrutamiento basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="b6eae-172">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="b6eae-173">Si tiene agentes que usan Skype Empresarial, no habilite el enrutamiento de llamadas basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="b6eae-173">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="b6eae-174">**Tiempo de alerta de agente** especifica qué tanto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="b6eae-174">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="b6eae-175">Se recomienda la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="b6eae-175">The following settings are recommended:</span></span>

- <span data-ttu-id="b6eae-176">**Modo de conferencia** a **automático**</span><span class="sxs-lookup"><span data-stu-id="b6eae-176">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="b6eae-177">**Método de enrutamiento** a **distribución equilibrada** o **inactividad mayor**</span><span class="sxs-lookup"><span data-stu-id="b6eae-177">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="b6eae-178">**Enrutamiento basado en presencia** a **Activado**</span><span class="sxs-lookup"><span data-stu-id="b6eae-178">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="b6eae-179">**Hora de alerta de agente:** a **20 segundos**</span><span class="sxs-lookup"><span data-stu-id="b6eae-179">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="b6eae-180">Si el enrutamiento basado en presencia no está habilitado y hay varias llamadas en la cola, el sistema presentará estas llamadas simultáneamente a los agentes, independientemente de su estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="b6eae-180">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="b6eae-181">Esto provocará varias notificaciones de llamada a los agentes, especialmente si algunos agentes no responden a la llamada inicial que se les ha presentado.</span><span class="sxs-lookup"><span data-stu-id="b6eae-181">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="b6eae-182">Gestión de desbordamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="b6eae-182">Call overflow handling</span></span>

![Captura de pantalla de la configuración de desbordamiento de llamadas](media/call-queue-overflow-handling.png)

<span data-ttu-id="b6eae-184">**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b6eae-184">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="b6eae-185">El valor predeterminado es 50, pero puede elegir un valor entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="b6eae-185">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="b6eae-186">Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="b6eae-186">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="b6eae-187">Puede elegir desconectar la llamada o redirigirla a cualquiera de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b6eae-187">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="b6eae-188">Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola.</span><span class="sxs-lookup"><span data-stu-id="b6eae-188">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="b6eae-189">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) [las transferencias de números de teléfono externos (los detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) el formato de los números).</span><span class="sxs-lookup"><span data-stu-id="b6eae-189">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="b6eae-190">Si el número máximo de llamadas se establece en 0, no se reproducirá el mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="b6eae-190">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="b6eae-191">Gestión de la caducidad de la llamada</span><span class="sxs-lookup"><span data-stu-id="b6eae-191">Call timeout handling</span></span>

![Captura de pantalla de la configuración del tiempo de espera de la llamada](media/call-queue-timeout-handling.png)

<span data-ttu-id="b6eae-193">**Tiempo de espera de la llamada: tiempo máximo** especifica el tiempo máximo en que una llamada puede estar en espera en la cola antes de que se redirija o se desconecta.</span><span class="sxs-lookup"><span data-stu-id="b6eae-193">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="b6eae-194">Puede establecer un intervalo de entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="b6eae-194">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="b6eae-195">Puede elegir desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b6eae-195">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="b6eae-196">Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola.</span><span class="sxs-lookup"><span data-stu-id="b6eae-196">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="b6eae-197">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) [las transferencias de números de teléfono externos (los detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) el formato de los números).</span><span class="sxs-lookup"><span data-stu-id="b6eae-197">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="b6eae-198">Cuando haya seleccionado las opciones del tiempo de espera de la llamada, haga clic **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b6eae-198">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="b6eae-199">Identificador de llamada para llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="b6eae-199">Caller ID for outbound calls</span></span>

<span data-ttu-id="b6eae-200">Como los agentes en una cola de llamadas pueden marcar para devolver una llamada de cliente, considere la posibilidad de configurar el identificador de llamada de los miembros de una cola de llamada al número de servicio de un operador automático adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6eae-200">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="b6eae-201">Consulte [administrar las directivas de identificador de llamada en Microsoft Teams](caller-id-policies.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b6eae-201">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="b6eae-202">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="b6eae-202">Supported clients</span></span>

<span data-ttu-id="b6eae-203">Los siguientes clientes son compatibles con agentes de llamada en una cola de llamadas:</span><span class="sxs-lookup"><span data-stu-id="b6eae-203">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="b6eae-204">Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b6eae-204">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="b6eae-205">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b6eae-205">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="b6eae-206">Todos los modelos de teléfonos IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6eae-206">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="b6eae-207">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="b6eae-207">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="b6eae-208">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6eae-208">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="b6eae-209">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6eae-209">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="b6eae-210">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6eae-210">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="b6eae-211">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6eae-211">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="b6eae-212">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b6eae-212">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="b6eae-213">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="b6eae-213">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="b6eae-214">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="b6eae-214">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="b6eae-215">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="b6eae-215">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="b6eae-216">Las colas de llamadas a las que se les asigna un número de enrutamiento directo no admiten clientes de Skype Empresarial, clientes Lync o teléfonos IP de Skype Empresarial como agentes.</span><span class="sxs-lookup"><span data-stu-id="b6eae-216">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="b6eae-217">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="b6eae-217">Call queue cmdlets</span></span>

<span data-ttu-id="b6eae-218">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b6eae-218">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="b6eae-219">Estos son los cmdlets que necesita para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b6eae-219">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="b6eae-220">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b6eae-220">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="b6eae-221">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b6eae-221">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="b6eae-222">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b6eae-222">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="b6eae-223">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b6eae-223">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="b6eae-224">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b6eae-224">Related topics</span></span>

[<span data-ttu-id="b6eae-225">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="b6eae-225">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b6eae-226">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="b6eae-226">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="b6eae-227">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="b6eae-227">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="b6eae-228">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="b6eae-228">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="b6eae-229">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b6eae-229">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

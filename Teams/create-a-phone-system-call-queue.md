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
description: Aprenda a configurar el sistema telefónico para las colas de llamadas con Microsoft Teams, que proporciona un mensaje de saludo, mantiene música, redirige las llamadas y otras características.
ms.openlocfilehash: fb4510ce81b09569a8228916b7d05cc6697caac8
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49089344"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="3ce02-103">Crear una cola de llamada</span><span class="sxs-lookup"><span data-stu-id="3ce02-103">Create a call queue</span></span>

<span data-ttu-id="3ce02-104">Las colas de llamadas proporcionan un método para dirigir a las personas de su organización que pueden ayudarle con un problema o una pregunta en particular.</span><span class="sxs-lookup"><span data-stu-id="3ce02-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="3ce02-105">Las llamadas se distribuyen de una en una a las personas de la cola (que se conocen como *agentes*).</span><span class="sxs-lookup"><span data-stu-id="3ce02-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="3ce02-106">Las colas de llamadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="3ce02-106">Call queues provide:</span></span>

- <span data-ttu-id="3ce02-107">Un mensaje de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="3ce02-107">A greeting message.</span></span>

- <span data-ttu-id="3ce02-108">Música mientras las personas esperan en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="3ce02-109">Enrutamiento de llamadas: remisión de pedido-a de *salida* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="3ce02-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="3ce02-110">Administración de opciones para el desbordamiento de la cola y el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3ce02-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="3ce02-111">Asegúrese de que tiene el [plan de lectura de los operadores automáticos de Teams y las colas de llamadas](plan-auto-attendant-call-queue.md) y siga los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started) antes de seguir los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3ce02-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="3ce02-112">Para configurar una cola de llamadas, en el centro de administración de Teams, expanda **voz**, haga clic en **colas de llamadas** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ce02-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="3ce02-113">Cuenta de recursos e idioma</span><span class="sxs-lookup"><span data-stu-id="3ce02-113">Resource account and language</span></span>

![Captura de pantalla de la configuración de idioma y cuenta de recursos](media/call-queue-name-language.png)

1. <span data-ttu-id="3ce02-115">Escriba un nombre para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-115">Type a name for the call queue.</span></span> <span data-ttu-id="3ce02-116">Los agentes verán este nombre cuando reciban una llamada entrante de la cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="3ce02-117">Haga clic en **Agregar cuentas**, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en **Agregar** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ce02-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="3ce02-118">Elija un idioma.</span><span class="sxs-lookup"><span data-stu-id="3ce02-118">Choose a language.</span></span> <span data-ttu-id="3ce02-119">Este idioma se usará para las solicitudes de voz generadas por el sistema y la transcripción del buzón de voz (si las habilita).</span><span class="sxs-lookup"><span data-stu-id="3ce02-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="3ce02-120">Saludos y música en espera en la cola</span><span class="sxs-lookup"><span data-stu-id="3ce02-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="3ce02-121">Especifique si desea reproducir un saludo para las personas que llaman cuando llegan a la cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="3ce02-122">Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="3ce02-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="3ce02-123">Teams proporciona música predeterminada a las personas que llaman mientras están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="3ce02-124">Si desea reproducir un archivo de audio específico, elija **reproducir un archivo de audio** y cargar un archivo mp3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="3ce02-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="3ce02-125">La grabación cargada no puede tener más de 5 MB.</span><span class="sxs-lookup"><span data-stu-id="3ce02-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="3ce02-126">La música predeterminada que se proporciona en las colas de llamadas de Teams es gratuita para la organización.</span><span class="sxs-lookup"><span data-stu-id="3ce02-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="3ce02-127">Agentes de llamadas</span><span class="sxs-lookup"><span data-stu-id="3ce02-127">Call agents</span></span>

<span data-ttu-id="3ce02-128">Para poder agregar agentes a una cola de llamadas, consulta los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) .</span><span class="sxs-lookup"><span data-stu-id="3ce02-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Captura de pantalla de configuración de usuarios y grupos para colas de llamadas](media/call-queue-users-groups.png)

<span data-ttu-id="3ce02-130">Puede Agregar hasta 20 agentes de forma individual y hasta 200 agentes a través de grupos.</span><span class="sxs-lookup"><span data-stu-id="3ce02-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="3ce02-131">Para agregar un usuario a la cola, haga clic en **Agregar usuarios**, busque el usuario, haga clic en **Agregar** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ce02-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="3ce02-132">Para agregar un grupo a la cola, haga clic en **agregar grupos**, busque el grupo, haga clic en **Agregar** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ce02-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="3ce02-133">Puede usar listas de distribución, grupos de seguridad y grupos de Microsoft 365 o de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ce02-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3ce02-134">Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.</span><span class="sxs-lookup"><span data-stu-id="3ce02-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="3ce02-135">Enrutamiento de llamada</span><span class="sxs-lookup"><span data-stu-id="3ce02-135">Call routing</span></span>

![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="3ce02-137">El **modo de conferencia** reduce significativamente la cantidad de tiempo que tarda una persona que se conecte a un agente, después de que el agente acepte la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ce02-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="3ce02-138">Para que el modo de conferencia funcione, los agentes de la cola de llamadas deben usar uno de los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="3ce02-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="3ce02-139">La versión más reciente del cliente de escritorio de Microsoft Teams, la aplicación Android o la aplicación iOS</span><span class="sxs-lookup"><span data-stu-id="3ce02-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="3ce02-140">Microsoft Teams Phone versión 1449/1.0.94.2020051601 o posterior</span><span class="sxs-lookup"><span data-stu-id="3ce02-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="3ce02-141">Las cuentas de los agentes de Teams deben establecerse en el modo de solo equipos.</span><span class="sxs-lookup"><span data-stu-id="3ce02-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="3ce02-142">Los agentes que no cumplan con los requisitos no se incluyen en la lista de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="3ce02-143">Recomendamos habilitar el modo de conferencia para las colas de llamadas si todos los agentes usan clientes compatibles.</span><span class="sxs-lookup"><span data-stu-id="3ce02-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="3ce02-144">El modo de conferencia no admite el uso ocupado en ocupado.</span><span class="sxs-lookup"><span data-stu-id="3ce02-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="3ce02-145">Es posible que los agentes de las llamadas a colas que no sean de llamadas sigan apareciendo con una llamada en la cola de llamadas si el enrutamiento basado en presencia no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3ce02-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="3ce02-146">El **método de enrutamiento** determina el orden en el que los agentes reciben llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="3ce02-147">Elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="3ce02-147">Choose from these options:</span></span>

- <span data-ttu-id="3ce02-148">El **enrutamiento del operador** llama a todos los agentes de la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3ce02-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="3ce02-149">El primer agente de llamadas que atiende la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ce02-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="3ce02-150">El **enrutamiento en serie** llama a todos los agentes de llamadas uno por uno en el orden especificado en la lista agentes de **llamadas** .</span><span class="sxs-lookup"><span data-stu-id="3ce02-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="3ce02-151">Si un agente descarta o no atiende una llamada, la llamada sonará al próximo agente y probará con todos los agentes hasta que se seleccione o agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3ce02-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="3ce02-152">Equilibrar la **operación por turnos** el enrutamiento de las llamadas entrantes para que cada agente de llamadas obtenga el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="3ce02-153">Esto puede ser conveniente en un entorno de ventas entrante para asegurar la igualdad de oportunidades entre todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="3ce02-154">El más **largo** enruta las llamadas al agente que ha estado inactiva el tiempo más largo.</span><span class="sxs-lookup"><span data-stu-id="3ce02-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="3ce02-155">Un agente se considera inactivo si su estado de presencia está disponible o si su estado de presencia ha estado ausente por menos de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="3ce02-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="3ce02-156">Los agentes cuyo estado de presencia haya estado ausente más de 10 minutos no se consideran inactivos y no podrán recibir llamadas hasta que cambien su presencia a disponible.</span><span class="sxs-lookup"><span data-stu-id="3ce02-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Captura de pantalla de la configuración de enrutamiento, no participar y hora de alerta](media/call-queue-presence-agents-time.png)


<span data-ttu-id="3ce02-158">El **enrutamiento basado en la presencia** usa el estado de disponibilidad de los agentes de llamadas para determinar si un agente debería estar incluido en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3ce02-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="3ce02-159">Los agentes de llamadas cuyo estado de disponibilidad esté establecido en **disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="3ce02-160">Los agentes cuyo estado de disponibilidad esté establecido en cualquier otro Estado se excluyan de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que su estado de disponibilidad cambie de nuevo a **disponible**.</span><span class="sxs-lookup"><span data-stu-id="3ce02-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="3ce02-161">Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3ce02-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="3ce02-162">Si un agente opta por recibir llamadas, no se incluirán en la lista de enrutamiento de llamadas, independientemente del valor de su estado de disponibilidad en.</span><span class="sxs-lookup"><span data-stu-id="3ce02-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="3ce02-163">Los agentes que usan el cliente de Skype empresarial no se incluyen en la lista de enrutamiento de llamadas cuando el enrutamiento basado en presencia está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3ce02-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="3ce02-164">Si tiene agentes que usan Skype empresarial, no habilite el enrutamiento de llamadas basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="3ce02-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="3ce02-165">La hora de la **alerta del agente** especifica cuánto tiempo sonará el teléfono del agente antes de que la cola redirija la llamada al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="3ce02-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="3ce02-166">Para las colas de alto volumen, recomendamos la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ce02-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="3ce02-167">**Modo** de conferencia **automático**</span><span class="sxs-lookup"><span data-stu-id="3ce02-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="3ce02-168">**Método de enrutamiento** para **enrutamiento de operador**</span><span class="sxs-lookup"><span data-stu-id="3ce02-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="3ce02-169">**Enrutamiento basado en presencia** en **activado**</span><span class="sxs-lookup"><span data-stu-id="3ce02-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="3ce02-170">**Hora de la alerta del agente:** **20 segundos**</span><span class="sxs-lookup"><span data-stu-id="3ce02-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="3ce02-171">Control de desbordamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="3ce02-171">Call overflow handling</span></span>

![Captura de pantalla de configuración de desbordamiento de llamadas](media/call-queue-overflow-handling.png)

<span data-ttu-id="3ce02-173">Número **máximo de llamadas en la cola** especifica el número máximo de llamadas que pueden esperar en la cola en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="3ce02-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="3ce02-174">El valor predeterminado es 50, pero puede estar comprendido entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="3ce02-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="3ce02-175">Cuando se alcanza este límite, la llamada se maneja de la forma especificada por la configuración **cuando se alcanza el número máximo de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="3ce02-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="3ce02-176">Puede desconectar la llamada o redirigirla a cualquiera de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="3ce02-177">Por ejemplo, es posible que la persona que llama deje un buzón de voz para los agentes de la cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="3ce02-178">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) y las [transferencias de números de teléfono externos: detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de formato de número.</span><span class="sxs-lookup"><span data-stu-id="3ce02-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="3ce02-179">Si el número máximo de llamadas se establece en 0, el mensaje de bienvenida no se reproducirá.</span><span class="sxs-lookup"><span data-stu-id="3ce02-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="3ce02-180">Control de tiempo de espera de llamadas</span><span class="sxs-lookup"><span data-stu-id="3ce02-180">Call timeout handling</span></span>

![Captura de pantalla de configuración de tiempo de espera de llamada](media/call-queue-timeout-handling.png)

<span data-ttu-id="3ce02-182">Tiempo de espera de la **llamada: tiempo de espera máximo** especifica el tiempo máximo que una llamada puede estar en espera en la cola antes de que se redirija o desconecte.</span><span class="sxs-lookup"><span data-stu-id="3ce02-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="3ce02-183">Puede especificar un valor entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="3ce02-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="3ce02-184">Puede desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="3ce02-185">Por ejemplo, es posible que la persona que llama deje un buzón de voz para los agentes de la cola.</span><span class="sxs-lookup"><span data-stu-id="3ce02-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="3ce02-186">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) y las [transferencias de números de teléfono externos: detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de formato de número.</span><span class="sxs-lookup"><span data-stu-id="3ce02-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="3ce02-187">Cuando haya seleccionado las opciones de tiempo de espera de la llamada, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3ce02-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="3ce02-188">IDENTIFICACIÓN de llamadas para llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="3ce02-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="3ce02-189">Como los agentes de una cola de llamadas pueden marcar para devolver una llamada de cliente, considere la posibilidad de establecer la identificación de llamadas para los miembros de una cola de llamadas en el número de servicio de un operador automático adecuado.</span><span class="sxs-lookup"><span data-stu-id="3ce02-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="3ce02-190">Para obtener más información, consulte [Administrar directivas de identificación de llamadas en Microsoft Teams](caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="3ce02-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="3ce02-191">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="3ce02-191">Supported clients</span></span>

- <span data-ttu-id="3ce02-192">Los siguientes clientes son compatibles con los agentes de llamadas en una cola de llamadas:</span><span class="sxs-lookup"><span data-stu-id="3ce02-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="3ce02-193">Cliente de escritorio de Skype empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3ce02-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3ce02-194">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3ce02-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3ce02-195">Todos los modelos de teléfono IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ce02-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="3ce02-196">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3ce02-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="3ce02-197">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3ce02-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="3ce02-198">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3ce02-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="3ce02-199">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3ce02-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="3ce02-200">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3ce02-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="3ce02-201">Cliente de Windows de Microsoft Teams (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3ce02-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3ce02-202">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="3ce02-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="3ce02-203">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="3ce02-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="3ce02-204">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="3ce02-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ce02-205">Las colas de llamadas a las que se asigna un número de enrutamiento directo no son compatibles con clientes de Skype empresarial, clientes de Lync o teléfonos IP de Skype empresarial como agentes.</span><span class="sxs-lookup"><span data-stu-id="3ce02-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="3ce02-206">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="3ce02-206">Call queue cmdlets</span></span>

<span data-ttu-id="3ce02-207">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="3ce02-208">Estos son los cmdlets que usas para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3ce02-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="3ce02-209">Nuevo: CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ce02-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="3ce02-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ce02-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="3ce02-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ce02-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="3ce02-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ce02-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="3ce02-213">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3ce02-213">Related topics</span></span>

[<span data-ttu-id="3ce02-214">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="3ce02-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="3ce02-215">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="3ce02-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="3ce02-216">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="3ce02-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="3ce02-217">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="3ce02-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="3ce02-218">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3ce02-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

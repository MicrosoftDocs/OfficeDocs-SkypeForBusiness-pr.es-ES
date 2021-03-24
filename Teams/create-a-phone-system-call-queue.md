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
description: Aprenda a configurar el sistema telefónico para las colas de llamadas con Microsoft Teams, que brindan un mensaje de saludo, música en espera, redireccionamiento de llamadas y otras características.
ms.openlocfilehash: 9bb33e5590df1af6b70dffecba64eb313838b228
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092718"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="c1a7f-103">Crear una cola de llamada</span><span class="sxs-lookup"><span data-stu-id="c1a7f-103">Create a call queue</span></span>

<span data-ttu-id="c1a7f-104">Las colas de llamadas proporcionan un método para enrutamiento de autores de llamadas a personas de la organización que pueden ayudarle con un problema o pregunta en particular.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="c1a7f-105">Las llamadas se distribuyen de una en una a las personas que están en la cola (que se denominan *agentes*).</span><span class="sxs-lookup"><span data-stu-id="c1a7f-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="c1a7f-106">Las colas de llamadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="c1a7f-106">Call queues provide:</span></span>

- <span data-ttu-id="c1a7f-107">Un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-107">A greeting message.</span></span>

- <span data-ttu-id="c1a7f-108">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="c1a7f-109">Enrutamiento de llamadas *Primera en llegar, primera en salir* (FIFO),en la orden para los agentes.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="c1a7f-110">Opciones de gestión del desbordamiento de la cola y del tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="c1a7f-111">Asegúrese de haber leído las [colas de llamadas y los asistentes automáticos de Plan for Teams](plan-auto-attendant-call-queue.md) y de haber seguido los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started) antes de seguir los procedimientos de estos artículos.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="c1a7f-112">Para configurar una cola de llamadas, en el centro de administración de Teams, expanda **Voz**, haga clic en **Llamar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="c1a7f-113">Cuenta de recursos e idioma</span><span class="sxs-lookup"><span data-stu-id="c1a7f-113">Resource account and language</span></span>

![Captura de pantalla de la configuración de la cuenta de recursos y de idioma](media/call-queue-name-language.png)

1. <span data-ttu-id="c1a7f-115">Escriba un nombre descriptivo para la cola.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="c1a7f-116">Haga clic en **Agregar cuentas**, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="c1a7f-117">(Los agentes verán el nombre de la cuenta de recurso cuando reciban una llamada entrante).</span><span class="sxs-lookup"><span data-stu-id="c1a7f-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="c1a7f-118">Elija un [idioma compatible.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="c1a7f-119">Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción de correo de voz (si las habilita).</span><span class="sxs-lookup"><span data-stu-id="c1a7f-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="c1a7f-120">Saludos y música en espera en cola</span><span class="sxs-lookup"><span data-stu-id="c1a7f-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="c1a7f-121">Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="c1a7f-122">Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="c1a7f-123">Los equipos proporcionan música predeterminada a los autores de llamadas mientras están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="c1a7f-124">Si desea reproducir un archivo de audio específico, elija **Reproducir un archivo de audio en** y cargar un archivo MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="c1a7f-125">La grabación cargada no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="c1a7f-126">La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar ningún pago de la organización.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="c1a7f-127">Llamar a agentes</span><span class="sxs-lookup"><span data-stu-id="c1a7f-127">Call agents</span></span>

<span data-ttu-id="c1a7f-128">Consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para poder agregar agentes a una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Captura de pantalla de la configuración de usuarios y grupos para las colas de llamadas](media/call-queue-users-groups.png)

<span data-ttu-id="c1a7f-130">Puede agregar hasta 20 agentes individualmente y hasta 200 agentes a través de grupos.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="c1a7f-131">Para agregar un usuario a la cola, haga clic en **Agregar usuarios**, busque el usuario, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="c1a7f-132">Para agregar un grupo a la cola, haga clic en **Agregar grupos**, busque el grupo, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="c1a7f-133">Puede usar listas de distribución, grupos de seguridad, grupos de seguridad, grupos de Microsoft 365 o equipos de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c1a7f-134">Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="c1a7f-135">Enrutamiento de llamada</span><span class="sxs-lookup"><span data-stu-id="c1a7f-135">Call routing</span></span>

![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="c1a7f-137">**El modo de conferencia** reduce de forma significativa la cantidad de tiempo que tarda un autor de llamada en estar conectado con un agente, después de que el agente acepte la llamada.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="c1a7f-138">Para que el modo de conferencia funcione, los agentes en la cola de llamadas deben usar uno de los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="c1a7f-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="c1a7f-139">Última versión del cliente de escritorio de Microsoft Teams, la aplicación de Android o la aplicación de iOS</span><span class="sxs-lookup"><span data-stu-id="c1a7f-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="c1a7f-140">Versión de teléfono 1449/1.0.94.2020051601 o posterior de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a7f-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="c1a7f-141">Las cuentas de Teams de los agentes deben establecerse en modo solo Teams.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="c1a7f-142">Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="c1a7f-143">Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="c1a7f-144">**El método de enrutamiento** determina el orden en que los agentes reciben llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="c1a7f-145">Elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="c1a7f-145">Choose from these options:</span></span>

- <span data-ttu-id="c1a7f-146">**El enrutamiento de operador** hace una llamada a todos los agentes en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="c1a7f-147">El primer agente de llamada que tome la llamada la recibe.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c1a7f-148">**El enrutamiento de serie** a todos los agentes de llamada uno por uno en el orden especificado en la **Llamar a** lista.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="c1a7f-149">Si un agente desestima o no contesta una llamada, se realizará una llamada al siguiente agente y se intentará con todos los agentes hasta que la llamada sea contestada o se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="c1a7f-150">**Distribución equilibrada** equilibra el enrutamiento de llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c1a7f-151">Esto puede ser deseable en un entorno de ventas de entrada para asegurar la misma oportunidad entre todos los agentes de llamada.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="c1a7f-152">**Inactividad mayor** dirige cada llamada al agente que ha estado inactivo por más tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="c1a7f-153">Un agente se considera inactivo si su estado de presencia está disponible o si su estado de presencia ha estado inactivo durante menos de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="c1a7f-154">Los agentes cuyo estado de presencia ha estado inactivo durante más de 10 minutos no se consideran inactivos y no podrán recibir llamadas hasta que cambien su presencia a Disponible.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Captura de pantalla de configuración de enrutamiento, de baja y de hora de alerta](media/call-queue-presence-agents-time.png)


<span data-ttu-id="c1a7f-156">**La red de enrutamiento basada en** usa el estado de disponibilidad de los agentes de llamada para determinar si un agente debe incluirse en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="c1a7f-157">Los agentes de llamadas cuyo estado de disponibilidad está establecido en **Disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="c1a7f-158">Los agentes cuyo estado de disponibilidad se establezca en cualquier otro estado se excluyen de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que el estado de disponibilidad vuelva a cambiar a **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="c1a7f-159">Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="c1a7f-160">Si un agente opta por no recibir llamadas, no se incluirán en la lista de enrutamiento de llamadas independientemente de cómo esté configurado su estado de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="c1a7f-161">Los agentes que usan el cliente de Skype Empresarial no se incluyen en la lista de enrutamiento de llamadas cuando está habilitado el enrutamiento basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="c1a7f-162">Si tiene agentes que usan Skype Empresarial, no habilite el enrutamiento de llamadas basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="c1a7f-163">**Tiempo de alerta de agente** especifica qué tanto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="c1a7f-164">Se recomienda la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="c1a7f-164">The following settings are recommended:</span></span>

- <span data-ttu-id="c1a7f-165">**Modo de conferencia** a **automático**</span><span class="sxs-lookup"><span data-stu-id="c1a7f-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="c1a7f-166">**Método de enrutamiento** a **distribución equilibrada** o **inactividad mayor**</span><span class="sxs-lookup"><span data-stu-id="c1a7f-166">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="c1a7f-167">**Enrutamiento basado en presencia** a **Activado**</span><span class="sxs-lookup"><span data-stu-id="c1a7f-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="c1a7f-168">**Hora de alerta de agente:** a **20 segundos**</span><span class="sxs-lookup"><span data-stu-id="c1a7f-168">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="c1a7f-169">Si el enrutamiento basado en presencia no está habilitado y hay varias llamadas en la cola, el sistema presentará estas llamadas simultáneamente a los agentes, independientemente de su estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-169">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="c1a7f-170">Esto provocará varias notificaciones de llamada a los agentes, especialmente si algunos agentes no responden a la llamada inicial que se les ha presentado.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-170">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="c1a7f-171">Gestión de desbordamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="c1a7f-171">Call overflow handling</span></span>

![Captura de pantalla de la configuración de desbordamiento de llamadas](media/call-queue-overflow-handling.png)

<span data-ttu-id="c1a7f-173">**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="c1a7f-174">El valor predeterminado es 50, pero puede elegir un valor entre 0 y 200.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c1a7f-175">Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="c1a7f-176">Puede elegir desconectar la llamada o redirigirla a cualquiera de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="c1a7f-177">Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c1a7f-178">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) [las transferencias de números de teléfono externos (los detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) el formato de los números).</span><span class="sxs-lookup"><span data-stu-id="c1a7f-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="c1a7f-179">Si el número máximo de llamadas se establece en 0, no se reproducirá el mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="c1a7f-180">Gestión de la caducidad de la llamada</span><span class="sxs-lookup"><span data-stu-id="c1a7f-180">Call timeout handling</span></span>

![Captura de pantalla de la configuración del tiempo de espera de la llamada](media/call-queue-timeout-handling.png)

<span data-ttu-id="c1a7f-182">**Tiempo de espera de la llamada: tiempo máximo** especifica el tiempo máximo en que una llamada puede estar en espera en la cola antes de que se redirija o se desconecta.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="c1a7f-183">Puede establecer un intervalo de entre 0 y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="c1a7f-184">Puede elegir desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="c1a7f-185">Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c1a7f-186">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) [las transferencias de números de teléfono externos (los detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) el formato de los números).</span><span class="sxs-lookup"><span data-stu-id="c1a7f-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="c1a7f-187">Cuando haya seleccionado las opciones del tiempo de espera de la llamada, haga clic **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="c1a7f-188">Identificador de llamada para llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="c1a7f-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="c1a7f-189">Como los agentes en una cola de llamadas pueden marcar para devolver una llamada de cliente, considere la posibilidad de configurar el identificador de llamada de los miembros de una cola de llamada al número de servicio de un operador automático adecuado.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="c1a7f-190">Consulte [administrar las directivas de identificador de llamada en Microsoft Teams](caller-id-policies.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="c1a7f-191">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="c1a7f-191">Supported clients</span></span>

<span data-ttu-id="c1a7f-192">Los siguientes clientes son compatibles con agentes de llamada en una cola de llamadas:</span><span class="sxs-lookup"><span data-stu-id="c1a7f-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="c1a7f-193">Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c1a7f-194">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c1a7f-195">Todos los modelos de teléfonos IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c1a7f-196">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c1a7f-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="c1a7f-197">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="c1a7f-198">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="c1a7f-199">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c1a7f-200">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c1a7f-201">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c1a7f-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c1a7f-202">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="c1a7f-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="c1a7f-203">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="c1a7f-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="c1a7f-204">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="c1a7f-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1a7f-205">Las colas de llamadas a las que se les asigna un número de enrutamiento directo no admiten clientes de Skype Empresarial, clientes Lync o teléfonos IP de Skype Empresarial como agentes.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c1a7f-206">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="c1a7f-206">Call queue cmdlets</span></span>

<span data-ttu-id="c1a7f-207">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c1a7f-208">Estos son los cmdlets que necesita para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c1a7f-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="c1a7f-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c1a7f-209">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="c1a7f-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c1a7f-210">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="c1a7f-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c1a7f-211">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="c1a7f-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c1a7f-212">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="c1a7f-213">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c1a7f-213">Related topics</span></span>

[<span data-ttu-id="c1a7f-214">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="c1a7f-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c1a7f-215">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="c1a7f-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c1a7f-216">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="c1a7f-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c1a7f-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c1a7f-217">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="c1a7f-218">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c1a7f-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
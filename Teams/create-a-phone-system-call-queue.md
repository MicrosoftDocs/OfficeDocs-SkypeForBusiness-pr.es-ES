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
description: Aprenda a configurar Sistema telefónico para colas de llamadas con Microsoft Teams, que proporciona un mensaje de saludo, música en espera, redirección de llamadas y otras características.
ms.openlocfilehash: d696b37f95d06c529aa330bd77e2ec91e1ffc9ad
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919048"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="3141a-103">Crear una cola de llamada</span><span class="sxs-lookup"><span data-stu-id="3141a-103">Create a call queue</span></span>

<span data-ttu-id="3141a-104">Las colas de llamadas proporcionan un método para enrutar autores de llamadas a personas de su organización que pueden ayudarle con un problema o una pregunta en particular.</span><span class="sxs-lookup"><span data-stu-id="3141a-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="3141a-105">Las llamadas se distribuyen de una en una a las personas de la cola (que se conocen como *agentes).*</span><span class="sxs-lookup"><span data-stu-id="3141a-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="3141a-106">Las colas de llamadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="3141a-106">Call queues provide:</span></span>

- <span data-ttu-id="3141a-107">Un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="3141a-107">A greeting message.</span></span>

- <span data-ttu-id="3141a-108">Música mientras los usuarios están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="3141a-109">Enrutamiento de llamadas, *en orden de primero en entrada,* orden first out (FIFO), a agentes.</span><span class="sxs-lookup"><span data-stu-id="3141a-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="3141a-110">Opciones de control para el desbordamiento de la cola y el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3141a-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="3141a-111">Asegúrese de que ha leído el Plan para operadores [](plan-auto-attendant-call-queue.md#getting-started) automáticos y colas de llamadas de [Teams,](plan-auto-attendant-call-queue.md) y de que ha seguido los pasos de introducción antes de seguir los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3141a-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="3141a-112">Para configurar una cola de llamadas, en el centro de administración de Teams, expanda **Voz,** haga clic en Colas de llamadas **y,** a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="3141a-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="3141a-113">Cuenta e idioma del recurso</span><span class="sxs-lookup"><span data-stu-id="3141a-113">Resource account and language</span></span>

![Captura de pantalla de la configuración de cuenta de recursos e idioma](media/call-queue-name-language.png)

1. <span data-ttu-id="3141a-115">Escriba un nombre para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-115">Type a name for the call queue.</span></span> <span data-ttu-id="3141a-116">Los agentes verán este nombre cuando reciban una llamada entrante de la cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="3141a-117">Haga **clic en Agregar** cuentas, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en Agregar y, a continuación, haga clic en **Agregar.** </span><span class="sxs-lookup"><span data-stu-id="3141a-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="3141a-118">Elige un idioma.</span><span class="sxs-lookup"><span data-stu-id="3141a-118">Choose a language.</span></span> <span data-ttu-id="3141a-119">Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción del correo de voz (si los habilita).</span><span class="sxs-lookup"><span data-stu-id="3141a-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="3141a-120">Saludos y música en espera en cola</span><span class="sxs-lookup"><span data-stu-id="3141a-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="3141a-121">Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="3141a-122">Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que quiere reproducir.</span><span class="sxs-lookup"><span data-stu-id="3141a-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="3141a-123">Teams proporciona música predeterminada a los autores de llamadas mientras están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="3141a-124">Si desea reproducir un archivo de audio específico, elija Reproducir un archivo de **audio** y cargue un archivo MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="3141a-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="3141a-125">La grabación cargada no puede tener un tamaño superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="3141a-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="3141a-126">La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar regalías por su organización.</span><span class="sxs-lookup"><span data-stu-id="3141a-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="3141a-127">Agentes de llamadas</span><span class="sxs-lookup"><span data-stu-id="3141a-127">Call agents</span></span>

<span data-ttu-id="3141a-128">Consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para poder agregar agentes a una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Captura de pantalla de la configuración de usuarios y grupos para colas de llamadas](media/call-queue-users-groups.png)

<span data-ttu-id="3141a-130">Puede agregar hasta 20 agentes de forma individual y hasta 200 agentes a través de grupos.</span><span class="sxs-lookup"><span data-stu-id="3141a-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="3141a-131">Para agregar un usuario a la cola, haga clic en Agregar **usuarios,** busque el usuario, haga clic en Agregar **y,** a continuación, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="3141a-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="3141a-132">Para agregar un grupo a la cola, haga clic en **Agregar grupos,** busque el grupo, haga clic en Agregar **y,** a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="3141a-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="3141a-133">Puede usar listas de distribución, grupos de seguridad y grupos de Microsoft 365 o equipos de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3141a-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3141a-134">Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.</span><span class="sxs-lookup"><span data-stu-id="3141a-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="3141a-135">Enrutamiento de llamada</span><span class="sxs-lookup"><span data-stu-id="3141a-135">Call routing</span></span>

![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="3141a-137">**El modo** de conferencia reduce significativamente la cantidad de tiempo que tarda un autor de llamada en conectarse con un agente, después de que el agente acepte la llamada.</span><span class="sxs-lookup"><span data-stu-id="3141a-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="3141a-138">Para que el modo de conferencia funcione, los agentes de la cola de llamadas deben usar uno de los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="3141a-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="3141a-139">La última versión del cliente de escritorio de Microsoft Teams, la aplicación para Android o la aplicación de iOS</span><span class="sxs-lookup"><span data-stu-id="3141a-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="3141a-140">Microsoft Teams phone versión 1449/1.0.94.2020051601 o posterior</span><span class="sxs-lookup"><span data-stu-id="3141a-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="3141a-141">Las cuentas de equipos de agentes deben configurarse en modo solo para equipos.</span><span class="sxs-lookup"><span data-stu-id="3141a-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="3141a-142">Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="3141a-143">Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.</span><span class="sxs-lookup"><span data-stu-id="3141a-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="3141a-144">El modo de conferencia no es compatible con Ocupado.</span><span class="sxs-lookup"><span data-stu-id="3141a-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="3141a-145">Es posible que se presenten agentes en llamadas de cola que no sean de llamada si el enrutamiento basado en presencia no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3141a-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="3141a-146">**El método de** enrutamiento determina el orden en que los agentes reciben llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="3141a-147">Elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="3141a-147">Choose from these options:</span></span>

- <span data-ttu-id="3141a-148">**El enrutamiento del operador** suena a todos los agentes de la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3141a-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="3141a-149">El primer agente de llamada que recibe la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="3141a-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="3141a-150">**El enrutamiento serial** suena a todos los agentes de llamadas uno por uno en el orden especificado en la **lista de agentes de** llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="3141a-151">Si un agente descarta o no acepta una llamada, la llamada llamará al siguiente agente y probará con todos los agentes hasta que se le atende o se atenten.</span><span class="sxs-lookup"><span data-stu-id="3141a-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="3141a-152">**Redondear robin** equilibra el enrutamiento de las llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="3141a-153">Esto puede ser deseable en un entorno de ventas entrantes para garantizar la misma oportunidad entre todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="3141a-154">**La inactividad más** larga enruta cada llamada al agente que haya estado inactivo más tiempo.</span><span class="sxs-lookup"><span data-stu-id="3141a-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="3141a-155">Un agente se considera inactivo si su estado de presencia está disponible o si su estado de presencia ha estado fuera durante menos de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="3141a-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="3141a-156">Los agentes cuyo estado de presencia ha estado fuera durante más de 10 minutos no se consideran inactivos y no podrán recibir llamadas hasta que cambien su presencia a Disponible.</span><span class="sxs-lookup"><span data-stu-id="3141a-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Captura de pantalla de la configuración de enrutamiento, de no participar y de hora de alerta](media/call-queue-presence-agents-time.png)


<span data-ttu-id="3141a-158">**El enrutamiento basado en presencia usa** el estado de disponibilidad de agentes de llamadas para determinar si un agente debe incluirse en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3141a-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="3141a-159">Los agentes de llamadas cuyo estado de disponibilidad se establece en **Disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="3141a-160">Los agentes cuyo estado de disponibilidad se establece en cualquier otro estado se excluyen de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que el estado de disponibilidad cambie de nuevo a **Disponible.**</span><span class="sxs-lookup"><span data-stu-id="3141a-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="3141a-161">Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3141a-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="3141a-162">Si un agente decide no recibir llamadas, no se incluirá en la lista de enrutamiento de llamadas independientemente de cuál sea su estado de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3141a-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="3141a-163">Los agentes que usan el cliente de Skype Empresarial no están incluidos en la lista de enrutamiento de llamadas cuando el enrutamiento basado en presencia está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3141a-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="3141a-164">Si tiene agentes que usan Skype Empresarial, no habilite el enrutamiento de llamadas basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="3141a-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="3141a-165">**La hora de alerta** de agente especifica cuánto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="3141a-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="3141a-166">Para las colas de gran volumen, le recomendamos la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="3141a-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="3141a-167">**Modo de conferencia** a **Automático**</span><span class="sxs-lookup"><span data-stu-id="3141a-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="3141a-168">**Método de enrutamiento** para **el enrutamiento de Attendant**</span><span class="sxs-lookup"><span data-stu-id="3141a-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="3141a-169">**Enrutamiento basado en presencia** a **On**</span><span class="sxs-lookup"><span data-stu-id="3141a-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="3141a-170">**Hora de alerta de agente:** **20 segundos**</span><span class="sxs-lookup"><span data-stu-id="3141a-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="3141a-171">Administración de desbordamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="3141a-171">Call overflow handling</span></span>

![Captura de pantalla de la configuración de desbordamiento de llamadas](media/call-queue-overflow-handling.png)

<span data-ttu-id="3141a-173">**El número máximo de llamadas en** la cola especifica el número máximo de llamadas que pueden esperar en la cola en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="3141a-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="3141a-174">El valor predeterminado es 50, pero puede variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="3141a-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="3141a-175">Cuando se alcanza este límite, la llamada se administra según lo especificado por la configuración Cuando se alcanza el número máximo de **llamadas.**</span><span class="sxs-lookup"><span data-stu-id="3141a-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="3141a-176">Puede elegir desconectar la llamada o redirigirla a cualquiera de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="3141a-177">Por ejemplo, puede hacer que el autor de la llamada deje un correo de voz para los agentes de la cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="3141a-178">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) y las transferencias de números de teléfono [externos: detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para el formato del número.</span><span class="sxs-lookup"><span data-stu-id="3141a-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="3141a-179">Si se establece el número máximo de llamadas en 0, el mensaje de saludo no se reproducirá.</span><span class="sxs-lookup"><span data-stu-id="3141a-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="3141a-180">Administración del tiempo de espera de llamadas</span><span class="sxs-lookup"><span data-stu-id="3141a-180">Call timeout handling</span></span>

![Captura de pantalla de la configuración de tiempo de espera de llamada](media/call-queue-timeout-handling.png)

<span data-ttu-id="3141a-182">**Tiempo de espera de llamada:** el tiempo máximo de espera especifica el tiempo máximo que una llamada puede estar en espera en la cola antes de que se redirija o se desconecte.</span><span class="sxs-lookup"><span data-stu-id="3141a-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="3141a-183">Puede especificar un valor entre 0 segundos y 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="3141a-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="3141a-184">Puede elegir desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="3141a-185">Por ejemplo, puede hacer que el autor de la llamada deje un correo de voz para los agentes de la cola.</span><span class="sxs-lookup"><span data-stu-id="3141a-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="3141a-186">Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) y las transferencias de números de teléfono [externos: detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para el formato del número.</span><span class="sxs-lookup"><span data-stu-id="3141a-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="3141a-187">Cuando haya seleccionado las opciones de tiempo de espera de la llamada, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="3141a-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="3141a-188">Identificación de llamadas para llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="3141a-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="3141a-189">Como los agentes de una cola de llamadas pueden llamar para devolver una llamada del cliente, considere la posibilidad de establecer el identificador de llamada de los miembros de una cola de llamadas en el número de servicio de un operador automático adecuado.</span><span class="sxs-lookup"><span data-stu-id="3141a-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="3141a-190">Vea [Administrar directivas de identificador de llamada en Microsoft Teams](caller-id-policies.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3141a-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="3141a-191">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="3141a-191">Supported clients</span></span>

<span data-ttu-id="3141a-192">Los siguientes clientes son compatibles con agentes de llamadas en una cola de llamadas:</span><span class="sxs-lookup"><span data-stu-id="3141a-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="3141a-193">Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3141a-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3141a-194">Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3141a-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3141a-195">Todos los modelos de teléfonos IP compatibles con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3141a-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="3141a-196">Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3141a-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="3141a-197">Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3141a-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="3141a-198">Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3141a-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="3141a-199">Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3141a-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="3141a-200">Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="3141a-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="3141a-201">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3141a-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3141a-202">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="3141a-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="3141a-203">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="3141a-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="3141a-204">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="3141a-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="3141a-205">Las colas de llamadas que tienen asignado un número de enrutamiento directo no admiten clientes de Skype Empresarial, clientes Lync o teléfonos IP de Skype Empresarial como agentes.</span><span class="sxs-lookup"><span data-stu-id="3141a-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="3141a-206">Cmdlets de colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="3141a-206">Call queue cmdlets</span></span>

<span data-ttu-id="3141a-207">También puede usar Windows PowerShell para crear y configurar colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="3141a-208">Estos son los cmdlets que usa para administrar una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3141a-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="3141a-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3141a-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="3141a-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3141a-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="3141a-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3141a-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="3141a-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3141a-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="3141a-213">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3141a-213">Related topics</span></span>

[<span data-ttu-id="3141a-214">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="3141a-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="3141a-215">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="3141a-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="3141a-216">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="3141a-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="3141a-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="3141a-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="3141a-218">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3141a-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

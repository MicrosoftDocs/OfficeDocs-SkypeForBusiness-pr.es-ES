---
title: 'Crear una cola de llamadas en Microsoft Teams: tutorial para pequeñas empresas'
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Obtenga información sobre cómo configurar colas de llamadas con Microsoft 365 Business Voice.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909663"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="bf617-103">Crear una cola de llamadas: tutorial para pequeñas empresas</span><span class="sxs-lookup"><span data-stu-id="bf617-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="bf617-104">Las colas de llamadas proporcionan un método para enrutar a los autores de llamadas a personas de su organización que pueden ayudarle con un problema o pregunta en particular.</span><span class="sxs-lookup"><span data-stu-id="bf617-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="bf617-105">Las llamadas se distribuyen de una en una a las personas de la cola (que se conocen como *agentes).*</span><span class="sxs-lookup"><span data-stu-id="bf617-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="bf617-106">Las colas de llamadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="bf617-106">Call queues provide:</span></span>

- <span data-ttu-id="bf617-107">Un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="bf617-107">A greeting message.</span></span>

- <span data-ttu-id="bf617-108">Música mientras los usuarios están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="bf617-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="bf617-109">Enrutamiento de llamadas, *en orden de primero en entrada,* orden first out (FIFO), a agentes.</span><span class="sxs-lookup"><span data-stu-id="bf617-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="bf617-110">Opciones de control para el desbordamiento de la cola y el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bf617-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="bf617-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="bf617-111">Before you begin</span></span>

<span data-ttu-id="bf617-112">Obtener algunas [licencias de Sistema telefónico: Usuario](../teams-add-on-licensing/virtual-user.md) virtual si aún no las tiene.</span><span class="sxs-lookup"><span data-stu-id="bf617-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="bf617-113">Obtenga una para cada cola de llamadas y operador automático que planee configurar.</span><span class="sxs-lookup"><span data-stu-id="bf617-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="bf617-114">Estas licencias son gratuitas, por lo que le recomendamos que le ofrecemos unas cuantas adicionales en caso de que decida realizar cambios en su configuración en el futuro.</span><span class="sxs-lookup"><span data-stu-id="bf617-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="bf617-115">Como los agentes de una cola de llamadas pueden llamar para devolver una llamada del cliente, considere la posibilidad de establecer el identificador de llamada de los agentes de llamadas en el número de teléfono principal o en el número de un operador automático adecuado.</span><span class="sxs-lookup"><span data-stu-id="bf617-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="bf617-116">Vea [Administrar directivas de identificador de llamada en Microsoft Teams](../caller-id-policies.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bf617-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="bf617-117">Siga estos pasos para configurar la cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="bf617-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="bf617-118">Paso <br> 1: Crear un equipo</span><span class="sxs-lookup"><span data-stu-id="bf617-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="bf617-119">Al crear una cola de llamadas, puede agregar usuarios individuales a la cola o puede usar un grupo de seguridad existente, un grupo de Microsoft 365 o un equipo de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bf617-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="bf617-120">Se recomienda usar un equipo.</span><span class="sxs-lookup"><span data-stu-id="bf617-120">We recommend using a team.</span></span> <span data-ttu-id="bf617-121">Esto permite a los miembros de la cola chatear entre sí, compartir ideas y crear documentos u otros recursos para ayudarles a ayudar a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="bf617-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="bf617-122">Un equipo también proporciona un buzón de voz para que los autores de llamadas dejen un mensaje fuera del horario laboral o si la cola alcanza su capacidad máxima.</span><span class="sxs-lookup"><span data-stu-id="bf617-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="bf617-123">Para crear un equipo</span><span class="sxs-lookup"><span data-stu-id="bf617-123">To create a team</span></span>

1. <span data-ttu-id="bf617-124">En primer lugar, haga clic en **Teams** en el lado izquierdo de la aplicación y, a continuación, haga clic en Unirse o crear **un** equipo en la parte inferior de la lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="bf617-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="bf617-125">A **continuación, haga clic en Crear** equipo (primera tarjeta, esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="bf617-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="bf617-126">Elija **Crear un equipo desde cero.**</span><span class="sxs-lookup"><span data-stu-id="bf617-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="bf617-127">A continuación, elija si desea un equipo público o privado.</span><span class="sxs-lookup"><span data-stu-id="bf617-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="bf617-128">Se recomienda **Privado para** la cola de llamadas para evitar que los usuarios se conviertan en parte de la cola involuntaramente uniéndose al equipo.</span><span class="sxs-lookup"><span data-stu-id="bf617-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="bf617-129">Asigne un nombre a su equipo y agregue una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="bf617-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="bf617-130">Cuando haya terminado, haga clic en **Crear.**</span><span class="sxs-lookup"><span data-stu-id="bf617-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="bf617-131">Escriba los nombres de las personas que desea que tengan en la cola de llamadas y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="bf617-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="bf617-132">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bf617-132">Click **Close**.</span></span> <span data-ttu-id="bf617-133">Las personas que agregue a un equipo recibirán un correo electrónico para hacerles saber que ahora son miembros del equipo y el equipo aparecerá en su lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="bf617-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf617-134">Paso 2: Las cuentas de recursos ></span><span class="sxs-lookup"><span data-stu-id="bf617-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="bf617-135">Paso <br> 2: Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="bf617-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="bf617-136">Cada cola de llamadas que cree necesita una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="bf617-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="bf617-137">Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada a un operador automático o a una cola de llamadas en lugar de a una persona.</span><span class="sxs-lookup"><span data-stu-id="bf617-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="bf617-138">En este paso, crearemos la cuenta, le asignaremos una licencia de Sistema telefónico de *Microsoft 365:* usuario virtual y, a continuación, la usaremos para empezar a crear la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="bf617-139">Crear una cuenta de recurso</span><span class="sxs-lookup"><span data-stu-id="bf617-139">Create a resource account</span></span>

<span data-ttu-id="bf617-140">Puede crear una cuenta de recurso en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="bf617-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="bf617-141">En el Centro de administración de Teams, expanda **la configuración de toda la** organización y, a continuación, haga clic en Cuentas de **recursos.**</span><span class="sxs-lookup"><span data-stu-id="bf617-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="bf617-142">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bf617-142">Click **Add**.</span></span>

3. <span data-ttu-id="bf617-143">En el **panel Agregar cuenta de** recurso, rellene **Nombre** para **mostrar,** Nombre de usuario y elija Cola de **llamadas** para el tipo de cuenta **de recursos.**</span><span class="sxs-lookup"><span data-stu-id="bf617-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Captura de pantalla de la interfaz de usuario para agregar una cuenta de recurso](../media/resource-account-add-cq.png)

4. <span data-ttu-id="bf617-145">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bf617-145">Click **Save**.</span></span>

<span data-ttu-id="bf617-146">La nueva cuenta aparecerá en la lista de cuentas.</span><span class="sxs-lookup"><span data-stu-id="bf617-146">The new account will appear in the list of accounts.</span></span>

![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="bf617-148">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="bf617-148">Assign a license</span></span>

<span data-ttu-id="bf617-149">Debe asignar una licencia *de Microsoft 365 Phone System - Virtual User* a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="bf617-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="bf617-150">En el Centro de administración de Microsoft 365, haga clic en la cuenta de recursos a la que desea asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="bf617-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="bf617-151">En la **pestaña Licencias y aplicaciones,** en **Licencias,** seleccione Sistema telefónico de **Microsoft 365 - Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="bf617-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="bf617-152">Haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="bf617-152">Click **Save changes**.</span></span>

    ![Captura de pantalla de la interfaz de usuario de asignación de licencias en el Centro de administración de Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="bf617-154">Crear una cola de llamada</span><span class="sxs-lookup"><span data-stu-id="bf617-154">Create a call queue</span></span>

<span data-ttu-id="bf617-155">A continuación, empezaremos a crear una cola de llamadas y asignaremos la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="bf617-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="bf617-156">En el Centro de administración de Teams, expanda **Voz,** haga clic en **Colas de** llamadas y, a continuación, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="bf617-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="bf617-157">Escriba un nombre para la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-157">Type a name for the call queue.</span></span> <span data-ttu-id="bf617-158">Los agentes verán este nombre cuando reciban una llamada entrante de la cola.</span><span class="sxs-lookup"><span data-stu-id="bf617-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="bf617-159">Haga **clic en Agregar** cuentas, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en Agregar y, a continuación, haga clic en **Agregar.** </span><span class="sxs-lookup"><span data-stu-id="bf617-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="bf617-160">Elige un idioma.</span><span class="sxs-lookup"><span data-stu-id="bf617-160">Choose a language.</span></span> <span data-ttu-id="bf617-161">Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción del correo de voz (si los habilita).</span><span class="sxs-lookup"><span data-stu-id="bf617-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Captura de pantalla de la configuración de cuenta de recursos e idioma](../media/call-queue-name-language.png)

4. <span data-ttu-id="bf617-163">Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola.</span><span class="sxs-lookup"><span data-stu-id="bf617-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="bf617-164">Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que quiere reproducir.</span><span class="sxs-lookup"><span data-stu-id="bf617-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="bf617-165">Teams proporciona música predeterminada a los autores de llamadas mientras están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="bf617-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="bf617-166">Si desea reproducir un archivo de audio específico, elija Reproducir un archivo de **audio** y cargue un archivo MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="bf617-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="bf617-167">La grabación cargada no puede tener un tamaño superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="bf617-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="bf617-168">La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar regalías por su organización.</span><span class="sxs-lookup"><span data-stu-id="bf617-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf617-169">Paso 3: Llamar a agentes ></span><span class="sxs-lookup"><span data-stu-id="bf617-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="bf617-170">Paso 3: <br> agentes de llamadas</span><span class="sxs-lookup"><span data-stu-id="bf617-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="bf617-171">Para agregar agentes a la cola de llamadas, agregaremos el equipo que hemos creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bf617-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="bf617-172">Haga clic **en Agregar grupos.**</span><span class="sxs-lookup"><span data-stu-id="bf617-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="bf617-173">Escriba el nombre del equipo que creó.</span><span class="sxs-lookup"><span data-stu-id="bf617-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="bf617-174">Haga **clic en Agregar** y, a continuación, en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="bf617-174">Click **Add**, and then click **Add**.</span></span>

    ![Captura de pantalla de la configuración de usuarios y grupos para colas de llamadas](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="bf617-176">Puede agregar hasta 20 agentes de forma individual y hasta 200 agentes a través de grupos o equipos.</span><span class="sxs-lookup"><span data-stu-id="bf617-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="bf617-177">Cuando se agregan nuevos usuarios al equipo, la primera llamada puede tardar hasta ocho horas en llegar.</span><span class="sxs-lookup"><span data-stu-id="bf617-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf617-178">Paso 4: Las cuentas de recursos ></span><span class="sxs-lookup"><span data-stu-id="bf617-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="bf617-179">Paso 4: <br> Enrutamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="bf617-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="bf617-180">Elija el método de enrutamiento de llamadas que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="bf617-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="bf617-181">Establecer **el modo de conferencia** en **Automático.**</span><span class="sxs-lookup"><span data-stu-id="bf617-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="bf617-182">Elija el **método de enrutamiento** que desea usar.</span><span class="sxs-lookup"><span data-stu-id="bf617-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="bf617-183">Esto determina el orden en que los agentes reciben llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="bf617-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="bf617-184">Se recomienda enrutamiento **en serie o** round **robin.**</span><span class="sxs-lookup"><span data-stu-id="bf617-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="bf617-185">Elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="bf617-185">Choose from these options:</span></span>

    - <span data-ttu-id="bf617-186">**El enrutamiento del operador** suena a todos los agentes de la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="bf617-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="bf617-187">El primer agente de llamada que recibe la llamada recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf617-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="bf617-188">**El enrutamiento en** serie suena a todos los agentes de llamadas uno por uno.</span><span class="sxs-lookup"><span data-stu-id="bf617-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="bf617-189">Si un agente descarta o no acepta una llamada, la llamada llamará al siguiente agente y probará con todos los agentes hasta que se le llame o se le atende el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bf617-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="bf617-190">**Redondear robin** equilibra el enrutamiento de las llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="bf617-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="bf617-191">Esto puede ser deseable en un entorno de ventas entrantes para garantizar la misma oportunidad entre todos los agentes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="bf617-192">**La inactividad más** larga enruta cada llamada al agente que haya estado inactivo más tiempo.</span><span class="sxs-lookup"><span data-stu-id="bf617-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="bf617-193">(No se incluyen agentes cuyo estado de presencia haya estado durante más de 10 minutos).</span><span class="sxs-lookup"><span data-stu-id="bf617-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="bf617-195">Active **el enrutamiento basado en** presencia.</span><span class="sxs-lookup"><span data-stu-id="bf617-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="bf617-196">De esta forma se enruta las llamadas a agentes cuyo estado de presencia sea **Disponible.**</span><span class="sxs-lookup"><span data-stu-id="bf617-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="bf617-197">Elija si desea permitir que los agentes no puedan participar en las llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="bf617-198">Establezca una **hora de alerta de agente** para especificar cuánto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="bf617-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Captura de pantalla de la configuración de enrutamiento, de no participar y de hora de alerta](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf617-200">Paso 5: desbordamiento de llamadas ></span><span class="sxs-lookup"><span data-stu-id="bf617-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="bf617-201">Paso <br> 5: desbordamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="bf617-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="bf617-202">Elija cómo quiere administrar las llamadas que superan el máximo de la cola.</span><span class="sxs-lookup"><span data-stu-id="bf617-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="bf617-203">Establezca el **número máximo de llamadas en la cola.**</span><span class="sxs-lookup"><span data-stu-id="bf617-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="bf617-204">Elija qué desea hacer cuando se alcanza el número máximo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="bf617-205">Puede desconectar la llamada o redirigirla.</span><span class="sxs-lookup"><span data-stu-id="bf617-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="bf617-206">Le recomendamos redirigir la llamada a uno de los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="bf617-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="bf617-207">**Persona de la organización:** una persona de la organización que puede recibir llamadas de voz</span><span class="sxs-lookup"><span data-stu-id="bf617-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="bf617-208">**Aplicación de voz:** un operador automático u otra cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="bf617-209">(Elija la cuenta de recurso asociada al operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="bf617-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="bf617-210">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="bf617-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="bf617-211">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="bf617-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="bf617-212">**Correo** de voz: puede usar el buzón de voz del equipo que creó.</span><span class="sxs-lookup"><span data-stu-id="bf617-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de pantalla de la configuración de desbordamiento de llamadas](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf617-214">Paso 6: tiempo de espera de llamada ></span><span class="sxs-lookup"><span data-stu-id="bf617-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="bf617-215">Tiempo de espera de la llamada del paso 6 <br></span><span class="sxs-lookup"><span data-stu-id="bf617-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="bf617-216">Elija lo que quiere que suceda cuando las llamadas hayan estado en la cola demasiado tiempo.</span><span class="sxs-lookup"><span data-stu-id="bf617-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="bf617-217">Establezca el tiempo **de espera de la llamada: tiempo de espera máximo.**</span><span class="sxs-lookup"><span data-stu-id="bf617-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="bf617-218">Elija lo que desea hacer cuando se resalte el tiempo de espera de una llamada. Puede desconectar la llamada o redirigirla.</span><span class="sxs-lookup"><span data-stu-id="bf617-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="bf617-219">Le recomendamos redirigir la llamada a uno de los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="bf617-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="bf617-220">**Persona de la organización:** una persona de la organización que puede recibir llamadas de voz</span><span class="sxs-lookup"><span data-stu-id="bf617-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="bf617-221">**Aplicación de voz:** un operador automático u otra cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="bf617-222">(Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="bf617-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="bf617-223">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="bf617-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="bf617-224">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="bf617-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="bf617-225">**Correo** de voz: puede usar el buzón de voz del equipo que creó.</span><span class="sxs-lookup"><span data-stu-id="bf617-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de pantalla de la configuración de tiempo de espera de llamada](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="bf617-227">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bf617-227">Click **Save**.</span></span>

<span data-ttu-id="bf617-228">Con esto se completará la configuración de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf617-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="bf617-229">A continuación, es posible que desee [configurar un operador automático.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="bf617-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---


---
title: 'Crear una cola de llamadas en Microsoft Teams: tutorial de pequeña empresa'
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
description: Obtenga información sobre cómo configurar las colas de llamadas con Microsoft 365 Business Voice.
ms.openlocfilehash: ded780f0793a503e4f4089c7a201e659008e9eb7
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030130"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="94db5-103">Crear una cola de llamadas: tutorial para pequeñas empresas</span><span class="sxs-lookup"><span data-stu-id="94db5-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="94db5-104">Las colas de llamadas proporcionan un método para enrutamiento de autores de llamadas a personas de la organización que pueden ayudarle con un problema o pregunta en particular.</span><span class="sxs-lookup"><span data-stu-id="94db5-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="94db5-105">Las llamadas se distribuyen de una en una a las personas que están en la cola (que se denominan *agentes*).</span><span class="sxs-lookup"><span data-stu-id="94db5-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="94db5-106">Las colas de llamadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="94db5-106">Call queues provide:</span></span>

- <span data-ttu-id="94db5-107">Un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="94db5-107">A greeting message.</span></span>

- <span data-ttu-id="94db5-108">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="94db5-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="94db5-109">Enrutamiento de llamadas *Primera en llegar, primera en salir* (FIFO),en la orden para los agentes.</span><span class="sxs-lookup"><span data-stu-id="94db5-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="94db5-110">Opciones de gestión del desbordamiento de la cola y del tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="94db5-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="94db5-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="94db5-111">Before you begin</span></span>

<span data-ttu-id="94db5-112">Obtener algunas [licencias del sistema telefónico: licencias](../teams-add-on-licensing/virtual-user.md) de usuario virtual si aún no las tiene.</span><span class="sxs-lookup"><span data-stu-id="94db5-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="94db5-113">Obtenga una por cada cola de llamadas y operador automático que tiene previsto configurar.</span><span class="sxs-lookup"><span data-stu-id="94db5-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="94db5-114">Estas licencias son gratuitas, por lo que le recomendamos obtener algunas adicionales en caso de que decida realizar cambios en su configuración en el futuro.</span><span class="sxs-lookup"><span data-stu-id="94db5-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="94db5-115">Puesto que los agentes de una cola de llamadas pueden llamar para devolver una llamada de cliente, considere la posibilidad de establecer el identificador de llamada de los agentes de llamada en su número de teléfono principal o el número de un operador automático adecuado.</span><span class="sxs-lookup"><span data-stu-id="94db5-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="94db5-116">Consulte [administrar las directivas de identificador de llamada en Microsoft Teams](../caller-id-policies.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="94db5-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="94db5-117">Siga estos pasos para configurar la cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="94db5-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="94db5-118">Paso 1 <br> Crear un equipo</span><span class="sxs-lookup"><span data-stu-id="94db5-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="94db5-119">Al crear una cola de llamadas, puede agregar usuarios individuales a la cola o puede usar un grupo de seguridad existente, un grupo de Microsoft 365 o un equipo de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="94db5-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="94db5-120">Se recomienda [usar un canal de grupo.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="94db5-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="94db5-121">Esto permite a los miembros de la cola chatear entre sí, compartir ideas y crear documentos u otros recursos para ayudarles a ayudar a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="94db5-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="94db5-122">Un equipo también proporciona un buzón de voz para que los autores de llamadas dejen un mensaje fuera del horario laboral o si la cola alcanza su capacidad máxima.</span><span class="sxs-lookup"><span data-stu-id="94db5-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="94db5-123">Para crear un equipo</span><span class="sxs-lookup"><span data-stu-id="94db5-123">To create a team</span></span>

1. <span data-ttu-id="94db5-124">En primer lugar, haga clic en **Teams** en el lado izquierdo de la aplicación y, a continuación, haga clic en Unirse **o crear un** equipo en la parte inferior de la lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="94db5-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="94db5-125">A **continuación, haga** clic en Crear equipo (primera tarjeta, esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="94db5-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="94db5-126">Elija **Crear un equipo desde cero.**</span><span class="sxs-lookup"><span data-stu-id="94db5-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="94db5-127">A continuación, elija si desea un equipo público o privado.</span><span class="sxs-lookup"><span data-stu-id="94db5-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="94db5-128">Recomendamos **Privado para** la cola de llamadas para evitar que los usuarios se conviertan involuntaramente en parte de la cola uniéndose al equipo.</span><span class="sxs-lookup"><span data-stu-id="94db5-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="94db5-129">Asigne un nombre al equipo y agregue una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="94db5-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="94db5-130">Cuando haya terminado, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="94db5-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="94db5-131">Escriba los nombres de las personas que desea tener en la cola de llamadas y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="94db5-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="94db5-132">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-132">Click **Close**.</span></span> <span data-ttu-id="94db5-133">Las personas que agregue a un equipo recibirán un correo electrónico para que sepan que ahora son miembros de su equipo y que el equipo aparecerá en su lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="94db5-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="94db5-134">A continuación, agregaremos un canal para usarlo con la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94db5-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="94db5-135">Para agregar un canal</span><span class="sxs-lookup"><span data-stu-id="94db5-135">To add a channel</span></span>

1. <span data-ttu-id="94db5-136">En Teams, busque el equipo que acaba de crear, haga clic en **Más opciones** (...)y, a continuación, haga clic en **Agregar canal.**</span><span class="sxs-lookup"><span data-stu-id="94db5-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="94db5-137">Escriba un nombre y una descripción para el canal y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94db5-138">Paso 2: Cuentas de recursos ></span><span class="sxs-lookup"><span data-stu-id="94db5-138">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="94db5-139">Paso 2 <br> Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="94db5-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="94db5-140">Cada cola de llamadas que cree requiere una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="94db5-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="94db5-141">Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada con un operador automático o una cola de llamadas en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="94db5-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="94db5-142">En este paso, crearemos la cuenta, le asignaremos una licencia de *Microsoft 365 Phone System - Virtual User* y, a continuación, la usaremos para empezar a crear la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94db5-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="94db5-143">Crear una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="94db5-143">Create a resource account</span></span>

<span data-ttu-id="94db5-144">Puede crear una cuenta de recursos en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="94db5-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="94db5-145">En el Centro de administración de Teams, expanda **Configuración de toda la organización** y, a continuación, haga clic en Cuentas de **recursos.**</span><span class="sxs-lookup"><span data-stu-id="94db5-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="94db5-146">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-146">Click **Add**.</span></span>

3. <span data-ttu-id="94db5-147">En el **panel Agregar cuenta de** recursos, rellene **Nombre** para mostrar, **Nombre** de usuario y elija Cola **de llamadas** para el tipo de **cuenta Recurso.**</span><span class="sxs-lookup"><span data-stu-id="94db5-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="94db5-148">Los agentes verán el nombre para mostrar cuando reciban una llamada entrante desde la cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-148">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add-cq.png)

4. <span data-ttu-id="94db5-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-150">Click **Save**.</span></span>

   <span data-ttu-id="94db5-151">La nueva cuenta aparecerá en la lista de cuentas.</span><span class="sxs-lookup"><span data-stu-id="94db5-151">The new account will appear in the list of accounts.</span></span>

   ![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="94db5-153">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="94db5-153">Assign a license</span></span>

<span data-ttu-id="94db5-154">Debe asignar una licencia de Usuario virtual de *Microsoft 365 Phone System* a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="94db5-154">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="94db5-155">En el Centro de administración de  Microsoft 365, en la lista Usuarios activos, haga clic en la cuenta de recursos a la que desea asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="94db5-155">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="94db5-156">En la **pestaña Licencias y aplicaciones,** en **Licencias,** seleccione **Microsoft 365 Phone System - Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="94db5-156">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="94db5-157">Haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="94db5-157">Click **Save changes**.</span></span>

    ![Captura de pantalla de la interfaz de usuario asignar licencias en el Centro de administración de Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="94db5-159">Crear una cola de llamada</span><span class="sxs-lookup"><span data-stu-id="94db5-159">Create a call queue</span></span>

<span data-ttu-id="94db5-160">A continuación, empezaremos a crear una nueva cola de llamadas y asignaremos la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="94db5-160">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="94db5-161">En el Centro de administración de Teams, expanda **Voz,** haga clic en **Colas de** llamadas y, a continuación, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="94db5-161">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="94db5-162">Escriba un nombre descriptivo para la cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-162">Type a name for the call queue.</span></span>

2. <span data-ttu-id="94db5-163">Haga clic en **Agregar cuentas**, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="94db5-164">Elegir un idioma</span><span class="sxs-lookup"><span data-stu-id="94db5-164">Choose a language.</span></span> <span data-ttu-id="94db5-165">Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción de correo de voz (si las habilita).</span><span class="sxs-lookup"><span data-stu-id="94db5-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Captura de pantalla de la configuración de la cuenta de recursos y de idioma](../media/call-queue-name-language.png)

4. <span data-ttu-id="94db5-167">Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="94db5-168">Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="94db5-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="94db5-169">Los equipos proporcionan música predeterminada a los autores de llamadas mientras están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="94db5-170">Si desea reproducir un archivo de audio específico, elija **Reproducir un archivo de audio en** y cargar un archivo MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="94db5-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="94db5-171">La grabación cargada no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="94db5-171">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="94db5-172">La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar ningún pago de la organización.</span><span class="sxs-lookup"><span data-stu-id="94db5-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="94db5-173">Paso 3: llamar a agentes ></span><span class="sxs-lookup"><span data-stu-id="94db5-173">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="94db5-174">Paso 3 <br> Llamar a agentes</span><span class="sxs-lookup"><span data-stu-id="94db5-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="94db5-175">Para agregar agentes a la cola de llamadas, los agregaremos al equipo y al canal que creamos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="94db5-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="94db5-176">Seleccione la **opción Elegir un equipo** y haga clic en Agregar un **canal.**</span><span class="sxs-lookup"><span data-stu-id="94db5-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="94db5-177">Escriba el nombre del equipo que creó, selecciónelo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="94db5-178">Seleccione el canal que creó para la cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="94db5-179">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-179">Click **Apply**.</span></span>

    ![Captura de pantalla de la configuración de usuarios y grupos para las colas de llamadas](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="94db5-181">Cuando se agregan nuevos usuarios al equipo, la primera llamada puede tardar hasta ocho horas en llegar.</span><span class="sxs-lookup"><span data-stu-id="94db5-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94db5-182">Paso 4: Cuentas de recursos ></span><span class="sxs-lookup"><span data-stu-id="94db5-182">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="94db5-183">Paso 4 <br> Enrutamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="94db5-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="94db5-184">Elija el método de enrutamiento de llamadas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="94db5-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="94db5-185">Establecer **el modo de conferencia** en **Auto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="94db5-186">Elija el **método de enrutamiento** que desea usar.</span><span class="sxs-lookup"><span data-stu-id="94db5-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="94db5-187">Esto determina el orden en que los agentes reciben llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="94db5-188">Se recomienda **Enrutamiento en serie** o **Redondear.**</span><span class="sxs-lookup"><span data-stu-id="94db5-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="94db5-189">Elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="94db5-189">Choose from these options:</span></span>

    - <span data-ttu-id="94db5-190">**El enrutamiento de operador** hace una llamada a todos los agentes en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="94db5-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="94db5-191">El primer agente de llamada que tome la llamada la recibe.</span><span class="sxs-lookup"><span data-stu-id="94db5-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="94db5-192">**El enrutamiento en** serie llama a todos los agentes de llamada uno por uno.</span><span class="sxs-lookup"><span data-stu-id="94db5-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="94db5-193">Si un agente desestima o no contesta una llamada, se realizará una llamada al siguiente agente y se intentará con todos los agentes hasta que la llamada sea contestada o se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="94db5-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="94db5-194">**Distribución equilibrada** equilibra el enrutamiento de llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="94db5-195">Esto puede ser deseable en un entorno de ventas de entrada para asegurar la misma oportunidad entre todos los agentes de llamada.</span><span class="sxs-lookup"><span data-stu-id="94db5-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="94db5-196">**Inactividad mayor** dirige cada llamada al agente que ha estado inactivo por más tiempo.</span><span class="sxs-lookup"><span data-stu-id="94db5-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="94db5-197">(No se incluyen agentes cuyo estado de presencia ha estado fuera durante más de 10 minutos).</span><span class="sxs-lookup"><span data-stu-id="94db5-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="94db5-199">Active **el enrutamiento basado en presencia.**</span><span class="sxs-lookup"><span data-stu-id="94db5-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="94db5-200">Esto enruta las llamadas a agentes cuyo estado de presencia es **Disponible.**</span><span class="sxs-lookup"><span data-stu-id="94db5-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="94db5-201">Elija si desea permitir que los agentes no puedan realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="94db5-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="94db5-202">Establezca una **hora de alerta del agente** para especificar cuánto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="94db5-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Captura de pantalla de configuración de enrutamiento, de baja y de hora de alerta](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="94db5-204">Paso 5: desbordamiento de llamadas ></span><span class="sxs-lookup"><span data-stu-id="94db5-204">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="94db5-205">Paso 5 <br> Desbordamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="94db5-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="94db5-206">Elija cómo desea controlar las llamadas que superan el máximo de la cola.</span><span class="sxs-lookup"><span data-stu-id="94db5-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="94db5-207">Establezca el **valor Máximo de llamadas en la cola.**</span><span class="sxs-lookup"><span data-stu-id="94db5-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="94db5-208">Elija lo que desea hacer cuando se alcance el número máximo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94db5-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="94db5-209">Puede desconectar la llamada o redirigirla.</span><span class="sxs-lookup"><span data-stu-id="94db5-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="94db5-210">Se recomienda redirigir la llamada a uno de los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="94db5-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="94db5-211">**Persona de la organización:** una persona de su organización que puede recibir llamadas de voz</span><span class="sxs-lookup"><span data-stu-id="94db5-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="94db5-212">**Aplicación de voz:** un operador automático u otra cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94db5-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="94db5-213">(Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="94db5-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="94db5-214">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="94db5-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="94db5-215">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="94db5-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="94db5-216">**Correo** de voz: puede usar el buzón de voz del equipo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="94db5-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de pantalla de la configuración de desbordamiento de llamadas](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="94db5-218">Paso 6: tiempo de espera de la llamada ></span><span class="sxs-lookup"><span data-stu-id="94db5-218">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="94db5-219">Paso 6 <br> Tiempo de espera de llamada</span><span class="sxs-lookup"><span data-stu-id="94db5-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="94db5-220">Elija lo que desea que suceda cuando las llamadas hayan estado esperando en la cola durante demasiado tiempo.</span><span class="sxs-lookup"><span data-stu-id="94db5-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="94db5-221">Establecer el **tiempo de espera máximo**.</span><span class="sxs-lookup"><span data-stu-id="94db5-221">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="94db5-222">Elija lo que desea hacer cuando se resalte el tiempo de espera de una llamada. Puede desconectar la llamada o redirigirla.</span><span class="sxs-lookup"><span data-stu-id="94db5-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="94db5-223">Se recomienda redirigir la llamada a uno de los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="94db5-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="94db5-224">**Persona de la organización:** una persona de su organización que puede recibir llamadas de voz</span><span class="sxs-lookup"><span data-stu-id="94db5-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="94db5-225">**Aplicación de voz:** un operador automático u otra cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94db5-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="94db5-226">(Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="94db5-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="94db5-227">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="94db5-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="94db5-228">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="94db5-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="94db5-229">**Correo** de voz: puede usar el buzón de voz del equipo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="94db5-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de pantalla de la configuración del tiempo de espera de la llamada](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="94db5-231">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94db5-231">Click **Save**.</span></span>

<span data-ttu-id="94db5-232">Esto completa la configuración de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94db5-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="94db5-233">A continuación, es posible que desee [configurar un operador automático.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="94db5-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---


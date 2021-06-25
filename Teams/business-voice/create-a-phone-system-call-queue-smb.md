---
title: Crear una cola de llamadas en Microsoft Teams - tutorial de pequeña empresa
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
description: Obtenga información sobre cómo configurar colas de llamadas para pequeñas empresas en Microsoft 365 Business Voice.
ms.openlocfilehash: e7141d32015207469346e018bc12bc362254ba2f
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126926"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="67cd1-103">Crear una cola de llamadas: tutorial para pequeñas empresas</span><span class="sxs-lookup"><span data-stu-id="67cd1-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="67cd1-104">Las colas de llamadas proporcionan un método para enrutamiento de autores de llamadas a personas de la organización que pueden ayudarle con un problema o pregunta en particular.</span><span class="sxs-lookup"><span data-stu-id="67cd1-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="67cd1-105">Las llamadas se distribuyen de una en una a las personas que están en la cola (que se denominan *agentes*).</span><span class="sxs-lookup"><span data-stu-id="67cd1-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="67cd1-106">Las colas de llamadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="67cd1-106">Call queues provide:</span></span>

- <span data-ttu-id="67cd1-107">Un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="67cd1-107">A greeting message.</span></span>

- <span data-ttu-id="67cd1-108">Música que se reproduce mientras los usuarios se mantienen a la espera.</span><span class="sxs-lookup"><span data-stu-id="67cd1-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="67cd1-109">Enrutamiento de llamadas *Primera en llegar, primera en salir* (FIFO),en la orden para los agentes.</span><span class="sxs-lookup"><span data-stu-id="67cd1-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="67cd1-110">Opciones de gestión del desbordamiento de la cola y del tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="67cd1-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="67cd1-111">Demostración de vídeo</span><span class="sxs-lookup"><span data-stu-id="67cd1-111">Video demonstration</span></span>

<span data-ttu-id="67cd1-112">En este vídeo se muestra cómo crear una cola de llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="67cd1-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="67cd1-113">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="67cd1-113">Before you begin</span></span>

<span data-ttu-id="67cd1-114">Obtener algunas [Sistema telefónico: licencias de usuario virtual](../teams-add-on-licensing/virtual-user.md) si aún no las tiene.</span><span class="sxs-lookup"><span data-stu-id="67cd1-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="67cd1-115">Obtenga una por cada cola de llamadas y operador automático que tiene previsto configurar.</span><span class="sxs-lookup"><span data-stu-id="67cd1-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="67cd1-116">Estas licencias son gratuitas, por lo que le recomendamos obtener algunas adicionales en caso de que decida realizar cambios en su configuración en el futuro.</span><span class="sxs-lookup"><span data-stu-id="67cd1-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="67cd1-117">Puesto que los agentes de una cola de llamadas pueden llamar para devolver una llamada de cliente, considere la posibilidad de establecer el identificador de llamada de los agentes de llamada en su número de teléfono principal o el número de un operador automático adecuado.</span><span class="sxs-lookup"><span data-stu-id="67cd1-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="67cd1-118">Consulte [administrar las directivas de identificador de llamada en Microsoft Teams](../caller-id-policies.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="67cd1-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="67cd1-119">Siga estos pasos para configurar la cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="67cd1-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="67cd1-120">Paso 1 <br> Crear un equipo</span><span class="sxs-lookup"><span data-stu-id="67cd1-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="67cd1-121">Al crear una cola de llamadas, puede agregar usuarios individuales a la cola o puede usar un grupo de seguridad existente, Microsoft 365 grupo o Microsoft Teams grupo.</span><span class="sxs-lookup"><span data-stu-id="67cd1-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="67cd1-122">Se recomienda [usar un canal de grupo.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="67cd1-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="67cd1-123">Esto permite a los miembros de la cola chatear entre sí, compartir ideas y crear documentos u otros recursos para ayudarles a ayudar a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="67cd1-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="67cd1-124">Un equipo también proporciona un buzón de voz para que los autores de llamadas dejen un mensaje fuera del horario laboral o si la cola alcanza su capacidad máxima.</span><span class="sxs-lookup"><span data-stu-id="67cd1-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="67cd1-125">Para crear un equipo</span><span class="sxs-lookup"><span data-stu-id="67cd1-125">To create a team</span></span>

1. <span data-ttu-id="67cd1-126">En primer lugar, **haga clic Teams** en el lado izquierdo de la aplicación y, a continuación, haga clic en Unirse o crear **un** equipo en la parte inferior de la lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="67cd1-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="67cd1-127">A **continuación, haga** clic en Crear equipo (primera tarjeta, esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="67cd1-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="67cd1-128">Elija **Crear un equipo desde cero.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="67cd1-129">A continuación, elija si desea un equipo público o privado.</span><span class="sxs-lookup"><span data-stu-id="67cd1-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="67cd1-130">Recomendamos **Privado para** la cola de llamadas para evitar que los usuarios se conviertan involuntaramente en parte de la cola uniéndose al equipo.</span><span class="sxs-lookup"><span data-stu-id="67cd1-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="67cd1-131">Asigne un nombre al equipo y agregue una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="67cd1-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="67cd1-132">Cuando haya terminado, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="67cd1-133">Escriba los nombres de las personas que desea tener en la cola de llamadas y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="67cd1-134">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-134">Click **Close**.</span></span> <span data-ttu-id="67cd1-135">Las personas que agregue a un equipo recibirán un correo electrónico para que sepan que ahora son miembros de su equipo y que el equipo aparecerá en su lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="67cd1-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="67cd1-136">A continuación, agregaremos un canal para usarlo con la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="67cd1-137">Para agregar un canal</span><span class="sxs-lookup"><span data-stu-id="67cd1-137">To add a channel</span></span>

1. <span data-ttu-id="67cd1-138">En Teams, busque el equipo que acaba de crear, haga clic en **Más opciones** (...)y, a continuación, haga clic en **Agregar canal.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="67cd1-139">Escriba un nombre y una descripción para el canal y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="67cd1-140">Paso 2: Cuentas de recursos ></span><span class="sxs-lookup"><span data-stu-id="67cd1-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="67cd1-141">Paso 2 <br> Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="67cd1-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="67cd1-142">Cada cola de llamadas que cree requiere una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="67cd1-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="67cd1-143">Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada con un operador automático o una cola de llamadas en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="67cd1-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="67cd1-144">En este paso, crearemos la cuenta, le asignaremos una *Microsoft 365 Sistema telefónico:* licencia de usuario virtual y, a continuación, la usaremos para empezar a crear la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="67cd1-145">Crear una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="67cd1-145">Create a resource account</span></span>

<span data-ttu-id="67cd1-146">Puede crear una cuenta de recursos en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="67cd1-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="67cd1-147">En el Teams de administración, expanda **Configuración de** toda la organización y, a continuación, haga clic en Cuentas **de recursos.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="67cd1-148">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-148">Click **Add**.</span></span>

3. <span data-ttu-id="67cd1-149">En el **panel Agregar cuenta de** recursos, rellene **Nombre** para mostrar, **Nombre** de usuario y elija Cola **de llamadas** para el tipo de **cuenta Recurso.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="67cd1-150">Los agentes verán el nombre para mostrar cuando reciban una llamada entrante desde la cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add-cq.png)

4. <span data-ttu-id="67cd1-152">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-152">Click **Save**.</span></span>

   <span data-ttu-id="67cd1-153">La nueva cuenta aparecerá en la lista de cuentas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-153">The new account will appear in the list of accounts.</span></span>

   ![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="67cd1-155">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="67cd1-155">Assign a license</span></span>

<span data-ttu-id="67cd1-156">Debe asignar una licencia *Microsoft 365 Sistema telefónico usuario virtual* a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="67cd1-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="67cd1-157">En la Centro de administración de Microsoft 365, en la **lista Usuarios** activos, haga clic en la cuenta de recursos a la que desea asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="67cd1-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="67cd1-158">En la **pestaña Licencias y aplicaciones,** en **Licencias,** **seleccione Microsoft 365 Sistema telefónico - Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="67cd1-159">Haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-159">Click **Save changes**.</span></span>

    ![Captura de pantalla de la interfaz de usuario asignar licencias en el Centro de administración de Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="67cd1-161">Crear una cola de llamada</span><span class="sxs-lookup"><span data-stu-id="67cd1-161">Create a call queue</span></span>

<span data-ttu-id="67cd1-162">A continuación, empezaremos a crear una nueva cola de llamadas y asignaremos la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="67cd1-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="67cd1-163">En el Teams de administración, expanda **Voz,** haga clic en **Colas de** llamadas y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="67cd1-164">Escriba un nombre descriptivo para la cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="67cd1-165">Haga clic en **Agregar cuentas**, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en **Agregar** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="67cd1-166">(Opcional) En **Asignar id. de** llamada, haga clic en **Agregar**, busque las cuentas de recursos que creó para el operador automático, haga clic en Agregar **y,** a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-166">(Optional) Under **Assign calling ID**, click **Add**, search for the resource accounts that you created for your auto attendant, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="67cd1-167">Esto dará a los agentes de llamada el identificador de llamada de la línea principal cuando llamen.</span><span class="sxs-lookup"><span data-stu-id="67cd1-167">This will give your call agents the caller ID of your main line when they call out.</span></span>

    ![Captura de pantalla de la configuración de id. de llamada](../media/call-queue-assign-calling-id.png)

3. <span data-ttu-id="67cd1-169">Elegir un idioma</span><span class="sxs-lookup"><span data-stu-id="67cd1-169">Choose a language.</span></span> <span data-ttu-id="67cd1-170">Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción de correo de voz (si las habilita).</span><span class="sxs-lookup"><span data-stu-id="67cd1-170">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Captura de pantalla de la configuración de la cuenta de recursos](../media/call-queue-name-language.png)

4. <span data-ttu-id="67cd1-172">Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-172">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="67cd1-173">Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="67cd1-173">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="67cd1-174">Los equipos proporcionan música predeterminada a los autores de llamadas mientras están en espera en una cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-174">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="67cd1-175">Si desea reproducir un archivo de audio específico, elija **Reproducir un archivo de audio en** y cargar un archivo MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="67cd1-175">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="67cd1-176">La grabación cargada no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="67cd1-176">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="67cd1-177">La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar ningún pago de la organización.</span><span class="sxs-lookup"><span data-stu-id="67cd1-177">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="67cd1-178">Paso 3: llamar a agentes ></span><span class="sxs-lookup"><span data-stu-id="67cd1-178">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="67cd1-179">Paso 3 <br> Llamar a agentes</span><span class="sxs-lookup"><span data-stu-id="67cd1-179">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="67cd1-180">Para agregar agentes a la cola de llamadas, los agregaremos al equipo y al canal que creamos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="67cd1-180">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span> <span data-ttu-id="67cd1-181">Para ello, debe ser miembro del equipo.</span><span class="sxs-lookup"><span data-stu-id="67cd1-181">You need to be a member of the team to do this.</span></span>

1. <span data-ttu-id="67cd1-182">Seleccione la **opción Elegir un equipo** y haga clic en Agregar un **canal.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-182">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="67cd1-183">Escriba el nombre del equipo que creó, selecciónelo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-183">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="67cd1-184">Seleccione el canal que creó para la cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-184">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="67cd1-185">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-185">Click **Apply**.</span></span>

    ![Captura de pantalla de la configuración de usuarios y grupos para las colas de llamadas](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="67cd1-187">Cuando se agregan nuevos usuarios al equipo, la primera llamada puede tardar hasta ocho horas en llegar.</span><span class="sxs-lookup"><span data-stu-id="67cd1-187">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="67cd1-188">Paso 4: Cuentas de recursos ></span><span class="sxs-lookup"><span data-stu-id="67cd1-188">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="67cd1-189">Paso 4 <br> Enrutamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="67cd1-189">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="67cd1-190">Elija el método de enrutamiento de llamadas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="67cd1-190">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="67cd1-191">Establecer **el modo de conferencia** en **Auto**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-191">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="67cd1-192">Elija el **método de enrutamiento** que desea usar.</span><span class="sxs-lookup"><span data-stu-id="67cd1-192">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="67cd1-193">Esto determina el orden en que los agentes reciben llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-193">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="67cd1-194">Se recomienda **Enrutamiento en serie** o **Redondear.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-194">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="67cd1-195">Elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="67cd1-195">Choose from these options:</span></span>

    - <span data-ttu-id="67cd1-196">**El enrutamiento de operador** hace una llamada a todos los agentes en la cola al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="67cd1-196">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="67cd1-197">El primer agente de llamada que tome la llamada la recibe.</span><span class="sxs-lookup"><span data-stu-id="67cd1-197">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="67cd1-198">**El enrutamiento en** serie llama a todos los agentes de llamada uno por uno.</span><span class="sxs-lookup"><span data-stu-id="67cd1-198">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="67cd1-199">Si un agente desestima o no contesta una llamada, se realizará una llamada al siguiente agente y se intentará con todos los agentes hasta que la llamada sea contestada o se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="67cd1-199">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="67cd1-200">**Distribución equilibrada** equilibra el enrutamiento de llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-200">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="67cd1-201">Esto puede ser deseable en un entorno de ventas de entrada para asegurar la misma oportunidad entre todos los agentes de llamada.</span><span class="sxs-lookup"><span data-stu-id="67cd1-201">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="67cd1-202">**Inactividad mayor** dirige cada llamada al agente que ha estado inactivo por más tiempo.</span><span class="sxs-lookup"><span data-stu-id="67cd1-202">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="67cd1-203">(No se incluyen agentes cuyo estado de presencia ha estado fuera durante más de 10 minutos).</span><span class="sxs-lookup"><span data-stu-id="67cd1-203">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="67cd1-205">Active **el enrutamiento basado en presencia.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-205">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="67cd1-206">Esto enruta las llamadas a agentes cuyo estado de presencia es **Disponible.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-206">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="67cd1-207">Elija si desea permitir que los agentes no puedan realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-207">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="67cd1-208">Establezca una **hora de alerta del agente** para especificar cuánto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.</span><span class="sxs-lookup"><span data-stu-id="67cd1-208">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Captura de pantalla de configuración de enrutamiento, de baja y de hora de alerta](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="67cd1-210">Paso 5: desbordamiento de llamadas ></span><span class="sxs-lookup"><span data-stu-id="67cd1-210">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="67cd1-211">Paso 5 <br> Desbordamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="67cd1-211">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="67cd1-212">Elija cómo desea controlar las llamadas que superan el máximo de la cola.</span><span class="sxs-lookup"><span data-stu-id="67cd1-212">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="67cd1-213">Establezca el **valor Máximo de llamadas en la cola.**</span><span class="sxs-lookup"><span data-stu-id="67cd1-213">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="67cd1-214">Elija lo que desea hacer cuando se alcance el número máximo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-214">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="67cd1-215">Puede desconectar la llamada o redirigirla.</span><span class="sxs-lookup"><span data-stu-id="67cd1-215">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="67cd1-216">Se recomienda redirigir la llamada a uno de los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="67cd1-216">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="67cd1-217">**Persona de la organización:** una persona de su organización que puede recibir llamadas de voz</span><span class="sxs-lookup"><span data-stu-id="67cd1-217">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="67cd1-218">**Aplicación de voz:** un operador automático u otra cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-218">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="67cd1-219">(Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="67cd1-219">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="67cd1-220">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="67cd1-220">**External phone number** - any phone number.</span></span> <span data-ttu-id="67cd1-221">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="67cd1-221">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="67cd1-222">**Correo** de voz: puede usar el buzón de voz del equipo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="67cd1-222">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de pantalla de la configuración de desbordamiento de llamadas](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="67cd1-224">Paso 6: tiempo de espera de la llamada ></span><span class="sxs-lookup"><span data-stu-id="67cd1-224">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="67cd1-225">Paso 6 <br> Tiempo de espera de llamada</span><span class="sxs-lookup"><span data-stu-id="67cd1-225">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="67cd1-226">Elija lo que desea que suceda cuando las llamadas hayan estado esperando en la cola durante demasiado tiempo.</span><span class="sxs-lookup"><span data-stu-id="67cd1-226">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="67cd1-227">Establecer el **tiempo de espera máximo**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-227">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="67cd1-228">Elija lo que desea hacer cuando se resalte el tiempo de espera de una llamada. Puede desconectar la llamada o redirigirla.</span><span class="sxs-lookup"><span data-stu-id="67cd1-228">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="67cd1-229">Se recomienda redirigir la llamada a uno de los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="67cd1-229">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="67cd1-230">**Persona de la organización:** una persona de su organización que puede recibir llamadas de voz</span><span class="sxs-lookup"><span data-stu-id="67cd1-230">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="67cd1-231">**Aplicación de voz:** un operador automático u otra cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-231">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="67cd1-232">(Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="67cd1-232">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="67cd1-233">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="67cd1-233">**External phone number** - any phone number.</span></span> <span data-ttu-id="67cd1-234">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="67cd1-234">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="67cd1-235">**Correo** de voz: puede usar el buzón de voz del equipo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="67cd1-235">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de pantalla de la configuración del tiempo de espera de la llamada](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="67cd1-237">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="67cd1-237">Click **Save**.</span></span>

<span data-ttu-id="67cd1-238">Esto completa la configuración de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="67cd1-238">This completes the setup of your call queue.</span></span> <span data-ttu-id="67cd1-239">A continuación, es posible que desee [configurar un operador automático.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="67cd1-239">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---


#### <a name="video-demonstration"></a><span data-ttu-id="e3cd7-101">Demostración de vídeo</span><span class="sxs-lookup"><span data-stu-id="e3cd7-101">Video demonstration</span></span>

<span data-ttu-id="e3cd7-102">En este vídeo se muestra un ejemplo básico de cómo crear un operador automático en Teams.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-102">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="e3cd7-103">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e3cd7-103">Before you begin</span></span>

<span data-ttu-id="e3cd7-104">Obtenga los números de servicio (los números de servicio son un tipo especial de número de teléfono que usan los operadores automáticos) que necesita para los operadores automáticos a los que desea obtener acceso mediante la marcación directa desde fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-104">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="e3cd7-105">Esto puede incluir [la transferencia de números de otro proveedor](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la solicitud de nuevos números de [servicio.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="e3cd7-105">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="e3cd7-106">A cada operador automático se le debe asignar una Sistema telefónico: licencia de usuario virtual.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-106">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="e3cd7-107">Al comprar Business Voice, también recibió una serie de Sistema telefónico: licencias de usuario virtual, por lo que probablemente no necesite solicitar más.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-107">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="e3cd7-108">Sin embargo, si necesita más en el futuro, puede obtenerlas siguiendo las instrucciones de [Sistema telefónico - Licencia de usuario virtual](../teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="e3cd7-108">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="e3cd7-109">Si desea que la ruta de operador automático [](../set-up-holidays-in-teams.md) llame de forma diferente los días festivos, cree los días festivos que quiera usar antes de crear el operador automático.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-109">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="e3cd7-110">Siga estos pasos para configurar el operador automático</span><span class="sxs-lookup"><span data-stu-id="e3cd7-110">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="e3cd7-111">Paso 1 <br> Teléfono número</span><span class="sxs-lookup"><span data-stu-id="e3cd7-111">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="e3cd7-112">Si sigue los pasos para configurar Business Voice por primera vez y está en el paso **6:** Configurar un operador automático para el número de teléfono principal de su empresa, ya ha terminado los pasos de esta pestaña. Ir a la pestaña siguiente: [Información general del operador automático.](?tabs=general-info#steps)</span><span class="sxs-lookup"><span data-stu-id="e3cd7-112">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="e3cd7-113">Cada operador automático que cree requiere una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-113">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="e3cd7-114">Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada con un operador automático o una cola de llamadas en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-114">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="e3cd7-115">En este paso, crearemos la cuenta, le asignaremos una licencia *Microsoft 365 Sistema telefónico usuario virtual* y, a continuación, asignaremos un número de servicio.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-115">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="e3cd7-116">Crear una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="e3cd7-116">Create a resource account</span></span>

<span data-ttu-id="e3cd7-117">Puede crear una cuenta de recursos en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-117">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="e3cd7-118">En el Teams de administración, expanda **Configuración de** toda la organización y, a continuación, haga clic en Cuentas **de recursos.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-118">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="e3cd7-119">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-119">Click **Add**.</span></span>

3. <span data-ttu-id="e3cd7-120">En el **panel Agregar cuenta de** recursos, rellene **Nombre** para mostrar, Nombre de **usuario** y elija **Operador automático** para el tipo de **cuenta Recurso**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-120">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add.png)

4. <span data-ttu-id="e3cd7-122">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-122">Click **Save**.</span></span>

    <span data-ttu-id="e3cd7-123">La nueva cuenta aparecerá en la lista de cuentas.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-123">The new account will appear in the list of accounts.</span></span>

    ![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="e3cd7-125">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="e3cd7-125">Assign a license</span></span>

<span data-ttu-id="e3cd7-126">Debe asignar una licencia *Microsoft 365 Sistema telefónico usuario virtual* a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-126">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="e3cd7-127">En el Microsoft 365 de administración, haga clic en la cuenta de recursos a la que desea asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-127">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="e3cd7-128">En la **pestaña Licencias y aplicaciones,** en **Licencias,** **seleccione Microsoft 365 Sistema telefónico - Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-128">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="e3cd7-129">Haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-129">Click **Save changes**.</span></span>

    ![Captura de pantalla de la interfaz de usuario asignar licencias en el Microsoft 365 de administración](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="e3cd7-131">Asignar un número de servicio</span><span class="sxs-lookup"><span data-stu-id="e3cd7-131">Assign a service number</span></span>

<span data-ttu-id="e3cd7-132">Si necesita que este operador automático sea accesible mediante un número de teléfono, asigne ese número a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-132">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="e3cd7-133">En el Teams de administración,  en la página Cuentas de recursos, seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en Asignar **o desasignación.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-133">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="e3cd7-134">En el **Teléfono de tipo de número,** elija el tipo de número que desea usar.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-134">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="e3cd7-135">En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-135">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="e3cd7-137">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-137">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e3cd7-138">Paso 2: Información general del operador automático ></span><span class="sxs-lookup"><span data-stu-id="e3cd7-138">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="e3cd7-139">Paso 2 <br> Información general del operador</span><span class="sxs-lookup"><span data-stu-id="e3cd7-139">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="e3cd7-140">Para configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="e3cd7-140">To set up an auto attendant</span></span>

1. <span data-ttu-id="e3cd7-141">En el Teams de administración, expanda **Voz,** haga clic en **Operadores automáticos** y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-141">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="e3cd7-142">Escriba un nombre para el operador automático en el cuadro de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-142">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="e3cd7-143">Si desea designar un operador, especifique el destino de las llamadas al operador.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-143">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="e3cd7-144">Esto es opcional (pero recomendado).</span><span class="sxs-lookup"><span data-stu-id="e3cd7-144">This is optional (but recommended).</span></span> <span data-ttu-id="e3cd7-145">Puede establecer la opción **Operador** para permitir a los autores de llamadas salir de los menús y hablar con una persona designada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-145">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="e3cd7-146">Especifique la zona horaria para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-146">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="e3cd7-147">La zona horaria se usa para calcular el horario laboral si crea un flujo de llamadas independiente para horas posteriores.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-147">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="e3cd7-148">Especifique un idioma para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-148">Specify a language for this auto attendant.</span></span> <span data-ttu-id="e3cd7-149">Este es el idioma que se usará para las solicitudes de voz generadas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-149">This is the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="e3cd7-150">Elija si desea habilitar las entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-150">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="e3cd7-151">Cuando se habilita, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-151">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="e3cd7-152">Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".</span><span class="sxs-lookup"><span data-stu-id="e3cd7-152">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Captura de pantalla de la configuración del operador automático para el nombre, el operador, la zona horaria, el idioma y las entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="e3cd7-154">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-154">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e3cd7-155">Paso 3: flujo de llamadas ></span><span class="sxs-lookup"><span data-stu-id="e3cd7-155">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="e3cd7-156">Paso 3 <br> Flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="e3cd7-156">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="e3cd7-157">Elegir las opciones de flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="e3cd7-157">Choose your call flow options</span></span>

1. <span data-ttu-id="e3cd7-158">Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-158">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="e3cd7-159">Si selecciona **Reproducir un archivo de audio,** puede usar el botón **Upload** archivo para cargar un mensaje de saludo grabado guardado como audio en . WAV, .MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-159">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="e3cd7-160">La grabación no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-160">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="e3cd7-161">Si selecciona Escribir un mensaje **de** saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-161">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Captura de pantalla de la configuración del mensaje de saludo](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="e3cd7-163">Elija cómo desea enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-163">Choose how you want to route the call.</span></span>

    <span data-ttu-id="e3cd7-164">Si selecciona **Desconectar,** el operador automático colgará la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-164">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="e3cd7-165">Si selecciona **Redirigir llamada,** puede elegir uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-165">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="e3cd7-166">Si selecciona Opciones **de menú** Reproducir, puede elegir Reproducir un archivo de **audio** o Escribir en un mensaje de saludo y, **a** continuación, elegir entre las opciones de menú y la búsqueda de directorio.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-166">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Captura de pantalla de la configuración de enrutamiento de llamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="e3cd7-168">Si desea que los autores de llamadas usen teclas de marcado para navegar, en Establecer opciones de **menú,** elija lo que quiere que suceda cuando los autores de llamadas presionen una tecla de marcado.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-168">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="e3cd7-169">(Si va a crear este operador automático como directorio de la empresa, deje las opciones de la tecla de marcado en blanco).</span><span class="sxs-lookup"><span data-stu-id="e3cd7-169">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="e3cd7-170">Puede establecer cualquiera de las teclas de marcado en los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="e3cd7-170">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="e3cd7-171">**Persona de la organización:** una persona de su organización que puede recibir llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-171">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="e3cd7-172">**Aplicación de voz:** otro operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-172">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="e3cd7-173">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-173">**External phone number** - any phone number.</span></span> <span data-ttu-id="e3cd7-174">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="e3cd7-174">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="e3cd7-175">**Correo de** voz: el buzón de voz asociado a Microsoft 365 grupo que especifique.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-175">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="e3cd7-176">**Operador:** el operador definido para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-176">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="e3cd7-177">Definir un operador es opcional.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-177">Defining an operator is optional.</span></span> <span data-ttu-id="e3cd7-178">El operador se puede definir como cualquiera de los otros destinos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-178">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="e3cd7-179">Se recomienda establecer 0 clave para el operador.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-179">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="e3cd7-180">Para cada opción de menú, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3cd7-180">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="e3cd7-181">**Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-181">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="e3cd7-182">**Comando de voz:** define el comando de voz que un autor de la llamada puede dar para obtener acceso a esta opción, si las entradas de voz están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-182">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="e3cd7-183">Puede contener varias palabras como "Servicio al cliente" o "Operaciones y motivos".</span><span class="sxs-lookup"><span data-stu-id="e3cd7-183">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="e3cd7-184">**Redirigir a:** a dónde quiere que vaya la llamada cuando los autores de llamadas elijan esta opción.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-184">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="e3cd7-185">Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-185">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Captura de pantalla de las opciones de la tecla de marcado](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="e3cd7-187">Si desea usar este operador automático como directorio de la empresa, en **Búsqueda** de directorios, **seleccione Marcar por nombre.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-187">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="e3cd7-188">Al habilitar esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-188">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="e3cd7-189">Cualquier usuario en línea con una Sistema telefónico es un usuario apto y se puede encontrar con Marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-189">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="e3cd7-190">(Puede elegir Marcar **por extensión,** pero la extensión debe configurarse en Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="e3cd7-190">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="e3cd7-191">Una vez que haya seleccionado una opción **de búsqueda de** directorio, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e3cd7-192">Paso 4: flujo de llamadas después de horas ></span><span class="sxs-lookup"><span data-stu-id="e3cd7-192">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="e3cd7-193">Paso 4 <br> Después de horas</span><span class="sxs-lookup"><span data-stu-id="e3cd7-193">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="e3cd7-194">El horario laboral se puede establecer para cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="e3cd7-195">Si el horario laboral no está establecido, todos los días y todas las horas del día se consideran horario laboral porque una programación 24/7 está establecida de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="e3cd7-196">El horario laboral se puede establecer con descansos en el tiempo durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="e3cd7-197">Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para las horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="e3cd7-198">Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas adicionales para los operadores automáticos con números de teléfono directos.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="e3cd7-199">Si quiere un enrutamiento de llamadas independiente para las personas que llaman fuera del horario laboral, especifique su horario laboral para cada día.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="e3cd7-200">Haga **clic en Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar un descanso para el almuerzo.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Captura de pantalla de la configuración de días y horas adicionales](../media/auto-attendant-business-hours.png)

<span data-ttu-id="e3cd7-202">Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-202">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="e3cd7-203">Las mismas opciones están disponibles que para el enrutamiento de llamadas en horario laboral que especificó en **el paso 3 : flujo de llamadas.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-203">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="e3cd7-204">Haga **clic en** Siguiente cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-204">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e3cd7-205">Paso 5: flujo de llamadas navideñas ></span><span class="sxs-lookup"><span data-stu-id="e3cd7-205">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="e3cd7-206">Paso 5 <br> Días festivos</span><span class="sxs-lookup"><span data-stu-id="e3cd7-206">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="e3cd7-207">Puede hacer que las llamadas a su operador automático se enrute de forma diferente en días festivos que en otros días.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-207">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="e3cd7-208">(Si no desea tener un flujo de llamadas diferente para días festivos, puede omitir este paso).</span><span class="sxs-lookup"><span data-stu-id="e3cd7-208">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="e3cd7-209">El operador automático puede tener un flujo de llamadas para cada día festivo que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-209">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="e3cd7-210">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-210">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="e3cd7-211">En la página Configuración de llamadas navideñas, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-211">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="e3cd7-212">Escriba un nombre para esta configuración navideña.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-212">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="e3cd7-213">En la **lista desplegable** Vacaciones, elija los días festivos que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-213">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="e3cd7-214">Elija el tipo de saludo que desea usar.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-214">Choose the type of greeting that you want to use.</span></span>

    ![Captura de pantalla de la configuración de saludo navideña y navideña](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="e3cd7-216">Elija si desea desconectar **o** **redirigir** la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-216">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="e3cd7-217">Si elige redirigir, elija el destino de enrutamiento de llamadas para la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-217">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Captura de pantalla de la configuración de acción de llamada navideña](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="e3cd7-219">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-219">Click **Save**.</span></span>

    <span data-ttu-id="e3cd7-220">Repita el procedimiento según sea necesario para cada vacaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-220">Repeat the procedure as needed for each additional holiday.</span></span>

    ![Captura de pantalla de la configuración de vacaciones con días festivos en la lista](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="e3cd7-222">Cuando haya agregado todos los días festivos, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-222">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e3cd7-223">Paso 6: elija quién está en el directorio ></span><span class="sxs-lookup"><span data-stu-id="e3cd7-223">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="e3cd7-224">Paso 6 <br> Miembros del directorio</span><span class="sxs-lookup"><span data-stu-id="e3cd7-224">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="e3cd7-225">El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de la llamada usa marcado por nombre o marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-225">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="e3cd7-226">El valor predeterminado de **Todos los usuarios en línea** incluye todos los usuarios de su organización que son usuarios en línea con una Sistema telefónico licencia.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-226">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="e3cd7-227">Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad. </span><span class="sxs-lookup"><span data-stu-id="e3cd7-227">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="e3cd7-228">Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-228">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="e3cd7-229">(Si un usuario está en ambas listas, se excluirá del directorio).</span><span class="sxs-lookup"><span data-stu-id="e3cd7-229">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Captura de pantalla del ámbito de marcado para incluir y excluir opciones](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="e3cd7-231">Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-231">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="e3cd7-232">Cuando haya terminado de configurar el ámbito de marcado, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-232">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e3cd7-233">Paso 7: Asignar una cuenta de recursos ></span><span class="sxs-lookup"><span data-stu-id="e3cd7-233">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="e3cd7-234">Paso 7 <br> Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="e3cd7-234">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="e3cd7-235">Todos los operadores automáticos deben tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-235">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="e3cd7-236">Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos que tenga un número de servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-236">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="e3cd7-237">Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-237">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="e3cd7-238">Para agregar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="e3cd7-238">To add a resource account</span></span>

1. <span data-ttu-id="e3cd7-239">Haga **clic en** Agregar y busque la cuenta que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-239">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="e3cd7-240">Haga **clic en Agregar** y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-240">Click **Add**, and then click **Add**.</span></span>

    ![Captura de pantalla del panel agregar cuentas de la cuenta de recursos](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="e3cd7-242">Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="e3cd7-242">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recursos con el número de servicio asignado](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="e3cd7-244">Esto completa la configuración del operador automático.</span><span class="sxs-lookup"><span data-stu-id="e3cd7-244">This completes the auto attendant configuration.</span></span>

---

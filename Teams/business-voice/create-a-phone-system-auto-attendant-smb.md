---
title: 'Configurar un operador automático para Microsoft Teams: tutorial de pequeña empresa'
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
- Phone System
description: Obtenga información sobre cómo configurar y probar operadores automáticos para Microsoft 365 Business Voice.
ms.openlocfilehash: d320c100937619960011cc378936c6954a00512a
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478380"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="94531-103">Configurar un operador automático : tutorial de pequeña empresa</span><span class="sxs-lookup"><span data-stu-id="94531-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="94531-104">Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el departamento adecuado, la cola de llamadas, una persona o un operador.</span><span class="sxs-lookup"><span data-stu-id="94531-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="94531-105">Puede crear operadores automáticos para su organización con el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="94531-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="94531-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="94531-106">Before you begin</span></span>

<span data-ttu-id="94531-107">Obtenga los números de servicio que necesita para los operadores automáticos a los que desea obtener acceso mediante el marcado directo desde fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="94531-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="94531-108">Esto puede incluir [la transferencia de números de otro proveedor](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la solicitud de nuevos números de [servicio.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="94531-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="94531-109">Obtener un [sistema telefónico: licencia de usuario virtual](../teams-add-on-licensing/virtual-user.md) para cada operador automático que tiene previsto crear.</span><span class="sxs-lookup"><span data-stu-id="94531-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="94531-110">Estas licencias son gratuitas, por lo que le recomendamos obtener algunas adicionales en caso de que decida realizar cambios en su configuración en el futuro.</span><span class="sxs-lookup"><span data-stu-id="94531-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="94531-111">Si desea que la ruta de operador automático [](../set-up-holidays-in-teams.md) llame de forma diferente los días festivos, cree los días festivos que quiera usar antes de crear el operador automático.</span><span class="sxs-lookup"><span data-stu-id="94531-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="94531-112">Siga estos pasos para configurar el operador automático</span><span class="sxs-lookup"><span data-stu-id="94531-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="94531-113">Paso 1 <br> Número de teléfono</span><span class="sxs-lookup"><span data-stu-id="94531-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="94531-114">Cada operador automático que cree requiere una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="94531-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="94531-115">Esto es similar a una cuenta de usuario, excepto que la cuenta está asociada con un operador automático o una cola de llamadas en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="94531-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="94531-116">En este paso, crearemos la cuenta, le asignaremos una licencia de *Microsoft 365 Phone System - Virtual User* y, a continuación, asignaremos un número de servicio.</span><span class="sxs-lookup"><span data-stu-id="94531-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="94531-117">Crear una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="94531-117">Create a resource account</span></span>

<span data-ttu-id="94531-118">Puede crear una cuenta de recursos en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="94531-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="94531-119">En el Centro de administración de Teams, expanda **Configuración de toda la organización** y, a continuación, haga clic en Cuentas de **recursos.**</span><span class="sxs-lookup"><span data-stu-id="94531-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="94531-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="94531-120">Click **Add**.</span></span>

3. <span data-ttu-id="94531-121">En el **panel Agregar cuenta de** recursos, rellene **Nombre** para mostrar, Nombre de **usuario** y elija **Operador automático** para el tipo de **cuenta Recurso**</span><span class="sxs-lookup"><span data-stu-id="94531-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add.png)

4. <span data-ttu-id="94531-123">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94531-123">Click **Save**.</span></span>

<span data-ttu-id="94531-124">La nueva cuenta aparecerá en la lista de cuentas.</span><span class="sxs-lookup"><span data-stu-id="94531-124">The new account will appear in the list of accounts.</span></span>

![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="94531-126">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="94531-126">Assign a license</span></span>

<span data-ttu-id="94531-127">Debe asignar una licencia de Usuario virtual de *Microsoft 365 Phone System* a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="94531-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="94531-128">En el Centro de administración de Microsoft 365, haga clic en la cuenta de recursos a la que desea asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="94531-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="94531-129">En la **pestaña Licencias y aplicaciones,** en **Licencias,** seleccione **Microsoft 365 Phone System - Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="94531-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="94531-130">Haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="94531-130">Click **Save changes**.</span></span>

    ![Captura de pantalla de la interfaz de usuario asignar licencias en el Centro de administración de Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="94531-132">Asignar un número de servicio</span><span class="sxs-lookup"><span data-stu-id="94531-132">Assign a service number</span></span>

<span data-ttu-id="94531-133">Si necesita que este operador automático sea accesible mediante un número de teléfono, asigne ese número a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="94531-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="94531-134">En el Centro de  administración de Teams, en la página Cuentas de recursos, seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en Asignar **o desasignación.**</span><span class="sxs-lookup"><span data-stu-id="94531-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="94531-135">En la **lista desplegable Tipo de número de** teléfono, elija el tipo de número que desea usar.</span><span class="sxs-lookup"><span data-stu-id="94531-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="94531-136">En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="94531-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="94531-138">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94531-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94531-139">Paso 2: Información general del operador automático ></span><span class="sxs-lookup"><span data-stu-id="94531-139">Step 2 - Auto attendant general info ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="94531-140">Paso 2 <br> Información general del operador</span><span class="sxs-lookup"><span data-stu-id="94531-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="94531-141">Para configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="94531-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="94531-142">En el Centro de administración de Teams, expanda **Voz,** haga clic en **Operadores automáticos** y, a continuación, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="94531-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="94531-143">Escriba un nombre para el operador automático en el cuadro de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="94531-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="94531-144">Si desea designar un operador, especifique el destino de las llamadas al operador.</span><span class="sxs-lookup"><span data-stu-id="94531-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="94531-145">Esto es opcional (pero recomendado).</span><span class="sxs-lookup"><span data-stu-id="94531-145">This is optional (but recommended).</span></span> <span data-ttu-id="94531-146">Puede establecer la opción **Operador** para permitir a los autores de llamadas salir de los menús y hablar con una persona designada.</span><span class="sxs-lookup"><span data-stu-id="94531-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="94531-147">Especifique la zona horaria para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="94531-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="94531-148">La zona horaria se usa para calcular el horario laboral si crea un flujo de llamadas independiente para horas posteriores.</span><span class="sxs-lookup"><span data-stu-id="94531-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="94531-149">Especifique un idioma para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="94531-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="94531-150">Este es el idioma que se usará para las solicitudes de voz generadas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="94531-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="94531-151">Elija si desea habilitar las entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="94531-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="94531-152">Cuando se habilita, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="94531-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="94531-153">Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".</span><span class="sxs-lookup"><span data-stu-id="94531-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Captura de pantalla de la configuración del operador automático para el nombre, el operador, la zona horaria, el idioma y las entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="94531-155">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="94531-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94531-156">Paso 3: flujo de llamadas ></span><span class="sxs-lookup"><span data-stu-id="94531-156">Step 3 - Call flow ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="94531-157">Paso 3 <br> Flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="94531-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="94531-158">Elegir las opciones de flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="94531-158">Choose your call flow options</span></span>

1. <span data-ttu-id="94531-159">Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="94531-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="94531-160">Si selecciona Reproducir un archivo de  **audio,** puede usar el botón Cargar archivo para cargar un mensaje de saludo grabado guardado como audio en . WAV, . MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="94531-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="94531-161">La grabación no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="94531-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="94531-162">Si selecciona Escribir un mensaje **de** saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="94531-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Captura de pantalla de la configuración del mensaje de saludo](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="94531-164">Elija cómo desea enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="94531-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="94531-165">Si selecciona **Desconectar,** el operador automático colgará la llamada.</span><span class="sxs-lookup"><span data-stu-id="94531-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="94531-166">Si selecciona **Redirigir llamada,** puede elegir uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94531-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="94531-167">Si selecciona Opciones **de menú** Reproducir, puede elegir Reproducir un archivo de **audio** o Escribir en un mensaje de saludo y, **a** continuación, elegir entre las opciones de menú y la búsqueda de directorio.</span><span class="sxs-lookup"><span data-stu-id="94531-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Captura de pantalla de la configuración de enrutamiento de llamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="94531-169">Si desea que los autores de llamadas usen teclas de marcado para navegar, en Establecer opciones de **menú,** elija lo que quiere que suceda cuando los autores de llamadas presionen una tecla de marcado.</span><span class="sxs-lookup"><span data-stu-id="94531-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="94531-170">(Si va a crear este operador automático como directorio de la empresa, deje las opciones de la tecla de marcado en blanco).</span><span class="sxs-lookup"><span data-stu-id="94531-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="94531-171">Puede establecer cualquiera de las teclas de marcado en los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="94531-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="94531-172">**Persona de la organización:** una persona de su organización que puede recibir llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="94531-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="94531-173">**Aplicación de voz:** otro operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94531-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="94531-174">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="94531-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="94531-175">Use este formato: +[código de país][código de área][número de teléfono]</span><span class="sxs-lookup"><span data-stu-id="94531-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="94531-176">**Correo de** voz: el buzón de voz asociado a un grupo de Microsoft 365 que especifique.</span><span class="sxs-lookup"><span data-stu-id="94531-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="94531-177">**Operador:** el operador definido para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="94531-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="94531-178">Definir un operador es opcional.</span><span class="sxs-lookup"><span data-stu-id="94531-178">Defining an operator is optional.</span></span> <span data-ttu-id="94531-179">El operador se puede definir como cualquiera de los otros destinos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="94531-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="94531-180">Se recomienda establecer 0 clave para el operador.</span><span class="sxs-lookup"><span data-stu-id="94531-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="94531-181">Para cada opción de menú, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94531-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="94531-182">**Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.</span><span class="sxs-lookup"><span data-stu-id="94531-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="94531-183">**Comando de voz:** define el comando de voz que un autor de la llamada puede dar para obtener acceso a esta opción, si las entradas de voz están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="94531-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="94531-184">Puede contener varias palabras como "Servicio al cliente" o "Operaciones y motivos".</span><span class="sxs-lookup"><span data-stu-id="94531-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="94531-185">**Redirigir a:** a dónde quiere que vaya la llamada cuando los autores de llamadas elijan esta opción.</span><span class="sxs-lookup"><span data-stu-id="94531-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="94531-186">Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="94531-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Captura de pantalla de las opciones de la tecla de marcado](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="94531-188">Si desea usar este operador automático como directorio de la empresa, en **Búsqueda** de directorios, **seleccione Marcar por nombre.**</span><span class="sxs-lookup"><span data-stu-id="94531-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="94531-189">Al habilitar esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="94531-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="94531-190">Cualquier usuario en línea con una licencia del sistema telefónico es un usuario apto y se puede encontrar con Marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="94531-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="94531-191">(Puede elegir **Marcar por extensión,** pero la extensión debe configurarse en Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="94531-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="94531-192">Una vez que haya seleccionado una opción **de búsqueda de** directorio, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="94531-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94531-193">Paso 4: flujo de llamadas después de horas ></span><span class="sxs-lookup"><span data-stu-id="94531-193">Step 4 - After hours call flow ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="94531-194">Paso 4 <br> Después de horas</span><span class="sxs-lookup"><span data-stu-id="94531-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="94531-195">El horario laboral se puede establecer para cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="94531-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="94531-196">Si el horario laboral no está establecido, todos los días y todas las horas del día se consideran horario laboral porque una programación 24/7 está establecida de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="94531-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="94531-197">El horario laboral se puede establecer con descansos en el tiempo durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="94531-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="94531-198">Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para las horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="94531-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="94531-199">Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas adicionales para los operadores automáticos con números de teléfono directos.</span><span class="sxs-lookup"><span data-stu-id="94531-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="94531-200">Si quiere un enrutamiento de llamadas independiente para las personas que llaman fuera del horario laboral, especifique su horario laboral para cada día.</span><span class="sxs-lookup"><span data-stu-id="94531-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="94531-201">Haga **clic en Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar un descanso para el almuerzo.</span><span class="sxs-lookup"><span data-stu-id="94531-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Captura de pantalla de la configuración de días y horas adicionales](../media/auto-attendant-business-hours.png)

<span data-ttu-id="94531-203">Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="94531-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="94531-204">Las mismas opciones están disponibles que para el enrutamiento de llamadas en horario laboral que especificó en **el paso 3 : flujo de llamadas.**</span><span class="sxs-lookup"><span data-stu-id="94531-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="94531-205">Haga **clic en** Siguiente cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="94531-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94531-206">Paso 5: flujo de llamadas navideñas ></span><span class="sxs-lookup"><span data-stu-id="94531-206">Step 5 - Holiday call flow ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="94531-207">Paso 5 <br> Días festivos</span><span class="sxs-lookup"><span data-stu-id="94531-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="94531-208">Puede hacer que las llamadas a su operador automático se enrute de forma diferente en días festivos que en otros días.</span><span class="sxs-lookup"><span data-stu-id="94531-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="94531-209">(Si no desea tener un flujo de llamadas diferente para días festivos, puede omitir este paso).</span><span class="sxs-lookup"><span data-stu-id="94531-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="94531-210">El operador automático puede tener un flujo de llamadas para cada día festivo que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="94531-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="94531-211">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="94531-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="94531-212">En la página Configuración de llamadas navideñas, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="94531-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="94531-213">Escriba un nombre para esta configuración navideña.</span><span class="sxs-lookup"><span data-stu-id="94531-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="94531-214">En la **lista desplegable** Vacaciones, elija los días festivos que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="94531-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="94531-215">Elija el tipo de saludo que desea usar.</span><span class="sxs-lookup"><span data-stu-id="94531-215">Choose the type of greeting that you want to use.</span></span>

    ![Captura de pantalla de la configuración de saludo navideña y navideña](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="94531-217">Elija si desea desconectar **o** **redirigir** la llamada.</span><span class="sxs-lookup"><span data-stu-id="94531-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="94531-218">Si elige redirigir, elija el destino de enrutamiento de llamadas para la llamada.</span><span class="sxs-lookup"><span data-stu-id="94531-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Captura de pantalla de la configuración de acción de llamada navideña](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="94531-220">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94531-220">Click **Save**.</span></span>

<span data-ttu-id="94531-221">Repita el procedimiento según sea necesario para cada vacaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="94531-221">Repeat the procedure as needed for each additional holiday.</span></span>

![Captura de pantalla de la configuración de vacaciones con días festivos en la lista](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="94531-223">Cuando haya agregado todos los días festivos, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="94531-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94531-224">Paso 6: elija quién está en el directorio ></span><span class="sxs-lookup"><span data-stu-id="94531-224">Step 6 - Choose who's in the directory ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="94531-225">Paso 6 <br> Miembros del directorio</span><span class="sxs-lookup"><span data-stu-id="94531-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="94531-226">El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de la llamada usa marcado por nombre o marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="94531-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="94531-227">El valor predeterminado de **Todos los usuarios en línea** incluye todos los usuarios de su organización que son usuarios en línea con una licencia del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="94531-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="94531-228">Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad. </span><span class="sxs-lookup"><span data-stu-id="94531-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="94531-229">Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado.</span><span class="sxs-lookup"><span data-stu-id="94531-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="94531-230">(Si un usuario está en ambas listas, se excluirá del directorio).</span><span class="sxs-lookup"><span data-stu-id="94531-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Captura de pantalla del ámbito de marcado para incluir y excluir opciones](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="94531-232">Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio.</span><span class="sxs-lookup"><span data-stu-id="94531-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="94531-233">Cuando haya terminado de configurar el ámbito de marcado, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="94531-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94531-234">Paso 7: Asignar una cuenta de recursos ></span><span class="sxs-lookup"><span data-stu-id="94531-234">Step 7 - Assign a resource account ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="94531-235">Paso 7 <br> Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="94531-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="94531-236">Todos los operadores automáticos deben tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="94531-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="94531-237">Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos que tenga un número de servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="94531-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="94531-238">Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="94531-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="94531-239">Para agregar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="94531-239">To add a resource account</span></span>

1. <span data-ttu-id="94531-240">Haga **clic en Agregar** cuenta y busque la cuenta que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="94531-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="94531-241">Haga **clic en Agregar** y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="94531-241">Click **Add**, and then click **Add**.</span></span>

    ![Captura de pantalla del panel agregar cuentas de la cuenta de recursos](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="94531-243">Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="94531-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recursos con el número de servicio asignado](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="94531-245">Esto completa la configuración del operador automático.</span><span class="sxs-lookup"><span data-stu-id="94531-245">This completes the auto attendant configuration.</span></span>

---



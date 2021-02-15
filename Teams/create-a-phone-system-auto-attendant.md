---
title: Configurar un operador automático para Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
description: Aprenda a configurar y probar operadores automáticos en Microsoft Teams.
ms.openlocfilehash: bffe66fc59dfeb2f7028f2d5520b45930d753d07
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196634"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="80f46-103">Configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="80f46-103">Set up an auto attendant</span></span>

<span data-ttu-id="80f46-104">Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el departamento, la cola de llamadas, la persona o un operador adecuados.</span><span class="sxs-lookup"><span data-stu-id="80f46-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="80f46-105">Puede crear operadores automáticos para su organización con el Centro de administración de Microsoft Teams o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80f46-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="80f46-106">Asegúrese de haber leído plan para operadores [automáticos](plan-auto-attendant-call-queue.md) y [](plan-auto-attendant-call-queue.md#getting-started) colas de llamadas de Teams y de haber seguido los pasos de introducción antes de seguir los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="80f46-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="80f46-107">Los operadores automáticos pueden dirigir las llamadas, en función de la entrada de los autores de llamadas, a uno de los siguientes destinos: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="80f46-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="80f46-108">**Persona de la organización:** una persona de la organización que puede recibir llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="80f46-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="80f46-109">Puede ser un usuario en línea o un usuario alojado en local con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="80f46-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="80f46-110">**Aplicación de voz:** otro operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="80f46-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="80f46-111">(Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="80f46-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="80f46-112">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="80f46-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="80f46-113">(Consulte [los detalles técnicos de la transferencia externa).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="80f46-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="80f46-114">**Correo** de voz: el buzón de voz asociado a un grupo de Microsoft 365 que especifique.</span><span class="sxs-lookup"><span data-stu-id="80f46-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="80f46-115">**Operador** ( operador definido para el operador automático).</span><span class="sxs-lookup"><span data-stu-id="80f46-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="80f46-116">La definición de un operador es opcional.</span><span class="sxs-lookup"><span data-stu-id="80f46-116">Defining an operator is optional.</span></span> <span data-ttu-id="80f46-117">El operador se puede definir como cualquiera de los otros destinos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="80f46-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="80f46-118">Se le pedirá que elija una de estas opciones en varias fases a medida que configura un operador automático.</span><span class="sxs-lookup"><span data-stu-id="80f46-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="80f46-119">Para configurar un operador automático, en el centro de administración de Teams, expanda **Voz,** haga clic en **Operadores automáticos** y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="80f46-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="80f46-120">Información general</span><span class="sxs-lookup"><span data-stu-id="80f46-120">General info</span></span>

![Captura de pantalla de la configuración del operador automático para entradas de nombre, operador, zona horaria, idioma y voz](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="80f46-122">Escriba un nombre para el operador automático en el cuadro de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="80f46-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="80f46-123">Si desea designar un operador, especifique el destino de las llamadas al operador.</span><span class="sxs-lookup"><span data-stu-id="80f46-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="80f46-124">Esto es opcional (pero recomendado).</span><span class="sxs-lookup"><span data-stu-id="80f46-124">This is optional (but recommended).</span></span> <span data-ttu-id="80f46-125">Puede establecer la opción **Operador para** permitir que los autores de llamadas salgan de los menús y hablen con una persona designada.</span><span class="sxs-lookup"><span data-stu-id="80f46-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="80f46-126">Especifique la zona horaria de este operador automático.</span><span class="sxs-lookup"><span data-stu-id="80f46-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="80f46-127">La zona horaria se usa para calcular el horario laboral si crea un flujo de llamadas separado para horas [fuera del horario laboral.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="80f46-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="80f46-128">Especifique un [idioma admitido](create-a-phone-system-auto-attendant-languages.md) para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="80f46-128">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="80f46-129">Este es el idioma que se usará para los mensajes de voz generados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="80f46-129">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="80f46-130">Elija si desea habilitar las entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="80f46-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="80f46-131">Cuando está habilitada, el nombre de todas las opciones de menú se convierte en una palabra clave de reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="80f46-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="80f46-132">Por ejemplo, las personas que llaman pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".</span><span class="sxs-lookup"><span data-stu-id="80f46-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="80f46-133">Si elige un idioma en el paso 4 que no admite entradas de voz, esta opción se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="80f46-133">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="80f46-134">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="80f46-134">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="80f46-135">Flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="80f46-135">Call flow</span></span>

![Captura de pantalla de la configuración del mensaje de saludo](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="80f46-137">Elija si desea reproducir un saludo cuando el operador automático responda una llamada.</span><span class="sxs-lookup"><span data-stu-id="80f46-137">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="80f46-138">Si selecciona Reproducir un archivo de  **audio,** puede usar el botón Cargar archivo para cargar un mensaje de saludo grabado guardado como audio. WAV, . MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="80f46-138">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="80f46-139">La grabación no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="80f46-139">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="80f46-140">Si selecciona **Escribir** un mensaje de saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda una llamada.</span><span class="sxs-lookup"><span data-stu-id="80f46-140">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Captura de pantalla de la configuración de enrutamiento de llamadas](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="80f46-142">Elige cómo quieres enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="80f46-142">Choose how you want to route the call.</span></span>

<span data-ttu-id="80f46-143">Si selecciona **Desconectar,** el operador automático colgará la llamada.</span><span class="sxs-lookup"><span data-stu-id="80f46-143">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="80f46-144">Si selecciona Redirigir **llamada, puede** elegir uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="80f46-144">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="80f46-145">Si selecciona las **opciones del** menú Reproducir, puede elegir reproducir un archivo de **audio** o escribir un mensaje de saludo y, **después,** elegir entre las opciones de menú y la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="80f46-145">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="80f46-146">Opciones de menú</span><span class="sxs-lookup"><span data-stu-id="80f46-146">Menu options</span></span>

![Captura de pantalla de las opciones de tecla de marcado](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="80f46-148">Para las opciones de marcación, puede asignar las teclas de 0 a 9 del teclado telefónico a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="80f46-148">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="80f46-149">(Las teclas \* (Repetir) \# y (Volver) están reservados por el sistema y no se pueden reasignar).</span><span class="sxs-lookup"><span data-stu-id="80f46-149">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="80f46-150">Las asignaciones de teclas no tienen por qué ser continuas.</span><span class="sxs-lookup"><span data-stu-id="80f46-150">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="80f46-151">Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a opciones, mientras que la tecla 2 no se usa.</span><span class="sxs-lookup"><span data-stu-id="80f46-151">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="80f46-152">Se recomienda asignar la clave 0 al operador si ha configurado una.</span><span class="sxs-lookup"><span data-stu-id="80f46-152">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="80f46-153">Si el operador no está establecido en ninguna tecla, el comando de voz "Operador" también está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="80f46-153">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="80f46-154">Para cada opción de menú, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80f46-154">For each menu option, specify the following:</span></span>

- <span data-ttu-id="80f46-155">**Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.</span><span class="sxs-lookup"><span data-stu-id="80f46-155">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="80f46-156">Si hay entradas de voz disponibles, las personas que llaman también pueden decir este número para acceder a la opción.</span><span class="sxs-lookup"><span data-stu-id="80f46-156">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="80f46-157">**Comando de** voz: define el comando de voz que puede dar un autor de llamada para obtener acceso a esta opción, si las entradas de voz están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="80f46-157">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="80f46-158">Puede contener varias palabras como "Atención al cliente" u "Operaciones y campos".</span><span class="sxs-lookup"><span data-stu-id="80f46-158">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="80f46-159">Por ejemplo, el autor de la llamada puede presionar 2, decir "dos" o decir "Ventas" para seleccionar la opción asignada a la tecla 2.</span><span class="sxs-lookup"><span data-stu-id="80f46-159">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="80f46-160">Este texto también se representa de texto a voz para la confirmación del servicio, que puede ser algo parecido a "Transferir la llamada a ventas".</span><span class="sxs-lookup"><span data-stu-id="80f46-160">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="80f46-161">**Redirigir a:** el destino de enrutamiento de llamada que se usa cuando los autores de llamadas eligen esta opción.</span><span class="sxs-lookup"><span data-stu-id="80f46-161">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="80f46-162">Si redirige a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada con él.</span><span class="sxs-lookup"><span data-stu-id="80f46-162">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="80f46-163">Búsqueda en directorios</span><span class="sxs-lookup"><span data-stu-id="80f46-163">Directory search</span></span>

<span data-ttu-id="80f46-164">Si asigna teclas de marcado a destinos, le recomendamos que elija Ninguno **para** búsqueda **en el directorio.**</span><span class="sxs-lookup"><span data-stu-id="80f46-164">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="80f46-165">Si el autor de la llamada intenta marcar un nombre o una extensión con claves asignadas a destinos específicos, es posible que se enruten inesperadamente a un destino antes de terminar de escribir el nombre o la extensión.</span><span class="sxs-lookup"><span data-stu-id="80f46-165">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="80f46-166">Le recomendamos que cree un operador automático independiente para realizar búsquedas en el directorio y que tenga un vínculo al operador automático principal mediante una tecla de marcado.</span><span class="sxs-lookup"><span data-stu-id="80f46-166">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="80f46-167">Si no ha asignado las teclas de marcado, elija una opción para la **búsqueda en el directorio.**</span><span class="sxs-lookup"><span data-stu-id="80f46-167">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="80f46-168">**Marcado por nombre:** si habilita esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="80f46-168">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="80f46-169">Cualquier usuario en línea o cualquier usuario local que utilice Skype Empresarial Server es un usuario apto y se puede encontrar con Marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="80f46-169">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="80f46-170">(Puede establecer quién está incluido en el directorio y quién no en la [página Ámbito de](#dial-scope) marcado).</span><span class="sxs-lookup"><span data-stu-id="80f46-170">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="80f46-171">**Marcado por extensión:** si habilita esta opción, los autores de llamadas pueden conectarse con los usuarios de su organización marcando su extensión de teléfono.</span><span class="sxs-lookup"><span data-stu-id="80f46-171">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="80f46-172">Cualquier usuario en línea o cualquier usuario alojado en local que use Skype Empresarial Server es un usuario apto y se puede encontrar **con Marcado por extensión.**</span><span class="sxs-lookup"><span data-stu-id="80f46-172">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="80f46-173">(Puede establecer quién está incluido en el directorio y quién no en la página [Ámbito de](#dial-scope) marcado).</span><span class="sxs-lookup"><span data-stu-id="80f46-173">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="80f46-174">Los usuarios que quiera que estén disponibles para marcado por extensión deben tener una extensión especificada como parte de [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) uno de los siguientes atributos de teléfono definidos en Active Directory o Azure Active Directory (vea Agregar usuarios individualmente o en bloque para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="80f46-174">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="80f46-175">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="80f46-175">OfficePhone</span></span>
- <span data-ttu-id="80f46-176">HomePhone</span><span class="sxs-lookup"><span data-stu-id="80f46-176">HomePhone</span></span>
- <span data-ttu-id="80f46-177">Móvil/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="80f46-177">Mobile/MobilePhone</span></span>
- <span data-ttu-id="80f46-178">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="80f46-178">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="80f46-179">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="80f46-179">OtherTelephone</span></span>

<span data-ttu-id="80f46-180">El formato necesario para introducir la extensión en el campo de número de teléfono de usuario es:</span><span class="sxs-lookup"><span data-stu-id="80f46-180">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="80f46-181">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="80f46-181">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="80f46-182">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="80f46-182">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="80f46-183">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="80f46-183">*x\<extension>*</span></span>

- <span data-ttu-id="80f46-184">Ejemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="80f46-184">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="80f46-185">Ejemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="80f46-185">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="80f46-186">Ejemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="80f46-186">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="80f46-187">Puede establecer la extensión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com/) o en el [Centro de administración de Azure Active Directory.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="80f46-187">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="80f46-188">Los cambios pueden tardar hasta 12 horas en estar disponibles para los operadores automáticos y las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="80f46-188">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="80f46-189">Si desea usar las  características Marcado  por nombre y Marcado por extensión, puede asignar una tecla de marcado al operador automático principal para que llegue a un operador automático habilitado para Marcado por **nombre.**</span><span class="sxs-lookup"><span data-stu-id="80f46-189">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="80f46-190">Dentro de ese operador automático, puede asignar la tecla 1 (que no tiene letras asociadas) para alcanzar el operador automático **de** Marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="80f46-190">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="80f46-191">Una vez que haya seleccionado una opción **de búsqueda de** directorio, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="80f46-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="80f46-192">Flujo de llamadas para horas no laborales</span><span class="sxs-lookup"><span data-stu-id="80f46-192">Call flow for after hours</span></span>

![Captura de pantalla de la configuración de días y horas fuera del horario laboral](media/auto-attendant-business-hours.png)

<span data-ttu-id="80f46-194">El horario laboral se puede establecer para cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="80f46-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="80f46-195">Si no se establecen los horarios laborales, todos los días y todas las horas del día se considerarán laborables, ya que se establece una programación las 24 horas.</span><span class="sxs-lookup"><span data-stu-id="80f46-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="80f46-196">El horario laboral se puede establecer con saltos en el tiempo durante el día y todas las horas que no se establecen como horas de trabajo se tienen en cuenta fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="80f46-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="80f46-197">Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para después del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="80f46-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="80f46-198">En función de cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas no laborales para los operadores automáticos con números de teléfono directos.</span><span class="sxs-lookup"><span data-stu-id="80f46-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="80f46-199">Si desea usar otro enrutamiento de llamadas para los autores de llamadas fuera del horario laboral, especifique su horario laboral para cada día.</span><span class="sxs-lookup"><span data-stu-id="80f46-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="80f46-200">Haga **clic en Agregar nueva** hora para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar una hora de almuerzo.</span><span class="sxs-lookup"><span data-stu-id="80f46-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="80f46-201">Una vez que haya especificado su horario laboral, elija las opciones de enrutamiento de llamada para horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="80f46-201">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="80f46-202">Están disponibles las mismas opciones que para el enrutamiento de llamadas en horario laboral que ha especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="80f46-202">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="80f46-203">Haga **clic en** Siguiente cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="80f46-203">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="80f46-204">Flujos de llamadas durante los días festivos</span><span class="sxs-lookup"><span data-stu-id="80f46-204">Call flows during holidays</span></span>

![Captura de pantalla de la configuración de saludos navideñas y navideñas](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="80f46-206">El operador automático puede tener un flujo de llamadas para cada día festivo [que haya configurado.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="80f46-206">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="80f46-207">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="80f46-207">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="80f46-208">En la página configuración de la llamada navideña, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="80f46-208">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="80f46-209">Escriba un nombre para esta configuración navideña.</span><span class="sxs-lookup"><span data-stu-id="80f46-209">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="80f46-210">En la **lista** desplegable Vacaciones, elija las vacaciones que desea usar.</span><span class="sxs-lookup"><span data-stu-id="80f46-210">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="80f46-211">Elija el tipo de saludo que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="80f46-211">Choose the type of greeting that you want to use.</span></span>

    ![Captura de pantalla de la configuración de la acción de llamada navideña](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="80f46-213">Elija si desea desconectar **o** **redirigir** la llamada.</span><span class="sxs-lookup"><span data-stu-id="80f46-213">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="80f46-214">Si decide redirigir, elija el destino de enrutamiento de llamada para la llamada.</span><span class="sxs-lookup"><span data-stu-id="80f46-214">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="80f46-215">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="80f46-215">Click **Save**.</span></span>

![Captura de pantalla de la configuración de días festivos con la lista de días festivos](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="80f46-217">Repita el procedimiento según sea necesario para cada día festivo adicional.</span><span class="sxs-lookup"><span data-stu-id="80f46-217">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="80f46-218">Cuando haya agregado todos los días festivos, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="80f46-218">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="80f46-219">Ámbito de marcado</span><span class="sxs-lookup"><span data-stu-id="80f46-219">Dial scope</span></span>

![Captura de pantalla del ámbito de marcado con opciones de incluir y excluir](media/auto-attendant-dial-scope.png)

<span data-ttu-id="80f46-221">El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de llamada usa marcado por nombre o marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="80f46-221">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="80f46-222">El valor predeterminado de **Todos los** usuarios en línea incluye todos los usuarios de su organización que son usuarios en línea u hospedados en local con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="80f46-222">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="80f46-223">Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad. </span><span class="sxs-lookup"><span data-stu-id="80f46-223">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="80f46-224">Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcación.</span><span class="sxs-lookup"><span data-stu-id="80f46-224">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="80f46-225">(Si un usuario está en ambas listas, se excluirá del directorio).</span><span class="sxs-lookup"><span data-stu-id="80f46-225">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="80f46-226">Los nombres de los nuevos usuarios pueden tardar hasta 36 horas en aparecer en el directorio.</span><span class="sxs-lookup"><span data-stu-id="80f46-226">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="80f46-227">Cuando haya terminado de configurar el ámbito de marcado, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="80f46-227">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="80f46-228">Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="80f46-228">Resource accounts</span></span>

<span data-ttu-id="80f46-229">Todos los operadores automáticos deben tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="80f46-229">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="80f46-230">Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recurso que tenga un número de servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="80f46-230">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="80f46-231">Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="80f46-231">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Captura de pantalla del panel Agregar cuentas de la cuenta de recursos](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="80f46-233">Para agregar una cuenta de recurso, haga clic **en Agregar cuenta** y busque la cuenta que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="80f46-233">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="80f46-234">Haga **clic en Agregar** y, a continuación, en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="80f46-234">Click **Add**, and then click **Add**.</span></span>

![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recurso con el número de servicio asignado](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="80f46-236">Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="80f46-236">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="80f46-237">Esto completa la configuración del operador automático.</span><span class="sxs-lookup"><span data-stu-id="80f46-237">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="80f46-238">Transferencias de números de teléfono externos : detalles técnicos</span><span class="sxs-lookup"><span data-stu-id="80f46-238">External phone number transfers - technical details</span></span>

<span data-ttu-id="80f46-239">Consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que los operadores automáticos transfieran llamadas externamente.</span><span class="sxs-lookup"><span data-stu-id="80f46-239">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="80f46-240">Además:</span><span class="sxs-lookup"><span data-stu-id="80f46-240">In addition:</span></span>

- <span data-ttu-id="80f46-241">Para una cuenta de recurso con un número [de plan](calling-plans-for-office-365.md) de llamadas, el número de teléfono de transferencia externa debe introducirse en formato E.164 (+[código de país][código de área][número de teléfono]).</span><span class="sxs-lookup"><span data-stu-id="80f46-241">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="80f46-242">Para una cuenta de recurso con un número de enrutamiento directo, el formato de número de teléfono de transferencia externa depende de la configuración del controlador de borde de sesión [(SBC).](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="80f46-242">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="80f46-243">El número de teléfono saliente que se muestra se determina de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="80f46-243">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="80f46-244">Para los números del plan de llamadas, se muestra el número de teléfono del autor de la llamada original.</span><span class="sxs-lookup"><span data-stu-id="80f46-244">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="80f46-245">Para los números de enrutamiento directo, el número enviado se basa en la configuración de P-To-Identity (PAI) en el SBC, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="80f46-245">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="80f46-246">Si se establece en Deshabilitada, se muestra el número de teléfono del autor de la llamada original.</span><span class="sxs-lookup"><span data-stu-id="80f46-246">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="80f46-247">Esta es la configuración predeterminada y recomendada.</span><span class="sxs-lookup"><span data-stu-id="80f46-247">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="80f46-248">Si se establece en Habilitado, se muestra el número de teléfono de la cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="80f46-248">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="80f46-249">En un entorno híbrido de Skype Empresarial, para transferir una llamada de operador automático a la RTC, cree un nuevo usuario local con el reenvío de llamadas establecido en el número de RTC.</span><span class="sxs-lookup"><span data-stu-id="80f46-249">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="80f46-250">El usuario debe estar habilitado para Telefonía IP empresarial y tener asignada una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="80f46-250">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="80f46-251">Para obtener más información, consulte [Transferencia de llamadas del operador automático a RTC.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="80f46-251">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="80f46-252">Crear un operador automático con PowerShell</span><span class="sxs-lookup"><span data-stu-id="80f46-252">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="80f46-253">También puede usar PowerShell para crear y configurar operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="80f46-253">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="80f46-254">Estos son los cmdlets que necesita para administrar un operador automático:</span><span class="sxs-lookup"><span data-stu-id="80f46-254">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="80f46-255">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="80f46-255">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="80f46-256">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="80f46-256">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="80f46-257">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="80f46-257">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="80f46-258">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="80f46-258">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="80f46-259">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="80f46-259">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="80f46-260">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="80f46-260">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="80f46-261">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="80f46-261">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="80f46-262">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="80f46-262">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="80f46-263">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="80f46-263">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="80f46-264">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="80f46-264">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="80f46-265">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="80f46-265">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="80f46-266">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="80f46-266">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="80f46-267">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="80f46-267">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="80f46-268">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="80f46-268">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="80f46-269">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="80f46-269">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="80f46-270">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="80f46-270">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="80f46-271">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="80f46-271">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="80f46-272">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="80f46-272">Related topics</span></span>

[<span data-ttu-id="80f46-273">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="80f46-273">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="80f46-274">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="80f46-274">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="80f46-275">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="80f46-275">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="80f46-276">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="80f46-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

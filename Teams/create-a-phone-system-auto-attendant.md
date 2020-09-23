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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Aprenda a configurar y probar los operadores automáticos para Microsoft Teams.
ms.openlocfilehash: 2cb796db37f40025dc7a78123da729fd5812bbbb
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48220090"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="6ef6c-103">Configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="6ef6c-103">Set up an auto attendant</span></span>

<span data-ttu-id="6ef6c-104">Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el Departamento adecuado, la cola de llamadas, la persona o un operador.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="6ef6c-105">Puede crear operadores automáticos para su organización con el centro de administración de Microsoft Teams o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="6ef6c-106">Asegúrese de que tiene el [plan de lectura de los operadores automáticos de Teams y las colas de llamadas](plan-auto-attendant-call-queue.md) y siga los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started) antes de seguir los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="6ef6c-107">Los operadores automáticos pueden dirigir llamadas en función de la entrada de los autores de llamadas a uno de los siguientes destinos:</span><span class="sxs-lookup"><span data-stu-id="6ef6c-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations:</span></span>

- <span data-ttu-id="6ef6c-108">**Persona de la organización** : una persona de su organización que puede recibir llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="6ef6c-109">Puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="6ef6c-110">**Aplicación de voz** : otro operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="6ef6c-111">(Elija la cuenta de recursos asociada al operador automático o a la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="6ef6c-112">**Número de teléfono externo** , cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="6ef6c-113">(Consulta los [detalles técnicos de la transferencia externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="6ef6c-114">Buzón de **voz: el buzón de voz** asociado a un grupo de Microsoft 365 que especifique.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="6ef6c-115">**Operador** : el operador definido para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="6ef6c-116">Definir un operador es opcional.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-116">Defining an operator is optional.</span></span> <span data-ttu-id="6ef6c-117">El operador se puede definir como cualquiera de los otros destinos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="6ef6c-118">Cuando configure un operador automático, se le pedirá que elija una de estas opciones.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="6ef6c-119">Para configurar un operador automático, en el centro de administración de Teams, expanda **voz**, haga clic en **operadores automáticos**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="6ef6c-120">Información general</span><span class="sxs-lookup"><span data-stu-id="6ef6c-120">General info</span></span>

![](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="6ef6c-121">Escriba un nombre para el operador automático en el cuadro de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-121">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="6ef6c-122">Si desea designar un operador, especifique el destino de las llamadas al operador.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-122">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="6ef6c-123">Esto es opcional (pero se recomienda).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-123">This is optional (but recommended).</span></span> <span data-ttu-id="6ef6c-124">Puede configurar la opción de **operador** para permitir que los autores de llamadas interrumpan los menús y hablen con una persona designada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-124">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="6ef6c-125">Especifique la zona horaria de este operador automático.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-125">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="6ef6c-126">La zona horaria se usa para calcular el horario laboral si se [crea un flujo de llamada independiente para después del horario laboral](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-126">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="6ef6c-127">Especifique un idioma para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-127">Specify a language for this auto attendant.</span></span> <span data-ttu-id="6ef6c-128">Este es el idioma que se usará para los avisos de voz generados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-128">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="6ef6c-129">Elija si desea habilitar las entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-129">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="6ef6c-130">Cuando está habilitado, el nombre de todas las opciones de menú se convierte en una palabra clave de reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-130">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="6ef6c-131">Por ejemplo, las personas que llamen pueden decir "una" para seleccionar la opción de menú asignada a la clave 1, o pueden decir "ventas" para seleccionar la opción de menú denominada "ventas".</span><span class="sxs-lookup"><span data-stu-id="6ef6c-131">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="6ef6c-132">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-132">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="6ef6c-133">Flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="6ef6c-133">Call flow</span></span>

![](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="6ef6c-134">Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-134">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="6ef6c-135">Si selecciona **reproducir un archivo de audio** , puede usar el botón **Cargar archivo** para cargar un mensaje de saludo grabado guardado como audio en. WAV,. MP3 o. Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-135">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="6ef6c-136">La grabación no puede tener más de 5 MB.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-136">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="6ef6c-137">Si selecciona **escribir un mensaje de saludo** , el sistema leerá el texto con el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-137">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="6ef6c-138">Elige cómo quieres enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-138">Choose how you want to route the call.</span></span>

<span data-ttu-id="6ef6c-139">Si seleccionas **desconectar**, el operador automático colgará la llamada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-139">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="6ef6c-140">Si selecciona **redirigir llamada**, puede elegir uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-140">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="6ef6c-141">Si selecciona **reproducir opciones de menú**, puede elegir **reproducir un archivo de audio** o **escribir un mensaje de bienvenida** y, a continuación, elegir entre las opciones de menú y la búsqueda de directorio.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-141">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="6ef6c-142">Opciones de menú</span><span class="sxs-lookup"><span data-stu-id="6ef6c-142">Menu options</span></span>

![](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="6ef6c-143">Para las opciones de marcado, puede asignar las teclas de 0-9 en el teclado del teléfono a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-143">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="6ef6c-144">(Las teclas \* (Repetir) y \# (atrás) están reservados para el sistema y no se pueden reasignar.)</span><span class="sxs-lookup"><span data-stu-id="6ef6c-144">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="6ef6c-145">Las asignaciones de teclas no tienen que ser continuas.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-145">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="6ef6c-146">Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a las opciones, mientras que la tecla 2 no se usa.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-146">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="6ef6c-147">Se recomienda asignar la clave 0 al operador si se ha configurado una.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-147">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="6ef6c-148">Si el operador no se establece en ninguna tecla, el comando de voz "operador" también está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-148">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="6ef6c-149">Para cada opción de menú, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ef6c-149">For each menu option, specify the following:</span></span>

- <span data-ttu-id="6ef6c-150">**Tecla de marcado** : la tecla del teclado del teléfono para acceder a esta opción.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-150">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="6ef6c-151">Si hay entradas de voz disponibles, las personas que llaman también pueden decir este número para tener acceso a la opción.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-151">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="6ef6c-152">**Comando voz** : define el comando de voz que la persona que llama puede conceder para obtener acceso a esta opción, si las entradas de voz están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-152">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="6ef6c-153">Puede contener varias palabras como "servicio al cliente" o "operaciones y motivos".</span><span class="sxs-lookup"><span data-stu-id="6ef6c-153">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="6ef6c-154">Por ejemplo, la persona que llama puede presionar 2, decir "dos" o decir "ventas" para seleccionar la opción asignada a la tecla 2.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-154">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="6ef6c-155">Este texto se representa también por texto a voz para la pregunta de confirmación del servicio, que puede ser como "transfiriendo la llamada a ventas".</span><span class="sxs-lookup"><span data-stu-id="6ef6c-155">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="6ef6c-156">Redirigir al destino de enrutamiento de llamada **que se** usa cuando la persona que llama elige esta opción.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-156">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="6ef6c-157">Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada a él.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-157">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="6ef6c-158">Búsqueda en el directorio</span><span class="sxs-lookup"><span data-stu-id="6ef6c-158">Directory search</span></span>

<span data-ttu-id="6ef6c-159">Si asigna teclas de marcado a destinos, le recomendamos que elija **ninguno** para la búsqueda en el **directorio**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-159">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="6ef6c-160">Si una persona que llama intenta marcar un nombre o una extensión con las teclas que se asignan a destinos específicos, es posible que se dirijan de forma inesperada a un destino antes de que terminen de introducir el nombre o la extensión.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-160">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="6ef6c-161">Le recomendamos que cree un operador automático independiente para la búsqueda en el directorio y que le vincule su operador automático principal a través de una tecla de marcado.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-161">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="6ef6c-162">Si no ha asignado las teclas de marcado, elija una opción para la búsqueda en el **directorio**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-162">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="6ef6c-163">**Marcado por nombre** : Si habilita esta opción, las personas que llamen pueden decir el nombre del usuario o escribirla en el teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-163">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="6ef6c-164">Cualquier usuario en línea con una licencia de sistema telefónico o cualquier usuario local que use Skype empresarial Server es un usuario elegible y puede encontrarse con el marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-164">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="6ef6c-165">(Puede establecer quién está y no incluido en el directorio de la página de [ámbito de marcado](#dial-scope) ).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-165">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="6ef6c-166">**Marcado por extensión** : Si habilita esta opción, las personas que llamen podrán conectarse con los usuarios de su organización marcando su extensión de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-166">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="6ef6c-167">Cualquier usuario en línea con una licencia de sistema telefónico o cualquier usuario local que use Skype empresarial Server es un usuario elegible y puede encontrarse con la **función de marcado por extensión**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-167">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="6ef6c-168">(Puede establecer quién está y no incluido en el directorio de la página de [ámbito de marcado](#dial-scope) ).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-168">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="6ef6c-169">Los usuarios que desea que estén disponibles para marcar por extensión necesitan tener una extensión especificada como parte de uno de los siguientes atributos de teléfono definidos en Active Directory o Azure Active Directory (para obtener más información, consulte [Agregar usuarios individualmente o de forma masiva](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) .)</span><span class="sxs-lookup"><span data-stu-id="6ef6c-169">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="6ef6c-170">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="6ef6c-170">OfficePhone</span></span>
- <span data-ttu-id="6ef6c-171">Teléfono particular</span><span class="sxs-lookup"><span data-stu-id="6ef6c-171">HomePhone</span></span>
- <span data-ttu-id="6ef6c-172">Móvil/teléfono móvil</span><span class="sxs-lookup"><span data-stu-id="6ef6c-172">Mobile/MobilePhone</span></span>
- <span data-ttu-id="6ef6c-173">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="6ef6c-173">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="6ef6c-174">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="6ef6c-174">OtherTelephone</span></span>

<span data-ttu-id="6ef6c-175">El formato requerido para introducir la extensión en el campo número de teléfono del usuario es \* + <phone number> ext <extension> =\* o \* + <phone number> x <extension> \*.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-175">The required format to enter the extension in the user phone number field is either *+<phone number>ext=<extension>* or *+<phone number>x<extension>*.</span></span>

<span data-ttu-id="6ef6c-176">Puede establecer la extensión en el [centro de administración de Microsoft 365](https://admin.microsoft.com/) o en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-176">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="6ef6c-177">Pueden pasar hasta 12 horas antes de que los cambios estén disponibles para los operadores automáticos y las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-177">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="6ef6c-178">Si desea usar el **marcado por nombre** y las características de **marcado por extensión** , puede asignar una tecla de marcado en su operador automático principal para comunicarse con un operador automático habilitado para **el marcado por nombre**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-178">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="6ef6c-179">Dentro de ese operador automático, puedes asignar la tecla 1 (que no tiene ninguna letra asociada) para alcanzar el **marcado por** el operador automático de extensión.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-179">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="6ef6c-180">Una vez que haya seleccionado una opción de **búsqueda de directorio** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-180">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="6ef6c-181">Flujo de llamadas para después del horario</span><span class="sxs-lookup"><span data-stu-id="6ef6c-181">Call flow for after hours</span></span>

![](media/auto-attendant-business-hours.png)

<span data-ttu-id="6ef6c-182">Puede establecer el horario comercial para cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-182">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="6ef6c-183">Si no se han establecido las horas de trabajo, todos los días y todas las horas del día se consideran horario comercial porque una programación de 24/7 está establecida de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-183">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="6ef6c-184">El horario comercial se puede establecer con interrupciones en el tiempo durante el día, y todas las horas que no se configuran como horas laborales se consideran horas laborales.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-184">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="6ef6c-185">Puede establecer distintas opciones de tratamiento de llamadas entrantes y saludos para después de las horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-185">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="6ef6c-186">En función de cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas después de las horas para los operadores automáticos con números de teléfono directos.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-186">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="6ef6c-187">Si desea un enrutamiento de llamadas por separado para llamadas de fuera de horario laboral, especifique el horario laboral para cada día.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-187">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="6ef6c-188">Haga clic en **Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar una pausa para comer.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-188">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="6ef6c-189">Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para después de horas.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-189">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="6ef6c-190">Las mismas opciones están disponibles para el enrutamiento de llamadas de horario laboral que especificó más arriba.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-190">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="6ef6c-191">Cuando haya terminado, haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="6ef6c-191">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="6ef6c-192">Flujos de llamadas durante los días festivos</span><span class="sxs-lookup"><span data-stu-id="6ef6c-192">Call flows during holidays</span></span>

![](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="6ef6c-193">El operador automático puede tener un flujo de llamadas por cada [festividad que hayas configurado](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-193">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="6ef6c-194">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-194">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="6ef6c-195">En la página de configuración de llamadas, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-195">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="6ef6c-196">Escriba un nombre para esta configuración de días festivos.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-196">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="6ef6c-197">En la lista desplegable **vacaciones** , elija el día no laborable que desea usar.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-197">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="6ef6c-198">Elija el tipo de saludo que desea usar.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-198">Choose the type of greeting that you want to use.</span></span>

    ![](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="6ef6c-199">Elige si deseas **desconectar** o **desviar** la llamada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-199">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="6ef6c-200">Si eliges redirigir, elige el destino de enrutamiento de llamadas para la llamada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-200">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="6ef6c-201">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-201">Click **Save**.</span></span>

![](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="6ef6c-202">Repita el procedimiento según sea necesario para cada festividad adicional.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-202">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="6ef6c-203">Cuando haya agregado todos los días no laborables, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-203">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="6ef6c-204">Ámbito de marcado</span><span class="sxs-lookup"><span data-stu-id="6ef6c-204">Dial scope</span></span>

![](media/auto-attendant-dial-scope.png)

<span data-ttu-id="6ef6c-205">El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando una persona que llama usa el método de marcado por nombre o la extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-205">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="6ef6c-206">El valor predeterminado de **todos los usuarios en línea** incluye todos los usuarios de su organización que son usuarios en línea con una licencia de sistema de teléfono o que se han hospedado de forma local con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-206">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="6ef6c-207">Puede incluir o excluir determinados usuarios seleccionando **grupo de usuarios personalizado** en **incluir** o **excluir** y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-207">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="6ef6c-208">Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-208">For example, you might want to exclude executives in your organization from the dialing directory.</span></span>

> [!NOTE]
> <span data-ttu-id="6ef6c-209">Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-209">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="6ef6c-210">Cuando haya terminado de establecer el ámbito de marcado, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-210">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="6ef6c-211">Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="6ef6c-211">Resource accounts</span></span>

<span data-ttu-id="6ef6c-212">Todos los operadores automáticos deben tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-212">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="6ef6c-213">Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos con un número de servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-213">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="6ef6c-214">Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada uno con un número de servicio diferente.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-214">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="6ef6c-215">Para agregar una cuenta de recursos, haga clic en **Agregar cuenta** y busque la cuenta que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-215">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="6ef6c-216">Haga clic en **Agregar**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-216">Click **Add**, and then click **Add**.</span></span>

![](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="6ef6c-217">Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-217">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="6ef6c-218">Esto completa la configuración del operador automático.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-218">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="6ef6c-219">Transferencias de números de teléfono externos: detalles técnicos</span><span class="sxs-lookup"><span data-stu-id="6ef6c-219">External phone number transfers - technical details</span></span>

<span data-ttu-id="6ef6c-220">Al transferir llamadas a un número de teléfono externo, la cuenta de recursos asociada con el operador automático o la cola de llamadas debe tener un número de teléfono y una licencia de usuario virtual del sistema de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-220">When transferring calls to an external phone number, the resource account associated with the auto attendant or call queue must have a phone number and a Microsoft 365 Phone System - Virtual User license.</span></span> <span data-ttu-id="6ef6c-221">Limita</span><span class="sxs-lookup"><span data-stu-id="6ef6c-221">Additionally:</span></span>

- <span data-ttu-id="6ef6c-222">Para una cuenta de recursos con un número de plan de llamadas, asigne una licencia de [plan de llamadas](calling-plans-for-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="6ef6c-222">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="6ef6c-223">Para una cuenta de recursos con un número de enrutamiento directo, asigne una [Directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-223">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

<span data-ttu-id="6ef6c-224">El número de teléfono saliente que se muestra se determina de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6ef6c-224">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="6ef6c-225">Para los números de planes de llamadas, se muestra el número de teléfono de la persona que llama original.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-225">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="6ef6c-226">Para los números de enrutamiento directos, el número enviado se basa en la configuración P-asserted-Identity (PAI) en SBC, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6ef6c-226">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="6ef6c-227">Si se establece en deshabilitado, se muestra el número de teléfono de la persona que llama original.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-227">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="6ef6c-228">Esta es la configuración predeterminada y recomendada.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-228">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="6ef6c-229">Si se establece en habilitado, se muestra el número de teléfono de la cuenta del recurso.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-229">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="6ef6c-230">No se admiten las transferencias entre los troncos del plan de llamadas y los troncos de enrutamiento directos.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-230">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

<span data-ttu-id="6ef6c-231">En un entorno híbrido, para transferir una llamada de operador automático a la RTC a través de la integración RTC de Skype empresarial, cree un nuevo usuario local con el desvío de llamadas establecido en el número de RTC.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-231">In a hybrid environment, to transfer an auto attendant call to the PSTN via Skype for Business PSTN integration, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="6ef6c-232">El usuario debe estar habilitado para telefonía IP empresarial y tiene asignada una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-232">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="6ef6c-233">Para obtener más información, consulte [transferencia automática de llamadas de operador a RTC](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="6ef6c-233">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="6ef6c-234">Crear un operador automático con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef6c-234">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="6ef6c-235">También puede usar PowerShell para crear y configurar operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="6ef6c-235">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="6ef6c-236">Estos son los cmdlets que necesita para administrar un operador automático:</span><span class="sxs-lookup"><span data-stu-id="6ef6c-236">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="6ef6c-237">Nuevo: CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ef6c-237">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="6ef6c-238">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ef6c-238">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="6ef6c-239">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ef6c-239">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [<span data-ttu-id="6ef6c-240">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="6ef6c-240">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="6ef6c-241">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ef6c-241">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="6ef6c-242">Nuevo: CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="6ef6c-242">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="6ef6c-243">Nuevo: CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="6ef6c-243">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="6ef6c-244">Nuevo: CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="6ef6c-244">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="6ef6c-245">Exportar-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="6ef6c-245">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="6ef6c-246">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="6ef6c-246">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="6ef6c-247">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="6ef6c-247">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="6ef6c-248">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="6ef6c-248">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="6ef6c-249">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="6ef6c-249">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="6ef6c-250">Nuevo: CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="6ef6c-250">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="6ef6c-251">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="6ef6c-251">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="6ef6c-252">Importar-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="6ef6c-252">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="6ef6c-253">Nuevo: CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="6ef6c-253">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)


## <a name="related-topics"></a><span data-ttu-id="6ef6c-254">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6ef6c-254">Related topics</span></span>

[<span data-ttu-id="6ef6c-255">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="6ef6c-255">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="6ef6c-256">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="6ef6c-256">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="6ef6c-257">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="6ef6c-257">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="6ef6c-258">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="6ef6c-258">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="6ef6c-259">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6ef6c-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

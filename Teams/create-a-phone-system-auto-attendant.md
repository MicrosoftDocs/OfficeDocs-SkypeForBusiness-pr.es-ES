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
description: Obtenga información sobre cómo configurar y probar operadores automáticos para Microsoft Teams.
ms.openlocfilehash: 2aef87d1a7885df01b02a5708ac1079ea8021add
ms.sourcegitcommit: 745b37921a878f1b524a274bfb2fd0732716a5c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2021
ms.locfileid: "52498795"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="7a18f-103">Configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="7a18f-103">Set up an auto attendant</span></span>

<span data-ttu-id="7a18f-104">Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el departamento adecuado, la cola de llamadas, una persona o un operador.</span><span class="sxs-lookup"><span data-stu-id="7a18f-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="7a18f-105">Puede crear operadores automáticos para su organización con el Microsoft Teams de administración o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a18f-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="7a18f-106">Asegúrese de que ha leído Planear Teams operadores [automáticos](plan-auto-attendant-call-queue.md) y [](plan-auto-attendant-call-queue.md#getting-started) colas de llamadas y ha seguido los pasos de introducción antes de seguir los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="7a18f-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="7a18f-107">Los operadores automáticos pueden dirigir las llamadas, según la entrada de los autores de llamadas, a uno de los siguientes destinos: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="7a18f-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="7a18f-108">**Operador:** el operador definido para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="7a18f-109">Definir un operador es opcional.</span><span class="sxs-lookup"><span data-stu-id="7a18f-109">Defining an operator is optional.</span></span> <span data-ttu-id="7a18f-110">El operador se puede definir como cualquiera de los otros destinos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="7a18f-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="7a18f-111">**Persona de la organización:** una persona de su organización que puede recibir llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="7a18f-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="7a18f-112">Esta persona puede ser un usuario en línea o un usuario hospedado localmente mediante Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7a18f-112">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="7a18f-113">**Aplicación de voz:** otro operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7a18f-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="7a18f-114">(Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="7a18f-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="7a18f-115">**Correo de** voz: el buzón de voz asociado a Microsoft 365 grupo que especifique.</span><span class="sxs-lookup"><span data-stu-id="7a18f-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="7a18f-116">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="7a18f-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="7a18f-117">(Vea [detalles técnicos de transferencia externa).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="7a18f-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="7a18f-118">**Anuncio (archivo de audio):** reproducir un archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="7a18f-118">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="7a18f-119">Un mensaje de anuncio grabado que carga que se guarda como audio en . WAV, .MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="7a18f-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="7a18f-120">La grabación no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="7a18f-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="7a18f-121">El sistema reproduce el anuncio y, a continuación, vuelve al menú operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="7a18f-122">**Anuncio (con tipo):** escriba un mensaje.</span><span class="sxs-lookup"><span data-stu-id="7a18f-122">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="7a18f-123">Texto que desea que lea el sistema.</span><span class="sxs-lookup"><span data-stu-id="7a18f-123">Text you want the system to read.</span></span> <span data-ttu-id="7a18f-124">Puede escribir hasta 1000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a18f-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="7a18f-125">El sistema reproduce el anuncio y, a continuación, vuelve al menú operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="7a18f-126">Se le pedirá que elija una de estas opciones en varias fases mientras configura un operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

> [!NOTE]
> <span data-ttu-id="7a18f-127">Al elegir correo de voz como destino, hay dos opciones adicionales disponibles:</span><span class="sxs-lookup"><span data-stu-id="7a18f-127">When choosing Voicemail as a destination, two additional options are available:</span></span>
> - <span data-ttu-id="7a18f-128">**Transcripción** (Predeterminada: Desactivado): cuando esté habilitado, el mensaje de correo de voz se transcribirá e incluirá como parte del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7a18f-128">**Transcription** (Default: Off) - when enabled, the voicemail message will be transcribed and included as part of the email.</span></span>
> - <span data-ttu-id="7a18f-129">**Suprimir saludo** (predeterminado: desactivado): cuando está habilitado, el mensaje estándar del sistema "Deje un mensaje después del tono.</span><span class="sxs-lookup"><span data-stu-id="7a18f-129">**Suppress Greeting** (Default: Off) - when enabled, the standard system message "Please leave a message after the tone.</span></span> <span data-ttu-id="7a18f-130">Cuando haya terminado, cuelgue o presione la tecla hash para obtener más opciones".</span><span class="sxs-lookup"><span data-stu-id="7a18f-130">When you have finished please hang up or press the hash key for more options."</span></span> <span data-ttu-id="7a18f-131">se suprimirá.</span><span class="sxs-lookup"><span data-stu-id="7a18f-131">will be suppressed.</span></span>

<span data-ttu-id="7a18f-132">Para configurar un operador automático, en el centro de administración de Teams, expanda Voz **,** seleccione **Operadores automáticos** y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7a18f-132">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7a18f-133">Demostración de vídeo</span><span class="sxs-lookup"><span data-stu-id="7a18f-133">Video demonstration</span></span>

<span data-ttu-id="7a18f-134">En este vídeo se muestra un ejemplo básico de cómo crear un operador automático en Teams.</span><span class="sxs-lookup"><span data-stu-id="7a18f-134">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="7a18f-135">Información general</span><span class="sxs-lookup"><span data-stu-id="7a18f-135">General info</span></span>

![Captura de pantalla de la configuración del operador automático para el nombre, el operador, la zona horaria, el idioma y las entradas de voz](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="7a18f-137">Escriba un nombre para el operador automático en el cuadro de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="7a18f-137">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="7a18f-138">Para designar un operador, especifique el destino de las llamadas al operador.</span><span class="sxs-lookup"><span data-stu-id="7a18f-138">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="7a18f-139">Esta designación es opcional (pero recomendada).</span><span class="sxs-lookup"><span data-stu-id="7a18f-139">This designation is optional (but recommended).</span></span> <span data-ttu-id="7a18f-140">Establezca la **opción Operador** para permitir a los autores de llamadas salir de los menús y hablar con una persona designada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-140">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="7a18f-141">Especifique la zona horaria para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-141">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="7a18f-142">La zona horaria se usa para calcular el horario laboral si crea un flujo de [llamada independiente para horas 2010.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="7a18f-142">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="7a18f-143">Especifique un [idioma compatible](create-a-phone-system-auto-attendant-languages.md) para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-143">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="7a18f-144">Este es el idioma que se usará para las solicitudes de voz generadas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="7a18f-144">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="7a18f-145">Elija si desea habilitar las entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="7a18f-145">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="7a18f-146">Cuando se habilita, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="7a18f-146">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="7a18f-147">Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".</span><span class="sxs-lookup"><span data-stu-id="7a18f-147">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="7a18f-148">Si elige un idioma en el paso 4 que no admite entradas de voz, esta opción se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="7a18f-148">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="7a18f-149">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a18f-149">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="7a18f-150">Flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="7a18f-150">Call flow</span></span>

![Captura de pantalla de la configuración del mensaje de saludo](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="7a18f-152">Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-152">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="7a18f-153">Si selecciona **Reproducir un archivo de audio,** puede usar el botón **Upload** archivo para cargar un mensaje de saludo grabado guardado como audio en . WAV, .MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="7a18f-153">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="7a18f-154">La grabación no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="7a18f-154">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="7a18f-155">Si selecciona **Escribir un mensaje de** saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-155">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Captura de pantalla de la configuración de enrutamiento de llamadas](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="7a18f-157">Elija cómo desea enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-157">Choose how you want to route the call.</span></span>

<span data-ttu-id="7a18f-158">Si selecciona **Desconectar,** el operador automático colgará la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-158">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="7a18f-159">Si selecciona **Redirigir llamada,** puede elegir uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7a18f-159">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="7a18f-160">Si selecciona Opciones **de menú** Reproducir, puede elegir Reproducir un archivo de **audio** o Escribir en un mensaje de saludo y, **a** continuación, elegir entre las opciones de menú y la búsqueda de directorio.</span><span class="sxs-lookup"><span data-stu-id="7a18f-160">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="7a18f-161">Opciones de menú</span><span class="sxs-lookup"><span data-stu-id="7a18f-161">Menu options</span></span>

![Captura de pantalla de las opciones de la tecla de marcado](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="7a18f-163">Para las opciones de marcado, asigne las teclas 0-9 del teclado del teléfono a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7a18f-163">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="7a18f-164">(Las teclas \* (Repetir) y \# (Atrás) están reservados por el sistema y no se pueden reasignar).</span><span class="sxs-lookup"><span data-stu-id="7a18f-164">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="7a18f-165">Las asignaciones de claves no tienen que ser continuas.</span><span class="sxs-lookup"><span data-stu-id="7a18f-165">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="7a18f-166">Es posible crear un menú con las teclas 0, 1 y 3 asignadas a opciones, mientras que la tecla número 2 no se usa.</span><span class="sxs-lookup"><span data-stu-id="7a18f-166">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="7a18f-167">Se recomienda asignar la clave cero al operador si ha configurado una.</span><span class="sxs-lookup"><span data-stu-id="7a18f-167">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="7a18f-168">Si el operador no está establecido en ninguna tecla, el comando de voz "Operador" también está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="7a18f-168">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="7a18f-169">Para cada opción de menú, especifique la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="7a18f-169">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="7a18f-170">**Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.</span><span class="sxs-lookup"><span data-stu-id="7a18f-170">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="7a18f-171">Si hay entradas de voz disponibles, los autores de llamadas también pueden decir este número para acceder a la opción.</span><span class="sxs-lookup"><span data-stu-id="7a18f-171">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="7a18f-172">**Comando de voz:** define el comando de voz que un autor de la llamada puede dar para obtener acceso a esta opción, si las entradas de voz están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="7a18f-172">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="7a18f-173">Puede contener varias palabras como "Servicio al cliente" o "Operaciones y motivos".</span><span class="sxs-lookup"><span data-stu-id="7a18f-173">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="7a18f-174">Por ejemplo, el autor de la llamada puede presionar 2, decir "dos" o decir "Ventas" para seleccionar la opción asignada a las dos teclas.</span><span class="sxs-lookup"><span data-stu-id="7a18f-174">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="7a18f-175">Este texto también se representa de texto a voz para el mensaje de confirmación del servicio, que puede ser algo así como "Transferir la llamada a las ventas".</span><span class="sxs-lookup"><span data-stu-id="7a18f-175">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="7a18f-176">**Redirigir a:** el destino de enrutamiento de llamadas que se usa cuando los autores de llamadas eligen esta opción.</span><span class="sxs-lookup"><span data-stu-id="7a18f-176">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="7a18f-177">Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-177">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="7a18f-178">Búsqueda de directorios</span><span class="sxs-lookup"><span data-stu-id="7a18f-178">Directory search</span></span>

<span data-ttu-id="7a18f-179">Si asigna teclas de marcado a destinos, le recomendamos que elija **Ninguna para** búsqueda **de directorio.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-179">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="7a18f-180">Si un autor de la llamada intenta marcar un nombre o una extensión con claves asignadas a destinos específicos, es posible que se enruten inesperadamente a un destino antes de que terminen de escribir el nombre o la extensión.</span><span class="sxs-lookup"><span data-stu-id="7a18f-180">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="7a18f-181">Le recomendamos que cree un operador automático independiente para la búsqueda de directorios y que tenga el vínculo del operador automático principal con una tecla de marcado.</span><span class="sxs-lookup"><span data-stu-id="7a18f-181">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="7a18f-182">Si no ha asignado las teclas de marcado, elija una opción para búsqueda **de directorios.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-182">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="7a18f-183">**Marcar por nombre:** si habilita esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="7a18f-183">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="7a18f-184">Cualquier usuario en línea o cualquier usuario hospedado local que use Skype Empresarial Server, es un usuario apto y se puede encontrar con Marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="7a18f-184">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="7a18f-185">(Puede establecer quién es y quién no se incluye en el directorio en la [página Ámbito de](#dial-scope) marcado).</span><span class="sxs-lookup"><span data-stu-id="7a18f-185">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="7a18f-186">**Marcar por extensión:** si habilita esta opción, los autores de llamadas pueden conectarse con los usuarios de su organización marcando su extensión de teléfono.</span><span class="sxs-lookup"><span data-stu-id="7a18f-186">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="7a18f-187">Cualquier usuario en línea o cualquier usuario hospedado local que use Skype Empresarial Server, es un usuario apto y se puede encontrar **con Marcar por extensión.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-187">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="7a18f-188">(Puede establecer quién es y quién no se incluye en el directorio en la [página Ámbito de](#dial-scope) marcado).</span><span class="sxs-lookup"><span data-stu-id="7a18f-188">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="7a18f-189">Los usuarios que desea que estén disponibles para Marcar por extensión deben tener una extensión especificada como parte de [](/microsoft-365/admin/add-users/add-users) uno de los siguientes atributos de teléfono definidos en Active Directory o Azure Active Directory (vea Agregar usuarios individualmente o en masa para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="7a18f-189">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="7a18f-190">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="7a18f-190">OfficePhone</span></span>
- <span data-ttu-id="7a18f-191">HomePhone</span><span class="sxs-lookup"><span data-stu-id="7a18f-191">HomePhone</span></span>
- <span data-ttu-id="7a18f-192">Móvil/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="7a18f-192">Mobile/MobilePhone</span></span>
- <span data-ttu-id="7a18f-193">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="7a18f-193">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="7a18f-194">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="7a18f-194">OtherTelephone</span></span>

<span data-ttu-id="7a18f-195">El formato necesario para introducir la extensión en el campo de número de teléfono de usuario puede ser uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="7a18f-195">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="7a18f-196">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="7a18f-196">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="7a18f-197">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="7a18f-197">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="7a18f-198">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="7a18f-198">*x\<extension>*</span></span>

- <span data-ttu-id="7a18f-199">Ejemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="7a18f-199">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="7a18f-200">Ejemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="7a18f-200">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="7a18f-201">Ejemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="7a18f-201">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="7a18f-202">Puede establecer la extensión en el centro [Microsoft 365 de administración](https://admin.microsoft.com/) o en el Azure Active Directory de [administración.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="7a18f-202">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="7a18f-203">Los operadores automáticos y las colas de llamadas pueden tardar hasta 12 horas en estar disponibles para los cambios.</span><span class="sxs-lookup"><span data-stu-id="7a18f-203">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="7a18f-204">Si desea usar las  características Marcar  por nombre y Marcar por extensión, puede asignar una clave de marcado al operador automático principal para que llegue a un operador automático habilitado para Marcar **por nombre.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-204">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="7a18f-205">Dentro de ese operador automático, puede asignar la tecla 1 (que no tiene letras asociadas) para que llegue al operador automático Marcar por **extensión.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-205">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="7a18f-206">Una vez que haya seleccionado una **opción de búsqueda de** directorio, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-206">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="7a18f-207">Flujo de llamadas para horas pasadas</span><span class="sxs-lookup"><span data-stu-id="7a18f-207">Call flow for after hours</span></span>

![Captura de pantalla de la configuración de días y horas adicionales](media/auto-attendant-business-hours.png)

<span data-ttu-id="7a18f-209">El horario laboral se puede establecer para cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-209">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="7a18f-210">Si el horario laboral no está establecido, todos los días y todas las horas del día se consideran horario laboral porque una programación 24/7 está establecida de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-210">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="7a18f-211">El horario laboral se puede establecer con descansos en el tiempo durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="7a18f-211">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="7a18f-212">Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para las horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="7a18f-212">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="7a18f-213">Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas adicionales para los operadores automáticos con números de teléfono directos.</span><span class="sxs-lookup"><span data-stu-id="7a18f-213">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="7a18f-214">Si quiere un enrutamiento de llamadas independiente para las personas que llaman fuera del horario laboral, especifique su horario laboral para cada día.</span><span class="sxs-lookup"><span data-stu-id="7a18f-214">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="7a18f-215">Seleccione **Agregar nueva hora para** especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar un descanso para comer.</span><span class="sxs-lookup"><span data-stu-id="7a18f-215">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="7a18f-216">Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="7a18f-216">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="7a18f-217">Las mismas opciones están disponibles que para el enrutamiento de llamadas en horario laboral que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7a18f-217">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="7a18f-218">Seleccione **Siguiente** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="7a18f-218">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="7a18f-219">Flujos de llamadas durante los días festivos</span><span class="sxs-lookup"><span data-stu-id="7a18f-219">Call flows during holidays</span></span>

![Captura de pantalla de la configuración de saludo navideña y navideña](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="7a18f-221">El operador automático puede tener un flujo de llamadas para cada [vacaciones que haya configurado.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7a18f-221">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="7a18f-222">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-222">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="7a18f-223">En la página Configuración de la llamada navideña, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7a18f-223">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="7a18f-224">Escriba un nombre para esta configuración navideña.</span><span class="sxs-lookup"><span data-stu-id="7a18f-224">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="7a18f-225">En la **lista desplegable** Vacaciones, elija los días festivos que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="7a18f-225">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="7a18f-226">Elija el tipo de saludo que desea usar.</span><span class="sxs-lookup"><span data-stu-id="7a18f-226">Choose the type of greeting that you want to use.</span></span>

    ![Captura de pantalla de la configuración de acción de llamada navideña](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="7a18f-228">Elija si desea desconectar **o** **redirigir** la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-228">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="7a18f-229">Si elige redirigir, elija el destino de enrutamiento de llamadas para la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-229">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="7a18f-230">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7a18f-230">Select **Save**.</span></span>

![Captura de pantalla de la configuración de vacaciones con días festivos en la lista](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="7a18f-232">Repita el procedimiento según sea necesario para cada vacaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="7a18f-232">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="7a18f-233">Cuando haya agregado todos los días festivos, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-233">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="7a18f-234">Ámbito de marcado</span><span class="sxs-lookup"><span data-stu-id="7a18f-234">Dial scope</span></span>

![Captura de pantalla del ámbito de marcado para incluir y excluir opciones](media/auto-attendant-dial-scope.png)

<span data-ttu-id="7a18f-236">El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de la llamada usa marcado por nombre o marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="7a18f-236">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="7a18f-237">El valor predeterminado de **Todos los usuarios en** línea incluye todos los usuarios de su organización que son usuarios en línea o hospedados localmente mediante Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7a18f-237">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="7a18f-238">Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad. </span><span class="sxs-lookup"><span data-stu-id="7a18f-238">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="7a18f-239">Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado.</span><span class="sxs-lookup"><span data-stu-id="7a18f-239">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="7a18f-240">(Si un usuario está en ambas listas, se excluirá del directorio).</span><span class="sxs-lookup"><span data-stu-id="7a18f-240">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="7a18f-241">Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio.</span><span class="sxs-lookup"><span data-stu-id="7a18f-241">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="7a18f-242">Cuando haya terminado de configurar el ámbito de marcado, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="7a18f-242">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="7a18f-243">Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="7a18f-243">Resource accounts</span></span>

<span data-ttu-id="7a18f-244">Todos los operadores automáticos deben tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-244">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="7a18f-245">Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos que tenga un número de servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="7a18f-245">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="7a18f-246">Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="7a18f-246">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Captura de pantalla del panel agregar cuentas de la cuenta de recursos](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="7a18f-248">Para agregar una cuenta de recurso, seleccione **Agregar cuenta** y busque la cuenta que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="7a18f-248">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="7a18f-249">Seleccione **Agregar** y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7a18f-249">Select **Add**, and then select **Add**.</span></span>

![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recursos con el número de servicio asignado](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="7a18f-251">Cuando haya terminado de agregar cuentas de servicio, seleccione **Enviar** para completar la configuración de operador automático.</span><span class="sxs-lookup"><span data-stu-id="7a18f-251">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="7a18f-252">Transferencias de números de teléfono externos: detalles técnicos</span><span class="sxs-lookup"><span data-stu-id="7a18f-252">External phone number transfers - technical details</span></span>

<span data-ttu-id="7a18f-253">Consulte Los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que los operadores automáticos transfieran llamadas externamente.</span><span class="sxs-lookup"><span data-stu-id="7a18f-253">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="7a18f-254">Además:</span><span class="sxs-lookup"><span data-stu-id="7a18f-254">In addition:</span></span>

- <span data-ttu-id="7a18f-255">Para una cuenta de recurso con una licencia de [Plan](calling-plans-for-office-365.md)de llamadas, el número de teléfono de transferencia externa debe especificarse en formato E.164 (+[código de país][código de área][número de teléfono]).</span><span class="sxs-lookup"><span data-stu-id="7a18f-255">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="7a18f-256">Para una cuenta de recursos con una directiva de enrutamiento de voz Sistema telefónico licencia y enrutamiento directo en línea, el formato de número de teléfono de transferencia externa depende de la configuración del Controlador de borde de sesión [(SBC).](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="7a18f-256">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="7a18f-257">El número de teléfono saliente que se muestra se determina de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7a18f-257">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="7a18f-258">Para los números de plan de llamadas, se muestra el número de teléfono del autor de la llamada original.</span><span class="sxs-lookup"><span data-stu-id="7a18f-258">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="7a18f-259">Para los números de enrutamiento directo, el número enviado se basa en la configuración P-Asserted-Identity (PAI) en el SBC, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="7a18f-259">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="7a18f-260">Si se establece en Deshabilitado, se muestra el número de teléfono del autor de la llamada original.</span><span class="sxs-lookup"><span data-stu-id="7a18f-260">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="7a18f-261">Esta es la configuración predeterminada y recomendada.</span><span class="sxs-lookup"><span data-stu-id="7a18f-261">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="7a18f-262">Si se establece en Habilitado, se muestra el número de teléfono de la cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="7a18f-262">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="7a18f-263">En un Skype Empresarial híbrido, para transferir una llamada de operador automático a la RTC, cree un nuevo usuario local con el reenvío de llamadas establecido en el número RTC.</span><span class="sxs-lookup"><span data-stu-id="7a18f-263">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="7a18f-264">El usuario debe estar habilitado para Telefonía IP empresarial y tener asignada una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="7a18f-264">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="7a18f-265">Para obtener más información, vea [Transferencia automática de llamadas a RTC.](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="7a18f-265">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="7a18f-266">Crear un operador automático con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a18f-266">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="7a18f-267">También puede usar PowerShell para crear y configurar operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="7a18f-267">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="7a18f-268">Estos son los cmdlets que necesita para administrar un operador automático:</span><span class="sxs-lookup"><span data-stu-id="7a18f-268">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="7a18f-269">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7a18f-269">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="7a18f-270">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7a18f-270">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="7a18f-271">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7a18f-271">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="7a18f-272">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="7a18f-272">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="7a18f-273">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7a18f-273">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="7a18f-274">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="7a18f-274">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="7a18f-275">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="7a18f-275">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="7a18f-276">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="7a18f-276">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="7a18f-277">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="7a18f-277">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="7a18f-278">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="7a18f-278">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="7a18f-279">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="7a18f-279">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="7a18f-280">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="7a18f-280">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="7a18f-281">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="7a18f-281">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="7a18f-282">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="7a18f-282">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="7a18f-283">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="7a18f-283">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="7a18f-284">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="7a18f-284">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="7a18f-285">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="7a18f-285">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="7a18f-286">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7a18f-286">Related topics</span></span>

[<span data-ttu-id="7a18f-287">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="7a18f-287">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="7a18f-288">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="7a18f-288">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="7a18f-289">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="7a18f-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="7a18f-290">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7a18f-290">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

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
ms.openlocfilehash: 4809965eaad0f8cd81b59823d3890bd895998906
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919052"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="bf413-103">Configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="bf413-103">Set up an auto attendant</span></span>

<span data-ttu-id="bf413-104">Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el departamento, la cola de llamadas, la persona o un operador adecuados.</span><span class="sxs-lookup"><span data-stu-id="bf413-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="bf413-105">Puede crear operadores automáticos para su organización con el Centro de administración de Microsoft Teams o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf413-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="bf413-106">Asegúrese de haber leído plan para operadores [automáticos](plan-auto-attendant-call-queue.md) y [](plan-auto-attendant-call-queue.md#getting-started) colas de llamadas de Teams y de haber seguido los pasos de introducción antes de seguir los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="bf413-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="bf413-107">Los operadores automáticos pueden dirigir las llamadas, en función de la entrada de los autores de llamadas, a uno de los siguientes destinos: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="bf413-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="bf413-108">**Persona de la organización:** una persona de la organización que puede recibir llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="bf413-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="bf413-109">Puede ser un usuario en línea o un usuario alojado en local con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bf413-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="bf413-110">**Aplicación de voz:** otro operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf413-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="bf413-111">(Elija la cuenta de recurso asociada al operador automático o la cola de llamadas al elegir este destino).</span><span class="sxs-lookup"><span data-stu-id="bf413-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="bf413-112">**Número de teléfono externo:** cualquier número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="bf413-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="bf413-113">(Consulte [los detalles técnicos de la transferencia externa).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="bf413-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="bf413-114">**Correo** de voz: el buzón de voz asociado a un grupo de Microsoft 365 que especifique.</span><span class="sxs-lookup"><span data-stu-id="bf413-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="bf413-115">**Operador** ( operador definido para el operador automático).</span><span class="sxs-lookup"><span data-stu-id="bf413-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="bf413-116">La definición de un operador es opcional.</span><span class="sxs-lookup"><span data-stu-id="bf413-116">Defining an operator is optional.</span></span> <span data-ttu-id="bf413-117">El operador se puede definir como cualquiera de los otros destinos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="bf413-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="bf413-118">Se le pedirá que elija una de estas opciones en varias fases a medida que configura un operador automático.</span><span class="sxs-lookup"><span data-stu-id="bf413-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="bf413-119">Para configurar un operador automático, en el centro de administración de Teams, expanda **Voz,** haga clic en **Operadores automáticos** y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="bf413-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="bf413-120">Información general</span><span class="sxs-lookup"><span data-stu-id="bf413-120">General info</span></span>

![Captura de pantalla de la configuración del operador automático para entradas de nombre, operador, zona horaria, idioma y voz](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="bf413-122">Escriba un nombre para el operador automático en el cuadro de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="bf413-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="bf413-123">Si desea designar un operador, especifique el destino de las llamadas al operador.</span><span class="sxs-lookup"><span data-stu-id="bf413-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="bf413-124">Esto es opcional (pero recomendado).</span><span class="sxs-lookup"><span data-stu-id="bf413-124">This is optional (but recommended).</span></span> <span data-ttu-id="bf413-125">Puede establecer la opción **Operador para** permitir que los autores de llamadas salgan de los menús y hablen con la persona designada.</span><span class="sxs-lookup"><span data-stu-id="bf413-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="bf413-126">Especifique la zona horaria de este operador automático.</span><span class="sxs-lookup"><span data-stu-id="bf413-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="bf413-127">La zona horaria se usa para calcular el horario laboral si crea un flujo de llamadas separado para horas [fuera del horario laboral.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="bf413-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="bf413-128">Especifique un idioma para este operador automático.</span><span class="sxs-lookup"><span data-stu-id="bf413-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="bf413-129">Este es el idioma que se usará para los mensajes de voz generados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="bf413-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="bf413-130">Elija si desea habilitar las entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="bf413-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="bf413-131">Cuando está habilitada, el nombre de todas las opciones de menú se convierte en una palabra clave de reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="bf413-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="bf413-132">Por ejemplo, las personas que llaman pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".</span><span class="sxs-lookup"><span data-stu-id="bf413-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="bf413-133">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bf413-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="bf413-134">Flujo de llamadas</span><span class="sxs-lookup"><span data-stu-id="bf413-134">Call flow</span></span>

![Captura de pantalla de la configuración del mensaje de saludo](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="bf413-136">Elija si desea reproducir un saludo cuando el operador automático responda una llamada.</span><span class="sxs-lookup"><span data-stu-id="bf413-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="bf413-137">Si selecciona Reproducir un archivo de  **audio,** puede usar el botón Cargar archivo para cargar un mensaje de saludo grabado guardado como audio en. WAV, . MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="bf413-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="bf413-138">La grabación no puede ser superior a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="bf413-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="bf413-139">Si selecciona **Escribir** un mensaje de saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda una llamada.</span><span class="sxs-lookup"><span data-stu-id="bf413-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Captura de pantalla de la configuración de enrutamiento de llamadas](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="bf413-141">Elige cómo quieres enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf413-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="bf413-142">Si selecciona **Desconectar,** el operador automático colgará la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf413-142">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="bf413-143">Si selecciona Redirigir **llamada, puede** elegir uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf413-143">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="bf413-144">Si selecciona las **opciones del** menú Reproducir, puede  elegir reproducir un archivo de **audio** o escribir un mensaje de saludo y elegir entre las opciones de menú y la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="bf413-144">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="bf413-145">Opciones de menú</span><span class="sxs-lookup"><span data-stu-id="bf413-145">Menu options</span></span>

![Captura de pantalla de las opciones de tecla de marcado](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="bf413-147">Para las opciones de marcación, puede asignar las teclas de 0 a 9 del teclado telefónico a uno de los destinos de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf413-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="bf413-148">(Las teclas \* (Repetir) \# y (Volver) están reservados por el sistema y no se pueden reasignar).</span><span class="sxs-lookup"><span data-stu-id="bf413-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="bf413-149">Las asignaciones de teclas no tienen por qué ser continuas.</span><span class="sxs-lookup"><span data-stu-id="bf413-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="bf413-150">Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a opciones, mientras que la tecla 2 no se usa.</span><span class="sxs-lookup"><span data-stu-id="bf413-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="bf413-151">Se recomienda asignar la clave 0 al operador si ha configurado una.</span><span class="sxs-lookup"><span data-stu-id="bf413-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="bf413-152">Si el operador no está establecido en ninguna tecla, el comando de voz "Operador" también está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="bf413-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="bf413-153">Para cada opción de menú, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf413-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="bf413-154">**Tecla de marcado:** la tecla del teclado del teléfono para acceder a esta opción.</span><span class="sxs-lookup"><span data-stu-id="bf413-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="bf413-155">Si las entradas de voz están disponibles, las personas que llaman también pueden decir este número para acceder a la opción.</span><span class="sxs-lookup"><span data-stu-id="bf413-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="bf413-156">**Comando de** voz: define el comando de voz que puede dar un autor de llamada para obtener acceso a esta opción, si las entradas de voz están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="bf413-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="bf413-157">Puede contener varias palabras como "Atención al cliente" u "Operaciones y campos".</span><span class="sxs-lookup"><span data-stu-id="bf413-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="bf413-158">Por ejemplo, el autor de la llamada puede presionar 2, decir "dos" o decir "Ventas" para seleccionar la opción asignada a la tecla 2.</span><span class="sxs-lookup"><span data-stu-id="bf413-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="bf413-159">Este texto también se representa de texto a voz para la confirmación del servicio, que puede ser algo parecido a "Transferir la llamada a ventas".</span><span class="sxs-lookup"><span data-stu-id="bf413-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="bf413-160">**Redirigir a:** el destino de enrutamiento de llamada que se usa cuando los autores de llamadas eligen esta opción.</span><span class="sxs-lookup"><span data-stu-id="bf413-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="bf413-161">Si redirige a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada con él.</span><span class="sxs-lookup"><span data-stu-id="bf413-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="bf413-162">Búsqueda en directorios</span><span class="sxs-lookup"><span data-stu-id="bf413-162">Directory search</span></span>

<span data-ttu-id="bf413-163">Si asigna teclas de marcado a destinos, le recomendamos que elija Ninguno **para** búsqueda **en el directorio.**</span><span class="sxs-lookup"><span data-stu-id="bf413-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="bf413-164">Si el autor de la llamada intenta marcar un nombre o una extensión con claves asignadas a destinos específicos, es posible que se enruten inesperadamente a un destino antes de terminar de escribir el nombre o la extensión.</span><span class="sxs-lookup"><span data-stu-id="bf413-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="bf413-165">Le recomendamos que cree un operador automático independiente para realizar búsquedas en el directorio y que tenga un vínculo al operador automático principal mediante una tecla de marcado.</span><span class="sxs-lookup"><span data-stu-id="bf413-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="bf413-166">Si no ha asignado las teclas de marcado, elija una opción para la **búsqueda en el directorio.**</span><span class="sxs-lookup"><span data-stu-id="bf413-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="bf413-167">**Marcado por nombre:** si habilita esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="bf413-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="bf413-168">Cualquier usuario en línea o cualquier usuario local que utilice Skype Empresarial Server es un usuario apto y se puede encontrar con Marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="bf413-168">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="bf413-169">(Puede establecer quién está incluido en el directorio y quién no en la [página Ámbito de](#dial-scope) marcado).</span><span class="sxs-lookup"><span data-stu-id="bf413-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="bf413-170">**Marcado por extensión:** si habilita esta opción, los autores de llamadas pueden conectarse con los usuarios de su organización marcando su extensión de teléfono.</span><span class="sxs-lookup"><span data-stu-id="bf413-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="bf413-171">Cualquier usuario en línea o cualquier usuario local que utilice Skype Empresarial Server es un usuario apto y se puede encontrar **con Marcado por extensión.**</span><span class="sxs-lookup"><span data-stu-id="bf413-171">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="bf413-172">(Puede establecer quién está incluido en el directorio y quién no en la [página Ámbito de](#dial-scope) marcado).</span><span class="sxs-lookup"><span data-stu-id="bf413-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="bf413-173">Los usuarios que quiera que estén disponibles para marcado por extensión deben tener una extensión especificada como parte de [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) uno de los siguientes atributos de teléfono definidos en Active Directory o Azure Active Directory (vea Agregar usuarios individualmente o en bloque para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="bf413-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="bf413-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="bf413-174">OfficePhone</span></span>
- <span data-ttu-id="bf413-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="bf413-175">HomePhone</span></span>
- <span data-ttu-id="bf413-176">Móvil/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="bf413-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="bf413-177">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="bf413-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="bf413-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="bf413-178">OtherTelephone</span></span>

<span data-ttu-id="bf413-179">El formato necesario para introducir la extensión en el campo de número de teléfono de usuario es:</span><span class="sxs-lookup"><span data-stu-id="bf413-179">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="bf413-180">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="bf413-180">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="bf413-181">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="bf413-181">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="bf413-182">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="bf413-182">*x\<extension>*</span></span>

- <span data-ttu-id="bf413-183">Ejemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="bf413-183">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="bf413-184">Ejemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="bf413-184">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="bf413-185">Ejemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="bf413-185">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="bf413-186">Puede establecer la extensión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com/) o en el [Centro de administración de Azure Active Directory.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="bf413-186">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="bf413-187">Los cambios pueden tardar hasta 12 horas en estar disponibles para los operadores automáticos y las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf413-187">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="bf413-188">Si desea usar las  características Marcado  por nombre y Marcado por extensión, puede asignar una tecla de marcado al operador automático principal para que llegue a un operador automático habilitado para Marcado por **nombre.**</span><span class="sxs-lookup"><span data-stu-id="bf413-188">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="bf413-189">Dentro de ese operador automático, puede asignar la tecla 1 (que no tiene letras asociadas) para alcanzar el operador automático **de** Marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="bf413-189">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="bf413-190">Una vez que haya seleccionado una opción **de búsqueda de** directorio, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="bf413-190">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="bf413-191">Flujo de llamadas para horas no laborales</span><span class="sxs-lookup"><span data-stu-id="bf413-191">Call flow for after hours</span></span>

![Captura de pantalla de la configuración de días y horas fuera del horario laboral](media/auto-attendant-business-hours.png)

<span data-ttu-id="bf413-193">El horario laboral se puede establecer para cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="bf413-193">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="bf413-194">Si no se establecen los horarios laborales, todos los días y todas las horas del día se considerarán laborables, ya que se establece una programación las 24 horas.</span><span class="sxs-lookup"><span data-stu-id="bf413-194">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="bf413-195">El horario laboral se puede establecer con saltos en el tiempo durante el día y todas las horas que no se establecen como horas de trabajo se tienen en cuenta fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="bf413-195">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="bf413-196">Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para después del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="bf413-196">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="bf413-197">Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas no laborales para los operadores automáticos con números de teléfono directos.</span><span class="sxs-lookup"><span data-stu-id="bf413-197">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="bf413-198">Si desea enrutamiento de llamada independiente para los autores de llamadas fuera del horario laboral, especifique su horario laboral para cada día.</span><span class="sxs-lookup"><span data-stu-id="bf413-198">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="bf413-199">Haga **clic en Agregar nueva** hora para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar una hora de almuerzo.</span><span class="sxs-lookup"><span data-stu-id="bf413-199">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="bf413-200">Una vez que haya especificado su horario laboral, elija las opciones de enrutamiento de llamada para horas adicionales.</span><span class="sxs-lookup"><span data-stu-id="bf413-200">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="bf413-201">Están disponibles las mismas opciones que para el enrutamiento de llamadas en horario laboral que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bf413-201">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="bf413-202">Haga **clic en** Siguiente cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="bf413-202">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="bf413-203">Flujos de llamadas durante los días festivos</span><span class="sxs-lookup"><span data-stu-id="bf413-203">Call flows during holidays</span></span>

![Captura de pantalla de la configuración de saludos navideñas y navideñas](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="bf413-205">El operador automático puede tener un flujo de llamadas para cada día festivo [que haya configurado.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bf413-205">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="bf413-206">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="bf413-206">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="bf413-207">En la página configuración de la llamada navideña, haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="bf413-207">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="bf413-208">Escriba un nombre para esta configuración navideña.</span><span class="sxs-lookup"><span data-stu-id="bf413-208">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="bf413-209">En el **menú** desplegable Vacaciones, elija las vacaciones que desea usar.</span><span class="sxs-lookup"><span data-stu-id="bf413-209">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="bf413-210">Elija el tipo de saludo que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="bf413-210">Choose the type of greeting that you want to use.</span></span>

    ![Captura de pantalla de la configuración de la acción de llamada navideña](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="bf413-212">Elija si desea desconectar **o** **redirigir** la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf413-212">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="bf413-213">Si decide redirigir, elija el destino de enrutamiento de llamada para la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf413-213">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="bf413-214">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bf413-214">Click **Save**.</span></span>

![Captura de pantalla de la configuración de días festivos con la lista de días festivos](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="bf413-216">Repita el procedimiento según sea necesario para cada día festivo adicional.</span><span class="sxs-lookup"><span data-stu-id="bf413-216">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="bf413-217">Cuando haya agregado todos los días festivos, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="bf413-217">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="bf413-218">Ámbito de marcado</span><span class="sxs-lookup"><span data-stu-id="bf413-218">Dial scope</span></span>

![Captura de pantalla del ámbito de marcado con opciones de incluir y excluir](media/auto-attendant-dial-scope.png)

<span data-ttu-id="bf413-220">El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de llamada usa marcado por nombre o marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="bf413-220">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="bf413-221">El valor predeterminado de **Todos los** usuarios en línea incluye todos los usuarios de su organización que son usuarios en línea o que están hospedados en local con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bf413-221">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="bf413-222">Puede incluir o excluir usuarios  específicos seleccionando  Grupo de usuarios personalizados en Incluir o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad. </span><span class="sxs-lookup"><span data-stu-id="bf413-222">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="bf413-223">Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcación.</span><span class="sxs-lookup"><span data-stu-id="bf413-223">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="bf413-224">(Si un usuario está en ambas listas, se excluirá del directorio).</span><span class="sxs-lookup"><span data-stu-id="bf413-224">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="bf413-225">Los nombres de los nuevos usuarios pueden tardar hasta 36 horas en aparecer en el directorio.</span><span class="sxs-lookup"><span data-stu-id="bf413-225">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="bf413-226">Cuando haya terminado de configurar el ámbito de marcado, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="bf413-226">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="bf413-227">Cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="bf413-227">Resource accounts</span></span>

<span data-ttu-id="bf413-228">Todos los operadores automáticos deben tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="bf413-228">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="bf413-229">Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recurso que tenga un número de servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="bf413-229">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="bf413-230">Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="bf413-230">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Captura de pantalla del panel Agregar cuentas de la cuenta de recursos](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="bf413-232">Para agregar una cuenta de recurso, haga clic **en Agregar cuenta** y busque la cuenta que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="bf413-232">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="bf413-233">Haga **clic en** Agregar y, a continuación, en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="bf413-233">Click **Add**, and then click **Add**.</span></span>

![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recurso con el número de servicio asignado](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="bf413-235">Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="bf413-235">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="bf413-236">Esto completa la configuración del operador automático.</span><span class="sxs-lookup"><span data-stu-id="bf413-236">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="bf413-237">Transferencias de números de teléfono externos : detalles técnicos</span><span class="sxs-lookup"><span data-stu-id="bf413-237">External phone number transfers - technical details</span></span>

<span data-ttu-id="bf413-238">Consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que los operadores automáticos transfieran llamadas externamente.</span><span class="sxs-lookup"><span data-stu-id="bf413-238">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="bf413-239">Además:</span><span class="sxs-lookup"><span data-stu-id="bf413-239">In addition:</span></span>

- <span data-ttu-id="bf413-240">Para una cuenta de recurso con un número [de plan](calling-plans-for-office-365.md) de llamadas, el número de teléfono de transferencia externa debe introducirse en formato E.164 (+[código de país][código de área][número de teléfono]).</span><span class="sxs-lookup"><span data-stu-id="bf413-240">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="bf413-241">Para una cuenta de recurso con un número de enrutamiento directo, el formato de número de teléfono de transferencia externa depende de la configuración del controlador de borde de sesión [(SBC).](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="bf413-241">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="bf413-242">El número de teléfono saliente que se muestra se determina de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bf413-242">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="bf413-243">Para los números del plan de llamadas, se muestra el número de teléfono del autor de la llamada original.</span><span class="sxs-lookup"><span data-stu-id="bf413-243">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="bf413-244">Para los números de enrutamiento directo, el número enviado se basa en la configuración de la identidad ip (PAI) en el SBC, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="bf413-244">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="bf413-245">Si se establece en Deshabilitada, se muestra el número de teléfono del autor de la llamada original.</span><span class="sxs-lookup"><span data-stu-id="bf413-245">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="bf413-246">Esta es la configuración predeterminada y recomendada.</span><span class="sxs-lookup"><span data-stu-id="bf413-246">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="bf413-247">Si se establece en Habilitado, se muestra el número de teléfono de la cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="bf413-247">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="bf413-248">En un entorno híbrido de Skype Empresarial, para transferir una llamada de operador automático a la RTC, cree un nuevo usuario local con el reenvío de llamadas establecido en el número de RTC.</span><span class="sxs-lookup"><span data-stu-id="bf413-248">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="bf413-249">El usuario debe estar habilitado para Telefonía IP empresarial y tener asignada una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="bf413-249">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="bf413-250">Para obtener más información, consulte [Transferencia de llamadas del operador automático a RTC.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="bf413-250">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="bf413-251">Crear un operador automático con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf413-251">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="bf413-252">También puede usar PowerShell para crear y configurar operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="bf413-252">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="bf413-253">Estos son los cmdlets que necesita para administrar un operador automático:</span><span class="sxs-lookup"><span data-stu-id="bf413-253">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="bf413-254">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bf413-254">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="bf413-255">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bf413-255">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="bf413-256">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bf413-256">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="bf413-257">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="bf413-257">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="bf413-258">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bf413-258">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="bf413-259">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="bf413-259">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="bf413-260">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="bf413-260">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="bf413-261">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="bf413-261">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="bf413-262">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="bf413-262">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="bf413-263">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="bf413-263">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="bf413-264">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="bf413-264">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="bf413-265">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="bf413-265">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="bf413-266">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="bf413-266">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="bf413-267">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="bf413-267">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="bf413-268">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="bf413-268">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="bf413-269">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="bf413-269">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="bf413-270">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="bf413-270">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="bf413-271">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bf413-271">Related topics</span></span>

[<span data-ttu-id="bf413-272">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bf413-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="bf413-273">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="bf413-273">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="bf413-274">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="bf413-274">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="bf413-275">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bf413-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

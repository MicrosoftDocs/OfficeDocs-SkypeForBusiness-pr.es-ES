---
title: Configurar un operador automático en la nube
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Aprenda a configurar y probar los operadores automáticos de la nube para Microsoft Teams.
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375714"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="cea1e-103">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="cea1e-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="cea1e-104">Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para obtener acceso al Departamento adecuado, a la cola de llamadas, a la persona o al operador.</span><span class="sxs-lookup"><span data-stu-id="cea1e-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="cea1e-105">Puede crear un operador automático para su organización mediante el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cea1e-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="cea1e-106">Para crear un nuevo operador automático, vaya a **voz** en el navegación izquierdo y, después, seleccione >  **operadores automáticos**,**Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="cea1e-107">Si desea obtener más información sobre los operadores automáticos, vea [¿Qué son los operadores automáticos de la nube?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="cea1e-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="cea1e-108">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="cea1e-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="cea1e-109">Paso 1: introducción</span><span class="sxs-lookup"><span data-stu-id="cea1e-109">Step 1 — Get started</span></span>

- <span data-ttu-id="cea1e-110">Es necesario un operador automático para tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="cea1e-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="cea1e-111">Consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) para obtener información sobre las cuentas de recursos y todas las licencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="cea1e-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="cea1e-112">Para redirigir las llamadas a un operador o una opción de menú que sea un usuario en línea con una licencia de **sistema telefónico** , tendrá que habilitarlos para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="cea1e-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="cea1e-113">Consulte [asignar licencias de Skype empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="cea1e-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="cea1e-114">También puede usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cea1e-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="cea1e-115">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="cea1e-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="cea1e-116">Paso 2: crear un nuevo operador automático</span><span class="sxs-lookup"><span data-stu-id="cea1e-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cea1e-117">Cada operador automático debe tener una [cuenta de recursos](manage-resource-accounts.md)asociada.</span><span class="sxs-lookup"><span data-stu-id="cea1e-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="cea1e-118">Debe crear primero la cuenta de recursos y, a continuación, asociarla al operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cea1e-119">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cea1e-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="cea1e-120">En el **centro de administración de Microsoft Teams**, haga clic en**operadores automáticos**de **voz** > y, a continuación, haga clic en **+ nuevo**:</span><span class="sxs-lookup"><span data-stu-id="cea1e-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="cea1e-121">Página de información general</span><span class="sxs-lookup"><span data-stu-id="cea1e-121">General info page</span></span>

![Captura de pantalla de la página mi operador automático](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="cea1e-124">**Nombre** Escriba un nombre descriptivo para mostrar para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="cea1e-125">El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos.</span><span class="sxs-lookup"><span data-stu-id="cea1e-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="cea1e-126">Aparece en la columna **nombre** de la ficha **operadores automáticos** .</span><span class="sxs-lookup"><span data-stu-id="cea1e-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="cea1e-128"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="cea1e-128"></span></span>

<span data-ttu-id="cea1e-129">**Cuenta de recursos** Haga clic en este botón para seleccionar una o más cuentas de recursos para conectarse al nuevo operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-129">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="cea1e-130">Es necesario que todos los operadores automáticos tengan una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="cea1e-130">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="cea1e-131">Una cuenta de recursos puede tener un número de teléfono asociado a la cuenta, pero un número de teléfono no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cea1e-131">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="cea1e-132">Un operador automático de nivel superior suele tener una cuenta de recursos con un número de teléfono asignado, pero el operador automático anidado (usado como un menú de nivel 2 al que se conecta el operador automático de primer nivel) podría no tener asignado un número de teléfono a su cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="cea1e-132">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

<span data-ttu-id="cea1e-133">![Icono del número 3, que hace referencia a una llamada en la](media/sfbcallout3.png)
 <a name="timezone"> </a> captura de pantalla anterior</span><span class="sxs-lookup"><span data-stu-id="cea1e-133">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png)
<a name="timezone"> </a></span></span>

<span data-ttu-id="cea1e-134">**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización.</span><span class="sxs-lookup"><span data-stu-id="cea1e-134">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="cea1e-135">Cada operador automático puede tener una zona horaria diferente y el horario de oficina establecido para el operador automático se establece en función de la zona horaria que seleccione aquí.</span><span class="sxs-lookup"><span data-stu-id="cea1e-135">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

<span data-ttu-id="cea1e-137"><a name="language"> </a></span><span class="sxs-lookup"><span data-stu-id="cea1e-137"></span></span>

<span data-ttu-id="cea1e-138">**Idioma** Seleccione el idioma que desea usar para su operador automático en cualquiera de los idiomas disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="cea1e-138">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="cea1e-139">El idioma que establezca aquí es el idioma que usa el operador automático para interactuar con personas que llaman a este operador automático y todas las solicitudes del sistema se reproducen en este idioma.</span><span class="sxs-lookup"><span data-stu-id="cea1e-139">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![Icono del número 5, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout5.png)

<span data-ttu-id="cea1e-141"><a name="operator"> </a></span><span class="sxs-lookup"><span data-stu-id="cea1e-141"></span></span>

<span data-ttu-id="cea1e-142">**Operador** Esto es opcional, pero puede configurar la opción de **operador** para permitir que los autores de llamadas interrumpan los menús y hablen con una persona.</span><span class="sxs-lookup"><span data-stu-id="cea1e-142">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="cea1e-143">La tecla 0 está asignada al operador de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cea1e-143">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="cea1e-144">Si establece un operador, también tendrá que indicar a los usuarios que llamen sobre la opción en las **Opciones del menú Editar** en la página **Administración de llamadas de horario laboral** .</span><span class="sxs-lookup"><span data-stu-id="cea1e-144">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="cea1e-145">Si estableces un operador en tu operador automático, deberás escribir el texto del mensaje correspondiente en el cuadro de la **persona que llamarás** o cambiaremos el archivo de audio para incluir esta opción.</span><span class="sxs-lookup"><span data-stu-id="cea1e-145">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="cea1e-146">Por ejemplo, "Para hablar con el operador, pulse cero."</span><span class="sxs-lookup"><span data-stu-id="cea1e-146">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="cea1e-147">Tiene varias formas de configurar el operador:</span><span class="sxs-lookup"><span data-stu-id="cea1e-147">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="cea1e-148">**Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="cea1e-148">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="cea1e-149">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea1e-149">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="cea1e-150">**Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="cea1e-150">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="cea1e-151">Puedes configurarlo para que la persona que llama se envíe al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-151">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="cea1e-152">Para ello, seleccione **una persona de su empresa** y configure las llamadas de esta persona para que se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-152">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Icono del número 6, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout6.png)

<span data-ttu-id="cea1e-154">**Habilitar las entradas de voz** El reconocimiento de voz está disponible si esta opción está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cea1e-154">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="cea1e-155">Las personas que llaman pueden usar la entrada de voz en el [idioma que haya establecido](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cea1e-155">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="cea1e-156">Si solo quiere permitir que los usuarios usen el teclado del teléfono, puede deshabilitar el reconocimiento de voz si lo establece en desactivado.</span><span class="sxs-lookup"><span data-stu-id="cea1e-156">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="cea1e-157">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-157">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="cea1e-158">Página de horario comercial</span><span class="sxs-lookup"><span data-stu-id="cea1e-158">Business hours page</span></span>

<span data-ttu-id="cea1e-159">De forma predeterminada, el horario laboral se establece en 9:00 am a 5:00 PM, de lunes a viernes.</span><span class="sxs-lookup"><span data-stu-id="cea1e-159">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="cea1e-160">Todas las horas que no se incluyen en el horario comercial se consideran horas de oficina.</span><span class="sxs-lookup"><span data-stu-id="cea1e-160">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="cea1e-161">Puede hacer clic en **seleccionar 24/7** para hacer todas las horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cea1e-161">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="cea1e-162">A menos que seleccione la opción **seleccionar 24/7** , se usará la página de **configuración de llamada de poshorario** para configurar las reglas de administración de llamadas para el operador automático después del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="cea1e-162">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![Captura de pantalla de la página de horario comercial](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="cea1e-165">De forma predeterminada, el horario laboral se establece de lunes a viernes, 9:00 a.m.-5:00 p.m.</span><span class="sxs-lookup"><span data-stu-id="cea1e-165">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="cea1e-166">Seleccione **borrar todas las horas** para anular la selección de todas las horas de la programación.</span><span class="sxs-lookup"><span data-stu-id="cea1e-166">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="cea1e-167">Cuando selecciona **Restablecer valores predeterminados**, el horario laboral se restablece a lunes a viernes, 9:00 a.m.-5:00 p.m.</span><span class="sxs-lookup"><span data-stu-id="cea1e-167">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="cea1e-169">Para cambiar el horario de oficina, resalte las horas laborales que desea establecer en el calendario.</span><span class="sxs-lookup"><span data-stu-id="cea1e-169">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="cea1e-170">El calendario le permite seleccionar el horario laboral en intervalos de 30 minutos y las horas laborales que seleccione aquí se basan en la zona horaria que estableció en la página de **información general** .</span><span class="sxs-lookup"><span data-stu-id="cea1e-170">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="cea1e-171">Para configurar un descanso (almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario.</span><span class="sxs-lookup"><span data-stu-id="cea1e-171">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="cea1e-172">Puede establecer varios descansos dentro del horario comercial.</span><span class="sxs-lookup"><span data-stu-id="cea1e-172">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="cea1e-173">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-173">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="cea1e-174">Configuración de llamadas a horario laboral</span><span class="sxs-lookup"><span data-stu-id="cea1e-174">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="cea1e-175">Si usa una programación de horario laboral personalizada, también tendrá que configurar la mano de la llamada para después del horario comercial mediante la página de **Administración de llamadas de poshorario** , que le dará las mismas opciones que la **configuración de llamadas a horario laboral**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-175">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="cea1e-176">Puede configurar los saludos, los avisos y los menús que los usuarios escuchan al llamar al número de teléfono vinculado al operador automático de su organización durante el horario laboral.</span><span class="sxs-lookup"><span data-stu-id="cea1e-176">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="cea1e-177">![Captura de pantalla de la página](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![de tratamiento de llamadas de horario comercial captura de pantalla de la sección acciones de la página de administración de llamadas en horario comercial](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="cea1e-177">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="cea1e-179"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="cea1e-179"></span></span>

<span data-ttu-id="cea1e-180">**Saludo** Un saludo de horario laboral es opcional y puede configurarse como **sin saludo**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-180">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="cea1e-181">En este caso, el autor de la llamada no escuchará un mensaje o saludo antes de que una de las acciones que seleccione haya controlado la llamada.</span><span class="sxs-lookup"><span data-stu-id="cea1e-181">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="cea1e-182">También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-182">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="cea1e-183">**Cargar un archivo de audio** Si elige esta opción, grabe el saludo y, a continuación, cargue el archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="cea1e-183">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="cea1e-184">**Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que lea el sistema (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="cea1e-184">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="cea1e-185">Por ejemplo, puede escribir "Bienvenidos a Contoso.</span><span class="sxs-lookup"><span data-stu-id="cea1e-185">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="cea1e-186">Su llamada es muy importante para nosotros."</span><span class="sxs-lookup"><span data-stu-id="cea1e-186">Your call is important to us."</span></span> <span data-ttu-id="cea1e-187">en el cuadro **Los autores de llamadas escucharán**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-187">in the **Callers will hear** box.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="cea1e-189">Puede seleccionar lo que ocurre con las llamadas que se reciben durante el horario comercial.</span><span class="sxs-lookup"><span data-stu-id="cea1e-189">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="cea1e-190">Puede elegir entre las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cea1e-190">You can chose from the following actions:</span></span>

<span data-ttu-id="cea1e-191"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="cea1e-191"></span></span>

- <span data-ttu-id="cea1e-192">**Desconectar** Si se selecciona, la persona que llama sera desconectada tras escuchar un saludo de horario comercial.</span><span class="sxs-lookup"><span data-stu-id="cea1e-192">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="cea1e-193">**Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:</span><span class="sxs-lookup"><span data-stu-id="cea1e-193">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="cea1e-194">**Persona en la empresa** con una licencia de **sistema telefónico** habilitada para telefonía IP empresarial o planes de llamadas asignados en Office 365.</span><span class="sxs-lookup"><span data-stu-id="cea1e-194">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="cea1e-195">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="cea1e-195">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="cea1e-196">Para ello, seleccione **persona en la empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-196">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="cea1e-197">Una **persona en la empresa** puede ser un usuario en línea o un usuario local que use Skype empresarial Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea1e-197">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="cea1e-198">Otro **operador automático**</span><span class="sxs-lookup"><span data-stu-id="cea1e-198">Another **Auto attendant**</span></span>

   <span data-ttu-id="cea1e-199">Puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contengan un submenú.</span><span class="sxs-lookup"><span data-stu-id="cea1e-199">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="cea1e-200">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="cea1e-200">These are called nested auto attendants.</span></span> <span data-ttu-id="cea1e-201">Para enviar la llamada a un operador automático anidado, seleccione **persona en la empresa** y asigne una cuenta de recurso, ya sea una cuenta que ya tenga un operador automático asociado o que vaya a asociar a un operador automático una vez que haya terminado de crear este operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-201">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="cea1e-202">**Las opciones de menú reproducir** también se pueden usar para configurar el aviso que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="cea1e-202">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout3.png)

<span data-ttu-id="cea1e-204">**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="cea1e-204">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="cea1e-205">Puede escribir el mensaje en el cuadro **establecer la navegación del menú para las personas que llaman** o grabar un archivo de audio y decir, por ejemplo: "para ventas, diga o presione o diga 1.</span><span class="sxs-lookup"><span data-stu-id="cea1e-205">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="cea1e-206">Pulse o diga 2 para Servicios.</span><span class="sxs-lookup"><span data-stu-id="cea1e-206">For Services, press or say 2.</span></span> <span data-ttu-id="cea1e-207">Pulse o diga 3 para Atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="cea1e-207">For Customer Support, press or say 3.</span></span> <span data-ttu-id="cea1e-208">Para hablar con el operador, pulse o diga 0.</span><span class="sxs-lookup"><span data-stu-id="cea1e-208">For the operator, press or say 0.</span></span> <span data-ttu-id="cea1e-209">Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir".</span><span class="sxs-lookup"><span data-stu-id="cea1e-209">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="cea1e-210">**Escribir un mensaje de bienvenida** Si ha elegido esta acción, debe introducir el texto que quiere que lea el sistema (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="cea1e-210">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="cea1e-211">**Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="cea1e-211">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

<span data-ttu-id="cea1e-213">**Configuración de opciones de menú** Las opciones de menú con botones de teclas del teclado numérico se pueden agregar o quitar.</span><span class="sxs-lookup"><span data-stu-id="cea1e-213">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="cea1e-214">Para agregar una opción de menú, presione **+ asignar una tecla de marcado**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-214">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="cea1e-215">A continuación, aparece una fila de opciones correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cea1e-215">A corresponding row of options will appear below.</span></span> <span data-ttu-id="cea1e-216">Para eliminar una opción de menú, simplemente haga clic a la izquierda de la tecla correspondiente en el control del teclado y haga clic en el icono eliminar de arriba.</span><span class="sxs-lookup"><span data-stu-id="cea1e-216">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="cea1e-217">Se quitará la fila de asignación de teclas.</span><span class="sxs-lookup"><span data-stu-id="cea1e-217">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="cea1e-218">Tendrá que actualizar el mensaje de texto o volver a grabar el audio por separado al agregar opciones de eliminación, ya que no se realizará automáticamente en la solicitud de menú existente.</span><span class="sxs-lookup"><span data-stu-id="cea1e-218">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="cea1e-219">Cualquier opción del menú se puede Agregar y quitar en cualquier orden, y las asignaciones de teclas no tienen que ser continuas.</span><span class="sxs-lookup"><span data-stu-id="cea1e-219">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="cea1e-220">Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a las opciones, mientras que la clave 2 no se usa.</span><span class="sxs-lookup"><span data-stu-id="cea1e-220">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="cea1e-221">Las teclas \* (repetir) y \# (atrás) están reservadas por el sistema y no se pueden reasignar.</span><span class="sxs-lookup"><span data-stu-id="cea1e-221">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="cea1e-222">Si el reconocimiento de voz está habilitado, presionar \* se corresponde con "repetir" y # se corresponde con los comandos de voz "atrás".</span><span class="sxs-lookup"><span data-stu-id="cea1e-222">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="cea1e-223">Para configurar las opciones de menú, después de seleccionar las teclas de marcado, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="cea1e-223">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="cea1e-224">Escriba el **comando de voz** de la opción.</span><span class="sxs-lookup"><span data-stu-id="cea1e-224">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="cea1e-225">Puede tener hasta 64 caracteres y puede contener varias palabras, como "servicio al cliente" o "operaciones y motivos".</span><span class="sxs-lookup"><span data-stu-id="cea1e-225">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="cea1e-226">Si está habilitado el reconocimiento de voz, automáticamente se reconocerá el nombre y la persona que llama podrá, o bien presionar 3, decir "tres" o decir "servicio de asistencia al cliente" para seleccionar la opción asignada a la tecla 3.</span><span class="sxs-lookup"><span data-stu-id="cea1e-226">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="cea1e-227">Seleccione el lugar donde se enviará la llamada si se presiona la tecla correspondiente o se selecciona la opción con reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-227">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="cea1e-228">La llamada se puede enviar al:</span><span class="sxs-lookup"><span data-stu-id="cea1e-228">The call can be sent to:</span></span>

  - <span data-ttu-id="cea1e-229">**Operador** Si el operador ya está configurado, se asigna automáticamente a la tecla 0, pero también se puede eliminar o volverse a asignar a una tecla diferente.</span><span class="sxs-lookup"><span data-stu-id="cea1e-229">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="cea1e-230">Si el operador no está establecido para alguna tecla, entonces el comando de voz "Operador" se deshabilitará también.</span><span class="sxs-lookup"><span data-stu-id="cea1e-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="cea1e-231">**Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a un plan de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="cea1e-231">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="cea1e-232">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="cea1e-232">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="cea1e-233">Para ello, seleccione **una persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-233">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="cea1e-234">**La persona de su empresa** puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea1e-234">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>

  - <span data-ttu-id="cea1e-235">Otro **operador automático**</span><span class="sxs-lookup"><span data-stu-id="cea1e-235">Another **Auto attendant**</span></span>

       <span data-ttu-id="cea1e-236">Puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contengan un submenú.</span><span class="sxs-lookup"><span data-stu-id="cea1e-236">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="cea1e-237">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="cea1e-237">These are called nested auto attendants.</span></span> <span data-ttu-id="cea1e-238">Para enviar la llamada a un operador automático anidado, seleccione **persona en la empresa** y asigne una cuenta de recurso, ya sea una cuenta que ya tenga un operador automático asociado o que vaya a asociar a un operador automático una vez que haya terminado de crear este operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-238">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - <span data-ttu-id="cea1e-239">**Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="cea1e-239">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icono del número 5, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout5.png)

<span data-ttu-id="cea1e-241">**Marcado por nombre** Si elige esta opción, los usuarios que llamen para buscar personas de su organización podrán usar la búsqueda en el directorio.</span><span class="sxs-lookup"><span data-stu-id="cea1e-241">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="cea1e-242">Puede seleccionar qué personas se mostrarán como disponibles o no disponibles para el marcado por nombre mediante la configuración de esas opciones en la página **Ámbito de marcado**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-242">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="cea1e-243">Cualquier usuario en línea con una licencia de **sistema telefónico** o cualquier usuario local que use Skype empresarial Server o Lync Server 2013 puede encontrarse con el marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="cea1e-243">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="cea1e-244">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-244">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="cea1e-245">Configuración de llamadas navideñas</span><span class="sxs-lookup"><span data-stu-id="cea1e-245">Holiday call settings</span></span>

<span data-ttu-id="cea1e-246"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="cea1e-246"></span></span>

<span data-ttu-id="cea1e-247">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-247">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="cea1e-248">Puede ir a la pantalla a lo **ancho** > de la organización**días festivos** para crear días no laborables o puede crearlos como parte de la creación de un nuevo controlador de llamadas.</span><span class="sxs-lookup"><span data-stu-id="cea1e-248">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Captura de pantalla de la página de configuración de llamadas de vacaciones](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="cea1e-251">Si ya ha creado otros operadores automáticos, es posible que vea la opción que puede usar o modificar lo que necesita en esta lista.</span><span class="sxs-lookup"><span data-stu-id="cea1e-251">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="cea1e-252">De lo contrario, tendrás que crear un nuevo controlador de llamadas.</span><span class="sxs-lookup"><span data-stu-id="cea1e-252">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="cea1e-253">Para agregar un nuevo controlador de llamadas, haz clic en el **controlador de llamadas + nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-253">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Captura de pantalla que muestra cómo agregar un nuevo controlador de llamadas](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="cea1e-256">En la nueva ventana, escriba un nombre para el nuevo controlador de llamadas en la parte superior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="cea1e-256">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="cea1e-258">Si el nombre de tu día no laborable ya existe en la lista desplegable de **días festivos** , puedes usarlo.</span><span class="sxs-lookup"><span data-stu-id="cea1e-258">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="cea1e-259">Si el nombre de la festividad que necesita aún no existe, seleccione **crear nuevo día festivo** en la lista desplegable y asigne un nombre y una fecha para el nuevo día festivo en la nueva pantalla que aparece.</span><span class="sxs-lookup"><span data-stu-id="cea1e-259">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="cea1e-260">Haz clic en **Guardar** cuando esté listo.</span><span class="sxs-lookup"><span data-stu-id="cea1e-260">Click on **Save** when ready.</span></span>

<span data-ttu-id="cea1e-261">Los nombres de días festivos pueden constar de hasta 64 caracteres y deben ser únicos para el mismo operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-261">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="cea1e-262">Por ejemplo, no puede tener dos días festivos denominados "Navidad" en el mismo operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-262">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout3.png)

<span data-ttu-id="cea1e-264">**Saludo** El saludo es opcional y puede configurarse como **sin saludo**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-264">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="cea1e-265">En este caso, el autor de la llamada no escuchará ningún mensaje o saludo antes de que la llamada se gestione mediante una de las opciones que seleccione.</span><span class="sxs-lookup"><span data-stu-id="cea1e-265">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="cea1e-266">También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-266">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="cea1e-267">**Sin saludo** No se reproducirá ningún saludo cuando las personas llamen al número de teléfono del operador automático.</span><span class="sxs-lookup"><span data-stu-id="cea1e-267">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="cea1e-268">**Cargar un archivo de audio** Si elige esta opción, grabe el saludo de las vacaciones y, a continuación, cargue el archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="cea1e-268">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="cea1e-269">**Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que lea el sistema (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="cea1e-269">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="cea1e-270">Por ejemplo, puede escribir "¡Feliz año nuevo!</span><span class="sxs-lookup"><span data-stu-id="cea1e-270">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="cea1e-271">Nuestras oficinas están cerradas en este momento".</span><span class="sxs-lookup"><span data-stu-id="cea1e-271">Our offices are currently closed."</span></span> <span data-ttu-id="cea1e-272">en el cuadro **Escriba un mensaje de saludo** .</span><span class="sxs-lookup"><span data-stu-id="cea1e-272">in the **Type a greeting message** box.</span></span>

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

<span data-ttu-id="cea1e-274">**Acciones** Puede seleccionar qué sucede con las llamadas que llegan durante este día festivo.</span><span class="sxs-lookup"><span data-stu-id="cea1e-274">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="cea1e-275">Puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cea1e-275">You can chose from the following options:</span></span>

- <span data-ttu-id="cea1e-276">**Desconectar** La persona que llama será desconectada tras escuchar el saludo de días festivos.</span><span class="sxs-lookup"><span data-stu-id="cea1e-276">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="cea1e-277">**Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:</span><span class="sxs-lookup"><span data-stu-id="cea1e-277">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="cea1e-278">Una **persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="cea1e-278">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="cea1e-279">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="cea1e-279">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="cea1e-280">Para ello, seleccione **una persona de su empresa**y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-280">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="cea1e-281">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea1e-281">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="cea1e-282">**Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="cea1e-282">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="cea1e-283">De forma predeterminada, todas las llamadas que llegan durante un período de días festivos se establecen en desconectar después de saludo (si hay alguno), por lo que debe especificar un redireccionamiento si se desea obtener un comportamiento diferente.</span><span class="sxs-lookup"><span data-stu-id="cea1e-283">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a><span data-ttu-id="cea1e-284">Página Seleccionar ámbito de marcado</span><span class="sxs-lookup"><span data-stu-id="cea1e-284">Select dial scope page</span></span>

<span data-ttu-id="cea1e-285">En esta página, puede configurar los usuarios de su organización que aparecerán en el directorio y que estarán disponibles para marcar por su nombre cuando sea una persona que llame a su organización.</span><span class="sxs-lookup"><span data-stu-id="cea1e-285">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Captura de pantalla que muestra la página ámbito de marcado](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="cea1e-287">![Icono del número 1, que hace referencia a una llamada en la](media/sfbcallout1.png) captura de pantalla anterior con la opción **incluir** , tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="cea1e-287">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="cea1e-288">**Total de usuarios en línea**: esta opción le permite incluir a todas las personas de su organización en la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="cea1e-288">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="cea1e-289">Se mostrarán todos los usuarios conectados que tengan una licencia de **sistema telefónico** , así como los usuarios locales que utilicen Skype empresarial Server o Lync Server 2013 que tengan planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="cea1e-289">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="cea1e-290">**Grupo de usuarios personalizado** Si usa esta opción, puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad que se haya creado en su organización y las personas que se han agregado a este grupo de Office 365, una lista de distribución o un grupo de seguridad que sean **usuarios conectados con un Licencia de sistema telefónico** o se ha hospedado de forma local con Skype empresarial server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea1e-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="cea1e-291">Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cea1e-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<span data-ttu-id="cea1e-293">Con la opción **excluir** tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="cea1e-293">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="cea1e-294">**Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="cea1e-294">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="cea1e-295">**Grupo de usuarios personalizado** Si usa esta opción, puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad que se haya creado en su organización, y todas las personas agregadas a este grupo de Office 365, lista de distribución o grupos de seguridad se excluirán de la búsqueda en directorio.</span><span class="sxs-lookup"><span data-stu-id="cea1e-295">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="cea1e-296">Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cea1e-296">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="cea1e-297">Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio cuando alguien usa el marcado por nombre con reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="cea1e-297">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="cea1e-298">Después de especificar todos los campos obligatorios y configurar los menús y las opciones de administración de llamadas, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-298">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="cea1e-299">Editar y probar los operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="cea1e-299">Editing and testing auto attendants</span></span>

<span data-ttu-id="cea1e-300">Después de guardar un operador automático, este se mostrará en la página **Operadores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-300">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="cea1e-301">Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, como el nombre, el número de teléfono, el idioma y el estado.</span><span class="sxs-lookup"><span data-stu-id="cea1e-301">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="cea1e-302">Si desea realizar cambios en un operador automático, seleccione el operador automático y, a continuación, en el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cea1e-302">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="cea1e-303">También puede hacer una llamada de prueba a su operador automático con el botón **probar** del panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="cea1e-303">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="cea1e-304">Cmdlets para operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="cea1e-304">Auto attendant cmdlets</span></span>

<span data-ttu-id="cea1e-305">También puede usar Windows PowerShell para crear y configurar operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="cea1e-305">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="cea1e-306">Estos son los cmdlets que necesita para administrar un operador automático:</span><span class="sxs-lookup"><span data-stu-id="cea1e-306">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="cea1e-307">Nuevo: CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="cea1e-307">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="cea1e-308">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="cea1e-308">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="cea1e-309">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="cea1e-309">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="cea1e-310">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="cea1e-310">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="cea1e-311">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="cea1e-311">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="cea1e-312">Nuevo: CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="cea1e-312">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="cea1e-313">Nuevo: CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="cea1e-313">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="cea1e-314">Nuevo: CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="cea1e-314">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="cea1e-315">Exportar-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="cea1e-315">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="cea1e-316">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="cea1e-316">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="cea1e-317">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="cea1e-317">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="cea1e-318">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="cea1e-318">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="cea1e-319">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="cea1e-319">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="cea1e-320">Nuevo: CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="cea1e-320">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="cea1e-321">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="cea1e-321">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="cea1e-322">Importar-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="cea1e-322">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="cea1e-323">Nuevo: CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="cea1e-323">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="cea1e-324">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cea1e-324">More about Windows PowerShell</span></span>

- <span data-ttu-id="cea1e-325">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="cea1e-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="cea1e-326">Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams con un único punto de administración que puede simplificar su trabajo diario, cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="cea1e-326">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="cea1e-327">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="cea1e-327">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="cea1e-328">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="cea1e-328">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="cea1e-329">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="cea1e-329">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="cea1e-330">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="cea1e-330">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="cea1e-331">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="cea1e-331">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="cea1e-332">Administrar Office 365 con Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cea1e-332">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="cea1e-333">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="cea1e-333">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="cea1e-334">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cea1e-334">Related topics</span></span>

[<span data-ttu-id="cea1e-335">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="cea1e-335">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="cea1e-336">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="cea1e-336">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="cea1e-337">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="cea1e-337">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="cea1e-338">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="cea1e-338">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="cea1e-339">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="cea1e-339">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="cea1e-340">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="cea1e-340">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  

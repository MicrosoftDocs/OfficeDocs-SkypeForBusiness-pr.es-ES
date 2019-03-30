---
title: Configurar un operador automático para el Sistema telefónico
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre cómo configurar y probar a automáticos de sistema telefónico (PBX en la nube) para administración de la organización eficaz de las llamadas.
ms.openlocfilehash: 8bf33e911e11ab7561cc09e0cd18f4cfaf314d98
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013098"
---
# <a name="set-up-a-phone-system-auto-attendant"></a><span data-ttu-id="2d816-103">Configurar un operador automático para el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="2d816-103">Set up a Phone System auto attendant</span></span>

<span data-ttu-id="2d816-104">Operadores automáticos permiten a las personas que llaman a su organización y navegue a un sistema de menús a obtienen al departamento de derecho, cola, persona o el operador de llamada.</span><span class="sxs-lookup"><span data-stu-id="2d816-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="2d816-105">Puede crear a un operador automático para la organización mediante el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2d816-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="2d816-106">Para crear un nuevo operador automático de, vaya a **voz** en el panel de navegación izquierdo y, a continuación, seleccione **operadores automáticos** > **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2d816-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="2d816-107">Si desea obtener más información sobre los operadores automáticos, consulte [¿Qué son los operadores automáticos de sistema telefónico?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="2d816-107">If you want to learn more about auto attendants, see [What are Phone System auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="2d816-108">En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="2d816-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>



## <a name="step-1---get-started"></a><span data-ttu-id="2d816-109">Paso 1: Introducción</span><span class="sxs-lookup"><span data-stu-id="2d816-109">Step 1 - Get started</span></span>

- <span data-ttu-id="2d816-110">Un operador automático es necesario tener una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="2d816-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="2d816-111">Para obtener información detallada sobre las cuentas de recursos, vea [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="2d816-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="2d816-112">Si tiene previsto asignar un número de enrutamiento directa, debe adquirir y asignar las siguientes licencias para las cuentas de recursos \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico\).</span><span class="sxs-lookup"><span data-stu-id="2d816-112">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="2d816-113">Si se asigna un número de servicio de Microsoft en su lugar, debe adquirir y asignar las licencias siguientes a la cuenta del recurso \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico y un Plan de llamar a\).</span><span class="sxs-lookup"><span data-stu-id="2d816-113">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="2d816-114">Microsoft está trabajando en un modelo de licencias adecuado para aplicaciones como automáticos en la nube y las colas de llamadas, para ahora tiene que usar el modelo de licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="2d816-114">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!CAUTION]
> <span data-ttu-id="2d816-115">Para obtener y usar los números de teléfono gratuitos, necesita configurar créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="2d816-115">To get and use toll-free phone numbers, you need to set up Communications Credits.</span></span> <span data-ttu-id="2d816-116">Para ello, consulte [¿Qué son los créditos de comunicaciones?](what-are-communications-credits.md) y [Configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="2d816-116">To do this see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

> [!TIP]
> <span data-ttu-id="2d816-117">Para redirigir las llamadas a un operador o una opción de menú que es un usuario con una licencia de **Sistema telefónico** en línea, debe habilitarlos para Enterprise Voice o asignar al llamar a los planes en Office 365 a ellos.</span><span class="sxs-lookup"><span data-stu-id="2d816-117">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them.</span></span> <span data-ttu-id="2d816-118">Vea [Asignar Skype para licencias de negocio](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2d816-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="2d816-119">También puede usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d816-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="2d816-120">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="2d816-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="2d816-121">Paso 2: crear un operador automático nuevo</span><span class="sxs-lookup"><span data-stu-id="2d816-121">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d816-122">Cada cola de llamada es necesario tener asociado a una [cuenta del recurso](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2d816-122">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="2d816-123">Debe crear la cuenta del recurso en primer lugar, a continuación, puede asociar para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2d816-124">Desde el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2d816-124">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2d816-125">En el **Centro de administración de equipos de Microsoft**, haga clic en **voz** > **operadores automáticos**, a continuación, haga clic en **+ nuevo**:</span><span class="sxs-lookup"><span data-stu-id="2d816-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="2d816-126">Página de información general</span><span class="sxs-lookup"><span data-stu-id="2d816-126">General info page</span></span>

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="2d816-129">**Nombre** Escriba un nombre para mostrar descriptivo para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-129">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="2d816-130">El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos.</span><span class="sxs-lookup"><span data-stu-id="2d816-130">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="2d816-131">Se enumerará en la columna **Nombre** en la ficha **Operadores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="2d816-131">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="2d816-133">**Cuenta de recurso** Haga clic en este botón para seleccionar una o más cuentas de recursos para conectarse a su nuevo operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-133">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="2d816-134">Todos los operadores automáticos deben tener una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="2d816-134">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="2d816-135">Una cuenta de recurso puede tener un número de teléfono asociado a la cuenta, pero es posible que no.</span><span class="sxs-lookup"><span data-stu-id="2d816-135">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="2d816-136">Un operador automático de nivel superior casi sin duda sería tendría una cuenta de recursos con un número de teléfono asignado, pero un operador automático secundario (usado como un menú de nivel 2 que se conecta el primer operador automático de nivel a) fácilmente no podría tener un número de teléfono que se asigna a su cuenta del recurso.</span><span class="sxs-lookup"><span data-stu-id="2d816-136">A top-level auto attendant would almost certainly would have a resource account with an assigned phone number, but a secondary auto attendant (used as a level 2 menu that the first level auto attendant connects to) might easily not have a phone number assigned to its resource account.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="2d816-p108">**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente, y el horario laboral establecido para el operador automático se ajustará en función de la zona horaria seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2d816-p108">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="2d816-141">**Idioma** Seleccione el idioma que desea usar para el operador automático desde cualquiera de los idiomas disponibles que aparecen.</span><span class="sxs-lookup"><span data-stu-id="2d816-141">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="2d816-142">El idioma que establezca aquí es el idioma que usará el operador automático para interactuar con las personas que llaman a este operador automático y todos los mensajes del sistema se reproducirá en este idioma.</span><span class="sxs-lookup"><span data-stu-id="2d816-142">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![Número 5](media/sfbcallout5.png)

<span data-ttu-id="2d816-144">**Operador**: este ajuste es opcional y no es necesario activarlo para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-144">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="2d816-145">Sin embargo, puede establecer la opción de **operador** para las personas que llaman en que puedan interrumpir la ejecución de los menús para hablar con una persona que les ayudará a.</span><span class="sxs-lookup"><span data-stu-id="2d816-145">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="2d816-146">Automáticamente se asigna la tecla 0 a Operador.</span><span class="sxs-lookup"><span data-stu-id="2d816-146">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="2d816-147">Si configurar esta opción, también tendrá que indicar a las personas que llamar en que esto es una opción disponible en el **menú Opciones de edición** en la página de **control de llamadas de horario comercial** .</span><span class="sxs-lookup"><span data-stu-id="2d816-147">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="2d816-148">Si establece un operador en el operador automático, debe escribir el texto del mensaje correspondiente en el cuadro **escucharán los autores de llamadas** o cambiar su archivo de audio para incluir esta opción.</span><span class="sxs-lookup"><span data-stu-id="2d816-148">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="2d816-149">Por ejemplo, "Para hablar con el operador, pulse cero."</span><span class="sxs-lookup"><span data-stu-id="2d816-149">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="2d816-150">Puede elegir entre las siguientes opciones para designar un operador:</span><span class="sxs-lookup"><span data-stu-id="2d816-150">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="2d816-151">**Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d816-151">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="2d816-152">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d816-152">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="2d816-153">Una **cola de llamadas** que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="2d816-153">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="2d816-154">Puede establecer que el autor de la llamada se derive a un correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-154">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="2d816-155">Para ello, seleccione la **persona de la compañía** y establecer las llamadas de esta persona se transfieran directamente al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-155">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Número 6](media/sfbcallout6.png)

<span data-ttu-id="2d816-157">**Habilitar las entradas de voz** Reconocimiento de voz está disponible si está seleccionada esta opción.</span><span class="sxs-lookup"><span data-stu-id="2d816-157">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="2d816-158">Las personas que llaman en pueden usar la entrada de voz en el [idioma que establece](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2d816-158">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="2d816-159">Puede deshabilitar el reconocimiento de voz si se establece en off si desea que sólo permiten a los usuarios utilizar su teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="2d816-159">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="2d816-160">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2d816-160">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="2d816-161">Página de horario comercial</span><span class="sxs-lookup"><span data-stu-id="2d816-161">Business hours page</span></span>

<span data-ttu-id="2d816-162">De forma predeterminada, se establecen horario en 9 a.m. a 5 p.m., del lunes al viernes.</span><span class="sxs-lookup"><span data-stu-id="2d816-162">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="2d816-163">Todas las horas que no se incluyan en el horario laboral se consideran no laborales.</span><span class="sxs-lookup"><span data-stu-id="2d816-163">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="2d816-164">Puede hacer clic en **Seleccionar las 24 horas 7** para hacer que todas las horas de horario.</span><span class="sxs-lookup"><span data-stu-id="2d816-164">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="2d816-165">A menos que seleccione la opción **Seleccionar las 24 horas 7** , se usará la página **después de configuración de llamadas de horas** para configurar la administración para después del horario laboral para el operador automático de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2d816-165">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="2d816-168">De forma predeterminada, se establecen horario en el lunes al viernes, de 9:00 am - 5:00 pm.</span><span class="sxs-lookup"><span data-stu-id="2d816-168">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="2d816-169">Seleccione **Borrar todas las horas de** opción para anular la selección de todas las horas de horas de la programación.</span><span class="sxs-lookup"><span data-stu-id="2d816-169">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="2d816-170">Al seleccionar **Restablecer a predeterminado**, horario se restablecerá al lunes al viernes, de 9:00 am - 5:00 pm.</span><span class="sxs-lookup"><span data-stu-id="2d816-170">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="2d816-172">Para cambiar el horario comercial, resalte el horario comercial que desea establecer con el calendario.</span><span class="sxs-lookup"><span data-stu-id="2d816-172">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="2d816-173">El calendario le permite seleccionar el horario comercial en intervalos de 30 minutos, y el horario que seleccione aquí se basará en la zona horaria que haya configurado en la página **Información general**.</span><span class="sxs-lookup"><span data-stu-id="2d816-173">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="2d816-174">Para configurar un descanso (almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario.</span><span class="sxs-lookup"><span data-stu-id="2d816-174">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="2d816-175">Puede establecer varios descansos dentro del horario comercial.</span><span class="sxs-lookup"><span data-stu-id="2d816-175">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="2d816-176">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2d816-176">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="2d816-177">Configuración de llamadas de horario comercial</span><span class="sxs-lookup"><span data-stu-id="2d816-177">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="2d816-178">Si utiliza una programación de horario comercial, también tendrá que configurar una llamada de tener que proporcionar para después del horario de uso de la página **después de control de llamadas de horas** , que le proporcionará las mismas opciones que la **configuración de llamadas de horario comercial**.</span><span class="sxs-lookup"><span data-stu-id="2d816-178">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="2d816-179">Puede configurar el saludo, mensajes de voz y los menús que las personas que escuchará llamada al número de teléfono de operador automático de la organización durante el horario laboral.</span><span class="sxs-lookup"><span data-stu-id="2d816-179">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="2d816-180">![Control de llamadas de horario comercial. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Horario continuado de control de llamadas.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="2d816-180">![Business hours call handling.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Business hours call handling continued.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="2d816-182">**Saludo** Un saludo de horario comercial es opcional y se puede establecer en **ningún saludo**.</span><span class="sxs-lookup"><span data-stu-id="2d816-182">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="2d816-183">En este caso, el autor de la llamada no escuchará ningún mensaje o un saludo antes de la llamada se controla mediante una de las acciones que seleccione.</span><span class="sxs-lookup"><span data-stu-id="2d816-183">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="2d816-184">También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-184">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="2d816-185">**No hay saludo** Ningún saludo se reproducirá cuando llama personas el número de teléfono de operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-185">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="2d816-186">**Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="2d816-186">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="2d816-187">**Escriba un mensaje de saludo** Si elige esta opción, escriba el texto que desea que el sistema para leer (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="2d816-187">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="2d816-188">Por ejemplo, puede escribir "Bienvenidos a Contoso.</span><span class="sxs-lookup"><span data-stu-id="2d816-188">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="2d816-189">Su llamada es muy importante para nosotros."</span><span class="sxs-lookup"><span data-stu-id="2d816-189">Your call is important to us."</span></span> <span data-ttu-id="2d816-190">en el cuadro **Los autores de llamadas escucharán**.</span><span class="sxs-lookup"><span data-stu-id="2d816-190">in the **Callers will hear** box.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="2d816-192">Puede seleccionar lo que ocurre con las llamadas que se reciben durante el horario comercial.</span><span class="sxs-lookup"><span data-stu-id="2d816-192">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="2d816-193">Puede elegir entre las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2d816-193">You can chose from the following actions:</span></span>

- <span data-ttu-id="2d816-194">**Desconectar** Si se selecciona, la persona que llama sera desconectada tras escuchar un saludo de horario comercial.</span><span class="sxs-lookup"><span data-stu-id="2d816-194">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="2d816-195">**Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:</span><span class="sxs-lookup"><span data-stu-id="2d816-195">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="2d816-196">**Persona de empresa** con una licencia de **Sistema de teléfono** que está habilitada para Enterprise Voice o asignada al llamar a los planes en Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d816-196">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="2d816-197">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="2d816-197">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="2d816-198">Para ello, seleccione la **persona en la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-198">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="2d816-199">**Persona de empresa** puede ser un usuario en línea o un usuario hospedado local mediante Skype para Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d816-199">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="2d816-200">Otro **operador automático**</span><span class="sxs-lookup"><span data-stu-id="2d816-200">Another **Auto attendant**</span></span>

   <span data-ttu-id="2d816-201">Puede usar a un operador automático existente para crear un segundo nivel de opciones de menú que contiene un submenú.</span><span class="sxs-lookup"><span data-stu-id="2d816-201">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="2d816-202">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="2d816-202">These are called nested auto attendants.</span></span> <span data-ttu-id="2d816-203">Para enviar la llamada a un operador automático anidadas, seleccione la **persona en la empresa** y asignar una cuenta de recursos, uno que ya tiene un operador automático asociado o uno que se va a asociar a un operador automático de una vez que haya terminado de crear este operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-203">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="2d816-204">También puede utilizarse el **menú Opciones de reproducción** para que le permite configurar un símbolo del sistema que desee que se reproduzca.</span><span class="sxs-lookup"><span data-stu-id="2d816-204">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="2d816-206">**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="2d816-206">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="2d816-207">Puede escribir el símbolo del sistema en el cuadro **establecer la navegación de menús para los autores de llamadas** o registrar un archivo de audio y diga, por ejemplo: "para ventas, diga o presione o diga 1.</span><span class="sxs-lookup"><span data-stu-id="2d816-207">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="2d816-208">Pulse o diga 2 para Servicios.</span><span class="sxs-lookup"><span data-stu-id="2d816-208">For Services, press or say 2.</span></span> <span data-ttu-id="2d816-209">Pulse o diga 3 para Atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="2d816-209">For Customer Support, press or say 3.</span></span> <span data-ttu-id="2d816-210">Para hablar con el operador, pulse o diga 0.</span><span class="sxs-lookup"><span data-stu-id="2d816-210">For the operator, press or say 0.</span></span> <span data-ttu-id="2d816-211">Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir".</span><span class="sxs-lookup"><span data-stu-id="2d816-211">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="2d816-212">**Escriba un mensaje de saludo** Si opta por esto, debe escribir el texto que desea que el sistema para leer (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="2d816-212">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="2d816-213">**Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="2d816-213">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="2d816-215">**Programa de instalación de las opciones de menú** Pueden agregar o quitar opciones de menú utilizando los botones de clave en el teclado numérico.</span><span class="sxs-lookup"><span data-stu-id="2d816-215">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="2d816-216">Para agregar una opción de menú, presione **+ asignar una tecla de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="2d816-216">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="2d816-217">Una fila de opciones correspondiente aparecerá debajo.</span><span class="sxs-lookup"><span data-stu-id="2d816-217">A corresponding row of options will appear below.</span></span> <span data-ttu-id="2d816-218">Para eliminar una opción de menú, haga clic en a la izquierda de la clave correspondiente en el control del teclado y haga clic en el icono de eliminación anterior.</span><span class="sxs-lookup"><span data-stu-id="2d816-218">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="2d816-219">Se quitará la fila de asignación de teclas.</span><span class="sxs-lookup"><span data-stu-id="2d816-219">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="2d816-220">Debe actualizar menú mensajes de texto o volver a registrar el audio por separado cuando se agrega a la eliminación de opciones porque no se realiza automáticamente para el símbolo del sistema de menú existente.</span><span class="sxs-lookup"><span data-stu-id="2d816-220">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="2d816-221">Cualquier opción de menú se puede agregar y quitar en cualquier orden, y las asignaciones de teclas no tienen que ser continuo.</span><span class="sxs-lookup"><span data-stu-id="2d816-221">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="2d816-222">Es posible, por ejemplo, para crear un menú con las teclas de 0, 1 y 3 que se asignan a opciones, mientras no se usa la tecla 2.</span><span class="sxs-lookup"><span data-stu-id="2d816-222">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="2d816-223">Las claves de \* (las veces) y \# (atrás) están reservados por el sistema y no se pueden reasignar.</span><span class="sxs-lookup"><span data-stu-id="2d816-223">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="2d816-224">Si está habilitado el reconocimiento de voz, al presionar \* corresponderá con "Repetir" y # se corresponden con los comandos de voz "Atrás".</span><span class="sxs-lookup"><span data-stu-id="2d816-224">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="2d816-225">Para configurar las opciones de menú, después de seleccionar las claves de acceso telefónico, necesitará:</span><span class="sxs-lookup"><span data-stu-id="2d816-225">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="2d816-226">Escriba el **comando de voz** de la opción.</span><span class="sxs-lookup"><span data-stu-id="2d816-226">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="2d816-227">Esto puede tener hasta 64 caracteres y puede contener varias palabras como "Servicio de atención al cliente" o "operaciones y motivos".</span><span class="sxs-lookup"><span data-stu-id="2d816-227">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="2d816-228">Si está habilitado el reconocimiento de voz, automáticamente se reconocerá el nombre y la persona que llama podrá, o bien presionar 3, decir "tres" o decir "servicio de asistencia al cliente" para seleccionar la opción asignada a la tecla 3.</span><span class="sxs-lookup"><span data-stu-id="2d816-228">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="2d816-229">Seleccione donde se enviarán si se presiona la tecla correspondiente, o se selecciona la opción utilizando el reconocimiento de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2d816-229">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="2d816-230">La llamada se puede enviar al:</span><span class="sxs-lookup"><span data-stu-id="2d816-230">The call can be sent to:</span></span>

  - <span data-ttu-id="2d816-231">**Operador** Si el operador ya está configurado, se asigna automáticamente a la tecla 0, pero también se puede eliminar o volverse a asignar a una tecla diferente.</span><span class="sxs-lookup"><span data-stu-id="2d816-231">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="2d816-232">Si el operador no está establecido para alguna tecla, entonces el comando de voz "Operador" se deshabilitará también.</span><span class="sxs-lookup"><span data-stu-id="2d816-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="2d816-233">**Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a un plan de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d816-233">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="2d816-234">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="2d816-234">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="2d816-235">Para ello, seleccione la **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-235">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="2d816-236">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d816-236">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="2d816-237">Lync Server 2010 no se admite.</span><span class="sxs-lookup"><span data-stu-id="2d816-237">Lync Server 2010 is not supported.</span></span>
    - <span data-ttu-id="2d816-238">Otro **operador automático**</span><span class="sxs-lookup"><span data-stu-id="2d816-238">Another **Auto attendant**</span></span>

       <span data-ttu-id="2d816-239">Puede usar a un operador automático existente para crear un segundo nivel de opciones de menú que contiene un submenú.</span><span class="sxs-lookup"><span data-stu-id="2d816-239">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="2d816-240">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="2d816-240">These are called nested auto attendants.</span></span> <span data-ttu-id="2d816-241">Para enviar la llamada a un operador automático anidadas, seleccione la **persona en la empresa** y asignar una cuenta de recursos, uno que ya tiene un operador automático asociado o uno que se va a asociar a un operador automático de una vez que haya terminado de crear este operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-241">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="2d816-242">El **Horario comercial** de operadores automáticos anidados (o de segundo nivel) también se utilizará, lo que incluye las llamadas enviadas desde otros operadores automáticos que se hayan configurado.</span><span class="sxs-lookup"><span data-stu-id="2d816-242">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Número 5](media/sfbcallout5.png)

<span data-ttu-id="2d816-244">**Marcado por nombre** Si elige esta opción, esto permitirá que a las personas que llaman a buscar personas en su organización con búsqueda en el directorio.</span><span class="sxs-lookup"><span data-stu-id="2d816-244">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="2d816-245">Puede seleccionar qué personas se mostrarán como disponibles o no disponibles para el marcado por nombre mediante la configuración de esas opciones en la página **Ámbito de marcado**.</span><span class="sxs-lookup"><span data-stu-id="2d816-245">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="2d816-246">Cualquier usuario en línea con una licencia de **sistema telefónico** o cualquier usuario hospedado localmente utilizando Skype for Business Server 2015 o Lync Server 2013, puede encontrarse con el marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="2d816-246">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.</span></span>

> [!WARNING]
> <span data-ttu-id="2d816-247">Los usuarios alojados en implementaciones locales con Lync 2010 **no se pueden alcanzar** con marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="2d816-247">Users hosted on-premises using Lync 2010 **can't be reached** with Dial by Name.</span></span>

* * *

<span data-ttu-id="2d816-248">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2d816-248">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="2d816-249">Configuración de la llamada de días festivos</span><span class="sxs-lookup"><span data-stu-id="2d816-249">Holiday call settings</span></span>

<span data-ttu-id="2d816-250">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-250">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="2d816-251">Puede ir el la pantalla de la **configuración de toda la organización** > **días festivos** para crear los días festivos, o bien puede crearlos como parte de la creación de un nuevo controlador de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2d816-251">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Configuración de días festivos en el operador automático](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="2d816-254">Si ya ha creado a otros operadores automáticos, es posible que vea una opción que puede usar o editar en lo que necesita en esta lista.</span><span class="sxs-lookup"><span data-stu-id="2d816-254">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="2d816-255">Si no es así, debe crear un nuevo controlador de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2d816-255">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="2d816-256">Para agregar un nuevo controlador de llamada, haga clic en **+ nuevo controlador de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="2d816-256">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Configurar los días festivos de operador automático de continuado](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="2d816-259">En la ventana nueva, escriba un nombre para el nuevo controlador de llamadas en la parte superior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="2d816-259">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="2d816-261">Si el nombre de las vacaciones ya existe en la lista desplegable de **días festivos** , puede usarlo.</span><span class="sxs-lookup"><span data-stu-id="2d816-261">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="2d816-262">Si el nombre del día festivo que necesita no existe ya, seleccione **Crear nuevo de días festivos** en la lista desplegable y asignar un nombre y una fecha para el día festivo nuevo en la nueva pantalla que aparece.</span><span class="sxs-lookup"><span data-stu-id="2d816-262">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="2d816-263">Haga clic en **Guardar** cuando esté listo.</span><span class="sxs-lookup"><span data-stu-id="2d816-263">Click on **Save** when ready.</span></span>

<span data-ttu-id="2d816-264">Los nombres de días festivos pueden constar de hasta 64 caracteres y deben ser únicos para el mismo operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-264">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="2d816-265">Por ejemplo, no puede tener dos días festivos denominados "Navidad" en el mismo operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-265">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="2d816-267">**Saludo** El saludo es opcional y se puede establecer en **ningún saludo**.</span><span class="sxs-lookup"><span data-stu-id="2d816-267">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="2d816-268">En este caso, el autor de la llamada no escuchará ningún mensaje o saludo antes de que la llamada se gestione mediante una de las opciones que seleccione.</span><span class="sxs-lookup"><span data-stu-id="2d816-268">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="2d816-269">También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-269">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="2d816-270">**No hay saludo** Ningún saludo se reproducirá cuando llama personas el número de teléfono de operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-270">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="2d816-271">**Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo de días festivos y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma)</span><span class="sxs-lookup"><span data-stu-id="2d816-271">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="2d816-272">**Escriba un mensaje de saludo** Si elige esta opción, escriba el texto que desea que el sistema para leer (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="2d816-272">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="2d816-273">Por ejemplo, puede escribir "¡Feliz año nuevo!</span><span class="sxs-lookup"><span data-stu-id="2d816-273">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="2d816-274">Nuestras oficinas están cerradas en este momento".</span><span class="sxs-lookup"><span data-stu-id="2d816-274">Our offices are currently closed."</span></span> <span data-ttu-id="2d816-275">en el cuadro **Escriba un mensaje de saludo** .</span><span class="sxs-lookup"><span data-stu-id="2d816-275">in the **Type a greeting message** box.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="2d816-277">**Acciones** Puede seleccionar lo que ocurre con las llamadas que se reciben durante este día festivo.</span><span class="sxs-lookup"><span data-stu-id="2d816-277">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="2d816-278">Puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2d816-278">You can chose from the following options:</span></span>

- <span data-ttu-id="2d816-279">**Desconectar** La persona que llama será desconectada tras escuchar el saludo de días festivos.</span><span class="sxs-lookup"><span data-stu-id="2d816-279">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="2d816-280">**Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:</span><span class="sxs-lookup"><span data-stu-id="2d816-280">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="2d816-281">Una **persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d816-281">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="2d816-282">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="2d816-282">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="2d816-283">Para ello, seleccione la **persona de la empresa**y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-283">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="2d816-284">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d816-284">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="2d816-285">Lync Server 2010 no se admite.</span><span class="sxs-lookup"><span data-stu-id="2d816-285">Lync Server 2010 is not supported.</span></span>

  - <span data-ttu-id="2d816-286">Una **cola de llamadas** para transferir la llamada a una cola existente de llamada que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="2d816-286">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="2d816-287">Otro **operador automático**, para crear un segundo nivel de opciones de menú que contiene un submenú.</span><span class="sxs-lookup"><span data-stu-id="2d816-287">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="2d816-288">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="2d816-288">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="2d816-289">De forma predeterminada, todas las llamadas que llegan durante un período de días festivos se establecen en desconectar después de saludo (si hay alguno), por lo que debe especificar un redireccionamiento si se desea obtener un comportamiento diferente.</span><span class="sxs-lookup"><span data-stu-id="2d816-289">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="2d816-290">Página Seleccionar ámbito de marcado</span><span class="sxs-lookup"><span data-stu-id="2d816-290">Select dial scope page</span></span>

<span data-ttu-id="2d816-291">En esta página, puede configurar qué usuarios de la organización estará enumerados en su directorio y están disponibles para marcado por nombre cuando una persona que llama la organización.</span><span class="sxs-lookup"><span data-stu-id="2d816-291">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="2d816-293">![Número 1](media/sfbcallout1.png) con la opción **incluir** , tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="2d816-293">![Number 1](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="2d816-294">**Total de usuarios en línea**: esta opción le permite incluir a todas las personas de su organización en la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="2d816-294">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="2d816-295">Se enumerarán todos los usuarios en línea con una licencia de **sistema telefónico**, así como los usuarios hospedados localmente utilizando Skype for Business Server 2015 o Lync Server 2013 que tengan planes de llamada en Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d816-295">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="2d816-296">**Grupo de usuario personalizadas** Si utiliza esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que se ha creado en la organización y las personas que agregan a este grupo de Office 365, lista de distribución o grupo de seguridad que están bien **usuarios en línea con un Licencia de sistema de teléfono** u hospedado local mediante Skype para Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d816-296">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="2d816-297">Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2d816-297">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

  > [!Caution]
  > <span data-ttu-id="2d816-298">Usuarios locales de las implementaciones de Lync Server 2010 no se muestran cuando alguien busca en el directorio mediante marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="2d816-298">On-premises users from deployments of Lync Server 2010 won't be listed when someone searches the directory using Dial by Name.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="2d816-300">Uso de la opción **Excluir** , tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="2d816-300">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="2d816-301">**Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="2d816-301">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="2d816-302">**Grupo de usuario personalizadas** Si utiliza esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que se ha creado en su organización, y todas las personas agregaron a este grupo de Office 365, lista de distribución o grupos de seguridad se excluirá de búsqueda en el directorio.</span><span class="sxs-lookup"><span data-stu-id="2d816-302">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="2d816-303">Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2d816-303">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

  > [!Caution]
  > <span data-ttu-id="2d816-304">Usuarios locales de las implementaciones de Lync Server 2010 no se muestran cuando alguien busca en el directorio mediante marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="2d816-304">On-premises users from deployments of Lync Server 2010 won't be listed when someone searches the directory using Dial by Name.</span></span>

> [!NOTE]
> <span data-ttu-id="2d816-305">Puede tardar hasta 36 horas para un nuevo usuario para que su nombre aparezca en el directorio cuando alguien utiliza marcado por nombre con el reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="2d816-305">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="2d816-306">Después de escribir todos los campos necesarios y configurar los menús y las opciones de administración de llamadas, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2d816-306">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="2d816-307">Edición y la prueba de operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="2d816-307">Editing and testing auto attendants</span></span>

<span data-ttu-id="2d816-308">Después de guardar un operador automático, este se mostrará en la página **Operadores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="2d816-308">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="2d816-309">Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, incluidos el nombre, número de teléfono, idioma y estado.</span><span class="sxs-lookup"><span data-stu-id="2d816-309">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="2d816-310">Si desea realizar cambios en un operador automático, seleccione al operador automático y, a continuación, en el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2d816-310">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="2d816-311">Puede colocar una llamada de prueba a su operador automático también rápidamente mediante el botón **de prueba** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="2d816-311">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="want-to-know-more"></a><span data-ttu-id="2d816-312">¿Desea obtener más información?</span><span class="sxs-lookup"><span data-stu-id="2d816-312">Want to know more?</span></span>

<span data-ttu-id="2d816-313">También puede usar Windows PowerShell para crear y configurar operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="2d816-313">You can also use Windows PowerShell to create and set up auto attendants.</span></span>

### <a name="auto-attendant-cmdlets"></a><span data-ttu-id="2d816-314">Cmdlets para operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="2d816-314">Auto attendant cmdlets</span></span>

<span data-ttu-id="2d816-315">Estos son los cmdlets que necesita para administrar un operador automático.</span><span class="sxs-lookup"><span data-stu-id="2d816-315">Here are the cmdlets that you need to manage an auto attendant.</span></span>

 
- [<span data-ttu-id="2d816-316">Nueva CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2d816-316">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="2d816-317">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2d816-317">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="2d816-318">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2d816-318">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="2d816-319">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="2d816-319">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="2d816-320">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2d816-320">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="2d816-321">Nueva CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="2d816-321">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [<span data-ttu-id="2d816-322">Nueva CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="2d816-322">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [<span data-ttu-id="2d816-323">Nueva CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="2d816-323">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [<span data-ttu-id="2d816-324">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="2d816-324">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [<span data-ttu-id="2d816-325">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="2d816-325">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [<span data-ttu-id="2d816-326">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="2d816-326">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [<span data-ttu-id="2d816-327">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="2d816-327">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [<span data-ttu-id="2d816-328">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="2d816-328">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps) 
- [<span data-ttu-id="2d816-329">Nueva CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="2d816-329">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps) 
- [<span data-ttu-id="2d816-330">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="2d816-330">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps) 
- [<span data-ttu-id="2d816-331">CsAutoAttendantHolidays de importación</span><span class="sxs-lookup"><span data-stu-id="2d816-331">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="2d816-332">Nueva CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="2d816-332">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a><span data-ttu-id="2d816-333">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d816-333">More about Windows PowerShell</span></span>

- <span data-ttu-id="2d816-334">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="2d816-334">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2d816-335">Con Windows PowerShell, puede administrar Office 365 y Teams Microsoft mediante un único punto de administración que puede simplificar su trabajo diario, cuando haya varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="2d816-335">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="2d816-336">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="2d816-336">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="2d816-337">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2d816-337">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="2d816-338">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="2d816-338">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="2d816-p147">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="2d816-p147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="2d816-341">Administración de Office 365 con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="2d816-341">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="2d816-342">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2d816-342">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="2d816-343">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2d816-343">Related topics</span></span>

[<span data-ttu-id="2d816-344">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="2d816-344">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="2d816-345">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="2d816-345">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="2d816-346">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="2d816-346">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="2d816-347">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2d816-347">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="2d816-348">¿Qué son los operadores automáticos del Sistema telefónico?</span><span class="sxs-lookup"><span data-stu-id="2d816-348">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="2d816-349">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="2d816-349">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  

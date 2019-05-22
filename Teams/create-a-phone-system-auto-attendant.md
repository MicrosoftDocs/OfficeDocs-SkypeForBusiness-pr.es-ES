---
title: Configurar un operador automático en la nube
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: makolomi
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
description: Aprenda a configurar y probar operadores automáticos en la nube para una administración eficaz de las llamadas de su organización.
ms.openlocfilehash: d4889f7a33306c970b73651bcaafe9f3e2c8009b
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "34330927"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="204c6-103">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="204c6-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="204c6-104">Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para obtener acceso al Departamento adecuado, a la cola de llamadas, a la persona o al operador.</span><span class="sxs-lookup"><span data-stu-id="204c6-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="204c6-105">Puede crear un operador automático para su organización mediante el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="204c6-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="204c6-106">Para crear un nuevo operador automático, vaya a **voz** en el navegación izquierdo y, después, seleccione **operadores** > automáticos,**Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="204c6-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="204c6-107">Si desea obtener más información sobre los operadores automáticos, vea [¿Qué son los operadores automáticos de la nube?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="204c6-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="204c6-108">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="204c6-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>



## <a name="step-1---get-started"></a><span data-ttu-id="204c6-109">Paso 1: introducción</span><span class="sxs-lookup"><span data-stu-id="204c6-109">Step 1 - Get started</span></span>

- <span data-ttu-id="204c6-110">Es necesario un operador automático para tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="204c6-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="204c6-111">Para obtener más información sobre las cuentas de recursos, consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="204c6-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="204c6-112">Si planea asignar un número de enrutamiento directo, debe adquirir y asignar las siguientes licencias a sus cuentas \(de recursos Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico.\)</span><span class="sxs-lookup"><span data-stu-id="204c6-112">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="204c6-113">Si está asignando un número de servicio de Microsoft, debe adquirir y asignar las siguientes licencias a su cuenta \(de recursos Office 365 Enterprise E1, E3 o E5, con el complemento del sistema telefónico y un plan\)de llamadas.</span><span class="sxs-lookup"><span data-stu-id="204c6-113">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="204c6-114">Microsoft está trabajando en un modelo de licencias sin costo para aplicaciones como los operadores automáticos de la nube y las colas de llamadas, por ahora necesita usar el modelo de licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="204c6-114">Microsoft is working on a cost-free licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!CAUTION]
> <span data-ttu-id="204c6-115">Para obtener y usar los números de teléfono gratuitos, necesita configurar créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="204c6-115">To get and use toll-free phone numbers, you need to set up Communications Credits.</span></span> <span data-ttu-id="204c6-116">Para ello, consulte [¿Qué son los créditos de comunicaciones?](what-are-communications-credits.md) y [Configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="204c6-116">To do this see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

> [!TIP]
> <span data-ttu-id="204c6-117">Para redirigir las llamadas a un operador o una opción de menú que sea un usuario en línea con una licencia de **sistema telefónico** , tendrá que habilitarlos para telefonía IP empresarial o asignar planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="204c6-117">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them.</span></span> <span data-ttu-id="204c6-118">Consulte [asignar licencias de Skype empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="204c6-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="204c6-119">También puede usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="204c6-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="204c6-120">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="204c6-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="204c6-121">Paso 2: crear un operador automático nuevo</span><span class="sxs-lookup"><span data-stu-id="204c6-121">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="204c6-122">Cada operador automático debe tener una [cuenta de recursos](manage-resource-accounts.md)asociada.</span><span class="sxs-lookup"><span data-stu-id="204c6-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="204c6-123">Debe crear primero la cuenta de recursos y, a continuación, asociarla al operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="204c6-124">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="204c6-124">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="204c6-125">En el **centro de administración de Microsoft Teams**, haga clic en**operadores automáticos**de **voz** > y, a continuación, haga clic en **+ nuevo**:</span><span class="sxs-lookup"><span data-stu-id="204c6-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="204c6-126">Página de información general</span><span class="sxs-lookup"><span data-stu-id="204c6-126">General info page</span></span>

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="204c6-129">**Nombre** Escriba un nombre descriptivo para mostrar para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-129">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="204c6-130">El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos.</span><span class="sxs-lookup"><span data-stu-id="204c6-130">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="204c6-131">Se enumerará en la columna **Nombre** en la ficha **Operadores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="204c6-131">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="204c6-133">**Cuenta de recursos** Haga clic en este botón para seleccionar una o más cuentas de recursos para conectarse al nuevo operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-133">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="204c6-134">Es necesario que todos los operadores automáticos tengan una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="204c6-134">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="204c6-135">Una cuenta de recursos puede tener un número de teléfono asociado a la cuenta, pero es posible que no lo tenga.</span><span class="sxs-lookup"><span data-stu-id="204c6-135">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="204c6-136">Un operador automático de nivel superior normalmente tiene una cuenta de recursos con un número de teléfono asignado, pero el operador automático anidado (usado como un menú de nivel 2 en el que se conecta el primer operador automático de nivel) podría no tener un número de teléfono asignado a su cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="204c6-136">A top-level auto attendant usually have a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="204c6-p108">**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente, y el horario laboral establecido para el operador automático se ajustará en función de la zona horaria seleccionada.</span><span class="sxs-lookup"><span data-stu-id="204c6-p108">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="204c6-141">**Idioma** Seleccione el idioma que desea usar para su operador automático en cualquiera de los idiomas disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="204c6-141">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="204c6-142">El idioma que estableces aquí es el idioma que el operador automático usará para interactuar con las personas que llaman a este operador automático y todas las solicitudes del sistema se reproducirán en este idioma.</span><span class="sxs-lookup"><span data-stu-id="204c6-142">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![Número 5](media/sfbcallout5.png)

<span data-ttu-id="204c6-144">**Operador**: este ajuste es opcional y no es necesario activarlo para el operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-144">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="204c6-145">Sin embargo, puede establecer la opción de **operador** para las personas que llaman para poder salir de los menús para hablar con una persona para ayudarle.</span><span class="sxs-lookup"><span data-stu-id="204c6-145">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="204c6-146">Automáticamente se asigna la tecla 0 a Operador.</span><span class="sxs-lookup"><span data-stu-id="204c6-146">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="204c6-147">Si establece esta opción, también tendrá que indicar a las personas que llaman que esta es una opción disponible en las opciones del **menú Editar** en la página **Administración de llamadas de horario laboral** .</span><span class="sxs-lookup"><span data-stu-id="204c6-147">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="204c6-148">Si estableces un operador en tu operador automático, tendrás que escribir el texto del mensaje correspondiente en el cuadro de la **persona que llamas oirá** o cambiará el archivo de audio para incluir esta opción.</span><span class="sxs-lookup"><span data-stu-id="204c6-148">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="204c6-149">Por ejemplo, "Para hablar con el operador, pulse cero."</span><span class="sxs-lookup"><span data-stu-id="204c6-149">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="204c6-150">Puede elegir entre las siguientes opciones para designar un operador:</span><span class="sxs-lookup"><span data-stu-id="204c6-150">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="204c6-151">**Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="204c6-151">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="204c6-152">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204c6-152">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="204c6-153">Una **cola de llamadas** que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="204c6-153">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="204c6-154">Puede establecer que el autor de la llamada se derive a un correo de voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-154">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="204c6-155">Para ello, seleccione **una persona de su empresa** y configure las llamadas de esta persona para que se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-155">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Número 6](media/sfbcallout6.png)

<span data-ttu-id="204c6-157">**Habilitar las entradas de voz** El reconocimiento de voz está disponible si esta opción está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="204c6-157">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="204c6-158">Las personas que llaman pueden usar la entrada de voz en el [idioma que haya establecido](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="204c6-158">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="204c6-159">Puede deshabilitar el reconocimiento de voz si solo quiere permitir que los usuarios usen el teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="204c6-159">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="204c6-160">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="204c6-160">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="204c6-161">Página de horario comercial</span><span class="sxs-lookup"><span data-stu-id="204c6-161">Business hours page</span></span>

<span data-ttu-id="204c6-162">De forma predeterminada, el horario laboral se establece en 9:00 a 17:00, de lunes a viernes.</span><span class="sxs-lookup"><span data-stu-id="204c6-162">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="204c6-163">Todas las horas que no se incluyan en el horario laboral se consideran no laborales.</span><span class="sxs-lookup"><span data-stu-id="204c6-163">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="204c6-164">Puede hacer clic en **seleccionar 24/7** para hacer todas las horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="204c6-164">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="204c6-165">A menos que seleccione la opción **seleccionar 24/7** , se usará la página de **configuración de llamadas** de poshorario para configurar el control de llamadas para el operador automático después del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="204c6-165">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="204c6-168">De forma predeterminada, el horario laboral se establece de lunes a viernes, 9:00 a.m.-5:00 p.m.</span><span class="sxs-lookup"><span data-stu-id="204c6-168">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="204c6-169">Seleccione **borrar todas las** horas para anular la selección de todas las horas de horas en la programación.</span><span class="sxs-lookup"><span data-stu-id="204c6-169">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="204c6-170">Si selecciona **Restablecer valores**predeterminados, el horario laboral se restablecerá a lunes a viernes, 9:00 a.m.-5:00 p.m.</span><span class="sxs-lookup"><span data-stu-id="204c6-170">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="204c6-172">Para cambiar el horario comercial, resalte el horario comercial que desea establecer con el calendario.</span><span class="sxs-lookup"><span data-stu-id="204c6-172">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="204c6-173">El calendario le permite seleccionar el horario comercial en intervalos de 30 minutos, y el horario que seleccione aquí se basará en la zona horaria que haya configurado en la página **Información general**.</span><span class="sxs-lookup"><span data-stu-id="204c6-173">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="204c6-174">Para configurar un descanso (almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario.</span><span class="sxs-lookup"><span data-stu-id="204c6-174">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="204c6-175">Puede establecer varios descansos dentro del horario comercial.</span><span class="sxs-lookup"><span data-stu-id="204c6-175">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="204c6-176">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="204c6-176">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="204c6-177">Configuración de llamadas a horario laboral</span><span class="sxs-lookup"><span data-stu-id="204c6-177">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="204c6-178">Si usa una programación de horario laboral personalizada, también tendrá que configurar la mano de la llamada para después del horario comercial mediante la página de **Administración de llamadas** de poshorario, que le dará las mismas opciones que la **configuración de llamadas a horario laboral**.</span><span class="sxs-lookup"><span data-stu-id="204c6-178">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="204c6-179">Puede configurar los saludos, los avisos y los menús que escucharán las personas que llaman al operador automático de su organización durante el horario laboral.</span><span class="sxs-lookup"><span data-stu-id="204c6-179">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="204c6-180">![Administración de llamadas en horario laboral. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
La administración de llamadas en horario laboral ![continuó.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="204c6-180">![Business hours call handling.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Business hours call handling continued.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="204c6-182">**Saludo** Un saludo de horario laboral es opcional y puede configurarse como **sin saludo**.</span><span class="sxs-lookup"><span data-stu-id="204c6-182">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="204c6-183">En este caso, la persona que llama no escuchará mensaje o saludo antes de que una de las acciones que seleccione represente la llamada.</span><span class="sxs-lookup"><span data-stu-id="204c6-183">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="204c6-184">También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-184">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="204c6-185">**Sin saludo** No se reproducirá ningún saludo cuando las personas llamen al número de teléfono del operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-185">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="204c6-186">**Cargar un archivo de audio** Si elige esta opción, grabe el saludo y, a continuación, cargue el archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="204c6-186">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="204c6-187">**Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que lea el sistema (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="204c6-187">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="204c6-188">Por ejemplo, puede escribir "Bienvenidos a Contoso.</span><span class="sxs-lookup"><span data-stu-id="204c6-188">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="204c6-189">Su llamada es muy importante para nosotros."</span><span class="sxs-lookup"><span data-stu-id="204c6-189">Your call is important to us."</span></span> <span data-ttu-id="204c6-190">en el cuadro **Los autores de llamadas escucharán**.</span><span class="sxs-lookup"><span data-stu-id="204c6-190">in the **Callers will hear** box.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="204c6-192">Puede seleccionar lo que ocurre con las llamadas que se reciben durante el horario comercial.</span><span class="sxs-lookup"><span data-stu-id="204c6-192">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="204c6-193">Puede elegir entre las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="204c6-193">You can chose from the following actions:</span></span>

- <span data-ttu-id="204c6-194">**Desconectar** Si se selecciona, la persona que llama sera desconectada tras escuchar un saludo de horario comercial.</span><span class="sxs-lookup"><span data-stu-id="204c6-194">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="204c6-195">**Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:</span><span class="sxs-lookup"><span data-stu-id="204c6-195">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="204c6-196">**Persona en la empresa** con una licencia de **sistema telefónico** habilitada para telefonía IP empresarial o planes de llamadas asignados en Office 365.</span><span class="sxs-lookup"><span data-stu-id="204c6-196">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="204c6-197">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="204c6-197">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="204c6-198">Para ello, seleccione **persona en la empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-198">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="204c6-199">Una **persona en la empresa** puede ser un usuario en línea o un usuario local que use Skype empresarial Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204c6-199">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="204c6-200">Otro **operador automático**</span><span class="sxs-lookup"><span data-stu-id="204c6-200">Another **Auto attendant**</span></span>

   <span data-ttu-id="204c6-201">Puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contengan un submenú.</span><span class="sxs-lookup"><span data-stu-id="204c6-201">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="204c6-202">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="204c6-202">These are called nested auto attendants.</span></span> <span data-ttu-id="204c6-203">Para enviar la llamada a un operador automático anidado, seleccione **persona en la empresa** y asigne una cuenta de recurso, ya sea una cuenta que ya tenga un operador automático asociado o que vaya a asociar a un operador automático una vez que haya terminado de crear este operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-203">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="204c6-204">**Las opciones de menú reproducir** también se pueden usar para configurar el aviso que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="204c6-204">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="204c6-206">**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="204c6-206">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="204c6-207">Puede escribir el mensaje en el cuadro **establecer la navegación del menú para las personas que llaman** o grabar un archivo de audio y decir, por ejemplo: "para ventas, diga o presione o diga 1.</span><span class="sxs-lookup"><span data-stu-id="204c6-207">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="204c6-208">Pulse o diga 2 para Servicios.</span><span class="sxs-lookup"><span data-stu-id="204c6-208">For Services, press or say 2.</span></span> <span data-ttu-id="204c6-209">Pulse o diga 3 para Atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="204c6-209">For Customer Support, press or say 3.</span></span> <span data-ttu-id="204c6-210">Para hablar con el operador, pulse o diga 0.</span><span class="sxs-lookup"><span data-stu-id="204c6-210">For the operator, press or say 0.</span></span> <span data-ttu-id="204c6-211">Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir".</span><span class="sxs-lookup"><span data-stu-id="204c6-211">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="204c6-212">**Escribir un mensaje de bienvenida** Si ha elegido esta acción, debe introducir el texto que quiere que lea el sistema (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="204c6-212">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="204c6-213">**Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="204c6-213">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="204c6-215">**Configuración de opciones de menú** Las opciones de menú con botones de teclas del teclado numérico se pueden agregar o quitar.</span><span class="sxs-lookup"><span data-stu-id="204c6-215">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="204c6-216">Para agregar una opción de menú, presione **+ asignar una tecla de marcado**.</span><span class="sxs-lookup"><span data-stu-id="204c6-216">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="204c6-217">A continuación, aparece una fila de opciones correspondiente.</span><span class="sxs-lookup"><span data-stu-id="204c6-217">A corresponding row of options will appear below.</span></span> <span data-ttu-id="204c6-218">Para eliminar una opción de menú, simplemente haga clic a la izquierda de la tecla correspondiente en el control del teclado y haga clic en el icono eliminar de arriba.</span><span class="sxs-lookup"><span data-stu-id="204c6-218">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="204c6-219">Se quitará la fila de asignación de teclas.</span><span class="sxs-lookup"><span data-stu-id="204c6-219">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="204c6-220">Tendrá que actualizar el mensaje de texto o volver a grabar el audio por separado al agregar opciones de eliminación, ya que no se realizará automáticamente en la solicitud de menú existente.</span><span class="sxs-lookup"><span data-stu-id="204c6-220">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="204c6-221">Cualquier opción del menú se puede Agregar y quitar en cualquier orden, y las asignaciones de teclas no tienen que ser continuas.</span><span class="sxs-lookup"><span data-stu-id="204c6-221">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="204c6-222">Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a las opciones, mientras que la clave 2 no se usa.</span><span class="sxs-lookup"><span data-stu-id="204c6-222">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="204c6-223">Las teclas \* (repetir) y \# (atrás) están reservadas por el sistema y no se pueden reasignar.</span><span class="sxs-lookup"><span data-stu-id="204c6-223">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="204c6-224">Si el reconocimiento de voz está habilitado, presionar \* se corresponde con "repetir" y # se corresponde con los comandos de voz "atrás".</span><span class="sxs-lookup"><span data-stu-id="204c6-224">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="204c6-225">Para configurar las opciones de menú, después de seleccionar las teclas de marcado, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="204c6-225">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="204c6-226">Escriba el **comando de voz** de la opción.</span><span class="sxs-lookup"><span data-stu-id="204c6-226">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="204c6-227">Puede tener hasta 64 caracteres y puede contener varias palabras, como "servicio al cliente" o "operaciones y motivos".</span><span class="sxs-lookup"><span data-stu-id="204c6-227">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="204c6-228">Si está habilitado el reconocimiento de voz, automáticamente se reconocerá el nombre y la persona que llama podrá, o bien presionar 3, decir "tres" o decir "servicio de asistencia al cliente" para seleccionar la opción asignada a la tecla 3.</span><span class="sxs-lookup"><span data-stu-id="204c6-228">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="204c6-229">Seleccione el lugar donde se enviará la llamada si se presiona la tecla correspondiente o se selecciona la opción con reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-229">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="204c6-230">La llamada se puede enviar al:</span><span class="sxs-lookup"><span data-stu-id="204c6-230">The call can be sent to:</span></span>

  - <span data-ttu-id="204c6-231">**Operador** Si el operador ya está configurado, se asigna automáticamente a la tecla 0, pero también se puede eliminar o volverse a asignar a una tecla diferente.</span><span class="sxs-lookup"><span data-stu-id="204c6-231">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="204c6-232">Si el operador no está establecido para alguna tecla, entonces el comando de voz "Operador" se deshabilitará también.</span><span class="sxs-lookup"><span data-stu-id="204c6-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="204c6-233">**Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a un plan de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="204c6-233">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="204c6-234">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="204c6-234">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="204c6-235">Para ello, seleccione **una persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-235">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="204c6-236">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204c6-236">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 
    - <span data-ttu-id="204c6-237">Otro **operador automático**</span><span class="sxs-lookup"><span data-stu-id="204c6-237">Another **Auto attendant**</span></span>

       <span data-ttu-id="204c6-238">Puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contengan un submenú.</span><span class="sxs-lookup"><span data-stu-id="204c6-238">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="204c6-239">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="204c6-239">These are called nested auto attendants.</span></span> <span data-ttu-id="204c6-240">Para enviar la llamada a un operador automático anidado, seleccione **persona en la empresa** y asigne una cuenta de recurso, ya sea una cuenta que ya tenga un operador automático asociado o que vaya a asociar a un operador automático una vez que haya terminado de crear este operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-240">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="204c6-241">El **Horario comercial** de operadores automáticos anidados (o de segundo nivel) también se utilizará, lo que incluye las llamadas enviadas desde otros operadores automáticos que se hayan configurado.</span><span class="sxs-lookup"><span data-stu-id="204c6-241">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Número 5](media/sfbcallout5.png)

<span data-ttu-id="204c6-243">**Marcado por nombre** Si elige esta opción, los usuarios que llamen para buscar personas de su organización podrán usar la búsqueda en el directorio.</span><span class="sxs-lookup"><span data-stu-id="204c6-243">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="204c6-244">Puede seleccionar qué personas se mostrarán como disponibles o no disponibles para el marcado por nombre mediante la configuración de esas opciones en la página **Ámbito de marcado**.</span><span class="sxs-lookup"><span data-stu-id="204c6-244">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="204c6-245">Cualquier usuario en línea con una licencia de **sistema telefónico** o cualquier usuario hospedado localmente utilizando Skype for Business Server 2015 o Lync Server 2013, puede encontrarse con el marcado por nombre.</span><span class="sxs-lookup"><span data-stu-id="204c6-245">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.</span></span>


* * *

<span data-ttu-id="204c6-246">Cuando haya terminado con las selecciones, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="204c6-246">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="204c6-247">Configuración de llamadas navideñas</span><span class="sxs-lookup"><span data-stu-id="204c6-247">Holiday call settings</span></span>

<span data-ttu-id="204c6-248">Puede agregar un máximo de 20 días festivos programados a cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-248">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="204c6-249">Puede ir a la pantalla a lo **ancho** > de la organización**días festivos** para crear días no laborables o puede crearlos como parte de la creación de un nuevo controlador de llamadas.</span><span class="sxs-lookup"><span data-stu-id="204c6-249">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Configuración de días festivos en el operador automático](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="204c6-252">Si ya ha creado otros operadores automáticos, es posible que vea la opción que puede usar o modificar lo que necesita en esta lista.</span><span class="sxs-lookup"><span data-stu-id="204c6-252">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="204c6-253">De lo contrario, tendrás que crear un nuevo controlador de llamadas.</span><span class="sxs-lookup"><span data-stu-id="204c6-253">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="204c6-254">Para agregar un nuevo controlador de llamadas, haz clic en el **controlador de llamadas + nuevo**.</span><span class="sxs-lookup"><span data-stu-id="204c6-254">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Configurar los días no laborables en el operador automático continuó](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="204c6-257">En la nueva ventana, escriba un nombre para el nuevo controlador de llamadas en la parte superior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="204c6-257">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="204c6-259">Si el nombre de tu día no laborable ya existe en la lista desplegable de **días festivos** , puedes usarlo.</span><span class="sxs-lookup"><span data-stu-id="204c6-259">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="204c6-260">Si el nombre de la festividad que necesita aún no existe, seleccione **crear nuevo día festivo** en la lista desplegable y asigne un nombre y una fecha para el nuevo día festivo en la nueva pantalla que aparece.</span><span class="sxs-lookup"><span data-stu-id="204c6-260">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="204c6-261">Haz clic en **Guardar** cuando esté listo.</span><span class="sxs-lookup"><span data-stu-id="204c6-261">Click on **Save** when ready.</span></span>

<span data-ttu-id="204c6-262">Los nombres de días festivos pueden constar de hasta 64 caracteres y deben ser únicos para el mismo operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-262">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="204c6-263">Por ejemplo, no puede tener dos días festivos denominados "Navidad" en el mismo operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-263">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="204c6-265">**Saludo** El saludo es opcional y puede configurarse como **sin saludo**.</span><span class="sxs-lookup"><span data-stu-id="204c6-265">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="204c6-266">En este caso, el autor de la llamada no escuchará ningún mensaje o saludo antes de que la llamada se gestione mediante una de las opciones que seleccione.</span><span class="sxs-lookup"><span data-stu-id="204c6-266">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="204c6-267">También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-267">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="204c6-268">**Sin saludo** No se reproducirá ningún saludo cuando las personas llamen al número de teléfono del operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-268">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="204c6-269">**Cargar un archivo de audio** Si elige esta opción, grabe el saludo de las vacaciones y, a continuación, cargue el archivo de audio (en formato. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="204c6-269">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="204c6-270">**Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que lea el sistema (hasta 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="204c6-270">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="204c6-271">Por ejemplo, puede escribir "¡Feliz año nuevo!</span><span class="sxs-lookup"><span data-stu-id="204c6-271">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="204c6-272">Nuestras oficinas están cerradas en este momento".</span><span class="sxs-lookup"><span data-stu-id="204c6-272">Our offices are currently closed."</span></span> <span data-ttu-id="204c6-273">en el cuadro **Escriba un mensaje de saludo** .</span><span class="sxs-lookup"><span data-stu-id="204c6-273">in the **Type a greeting message** box.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="204c6-275">**Acciones** Puede seleccionar qué sucede con las llamadas que llegan durante este día festivo.</span><span class="sxs-lookup"><span data-stu-id="204c6-275">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="204c6-276">Puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="204c6-276">You can chose from the following options:</span></span>

- <span data-ttu-id="204c6-277">**Desconectar** La persona que llama será desconectada tras escuchar el saludo de días festivos.</span><span class="sxs-lookup"><span data-stu-id="204c6-277">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="204c6-278">**Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:</span><span class="sxs-lookup"><span data-stu-id="204c6-278">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="204c6-279">Una **persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="204c6-279">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="204c6-280">Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="204c6-280">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="204c6-281">Para ello, seleccione **una persona de su empresa**y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-281">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="204c6-282">La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204c6-282">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 

  - <span data-ttu-id="204c6-283">Una **cola de llamadas** para transferir la llamada a una cola de llamadas existente que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="204c6-283">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="204c6-284">Otro **operador automático**, para crear un segundo nivel de opciones de menú que contengan un submenú.</span><span class="sxs-lookup"><span data-stu-id="204c6-284">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="204c6-285">Estos se denominan a operadores automáticos anidados.</span><span class="sxs-lookup"><span data-stu-id="204c6-285">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="204c6-286">De forma predeterminada, todas las llamadas que llegan durante un período de días festivos se establecen en desconectar después de saludo (si hay alguno), por lo que debe especificar un redireccionamiento si se desea obtener un comportamiento diferente.</span><span class="sxs-lookup"><span data-stu-id="204c6-286">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="204c6-287">Página Seleccionar ámbito de marcado</span><span class="sxs-lookup"><span data-stu-id="204c6-287">Select dial scope page</span></span>

<span data-ttu-id="204c6-288">En esta página, puede configurar los usuarios de su organización que aparecerán en el directorio y que estarán disponibles para marcar por su nombre cuando sea una persona que llame a su organización.</span><span class="sxs-lookup"><span data-stu-id="204c6-288">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="204c6-290">![Número 1](media/sfbcallout1.png) con la opción **incluir** , tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="204c6-290">![Number 1](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="204c6-291">**Total de usuarios en línea**: esta opción le permite incluir a todas las personas de su organización en la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="204c6-291">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="204c6-292">Se enumerarán todos los usuarios en línea con una licencia de **sistema telefónico**, así como los usuarios hospedados localmente utilizando Skype for Business Server 2015 o Lync Server 2013 que tengan planes de llamada en Office 365.</span><span class="sxs-lookup"><span data-stu-id="204c6-292">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="204c6-293">**Grupo de usuarios personalizado** Si usa esta opción, puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad que se haya creado en su organización y las personas que se han agregado a este grupo de Office 365, una lista de distribución o un grupo de seguridad que sean **usuarios conectados con un Licencia de sistema telefónico** o se ha hospedado de forma local con Skype empresarial server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204c6-293">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="204c6-294">Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="204c6-294">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="204c6-296">Con la \*\*\*\* opción excluir tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="204c6-296">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="204c6-297">**Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios.</span><span class="sxs-lookup"><span data-stu-id="204c6-297">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="204c6-298">**Grupo de usuarios personalizado** Si usa esta opción, puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad que se haya creado en su organización, y todas las personas agregadas a este grupo de Office 365, lista de distribución o grupos de seguridad se excluirán de la búsqueda en directorio.</span><span class="sxs-lookup"><span data-stu-id="204c6-298">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="204c6-299">Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="204c6-299">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="204c6-300">Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio cuando alguien usa el marcado por nombre con reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="204c6-300">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="204c6-301">Después de especificar todos los campos obligatorios y configurar los menús y las opciones de administración de llamadas, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="204c6-301">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="204c6-302">Editar y probar los operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="204c6-302">Editing and testing auto attendants</span></span>

<span data-ttu-id="204c6-303">Después de guardar un operador automático, este se mostrará en la página **Operadores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="204c6-303">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="204c6-304">Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, como el nombre, el número de teléfono, el idioma y el estado.</span><span class="sxs-lookup"><span data-stu-id="204c6-304">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="204c6-305">Si desea realizar cambios en un operador automático, seleccione el operador automático y, a continuación, en el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="204c6-305">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="204c6-306">También puede hacer una llamada de prueba a su operador automático con el botón **probar** del panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="204c6-306">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="want-to-know-more"></a><span data-ttu-id="204c6-307">¿Desea obtener más información?</span><span class="sxs-lookup"><span data-stu-id="204c6-307">Want to know more?</span></span>

<span data-ttu-id="204c6-308">También puede usar Windows PowerShell para crear y configurar operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="204c6-308">You can also use Windows PowerShell to create and set up auto attendants.</span></span>

### <a name="auto-attendant-cmdlets"></a><span data-ttu-id="204c6-309">Cmdlets para operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="204c6-309">Auto attendant cmdlets</span></span>

<span data-ttu-id="204c6-310">Estos son los cmdlets que necesita para administrar un operador automático.</span><span class="sxs-lookup"><span data-stu-id="204c6-310">Here are the cmdlets that you need to manage an auto attendant.</span></span>

- [<span data-ttu-id="204c6-311">Nuevo: CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="204c6-311">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="204c6-312">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="204c6-312">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="204c6-313">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="204c6-313">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [<span data-ttu-id="204c6-314">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="204c6-314">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="204c6-315">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="204c6-315">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="204c6-316">Nuevo: CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="204c6-316">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [<span data-ttu-id="204c6-317">Nuevo: CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="204c6-317">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [<span data-ttu-id="204c6-318">Nuevo: CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="204c6-318">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [<span data-ttu-id="204c6-319">Exportar-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="204c6-319">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [<span data-ttu-id="204c6-320">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="204c6-320">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [<span data-ttu-id="204c6-321">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="204c6-321">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [<span data-ttu-id="204c6-322">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="204c6-322">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [<span data-ttu-id="204c6-323">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="204c6-323">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="204c6-324">Nuevo: CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="204c6-324">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="204c6-325">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="204c6-325">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="204c6-326">Importar-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="204c6-326">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="204c6-327">Nuevo: CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="204c6-327">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a><span data-ttu-id="204c6-328">Más información sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="204c6-328">More about Windows PowerShell</span></span>

- <span data-ttu-id="204c6-329">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="204c6-329">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="204c6-330">Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams con un único punto de administración que puede simplificar su trabajo diario, cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="204c6-330">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="204c6-331">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="204c6-331">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="204c6-332">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="204c6-332">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="204c6-333">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="204c6-333">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="204c6-334">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="204c6-334">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="204c6-335">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="204c6-335">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="204c6-336">Administrar Office 365 con Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="204c6-336">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="204c6-337">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="204c6-337">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="204c6-338">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="204c6-338">Related topics</span></span>

[<span data-ttu-id="204c6-339">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="204c6-339">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="204c6-340">Obtener números de teléfono de servicio</span><span class="sxs-lookup"><span data-stu-id="204c6-340">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="204c6-341">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="204c6-341">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="204c6-342">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="204c6-342">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="204c6-343">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="204c6-343">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="204c6-344">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="204c6-344">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  

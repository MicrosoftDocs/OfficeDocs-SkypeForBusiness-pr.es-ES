---
title: Asistencia de voz de Cortana en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Más información sobre cómo usar la asistencia de voz de Cortana con Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686446"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="2b8dd-103">Asistencia de voz de Cortana en Teams</span><span class="sxs-lookup"><span data-stu-id="2b8dd-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="2b8dd-104">La asistencia de voz de Cortana es compatible con las aplicaciones móviles iOS y Android de Microsoft Teams, las salas de Microsoft Teams en Windows y Microsoft Teams muestra, solo para los usuarios de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="2b8dd-105">Actualmente no está disponible para los inquilinos GCC, GCC-High, DoD, EDU.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="2b8dd-106">La expansión de las regiones y los idiomas adicionales se realizará como parte de las versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="2b8dd-107">La asistencia de voz de Cortana en Microsoft Team salas está publicada en vista previa.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="2b8dd-108">En su versión preliminar, Cortana solo se admite en los Estados Unidos con el idioma en-es en los dispositivos que han conectado micrófonos Rally.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="2b8dd-109">La asistencia de voz de Cortana en la aplicación móvil de Microsoft Teams, en salas de Microsoft Teams en Windows, y en los dispositivos de visualización de Microsoft Teams permite a los usuarios de Microsoft 365 Enterprise optimizar la comunicación, la colaboración y las tareas relacionadas con la reunión usando el lenguaje natural hablado.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="2b8dd-110">Los usuarios pueden hablar con Cortana seleccionando el botón de micrófono situado en la esquina superior derecha de la aplicación móvil de Teams o diciendo &#8220;Cortana&#8221; en la sala de Microsoft Teams o al usar una presentación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="2b8dd-111">Para conectarse rápidamente con sus manos libres de su equipo y mientras se desplazan, los usuarios pueden decir consultas como &#8220;llamar a Nuria&#8221; o &#8220;enviar un mensaje a la próxima reunión&#8221;.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="2b8dd-112">Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="2b8dd-113">Estas experiencias de asistencia por voz se proporcionan con los [servicios de calidad empresarial de Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal como se refleja en las condiciones de los [servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="2b8dd-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="2b8dd-114">La imagen muestra el envío de una conversación con Cortana en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="2b8dd-116">Control y limitaciones de administración</span><span class="sxs-lookup"><span data-stu-id="2b8dd-116">Admin control and limitations</span></span>

<span data-ttu-id="2b8dd-117">La asistencia de voz de Cortana en Teams se ofrece con servicios que cumplen con las promesas de privacidad, seguridad y cumplimiento normativo de Office 365, tal como se refleja en las condiciones de los servicios en línea (OST).</span><span class="sxs-lookup"><span data-stu-id="2b8dd-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="2b8dd-118">La característica se habilitará de forma predeterminada para los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="2b8dd-119">Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="2b8dd-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="2b8dd-120">Esta Directiva se puede establecer a nivel de cuenta de usuario o nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="2b8dd-121">Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, habilitada solo con la invocación del botón de comando o con la invocación de reactivación de Word (aplicable a los dispositivos que lo admiten, como la pantalla de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="2b8dd-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="2b8dd-122">Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta Directiva (la Directiva no está disponible en este momento en el centro de administración de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="2b8dd-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="2b8dd-123">Nuevo: CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2b8dd-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2b8dd-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2b8dd-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2b8dd-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2b8dd-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2b8dd-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2b8dd-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2b8dd-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2b8dd-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="2b8dd-128">Por ejemplo, el siguiente comando crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde la asistencia de voz Cortana en Microsoft Teams está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="2b8dd-129">En este ejemplo se muestra cómo actualizar una directiva existente con nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar la asistencia de voz de Cortana en Microsoft Teams solo con la llamada del botón de comando.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="2b8dd-130">Los usuarios podrán invocar a Cortana seleccionando el botón de micrófono de Cortana en Teams.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="2b8dd-131">Activar Word (&#8220;se deshabilitará la invocación de Cortana&#8221; o &#8220;Cortana&#8221;).</span><span class="sxs-lookup"><span data-stu-id="2b8dd-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="2b8dd-132">En este ejemplo se muestra cómo actualizar la Directiva y habilitar la asistencia de voz de Cortana con la llamada de activación de Word y el botón Insertar.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="2b8dd-133">En el momento, la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos en inglés, las siguientes son funciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="2b8dd-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="2b8dd-134">La aplicación móvil de Teams no admitirá la activación de la aplicación para activar Word, pero será compatible en el futuro.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="2b8dd-135">Salas de Microsoft Teams en Windows y Microsoft Teams los dispositivos de visualización admitirán la activación de la activación de Word.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="2b8dd-136">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="2b8dd-136">User control</span></span>

<span data-ttu-id="2b8dd-137">Los usuarios individuales pueden probar la asistencia de voz de Cortana en diferentes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="2b8dd-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="2b8dd-138">Seleccione el botón micrófono en la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="2b8dd-139">Seleccione el botón micrófono o diga "Cortana" en salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="2b8dd-140">Di "Cortana" en dispositivos de visualización de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="2b8dd-141">Puede controlar si Cortana de Teams está habilitada para el dispositivo mediante una configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="2b8dd-142">La aplicación móvil de Teams o la pantalla de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b8dd-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="2b8dd-143">Abra la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="2b8dd-144">Seleccione **configuración**  >  **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="2b8dd-145">Activar o **desactivar** el botón **de** alternancia.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="2b8dd-146">Pantalla de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b8dd-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="2b8dd-147">Vaya a la pantalla ambiente (Inicio) de la pantalla de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="2b8dd-148">Seleccione el avatar del usuario y, a continuación, seleccione **configuración**.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="2b8dd-149">Si Cortana está habilitada, diga "Cortana, ir a configuración".</span><span class="sxs-lookup"><span data-stu-id="2b8dd-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="2b8dd-150">Activar o **desactivar** el botón **de** alternancia.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="2b8dd-151">Salas de Microsoft Teams en Windows</span><span class="sxs-lookup"><span data-stu-id="2b8dd-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="2b8dd-152">La realización de cambios en el nivel de dispositivo está disponible si Cortana está habilitada en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="2b8dd-153">Cortana se desactivará de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="2b8dd-154">Para habilitar Cortana en el nivel de dispositivo, estos atributos XML deben agregarse en el archivo XML SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="2b8dd-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="2b8dd-155">Puede realizar cambios en el nivel de reunión si Cortana está habilitada en el nivel del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="2b8dd-156">Para habilitar la asistencia de voz de Cortana durante una reunión, mueva el botón **de alternancia a activado** o **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="2b8dd-157">Una vez finalizada la reunión, Cortana vuelve a la configuración de nivel de dispositivo establecida.</span><span class="sxs-lookup"><span data-stu-id="2b8dd-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>

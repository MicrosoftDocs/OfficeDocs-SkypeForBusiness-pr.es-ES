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
description: Obtener información sobre cómo usar el asistente de voz Cortana con Teams
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
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="31e58-103">Asistencia de voz de Cortana en Teams</span><span class="sxs-lookup"><span data-stu-id="31e58-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="31e58-104">La asistencia de voz de Cortana se admite en las aplicaciones móviles para iOS y Android de Microsoft Teams, salas de Microsoft Teams en Windows y en pantallas de Microsoft Teams, solo para los usuarios de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="31e58-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="31e58-105">No está disponible actualmente para inquilinos de GCC, GCC-High, DoD, EDU.</span><span class="sxs-lookup"><span data-stu-id="31e58-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="31e58-106">La expansión a idiomas y regiones adicionales se realizará como parte de las futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="31e58-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="31e58-107">La asistencia de voz de Cortana en salas de Microsoft Teams se ofrece en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="31e58-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="31e58-108">En su versión preliminar, Cortana solo es compatible en EE. UU. con idioma EN-US en dispositivos que tienen micrófonos Móviles conectados.</span><span class="sxs-lookup"><span data-stu-id="31e58-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="31e58-109">La asistencia de voz de Cortana en la aplicación móvil de Teams, en Salas de Microsoft Teams en Windows y en los dispositivos de visualización de Microsoft Teams permite a los usuarios de Microsoft 365 Enterprise simplificar la comunicación, la colaboración y las tareas relacionadas con las reuniones usando lenguaje natural hablado.</span><span class="sxs-lookup"><span data-stu-id="31e58-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="31e58-110">Los usuarios pueden hablar con Cortana seleccionando el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams o diciendo &#8220;Cortana&#8221; en la sala de Microsoft Teams o cuando se usa una pantalla de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="31e58-111">Para conectarse rápidamente con el equipo manos libres y mientras está fuera, los usuarios pueden decir consultas como &#8220;llamar&#8221; O &#8220;enviar un mensaje a mi próxima reunión&#8221;.</span><span class="sxs-lookup"><span data-stu-id="31e58-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="31e58-112">Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar asistencia de voz para compartir archivos, comprobar su calendario y mucho más.</span><span class="sxs-lookup"><span data-stu-id="31e58-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="31e58-113">Estas experiencias de asistencia de voz se entregan con servicios de nivel empresarial de [Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen completamente las promesas de privacidad, seguridad y cumplimiento de Office 365, tal y como se reflejan en los Términos de servicios en línea [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="31e58-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="31e58-114">La imagen muestra cómo enviar un chat con Cortana en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="31e58-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="31e58-116">Control de administración y limitaciones</span><span class="sxs-lookup"><span data-stu-id="31e58-116">Admin control and limitations</span></span>

<span data-ttu-id="31e58-117">La asistencia de voz de Cortana en Teams se entrega con servicios que cumplen completamente las promesas de cumplimiento, seguridad y privacidad de nivel empresarial de Office 365, tal y como se reflejan en los Términos de servicios en línea (OST).</span><span class="sxs-lookup"><span data-stu-id="31e58-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="31e58-118">La característica se habilitará de forma predeterminada para los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="31e58-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="31e58-119">Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="31e58-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="31e58-120">Esta directiva se puede establecer en un nivel de cuenta de usuario o en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="31e58-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="31e58-121">Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, habilitada solo con invocación de botón rápido o con la invocación de activar palabra también (aplicable a los dispositivos que la admiten, como la presentación de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="31e58-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="31e58-122">Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta directiva (la directiva no está disponible actualmente en el Centro de administración de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="31e58-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="31e58-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="31e58-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="31e58-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="31e58-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="31e58-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="31e58-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="31e58-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="31e58-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="31e58-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="31e58-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="31e58-128">Por ejemplo, el comando siguiente crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde se deshabilita la asistencia de voz de Cortana en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="31e58-129">En este ejemplo se muestra cómo actualizar una directiva existente con el nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar la asistencia de voz de Cortana en Microsoft Teams solo con invocación de botones de comando.</span><span class="sxs-lookup"><span data-stu-id="31e58-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="31e58-130">Los usuarios podrán invocar Cortana seleccionando el botón de micrófono Cortana en Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="31e58-131">La invocación de reactivación (&#8220;Hola Cortana&#8221; o &#8220;cortana&#8221;) se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="31e58-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="31e58-132">En este ejemplo se muestra cómo actualizar la directiva y habilitar la asistencia de voz de Cortana con el botón de presionar y reactivar la invocación de palabras.</span><span class="sxs-lookup"><span data-stu-id="31e58-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="31e58-133">En el momento de la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos en inglés, las siguientes son funciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="31e58-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="31e58-134">La aplicación móvil de Teams no admite la activación de Word, pero será compatible en el futuro.</span><span class="sxs-lookup"><span data-stu-id="31e58-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="31e58-135">Los salas de Microsoft Teams en windows y los dispositivos de visualización de Microsoft Teams admitirán la activación de Word.</span><span class="sxs-lookup"><span data-stu-id="31e58-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="31e58-136">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="31e58-136">User control</span></span>

<span data-ttu-id="31e58-137">Los usuarios individuales pueden probar la asistencia de voz de Cortana en diferentes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="31e58-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="31e58-138">Seleccione el botón del micrófono en la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="31e58-139">Seleccione el botón del micrófono o diga "Cortana" en salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="31e58-140">Di "Cortana" en los dispositivos de visualización de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="31e58-141">Puede controlar si Cortana en Teams está habilitada para su dispositivo mediante una configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="31e58-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="31e58-142">Aplicación móvil de Teams o la pantalla de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31e58-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="31e58-143">Abra la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="31e58-144">Selecciona **Configuración**  >  **cortana.**</span><span class="sxs-lookup"><span data-stu-id="31e58-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="31e58-145">Mueva el botón **de alternancia para activarlo** o **desactivarlo.**</span><span class="sxs-lookup"><span data-stu-id="31e58-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="31e58-146">Pantalla de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31e58-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="31e58-147">Vaya a la pantalla ambiente (principal) de la pantalla de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31e58-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="31e58-148">Selecciona el avatar del usuario y, a continuación, selecciona **Configuración.**</span><span class="sxs-lookup"><span data-stu-id="31e58-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="31e58-149">Si Cortana está habilitada, di "Cortana, ve a Configuración".</span><span class="sxs-lookup"><span data-stu-id="31e58-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="31e58-150">Mueva el botón **de alternancia para activarlo** o **desactivarlo.**</span><span class="sxs-lookup"><span data-stu-id="31e58-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="31e58-151">Salas de Microsoft Teams en Windows</span><span class="sxs-lookup"><span data-stu-id="31e58-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="31e58-152">La realización de cambios en el nivel del dispositivo está disponible si Cortana está habilitada en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="31e58-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="31e58-153">Cortana se desactivará de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="31e58-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="31e58-154">Para habilitar Cortana en el nivel del dispositivo, estos atributos XML deben agregarse al archivo XML de SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="31e58-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="31e58-155">La realización de cambios en el nivel de reunión está disponible si Cortana está habilitada en el nivel del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="31e58-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="31e58-156">Para habilitar la asistencia de voz de Cortana durante una reunión, activa **o** desactiva el botón de **alternancia.**</span><span class="sxs-lookup"><span data-stu-id="31e58-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="31e58-157">Una vez que finaliza la reunión, Cortana vuelve a la configuración de nivel de dispositivo establecida.</span><span class="sxs-lookup"><span data-stu-id="31e58-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>

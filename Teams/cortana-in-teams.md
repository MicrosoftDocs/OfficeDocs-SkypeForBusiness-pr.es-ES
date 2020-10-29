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
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785394"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="59f94-103">Asistencia de voz de Cortana en Teams</span><span class="sxs-lookup"><span data-stu-id="59f94-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="59f94-104">La asistencia de voz de Cortana es compatible con las aplicaciones móviles iOS y Android de Microsoft Teams, y en Microsoft Teams se muestra solo para los usuarios de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="59f94-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="59f94-105">Actualmente no está disponible para los inquilinos GCC, GCC-High, DoD, EDU.</span><span class="sxs-lookup"><span data-stu-id="59f94-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="59f94-106">La expansión de las regiones y los idiomas adicionales se realizará como parte de las versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="59f94-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="59f94-107">La asistencia por voz de Cortana en la aplicación móvil de Teams y en los dispositivos de visualización de Microsoft Teams permite a los usuarios empresariales de Microsoft 365 mejorar la comunicación, la colaboración y las tareas relacionadas con la reunión usando el lenguaje natural hablado.</span><span class="sxs-lookup"><span data-stu-id="59f94-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="59f94-108">Los usuarios pueden hablar con Cortana seleccionando el botón de micrófono situado en la parte superior derecha de la aplicación móvil de Teams o diciendo &#8220;Cortana&#8221; en la pantalla de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59f94-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="59f94-109">Para conectarse rápidamente con sus manos libres de su equipo y mientras se desplazan, los usuarios pueden decir consultas como &#8220;llamar a Nuria&#8221; o &#8220;enviar un mensaje a la próxima reunión&#8221;.</span><span class="sxs-lookup"><span data-stu-id="59f94-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="59f94-110">Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más.</span><span class="sxs-lookup"><span data-stu-id="59f94-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="59f94-111">Estas experiencias de asistencia por voz se proporcionan con los [servicios de calidad empresarial de Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal como se refleja en las condiciones de los [servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="59f94-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="59f94-112">La imagen muestra el envío de una conversación con Cortana en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="59f94-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![La imagen muestra una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="59f94-114">Control y limitaciones de administración</span><span class="sxs-lookup"><span data-stu-id="59f94-114">Admin control and limitations</span></span>

<span data-ttu-id="59f94-115">La asistencia de voz de Cortana en Teams se ofrece con servicios que cumplen con las promesas de privacidad, seguridad y cumplimiento normativo de Office 365, tal como se refleja en las condiciones de los servicios en línea (OST).</span><span class="sxs-lookup"><span data-stu-id="59f94-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="59f94-116">La característica se habilitará de forma predeterminada para los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="59f94-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="59f94-117">Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="59f94-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="59f94-118">Esta Directiva se puede establecer a nivel de cuenta de usuario o nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="59f94-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="59f94-119">Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, está habilitada solamente con la invocación del botón de comando o con la invocación de reactivación de Word (aplicable a dispositivos que lo admiten, como la presentación de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="59f94-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="59f94-120">Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta Directiva (la Directiva no está disponible en este momento en el centro de administración de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="59f94-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="59f94-121">Nuevo: CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="59f94-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="59f94-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="59f94-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="59f94-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="59f94-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="59f94-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="59f94-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="59f94-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="59f94-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="59f94-126">Por ejemplo, el siguiente comando crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde la asistencia de voz Cortana en Microsoft Teams está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="59f94-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="59f94-127">En este ejemplo se muestra cómo actualizar una directiva existente con nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar la asistencia de voz de Cortana en Microsoft Teams solo con la llamada del botón de comando.</span><span class="sxs-lookup"><span data-stu-id="59f94-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="59f94-128">Los usuarios podrán invocar a Cortana seleccionando el botón de micrófono de Cortana en Teams.</span><span class="sxs-lookup"><span data-stu-id="59f94-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="59f94-129">Activar Word (&#8220;se deshabilitará la invocación de Cortana&#8221; o &#8220;Cortana&#8221;).</span><span class="sxs-lookup"><span data-stu-id="59f94-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="59f94-130">En este ejemplo se muestra cómo actualizar la Directiva y habilitar la asistencia de voz de Cortana con la llamada de activación de Word y el botón Insertar.</span><span class="sxs-lookup"><span data-stu-id="59f94-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="59f94-131">En el momento de la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos, la aplicación móvil de Teams no admitirá la activación de reactivación de Word, pero será admitida en el futuro.</span><span class="sxs-lookup"><span data-stu-id="59f94-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="59f94-132">La activación de Word Wake funciona en dispositivos de pantalla de Microsoft Teams en la versión inicial.</span><span class="sxs-lookup"><span data-stu-id="59f94-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="59f94-133">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="59f94-133">User control</span></span>

<span data-ttu-id="59f94-134">Los usuarios individuales pueden probar la asistencia de voz de Cortana en la aplicación móvil de Teams seleccionando el botón del micrófono.</span><span class="sxs-lookup"><span data-stu-id="59f94-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="59f94-135">Pueden probar la asistencia de voz de Cortana en dispositivos de visualización de Microsoft Teams simplemente diciendo &#8220;Cortana. &#8221; también pueden controlar si Cortana de Teams está habilitado para su dispositivo con una configuración de la aplicación móvil de Teams o de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59f94-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="59f94-136">Abra la aplicación móvil de Teams o vaya a la pantalla ambiente (Inicio) de la pantalla de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59f94-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="59f94-137">En la aplicación móvil de Teams, vaya a **configuración** .</span><span class="sxs-lookup"><span data-stu-id="59f94-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="59f94-138">En la pantalla de Microsoft Teams, seleccione el avatar de usuario y, a continuación, seleccione Configuración.</span><span class="sxs-lookup"><span data-stu-id="59f94-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="59f94-139">Si Cortana está habilitada, diga &#8220;Cortana, vaya a configuración. &#8221;</span><span class="sxs-lookup"><span data-stu-id="59f94-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="59f94-140">Seleccione **Cortana** .</span><span class="sxs-lookup"><span data-stu-id="59f94-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="59f94-141">Mueva el botón de alternancia a **activado** o **desactivado** , en función de si quiere usar la asistencia de voz de Cortana en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59f94-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>

---
title: Asistente de voz de Cortana en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Más información sobre cómo usar el Asistente de voz de Cortana con Teams
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522326"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="4f0e1-103">Asistencia de voz de Cortana en Teams</span><span class="sxs-lookup"><span data-stu-id="4f0e1-103">Cortana voice assistance in Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> <span data-ttu-id="4f0e1-104">La asistencia de voz de Cortana solo se admite en aplicaciones móviles iOS y Android de Microsoft Teams para usuarios de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="4f0e1-105">Actualmente no está disponible para los inquilinos GCC, GCC-High, DoD, EDU.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="4f0e1-106">La expansión de las regiones y los idiomas adicionales se realizará como parte de las versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="4f0e1-107">La asistencia de voz de Cortana de la aplicación móvil de Teams permite a los usuarios empresariales de Microsoft 365 mejorar la comunicación, la colaboración y las tareas relacionadas con la reunión usando el lenguaje natural hablado.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="4f0e1-108">Los usuarios pueden hablar con Cortana haciendo clic en el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="4f0e1-109">Para conectarse rápidamente con su equipo mientras está de viaje, los usuarios pueden decir consultas como "llamar a Nuria" o "enviar un mensaje a mi próxima reunión".</span><span class="sxs-lookup"><span data-stu-id="4f0e1-109">To quickly connect with their team while on the go, users can say queries such as “call Megan” or “send a message to my next meeting.”</span></span> <span data-ttu-id="4f0e1-110">Los usuarios también pueden unirse a reuniones diciendo "unirse a mi próxima reunión" y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-110">Users can also join meetings by saying “join my next meeting” and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="4f0e1-111">Estas experiencias de asistencia por voz se proporcionan con los [servicios de calidad empresarial de Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal como se refleja en las condiciones de los [servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="4f0e1-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="4f0e1-112">La imagen muestra el envío de una conversación en Cortana en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![La imagen muestra una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="4f0e1-114">Control y limitaciones de administración</span><span class="sxs-lookup"><span data-stu-id="4f0e1-114">Admin control and Limitations</span></span>

<span data-ttu-id="4f0e1-115">La asistencia de voz de Cortana en Teams se ofrece con servicios que cumplen con las promesas de privacidad, seguridad y cumplimiento normativo de Office 365, tal como se refleja en las condiciones de los servicios en línea (OST).</span><span class="sxs-lookup"><span data-stu-id="4f0e1-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="4f0e1-116">La característica se habilitará de forma predeterminada para los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="4f0e1-117">Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="4f0e1-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="4f0e1-118">Esta Directiva se puede establecer a nivel de cuenta de usuario o nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="4f0e1-119">Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, está habilitada solo con la invocación del botón de comando o con la invocación de activación de Word (aplicable a los dispositivos que lo admiten).</span><span class="sxs-lookup"><span data-stu-id="4f0e1-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="4f0e1-120">Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta Directiva (la Directiva no está disponible en este momento en el centro de administración de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="4f0e1-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="4f0e1-121">Nuevo: CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4f0e1-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4f0e1-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4f0e1-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4f0e1-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4f0e1-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4f0e1-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4f0e1-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4f0e1-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4f0e1-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="4f0e1-126">Por ejemplo, el siguiente comando crea una nueva directiva con el nombre "EmployeeCortanaPolicy" donde el Asistente de voz de Cortana de Microsoft Teams está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-126">For example, the command below creates a new policy with name "EmployeeCortanaPolicy" where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="4f0e1-127">En este ejemplo se muestra cómo actualizar una directiva existente con el nombre "EmployeeCortanaPolicy" y cómo habilitar el Asistente de voz de Cortana en Microsoft Teams con solo la llamada del botón de comando.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-127">This example shows updating an existing policy with name "EmployeeCortanaPolicy" and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="4f0e1-128">Los usuarios podrán invocar a Cortana pulsando en el botón de micrófono de Cortana en Teams.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="4f0e1-129">Se deshabilitará la invocación de reactivar Word ("Hola Cortana").</span><span class="sxs-lookup"><span data-stu-id="4f0e1-129">Wake word ("Hey Cortana”) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="4f0e1-130">En este ejemplo se muestra cómo actualizar la Directiva y habilitar el Asistente de voz de Cortana con el botón de comando y la invocación de Wake-Word.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="4f0e1-131">En el momento de la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos, la aplicación móvil de Teams no admitirá la activación de reactivación de Word, pero será admitida en el futuro.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="4f0e1-132">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="4f0e1-132">User control</span></span>

<span data-ttu-id="4f0e1-133">Los usuarios individuales pueden probar la asistencia de voz de Cortana en la aplicación móvil de Teams haciendo clic en el botón micrófono.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="4f0e1-134">También pueden controlar si Cortana de Teams está habilitada para su dispositivo con una configuración de la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="4f0e1-135">Abra la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="4f0e1-136">Vaya a **configuración**.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="4f0e1-137">Seleccione **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="4f0e1-138">Mueva el botón de alternancia a **activado** o **desactivado**, en función de si quiere usar la asistencia de voz de Cortana en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f0e1-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>

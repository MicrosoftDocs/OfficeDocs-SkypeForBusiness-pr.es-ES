---
title: Cortana de voz en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Obtenga información sobre cómo usar Cortana de voz con Teams
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
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428216"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="7fd4e-103">Cortana de voz en Teams</span><span class="sxs-lookup"><span data-stu-id="7fd4e-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="7fd4e-104">Cortana de voz es compatible con las aplicaciones móviles de Microsoft Teams para iOS y Android y Microsoft Teams para usuarios de Estados Unidos, Reino Unido, Canadá, India y Australia.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="7fd4e-105">Salas de Microsoft Teams en Windows solo es compatible con los usuarios de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="7fd4e-106">Cortana asistencia de voz no está disponible actualmente para los inquilinos GCC, GCC-High, DoD y otros inquilinos edu.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="7fd4e-107">Cortana asistencia de voz en la Teams móvil ya está disponible para los clientes de EDU en Ee. UU.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="7fd4e-108">La expansión a idiomas y regiones adicionales se realizará como parte de futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="7fd4e-109">Cortana asistencia de voz en Salas de Microsoft Teams se publicó en Vista previa.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="7fd4e-110">En su versión preliminar, Cortana solo se admite en los Estados Unidos con el idioma EN-EE. UU. en dispositivos que tienen micrófonos de Rally conectados.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="7fd4e-111">Cortana de voz en la aplicación móvil de Teams, en Salas de Microsoft Teams en Windows y en dispositivos de visualización de Microsoft Teams permite Microsoft 365 Enterprise los usuarios simplificar las tareas relacionadas con la comunicación, la colaboración y las reuniones con el lenguaje natural hablado.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="7fd4e-112">Los usuarios pueden hablar con Cortana seleccionando el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams, o diciendo &#8220;Cortana&#8221; en la sala de Microsoft Teams o al usar una pantalla Microsoft Teams pantalla.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="7fd4e-113">Para conectarse rápidamente con su equipo manos libres y mientras está en cualquier lugar, los usuarios pueden decir consultas como &#8220;llamar a Megan&#8221; o &#8220;enviar un mensaje a mi próxima reunión&#8221;.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="7fd4e-114">Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="7fd4e-115">Estas experiencias de asistencia de voz se entregan [Cortana con](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) servicios de nivel empresarial que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal y como se reflejan en los Términos de servicios en línea [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="7fd4e-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

## <a name="admin-control-and-limitations"></a><span data-ttu-id="7fd4e-116">Control de administración y limitaciones</span><span class="sxs-lookup"><span data-stu-id="7fd4e-116">Admin control and limitations</span></span>

<span data-ttu-id="7fd4e-117">Cortana de voz en Teams se entrega con servicios que cumplen completamente con las promesas de privacidad, seguridad y cumplimiento de Office 365 nivel empresarial, tal como se reflejan en los Términos de servicios en línea (OST).</span><span class="sxs-lookup"><span data-stu-id="7fd4e-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="7fd4e-118">La característica se habilitará de forma predeterminada para los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="7fd4e-119">Los administradores de inquilinos pueden controlar quién en su espacio empresarial puede usar Cortana de voz en Teams una directiva (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="7fd4e-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="7fd4e-120">Esta directiva se establece en un nivel de cuenta de usuario o de inquilino.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-120">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="7fd4e-121">Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitado, habilitado solo con la invocación de botón de inserción o también con la invocación de palabra reactiva (aplicable a los dispositivos que lo admiten, como la pantalla Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="7fd4e-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="7fd4e-122">Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta directiva (la directiva no está disponible actualmente en Microsoft Teams centro de administración).</span><span class="sxs-lookup"><span data-stu-id="7fd4e-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="7fd4e-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7fd4e-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7fd4e-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7fd4e-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7fd4e-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7fd4e-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7fd4e-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7fd4e-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7fd4e-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7fd4e-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="7fd4e-128">Por ejemplo, el comando siguiente crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde Cortana de voz en Microsoft Teams está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="7fd4e-129">En este ejemplo se muestra cómo actualizar una directiva existente con el nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar Cortana asistencia de voz en Microsoft Teams solo con invocación de botón.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="7fd4e-130">Los usuarios podrán invocar el Cortana seleccionando el Cortana de micrófono en Teams.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="7fd4e-131">Se deshabilitará &#8220;la invocación de Cortana&#8221; o &#8220;Cortana&#8221;).</span><span class="sxs-lookup"><span data-stu-id="7fd4e-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="7fd4e-132">En este ejemplo se muestra la actualización de la directiva y la habilitación Cortana de voz con el botón de activación y la invocación de palabras reactivas.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="7fd4e-133">En ese momento, de la versión inicial para Microsoft 365 Enterprise usuarios en ee. UU. en inglés, las siguientes son funciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="7fd4e-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="7fd4e-134">La Teams móvil no admite la activación de la palabra reactiva, pero será compatible en el futuro.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="7fd4e-135">Salas de Microsoft Teams en Windows y Microsoft Teams dispositivos de visualización admitirán la activación de las palabras reactivas.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="7fd4e-136">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="7fd4e-136">User control</span></span>

<span data-ttu-id="7fd4e-137">Los usuarios individuales pueden Cortana asistencia de voz en diferentes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="7fd4e-137">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="7fd4e-138">Seleccione el botón del micrófono en la Teams móvil.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="7fd4e-139">Seleccione el botón del micrófono o diga "Cortana" en Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="7fd4e-140">Di "Cortana" en Microsoft Teams muestra dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-140">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="7fd4e-141">Puede controlar si Cortana en Teams está habilitado para el dispositivo mediante una configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="7fd4e-142">Salas de Microsoft Teams en Windows</span><span class="sxs-lookup"><span data-stu-id="7fd4e-142">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="7fd4e-143">Realizar cambios en el nivel de dispositivo está disponible si Cortana está habilitado en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-143">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="7fd4e-144">Cortana se liberará desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-144">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="7fd4e-145">Para habilitar Cortana en el nivel de dispositivo, estos atributos XML deben agregarse en el archivo XML de SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="7fd4e-145">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="7fd4e-146">Realizar cambios en el nivel de reunión está disponible si Cortana está habilitado en el nivel de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-146">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="7fd4e-147">Para habilitar Cortana de voz durante una reunión, mueva el botón de alternancia **Activar** o **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-147">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="7fd4e-148">Una vez que finalice la reunión, Cortana volverá a la configuración de nivel de dispositivo establecida.</span><span class="sxs-lookup"><span data-stu-id="7fd4e-148">Once the meeting ends, Cortana returns to the device level settings set.</span></span>

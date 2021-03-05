---
title: Administrar directivas de llamadas y voz en Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Obtenga información sobre las directivas de llamadas y voz de Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460590"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="76c6e-103">Administrar directivas de llamadas y voz en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76c6e-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="76c6e-104">Las directivas de llamadas y voz se usan para controlar la voz y las llamadas en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76c6e-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="76c6e-105">Directivas de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="76c6e-105">Emergency calling policies</span></span>

<span data-ttu-id="76c6e-106">Use directivas [de llamadas de emergencia](manage-emergency-calling-policies.md) para configurar lo que ocurre cuando un usuario de su organización realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="76c6e-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="76c6e-107">Estas directivas se administran en el Centro de administración de Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c6e-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Captura de pantalla de la directiva de llamadas de emergencia.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="76c6e-109">Directivas de enrutamiento de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="76c6e-109">Emergency call routing policies</span></span>

<span data-ttu-id="76c6e-110">Si su organización ha implementado enrutamiento directo [](manage-emergency-call-routing-policies.md) del sistema **telefónico,** puede usar directivas de enrutamiento de llamadas de emergencia para determinar dónde se enruten las llamadas de emergencia, si los servicios de emergencia mejorados están habilitados y qué números se usan para los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="76c6e-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="76c6e-111">Estas directivas se administran con PowerShell o en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76c6e-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Captura de pantalla de la directiva de enrutamiento de llamadas de emergencia.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="76c6e-113">Directivas de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="76c6e-113">Caller ID policies</span></span>

<span data-ttu-id="76c6e-114">[Las directivas de identificación de](caller-id-policies.md) llamadas se usan para cambiar o bloquear el identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="76c6e-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Captura de pantalla de la directiva de identificación de llamadas.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="76c6e-116">Directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="76c6e-116">Voice routing policies</span></span>

<span data-ttu-id="76c6e-117">Una [directiva de enrutamiento de](manage-voice-routing-policies.md) voz es un contenedor para los registros de uso de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="76c6e-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="76c6e-118">Puede usar estas directivas si su organización ha implementado **enrutamiento directo del sistema telefónico.**</span><span class="sxs-lookup"><span data-stu-id="76c6e-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="76c6e-119">Las directivas de enrutamiento de voz se pueden administrar con PowerShell o en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="76c6e-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Captura de pantalla de la directiva de enrutamiento de voz.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="76c6e-121">Directivas de llamada</span><span class="sxs-lookup"><span data-stu-id="76c6e-121">Calling policies</span></span>

<span data-ttu-id="76c6e-122">[Las directivas de](teams-calling-policy.md) llamadas controlan qué características de llamadas y reenvío de llamadas están disponibles para los usuarios, incluido si un usuario puede realizar llamadas privadas, enviar llamadas a grupos de llamadas y enrutar llamadas al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="76c6e-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Captura de pantalla de la directiva de llamadas.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="76c6e-124">Parque de llamadas y directivas de recuperación</span><span class="sxs-lookup"><span data-stu-id="76c6e-124">Call park and retrieve policies</span></span>

<span data-ttu-id="76c6e-125">[El parque de llamadas y la recuperación](call-park-and-retrieve.md) permite a los usuarios poner a otros usuarios en espera y permite al mismo usuario o a otra persona continuar la llamada.</span><span class="sxs-lookup"><span data-stu-id="76c6e-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Captura de pantalla del parque de llamadas y la directiva de recuperación.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="76c6e-127">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="76c6e-127">Create and manage dial plans</span></span>

<span data-ttu-id="76c6e-128">[Los planes de marcado](create-and-manage-dial-plans.md) traducen los números de teléfono marcados para la autorización de llamadas y el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="76c6e-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="76c6e-129">Puede crear y administrar planes de marcado a través de PowerShell o en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76c6e-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Captura de pantalla del plan de marcado.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="76c6e-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="76c6e-131">Related topics</span></span>

* [<span data-ttu-id="76c6e-132">Administrar directivas de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76c6e-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="76c6e-133">Administrar directivas de enrutamiento de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="76c6e-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="76c6e-134">Administrar directivas del id. de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76c6e-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="76c6e-135">Administrar directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="76c6e-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="76c6e-136">Directivas de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76c6e-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="76c6e-137">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76c6e-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="76c6e-138">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="76c6e-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="76c6e-139">Administrar Teams con directivas</span><span class="sxs-lookup"><span data-stu-id="76c6e-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)

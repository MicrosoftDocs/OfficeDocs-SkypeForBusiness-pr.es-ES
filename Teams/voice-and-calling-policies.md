---
title: Administrar directivas de llamadas y voz en Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2021
ms.locfileid: "50348095"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="2ce7f-102">Administrar directivas de llamadas y voz en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ce7f-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="2ce7f-103">Las directivas de llamadas y voz se usan para controlar la voz y las llamadas en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="2ce7f-104">Directivas de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="2ce7f-104">Emergency calling policies</span></span>

<span data-ttu-id="2ce7f-105">Use directivas [de llamadas de emergencia](manage-emergency-calling-policies.md) para configurar lo que ocurre cuando un usuario de su organización realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="2ce7f-106">Estas directivas se administran en el Centro de administración de Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Captura de pantalla de la directiva de llamadas de emergencia.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="2ce7f-108">Directivas de enrutamiento de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="2ce7f-108">Emergency call routing policies</span></span>

<span data-ttu-id="2ce7f-109">Si su organización ha implementado enrutamiento directo [](manage-emergency-call-routing-policies.md) del sistema **telefónico,** puede usar directivas de enrutamiento de llamadas de emergencia para determinar dónde se enruten las llamadas de emergencia, si los servicios de emergencia mejorados están habilitados y qué números se usan para los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="2ce7f-110">Estas directivas se administran con PowerShell o en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Captura de pantalla de la directiva de enrutamiento de llamadas de emergencia.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="2ce7f-112">Directivas de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="2ce7f-112">Caller ID policies</span></span>

<span data-ttu-id="2ce7f-113">[Las directivas de identificación de](caller-id-policies.md) llamadas se usan para cambiar o bloquear el identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Captura de pantalla de la directiva de identificación de llamadas.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="2ce7f-115">Directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="2ce7f-115">Voice routing policies</span></span>

<span data-ttu-id="2ce7f-116">Una [directiva de enrutamiento de](manage-voice-routing-policies.md) voz es un contenedor para los registros de uso de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="2ce7f-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="2ce7f-117">Puede usar estas directivas si su organización ha implementado **enrutamiento directo del sistema telefónico.**</span><span class="sxs-lookup"><span data-stu-id="2ce7f-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="2ce7f-118">Las directivas de enrutamiento de voz se pueden administrar con PowerShell o en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Captura de pantalla de la directiva de enrutamiento de voz.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="2ce7f-120">Directivas de llamada</span><span class="sxs-lookup"><span data-stu-id="2ce7f-120">Calling policies</span></span>

<span data-ttu-id="2ce7f-121">[Las directivas de](teams-calling-policy.md) llamadas controlan qué características de llamadas y reenvío de llamadas están disponibles para los usuarios, incluido si un usuario puede realizar llamadas privadas, enviar llamadas a grupos de llamadas y enrutar llamadas al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Captura de pantalla de la directiva de llamadas.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="2ce7f-123">Parque de llamadas y directivas de recuperación</span><span class="sxs-lookup"><span data-stu-id="2ce7f-123">Call park and retrieve policies</span></span>

<span data-ttu-id="2ce7f-124">[El parque de llamadas y la recuperación](call-park-and-retrieve.md) permite a los usuarios poner a otros usuarios en espera y permite que el mismo usuario o otra persona continúen con la llamada.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Captura de pantalla del parque de llamadas y la directiva de recuperación.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="2ce7f-126">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="2ce7f-126">Create and manage dial plans</span></span>

<span data-ttu-id="2ce7f-127">[Los planes de marcado](create-and-manage-dial-plans.md) traducen los números de teléfono marcados para la autorización de llamadas y el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="2ce7f-128">Puede crear y administrar planes de marcado a través de PowerShell o en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Captura de pantalla del plan de marcado.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="2ce7f-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2ce7f-130">Related topics</span></span>

* [<span data-ttu-id="2ce7f-131">Administrar directivas de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ce7f-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="2ce7f-132">Administrar directivas de enrutamiento de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="2ce7f-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="2ce7f-133">Administrar directivas de identificación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ce7f-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="2ce7f-134">Administrar directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="2ce7f-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="2ce7f-135">Directivas de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ce7f-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="2ce7f-136">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ce7f-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="2ce7f-137">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="2ce7f-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="2ce7f-138">Administrar Teams con directivas</span><span class="sxs-lookup"><span data-stu-id="2ce7f-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)

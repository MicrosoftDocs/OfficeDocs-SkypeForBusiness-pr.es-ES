---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Experiencia de los equipos cliente y la compatibilidad con los modos de coexistencia
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4865d66d4d3ff1257d0fc4bd355a65c7c1330101
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934791"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="c530c-103">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="c530c-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="c530c-104">Esta página describe los cambios importantes, lanzados recientemente en el comportamiento del cliente de los equipos cuando los usuarios están en cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="c530c-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="c530c-105">El propósito de los modos de la coexistencia es proporcionar una experiencia sencilla y predecible para los usuarios finales como transición de las organizaciones de Skype para la empresa a los equipos.</span><span class="sxs-lookup"><span data-stu-id="c530c-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="c530c-106">Para una organización mover a los equipos, el modo de TeamsOnly es el destino final de cada usuario, aunque no todos los usuarios deben asignarse TeamsOnly (o cualquier otro modo) al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c530c-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="c530c-107">Antes de alcanzar el modo TeamsOnly de los usuarios, las organizaciones pueden usar cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantizar la comunicación entre los usuarios que están TeamsOnly y aquellos que no están todavía predecible.</span><span class="sxs-lookup"><span data-stu-id="c530c-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="c530c-108">Cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio, todos los chats entrantes y las llamadas se enrutan a Skype del usuario para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="c530c-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="c530c-109">Para evitar confusiones al usuario final y garantizar el enrutamiento correcto, llamadas y conversaciones funcionalidad en el cliente de los equipos está deshabilitada cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio.</span><span class="sxs-lookup"><span data-stu-id="c530c-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="c530c-110">De forma similar, programar reuniones en los equipos está deshabilitado de forma explícita cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y explícitamente habilitado cuando un usuario se encuentra en el modo de SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="c530c-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="c530c-111">¿Cómo se cambia la funcionalidad disponible en el cliente de los equipos basada en el modo</span><span class="sxs-lookup"><span data-stu-id="c530c-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="c530c-112">La funcionalidad disponible en los equipos dependes en modo de coexistencia del usuario, tal como lo establece TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="c530c-112">The available functionality in Teams dependes on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="c530c-113">En la tabla siguiente se resume el comportamiento:</span><span class="sxs-lookup"><span data-stu-id="c530c-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="c530c-114">Modo eficaz del usuario</span><span class="sxs-lookup"><span data-stu-id="c530c-114">User's effective mode</span></span>|<span data-ttu-id="c530c-115">Experiencia de cliente de los equipos</span><span class="sxs-lookup"><span data-stu-id="c530c-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="c530c-116">Cualquier Skype para el modo de negocio</span><span class="sxs-lookup"><span data-stu-id="c530c-116">Any Skype for Business mode</span></span>|<span data-ttu-id="c530c-117">Llamadas y conversaciones<sup>1</sup> están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="c530c-117">Calling and Chat<sup>1</sup> are disabled.</span></span>|
|<span data-ttu-id="c530c-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="c530c-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="c530c-119">Programación de la reunión está disponible</span><span class="sxs-lookup"><span data-stu-id="c530c-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="c530c-120">SfBWithTeamsCollab o SfBOnly<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c530c-120">SfBWithTeamsCollab or SfBOnly<sup>2</sup></span></span>|<span data-ttu-id="c530c-121">Programación de la reunión no está disponible</span><span class="sxs-lookup"><span data-stu-id="c530c-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="c530c-122">Las capturas de pantalla siguientes ilustran la diferencia entre el modo de TeamsOnly o islas y todos los demás modos.</span><span class="sxs-lookup"><span data-stu-id="c530c-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="c530c-123">Tenga en cuenta que están disponibles los iconos de chat y llamar al método con TeamsOnly o Islas modo (captura de pantalla de la izquierda), pero no con los demás modos (captura de pantalla derecha):</span><span class="sxs-lookup"><span data-stu-id="c530c-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Muestra las comparaciones de modo de equipos](media/teams-mode-comparison.png)


 
<span data-ttu-id="c530c-125">**Notas:**
<sup>1</sup> chat de reunión sigue estando disponible.</span><span class="sxs-lookup"><span data-stu-id="c530c-125">**Notes:**
<sup>1</sup> Meeting chat is still available.</span></span>

<span data-ttu-id="c530c-126"><sup>2</sup> por ahora, SfBwithTeamsCollab y SfBOnly comportan de la misma, pero la intención es para que el modo de SfBOnly deshabilitar también la funcionalidad de canales y los archivos en los equipos; Sin embargo, actualmente no hay ninguna opción que permite que esta funcionalidad en los equipos que va a deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="c530c-126"><sup>2</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="c530c-127">Impacto del modo en otras configuraciones de directiva</span><span class="sxs-lookup"><span data-stu-id="c530c-127">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="c530c-128">Como se describió anteriormente, del impacto del modo de coexistencia de un usuario qué funcionalidad está disponible en el cliente de los equipos del usuario.</span><span class="sxs-lookup"><span data-stu-id="c530c-128">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="c530c-129">Esto significa que el valor del modo puede tener prioridad sobre el valor de otras configuraciones de directiva, según el modo.</span><span class="sxs-lookup"><span data-stu-id="c530c-129">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="c530c-130">En concreto, afecta al modo de coexistencia si se respetan las siguientes opciones de directiva:</span><span class="sxs-lookup"><span data-stu-id="c530c-130">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="c530c-131">**Modalidad (aplicación)**</span><span class="sxs-lookup"><span data-stu-id="c530c-131">**Modality (App)**</span></span>|<span data-ttu-id="c530c-132">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="c530c-132">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="c530c-133">Chat</span><span class="sxs-lookup"><span data-stu-id="c530c-133">Chat</span></span>|<span data-ttu-id="c530c-134">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="c530c-134">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="c530c-135">Llamar a</span><span class="sxs-lookup"><span data-stu-id="c530c-135">Calling</span></span>|<span data-ttu-id="c530c-136">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="c530c-136">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="c530c-137">Programación de reuniones</span><span class="sxs-lookup"><span data-stu-id="c530c-137">Meeting scheduling</span></span>|<span data-ttu-id="c530c-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c530c-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="c530c-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c530c-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="c530c-140">Los administradores necesitan *no* establecer explícitamente estas configuraciones de directiva cuando se utiliza el modo de coexistencia, pero es importante comprender que estas opciones de configuración eficazmente se comportan como sigue para un modo determinado.</span><span class="sxs-lookup"><span data-stu-id="c530c-140">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="c530c-141">Modo</span><span class="sxs-lookup"><span data-stu-id="c530c-141">Mode</span></span>|<span data-ttu-id="c530c-142">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="c530c-142">AllowUserChat</span></span>|<span data-ttu-id="c530c-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="c530c-143">AllowPrivateCalling</span></span>|<span data-ttu-id="c530c-144">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c530c-144">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="c530c-145">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c530c-145">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="c530c-146">TeamsOnly o Islas</span><span class="sxs-lookup"><span data-stu-id="c530c-146">TeamsOnly or Islands</span></span>|<span data-ttu-id="c530c-147">Habilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-147">Enabled</span></span>|<span data-ttu-id="c530c-148">Habilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-148">Enabled</span></span>|<span data-ttu-id="c530c-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-149">Enabled</span></span>|<span data-ttu-id="c530c-150">Habilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-150">Enabled</span></span>|
|<span data-ttu-id="c530c-151">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="c530c-151">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="c530c-152">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-152">Disabled</span></span>|<span data-ttu-id="c530c-153">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-153">Disabled</span></span>|<span data-ttu-id="c530c-154">Habilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-154">Enabled</span></span>|<span data-ttu-id="c530c-155">Habilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-155">Enabled</span></span>|
|<span data-ttu-id="c530c-156">SfBWithTeamsCollab o SfBOnly</span><span class="sxs-lookup"><span data-stu-id="c530c-156">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="c530c-157">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-157">Disabled</span></span>|<span data-ttu-id="c530c-158">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-158">Disabled</span></span>|<span data-ttu-id="c530c-159">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-159">Disabled</span></span>|<span data-ttu-id="c530c-160">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="c530c-160">Disabled</span></span>|
||||||

<span data-ttu-id="c530c-161">En el futuro, el `Grant-CsTeamsUpgradePolicy` cmdlet comprobará la configuración de los valores correspondientes en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si esa configuración va a ser reemplazada por TeamsUpgradePolicy y si es así, un mensaje informativo se proporciona en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c530c-161">In the near future, the `Grant-CsTeamsUpgradePolicy` cmdlet will check the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings will be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="c530c-162">Como se mencionó anteriormente, ya no es necesario establecer estas otras configuraciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="c530c-162">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="c530c-163">A continuación es un ejemplo del aspecto qué la advertencia de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c530c-163">Below is an example of what the PowerShell warning  looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="c530c-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c530c-164">Related topics</span></span>

[<span data-ttu-id="c530c-165">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c530c-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)





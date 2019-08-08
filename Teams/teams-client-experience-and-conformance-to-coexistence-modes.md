---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Experiencia del cliente de Teams y cumplimiento de los modos de coexistencia
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243910"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="f0896-103">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="f0896-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="f0896-104">Esta página describe los cambios más importantes y recientes en el comportamiento del cliente de Teams cuando los usuarios están en cualquiera de los modos de Skype empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="f0896-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="f0896-105">El propósito de los modos de coexistencia es proporcionar una experiencia sencilla y predecible a los usuarios finales a medida que las organizaciones pasan de Skype empresarial a teams.</span><span class="sxs-lookup"><span data-stu-id="f0896-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="f0896-106">Para una organización que se desplaza a Teams, el modo TeamsOnly es el destino final de cada usuario, aunque no es necesario que todos los usuarios tengan asignado TeamsOnly (o cualquier otro modo) al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f0896-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="f0896-107">Antes de que los usuarios alcanzaran el modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de Skype empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantizar una comunicación predecible entre los usuarios que son TeamsOnly y aquellos que aún no lo están.</span><span class="sxs-lookup"><span data-stu-id="f0896-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="f0896-108">Cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial, todas las conversaciones y llamadas entrantes se enrutan al cliente de Skype empresarial del usuario.</span><span class="sxs-lookup"><span data-stu-id="f0896-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="f0896-109">Para evitar la confusión del usuario final y garantizar el enrutamiento adecuado, la funcionalidad de llamadas y chats en el cliente de equipos está deshabilitada cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="f0896-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="f0896-110">De forma similar, la programación de reuniones de Teams se deshabilita de forma explícita cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab, y se habilita de forma explícita cuando un usuario está en el modo de SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="f0896-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="f0896-111">Cómo cambia la funcionalidad disponible en el cliente de Teams según el modo</span><span class="sxs-lookup"><span data-stu-id="f0896-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="f0896-112">La funcionalidad disponible en Teams depende del modo de coexistencia del usuario, establecido por TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="f0896-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="f0896-113">En la tabla siguiente se resume el comportamiento:</span><span class="sxs-lookup"><span data-stu-id="f0896-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="f0896-114">Modo de efectividad del usuario</span><span class="sxs-lookup"><span data-stu-id="f0896-114">User's effective mode</span></span>|<span data-ttu-id="f0896-115">Experiencia en el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="f0896-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="f0896-116">Cualquier modo de Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="f0896-116">Any Skype for Business mode</span></span>|<span data-ttu-id="f0896-117">Las llamadas y los chats están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="f0896-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="f0896-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="f0896-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="f0896-119">Programación de reuniones disponible</span><span class="sxs-lookup"><span data-stu-id="f0896-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="f0896-120">SfBWithTeamsCollab o SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f0896-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="f0896-121">La programación de reuniones no está disponible</span><span class="sxs-lookup"><span data-stu-id="f0896-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="f0896-122">En las siguientes capturas de pantallas se muestra la diferencia entre el modo TeamsOnly o islas y todos los demás modos.</span><span class="sxs-lookup"><span data-stu-id="f0896-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="f0896-123">Tenga en cuenta que los iconos de llamadas y chats están disponibles con TeamsOnly o islas (captura de pantalla izquierda), pero no con los otros modos (captura de pantalla derecha):</span><span class="sxs-lookup"><span data-stu-id="f0896-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Una comparación en paralelo de los modos de Teams](media/teams-mode-comparison.png)


 
<span data-ttu-id="f0896-125">**Nota:**
<sup>1</sup> por ahora, SfBwithTeamsCollab y SfBOnly se comportan de la misma forma, pero el propósito es que el modo SfBOnly también deshabilite la funcionalidad de canales y archivos en Teams; sin embargo, en este momento no hay ninguna configuración que permita que esta funcionalidad en Teams esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f0896-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="f0896-126">Impacto del modo en otras configuraciones de Directiva</span><span class="sxs-lookup"><span data-stu-id="f0896-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="f0896-127">Como se describe anteriormente, el modo de coexistencia del usuario afecta a la funcionalidad que está disponible en el cliente de equipos del usuario.</span><span class="sxs-lookup"><span data-stu-id="f0896-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="f0896-128">Esto significa que el valor de MODE puede tener prioridad sobre el valor de otras configuraciones de Directiva, según el modo.</span><span class="sxs-lookup"><span data-stu-id="f0896-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="f0896-129">En concreto, el modo de coexistencia afecta al hecho de que se hayan respetado las siguientes configuraciones de directiva:</span><span class="sxs-lookup"><span data-stu-id="f0896-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="f0896-130">**Modalidad (aplicación)**</span><span class="sxs-lookup"><span data-stu-id="f0896-130">**Modality (App)**</span></span>|<span data-ttu-id="f0896-131">**Policy. setting**</span><span class="sxs-lookup"><span data-stu-id="f0896-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="f0896-132">Chat</span><span class="sxs-lookup"><span data-stu-id="f0896-132">Chat</span></span>|<span data-ttu-id="f0896-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="f0896-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="f0896-134">Llamadas</span><span class="sxs-lookup"><span data-stu-id="f0896-134">Calling</span></span>|<span data-ttu-id="f0896-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="f0896-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="f0896-136">Programación de reuniones</span><span class="sxs-lookup"><span data-stu-id="f0896-136">Meeting scheduling</span></span>|<span data-ttu-id="f0896-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f0896-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="f0896-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f0896-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="f0896-139">Los administradores *no* necesitan establecer explícitamente estas configuraciones de directiva al usar el modo de coexistencia, pero es importante comprender que esta configuración se comporta de la siguiente manera de forma eficaz para un modo determinado.</span><span class="sxs-lookup"><span data-stu-id="f0896-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="f0896-140">Multimodo</span><span class="sxs-lookup"><span data-stu-id="f0896-140">Mode</span></span>|<span data-ttu-id="f0896-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="f0896-141">AllowUserChat</span></span>|<span data-ttu-id="f0896-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="f0896-142">AllowPrivateCalling</span></span>|<span data-ttu-id="f0896-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f0896-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="f0896-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f0896-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="f0896-145">TeamsOnly o islas</span><span class="sxs-lookup"><span data-stu-id="f0896-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="f0896-146">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-146">Enabled</span></span>|<span data-ttu-id="f0896-147">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-147">Enabled</span></span>|<span data-ttu-id="f0896-148">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-148">Enabled</span></span>|<span data-ttu-id="f0896-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-149">Enabled</span></span>|
|<span data-ttu-id="f0896-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="f0896-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="f0896-151">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-151">Disabled</span></span>|<span data-ttu-id="f0896-152">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-152">Disabled</span></span>|<span data-ttu-id="f0896-153">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-153">Enabled</span></span>|<span data-ttu-id="f0896-154">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-154">Enabled</span></span>|
|<span data-ttu-id="f0896-155">SfBWithTeamsCollab o SfBOnly</span><span class="sxs-lookup"><span data-stu-id="f0896-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="f0896-156">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-156">Disabled</span></span>|<span data-ttu-id="f0896-157">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-157">Disabled</span></span>|<span data-ttu-id="f0896-158">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-158">Disabled</span></span>|<span data-ttu-id="f0896-159">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f0896-159">Disabled</span></span>|
||||||

<span data-ttu-id="f0896-160">Al usar PowerShell, el `Grant-CsTeamsUpgradePolicy` cmdlet comprueba la configuración de la configuración correspondiente en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si esa configuración sería reemplazada por TeamsUpgradePolicy y, si es así, una el mensaje informativo se proporciona en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0896-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="f0896-161">Como se indicó anteriormente, ya no es necesario establecer estas otras configuraciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="f0896-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="f0896-162">A continuación se muestra un ejemplo del aspecto de la advertencia de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0896-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="f0896-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f0896-163">Related topics</span></span>

[<span data-ttu-id="f0896-164">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f0896-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)





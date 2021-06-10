---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Obtenga información sobre Teams cliente y la conformidad con los modos de coexistencia (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119259"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="561b8-103">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="561b8-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="561b8-104">El propósito de los modos de coexistencia Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones transición de Skype Empresarial a Teams.</span><span class="sxs-lookup"><span data-stu-id="561b8-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="561b8-105">Para una organización que se mueve a Teams, el modo **solo Teams** es el destino final para cada usuario, aunque no todos los usuarios tienen que asignarse **Teams** Solo (o cualquier otro modo) al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="561b8-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="561b8-106">Antes de que los usuarios lleguen al modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de coexistencia de Skype Empresarial para garantizar una comunicación predecible entre los usuarios que son **Teams Only** y los que aún no lo están.</span><span class="sxs-lookup"><span data-stu-id="561b8-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="561b8-107">Cuando un usuario está en cualquiera de los modos Skype Empresarial, todos los chats y llamadas entrantes se enruta al cliente Skype Empresarial usuario.</span><span class="sxs-lookup"><span data-stu-id="561b8-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="561b8-108">Para evitar confusiones de los usuarios finales y asegurarse de que la funcionalidad de enrutamiento, llamadas y chats del cliente de Teams está deshabilitada cuando un usuario está en cualquiera de los Skype Empresarial modos.</span><span class="sxs-lookup"><span data-stu-id="561b8-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="561b8-109">De forma similar, la programación de reuniones en Teams se deshabilita explícitamente cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y se habilita explícitamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="561b8-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="561b8-110">Como la presencia es una indicación de la capacidad de acceso a través del chat y las llamadas, cuando el chat y las llamadas están deshabilitados, la presencia personal en Teams (es decir, la presentación de su propia presencia en el cliente de Teams en la imagen del usuario) también está oculta.</span><span class="sxs-lookup"><span data-stu-id="561b8-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="561b8-111">Cómo cambia la funcionalidad disponible Teams cliente en función del modo</span><span class="sxs-lookup"><span data-stu-id="561b8-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="561b8-112">La funcionalidad disponible en Teams depende del modo de coexistencia del usuario, establecido por TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="561b8-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="561b8-113">En la tabla siguiente se resume el comportamiento:</span><span class="sxs-lookup"><span data-stu-id="561b8-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="561b8-114">Modo efectivo del usuario</span><span class="sxs-lookup"><span data-stu-id="561b8-114">User's effective mode</span></span>|<span data-ttu-id="561b8-115">Experiencia en Teams cliente</span><span class="sxs-lookup"><span data-stu-id="561b8-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="561b8-116">Cualquier Skype Empresarial de datos</span><span class="sxs-lookup"><span data-stu-id="561b8-116">Any Skype for Business mode</span></span>|<span data-ttu-id="561b8-117">Las llamadas, el chat y la presencia propia están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="561b8-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="561b8-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="561b8-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="561b8-119">La programación de reuniones está disponible</span><span class="sxs-lookup"><span data-stu-id="561b8-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="561b8-120">SfBWithTeamsCollab o SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="561b8-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="561b8-121">La programación de reuniones no está disponible</span><span class="sxs-lookup"><span data-stu-id="561b8-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="561b8-122">Las siguientes capturas de pantalla ilustran la **diferencia entre Teams modo Solo** o Islas y todos los demás modos. </span><span class="sxs-lookup"><span data-stu-id="561b8-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="561b8-123">Tenga en cuenta que los iconos de chat y  llamadas están disponibles de forma predeterminada con el modo **solo Teams** o Islas (captura de pantalla izquierda), pero no con los otros modos (captura de pantalla derecha):</span><span class="sxs-lookup"><span data-stu-id="561b8-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Una comparación en paralelo de los Teams modos](media/teams-mode-comparison.png)

<span data-ttu-id="561b8-125">Además, la presencia personal no está disponible en los otros modos, como se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="561b8-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Captura de pantalla de presencia personal en Reuniones Primero](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="561b8-127">**Nota:** 
 <sup>1</sup> En este momento, SfBwithTeamsCollab y SfBOnly se comportan igual, pero la intención es que el modo SfBOnly también deshabilite la funcionalidad Canales y archivos en Teams.</span><span class="sxs-lookup"><span data-stu-id="561b8-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="561b8-128">Entre tanto, los canales se pueden ocultar con la directiva permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="561b8-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="561b8-129">Impacto del modo en otras configuraciones de directiva</span><span class="sxs-lookup"><span data-stu-id="561b8-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="561b8-130">Como se ha descrito anteriormente, el modo de coexistencia de un usuario afecta a la funcionalidad que está disponible en el cliente de Teams usuario.</span><span class="sxs-lookup"><span data-stu-id="561b8-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="561b8-131">Esto significa que el valor del modo puede tener prioridad sobre el valor de otras configuraciones de directiva, dependiendo del modo.</span><span class="sxs-lookup"><span data-stu-id="561b8-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="561b8-132">En concreto, el modo de coexistencia afecta a si se respetan las siguientes configuraciones de directiva:</span><span class="sxs-lookup"><span data-stu-id="561b8-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="561b8-133">**Modalidad (aplicación)**</span><span class="sxs-lookup"><span data-stu-id="561b8-133">**Modality (App)**</span></span>|<span data-ttu-id="561b8-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="561b8-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="561b8-135">Chat</span><span class="sxs-lookup"><span data-stu-id="561b8-135">Chat</span></span>|<span data-ttu-id="561b8-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="561b8-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="561b8-137">Llamadas</span><span class="sxs-lookup"><span data-stu-id="561b8-137">Calling</span></span>|<span data-ttu-id="561b8-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="561b8-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="561b8-139">Programación de reuniones</span><span class="sxs-lookup"><span data-stu-id="561b8-139">Meeting scheduling</span></span>|<span data-ttu-id="561b8-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="561b8-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="561b8-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="561b8-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="561b8-142">Los administradores *no* necesitan establecer explícitamente esta configuración de directiva al usar el modo de coexistencia, pero es importante comprender que estas configuraciones se comportan de la manera siguiente para un modo determinado.</span><span class="sxs-lookup"><span data-stu-id="561b8-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="561b8-143">Modo</span><span class="sxs-lookup"><span data-stu-id="561b8-143">Mode</span></span>|<span data-ttu-id="561b8-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="561b8-144">AllowUserChat</span></span>|<span data-ttu-id="561b8-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="561b8-145">AllowPrivateCalling</span></span>|<span data-ttu-id="561b8-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="561b8-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="561b8-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="561b8-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="561b8-148">TeamsOnly o Islas</span><span class="sxs-lookup"><span data-stu-id="561b8-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="561b8-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-149">Enabled</span></span>|<span data-ttu-id="561b8-150">Habilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-150">Enabled</span></span>|<span data-ttu-id="561b8-151">Habilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-151">Enabled</span></span>|<span data-ttu-id="561b8-152">Habilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-152">Enabled</span></span>|
|<span data-ttu-id="561b8-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="561b8-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="561b8-154">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-154">Disabled</span></span>|<span data-ttu-id="561b8-155">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-155">Disabled</span></span>|<span data-ttu-id="561b8-156">Habilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-156">Enabled</span></span>|<span data-ttu-id="561b8-157">Habilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-157">Enabled</span></span>|
|<span data-ttu-id="561b8-158">SfBWithTeamsCollab o SfBOnly</span><span class="sxs-lookup"><span data-stu-id="561b8-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="561b8-159">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-159">Disabled</span></span>|<span data-ttu-id="561b8-160">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-160">Disabled</span></span>|<span data-ttu-id="561b8-161">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-161">Disabled</span></span>|<span data-ttu-id="561b8-162">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="561b8-162">Disabled</span></span>|
||||||

<span data-ttu-id="561b8-163">Al usar PowerShell, el cmdlet comprueba la configuración de la configuración correspondiente en `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si TeamsUpgradePolicy reemplazaría dicha configuración y, si es así, se proporciona un mensaje informativo en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="561b8-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="561b8-164">Como se ha indicado anteriormente, ya no es necesario establecer estas otras configuraciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="561b8-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="561b8-165">A continuación se muestra un ejemplo de la apariencia de la advertencia de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="561b8-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="561b8-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="561b8-166">Related topics</span></span>

[<span data-ttu-id="561b8-167">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="561b8-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)
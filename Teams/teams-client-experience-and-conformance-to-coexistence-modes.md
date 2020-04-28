---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Obtenga más información sobre la experiencia del cliente de Teams y la conformidad con los modos de coexistencia (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903365"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="09214-103">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="09214-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="09214-104">El propósito de los modos de coexistencia de Skype empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible a los usuarios finales a medida que las organizaciones pasan de Skype empresarial a teams.</span><span class="sxs-lookup"><span data-stu-id="09214-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="09214-105">En el caso de una organización que se desplaza a Teams, el modo de **solo equipos** es el destino final de cada usuario, aunque no es necesario que todos los usuarios le asignen **solo equipos** (o cualquier otro modo) al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="09214-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="09214-106">Antes de que los usuarios alcanzaran el modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de coexistencia de Skype empresarial para garantizar una comunicación predecible entre los usuarios que **solo sean equipos** y aquellos que aún no lo están.</span><span class="sxs-lookup"><span data-stu-id="09214-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="09214-107">Cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial, todas las conversaciones y llamadas entrantes se enrutan al cliente de Skype empresarial del usuario.</span><span class="sxs-lookup"><span data-stu-id="09214-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="09214-108">Para evitar la confusión del usuario final y garantizar el enrutamiento adecuado, la funcionalidad de llamadas y chats en el cliente de equipos está deshabilitada cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="09214-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="09214-109">De forma similar, la programación de reuniones de Teams se deshabilita de forma explícita cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab, y se habilita de forma explícita cuando un usuario está en el modo de SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="09214-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="09214-110">Puesto que la presencia es una indicación de la posibilidad de comunicarse mediante chats y llamadas, cuando las llamadas y los chats están deshabilitadas, la presencia automática en Teams (es decir, la visualización de la propia presencia en el cliente de equipos en la imagen del usuario) también se oculta.</span><span class="sxs-lookup"><span data-stu-id="09214-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="09214-111">Cómo cambia la funcionalidad disponible en el cliente de Teams según el modo</span><span class="sxs-lookup"><span data-stu-id="09214-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="09214-112">La funcionalidad disponible en Teams depende del modo de coexistencia del usuario, establecido por TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="09214-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="09214-113">En la tabla siguiente se resume el comportamiento:</span><span class="sxs-lookup"><span data-stu-id="09214-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="09214-114">Modo de efectividad del usuario</span><span class="sxs-lookup"><span data-stu-id="09214-114">User's effective mode</span></span>|<span data-ttu-id="09214-115">Experiencia en el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="09214-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="09214-116">Cualquier modo de Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="09214-116">Any Skype for Business mode</span></span>|<span data-ttu-id="09214-117">Las llamadas, la conversación y la presencia automática están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="09214-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="09214-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="09214-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="09214-119">Programación de reuniones disponible</span><span class="sxs-lookup"><span data-stu-id="09214-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="09214-120">SfBWithTeamsCollab o SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="09214-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="09214-121">La programación de reuniones no está disponible</span><span class="sxs-lookup"><span data-stu-id="09214-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="09214-122">En las siguientes capturas de pantallas se muestra la diferencia entre los **equipos solo** o el modo **islas** y todos los demás modos.</span><span class="sxs-lookup"><span data-stu-id="09214-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="09214-123">Tenga en cuenta que los iconos de llamadas y chats están disponibles de forma predeterminada con **solo equipos** o con el modo **islas** (captura de pantalla izquierda), pero no con los otros modos (captura de pantalla derecha):</span><span class="sxs-lookup"><span data-stu-id="09214-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Una comparación en paralelo de los modos de Teams](media/teams-mode-comparison.png)

<span data-ttu-id="09214-125">Además, la presencia automática no está disponible en los otros modos, tal y como se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="09214-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Captura de pantalla de la presencia propia en las reuniones primero](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="09214-127">**Nota:**
<sup>1</sup> en este momento, SfBwithTeamsCollab y SfBOnly se comportan de la misma forma, pero el propósito es que el modo SfBOnly también deshabilite la funcionalidad de canales y archivos en Teams.</span><span class="sxs-lookup"><span data-stu-id="09214-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="09214-128">En el medio, los canales se pueden ocultar con la Directiva de permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="09214-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="09214-129">Impacto del modo en otras configuraciones de Directiva</span><span class="sxs-lookup"><span data-stu-id="09214-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="09214-130">Como se describe anteriormente, el modo de coexistencia del usuario afecta a la funcionalidad que está disponible en el cliente de equipos del usuario.</span><span class="sxs-lookup"><span data-stu-id="09214-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="09214-131">Esto significa que el valor de MODE puede tener prioridad sobre el valor de otras configuraciones de Directiva, según el modo.</span><span class="sxs-lookup"><span data-stu-id="09214-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="09214-132">En concreto, el modo de coexistencia afecta al hecho de que se hayan respetado las siguientes configuraciones de directiva:</span><span class="sxs-lookup"><span data-stu-id="09214-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="09214-133">**Modalidad (aplicación)**</span><span class="sxs-lookup"><span data-stu-id="09214-133">**Modality (App)**</span></span>|<span data-ttu-id="09214-134">**Policy. setting**</span><span class="sxs-lookup"><span data-stu-id="09214-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="09214-135">Chat</span><span class="sxs-lookup"><span data-stu-id="09214-135">Chat</span></span>|<span data-ttu-id="09214-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="09214-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="09214-137">Llamadas</span><span class="sxs-lookup"><span data-stu-id="09214-137">Calling</span></span>|<span data-ttu-id="09214-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="09214-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="09214-139">Programación de reuniones</span><span class="sxs-lookup"><span data-stu-id="09214-139">Meeting scheduling</span></span>|<span data-ttu-id="09214-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09214-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="09214-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09214-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="09214-142">Los administradores *no* necesitan establecer explícitamente estas configuraciones de directiva al usar el modo de coexistencia, pero es importante comprender que esta configuración se comporta de la siguiente manera de forma eficaz para un modo determinado.</span><span class="sxs-lookup"><span data-stu-id="09214-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="09214-143">Modo</span><span class="sxs-lookup"><span data-stu-id="09214-143">Mode</span></span>|<span data-ttu-id="09214-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="09214-144">AllowUserChat</span></span>|<span data-ttu-id="09214-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="09214-145">AllowPrivateCalling</span></span>|<span data-ttu-id="09214-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09214-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="09214-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09214-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="09214-148">TeamsOnly o islas</span><span class="sxs-lookup"><span data-stu-id="09214-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="09214-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="09214-149">Enabled</span></span>|<span data-ttu-id="09214-150">Habilitado</span><span class="sxs-lookup"><span data-stu-id="09214-150">Enabled</span></span>|<span data-ttu-id="09214-151">Habilitado</span><span class="sxs-lookup"><span data-stu-id="09214-151">Enabled</span></span>|<span data-ttu-id="09214-152">Habilitado</span><span class="sxs-lookup"><span data-stu-id="09214-152">Enabled</span></span>|
|<span data-ttu-id="09214-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="09214-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="09214-154">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="09214-154">Disabled</span></span>|<span data-ttu-id="09214-155">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="09214-155">Disabled</span></span>|<span data-ttu-id="09214-156">Habilitado</span><span class="sxs-lookup"><span data-stu-id="09214-156">Enabled</span></span>|<span data-ttu-id="09214-157">Habilitado</span><span class="sxs-lookup"><span data-stu-id="09214-157">Enabled</span></span>|
|<span data-ttu-id="09214-158">SfBWithTeamsCollab o SfBOnly</span><span class="sxs-lookup"><span data-stu-id="09214-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="09214-159">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="09214-159">Disabled</span></span>|<span data-ttu-id="09214-160">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="09214-160">Disabled</span></span>|<span data-ttu-id="09214-161">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="09214-161">Disabled</span></span>|<span data-ttu-id="09214-162">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="09214-162">Disabled</span></span>|
||||||

<span data-ttu-id="09214-163">Al usar PowerShell, el `Grant-CsTeamsUpgradePolicy` cmdlet comprueba la configuración de los valores correspondientes en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si esa configuración sería reemplazada por TeamsUpgradePolicy y, si es así, se proporciona un mensaje informativo en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09214-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="09214-164">Como se indicó anteriormente, ya no es necesario establecer estas otras configuraciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="09214-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="09214-165">A continuación se muestra un ejemplo del aspecto de la advertencia de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="09214-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="09214-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="09214-166">Related topics</span></span>

[<span data-ttu-id="09214-167">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="09214-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)





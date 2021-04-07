---
title: Administrar directivas de reunión para participantes e invitados
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de directiva de reunión en Teams para participantes e invitados.
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598756"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="69b6b-103">Configuración de la directiva de reuniones: participantes e invitados</span><span class="sxs-lookup"><span data-stu-id="69b6b-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="69b6b-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="69b6b-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="69b6b-105">Esta configuración controla qué participantes de la reunión se quedan en la sala de espera antes de ser admitidos en la reunión y qué nivel de participación se les permite.</span><span class="sxs-lookup"><span data-stu-id="69b6b-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="69b6b-106">Permitir que los usuarios anónimos inicien una reunión</span><span class="sxs-lookup"><span data-stu-id="69b6b-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="69b6b-107">Admitir automáticamente usuarios</span><span class="sxs-lookup"><span data-stu-id="69b6b-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="69b6b-108">Permitir que los usuarios de acceso telefónico omitan la sala de espera</span><span class="sxs-lookup"><span data-stu-id="69b6b-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="69b6b-109">Activar subtítulos en directo</span><span class="sxs-lookup"><span data-stu-id="69b6b-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="69b6b-110">Permitir el chat en las reuniones</span><span class="sxs-lookup"><span data-stu-id="69b6b-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="69b6b-111">Las opciones para unirse a una reunión pueden variar en función de la configuración de cada grupo de Teams y del método de conexión.</span><span class="sxs-lookup"><span data-stu-id="69b6b-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="69b6b-112">Si el grupo tiene audioconferencia y la usa para conectarse, consulte [Audioconferencia](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="69b6b-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="69b6b-113">Si el grupo de Teams no tiene ninguna Audioconferencia, consulte [Unirse a una reunión en Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span><span class="sxs-lookup"><span data-stu-id="69b6b-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="69b6b-114">Permitir que los usuarios anónimos inicien una reunión</span><span class="sxs-lookup"><span data-stu-id="69b6b-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="69b6b-115">Esta configuración es una directiva por organizador que permite reuniones de conferencias de acceso telefónico local sin líderes.</span><span class="sxs-lookup"><span data-stu-id="69b6b-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="69b6b-116">Esta configuración controla si los usuarios de acceso por marcado pueden unirse a la reunión sin que asista un usuario autenticado de la organización.</span><span class="sxs-lookup"><span data-stu-id="69b6b-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="69b6b-117">De forma predeterminada, esta configuración está desactivada, lo que significa que los usuarios de acceso telefónico local esperarán en la sala de espera hasta que un usuario autenticado de la organización se una a la reunión.</span><span class="sxs-lookup"><span data-stu-id="69b6b-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="69b6b-118">Si esta opción está desactivada y un usuario de marcado se une primero a la reunión y se le ubica en la sala de espera, el usuario de la organización debe unirse a la reunión con un cliente de Teams para admitir al usuario de la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="69b6b-119">No hay ningún control de sala de espera disponible para los usuarios con acceso de marcado.</span><span class="sxs-lookup"><span data-stu-id="69b6b-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="69b6b-120">Admitir automáticamente usuarios</span><span class="sxs-lookup"><span data-stu-id="69b6b-120">Automatically admit people</span></span>

<span data-ttu-id="69b6b-121">Esta es una directiva por organizador.</span><span class="sxs-lookup"><span data-stu-id="69b6b-121">This is a per-organizer policy.</span></span> <span data-ttu-id="69b6b-122">Esta configuración controla si los usuarios pueden unirse a una reunión directamente o esperar en la sala de espera hasta que un usuario autenticado los admita.</span><span class="sxs-lookup"><span data-stu-id="69b6b-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="69b6b-123">Esta configuración no se aplica a los usuarios de marcado.</span><span class="sxs-lookup"><span data-stu-id="69b6b-123">This setting does not apply to dial-in users.</span></span>

![Captura de pantalla que muestra una reunión con un usuario en la sala de espera](media/meeting-policies-lobby.png)

 <span data-ttu-id="69b6b-125">Los organizadores de la reunión pueden hacer clic en las **Opciones de reunión** en la invitación a la reunión para cambiar esta configuración en cada una de las reuniones programadas.</span><span class="sxs-lookup"><span data-stu-id="69b6b-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="69b6b-126">En las opciones de reunión, la configuración está etiquetada como "Quién puede omitir la sala de espera".</span><span class="sxs-lookup"><span data-stu-id="69b6b-126">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="69b6b-127">Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y las reuniones anteriores en las que el usuario no haya modificado las opciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="69b6b-127">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="69b6b-128">Valor de configuración</span><span class="sxs-lookup"><span data-stu-id="69b6b-128">Setting value</span></span>  |<span data-ttu-id="69b6b-129">Comportamiento para unirse</span><span class="sxs-lookup"><span data-stu-id="69b6b-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="69b6b-130">**Todos**</span><span class="sxs-lookup"><span data-stu-id="69b6b-130">**Everyone**</span></span>   |<span data-ttu-id="69b6b-131">Todos los participantes se unen a la reunión directamente sin tener que esperar en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="69b6b-132">Esto incluye a los usuarios autenticados, los usuarios externos de organizaciones de confianza (federados), los invitados y los usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="69b6b-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="69b6b-133">**Todos los usuarios de su organización y de organizaciones federadas**</span><span class="sxs-lookup"><span data-stu-id="69b6b-133">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="69b6b-134">Los usuarios autenticados en la organización, incluidos los usuarios invitados y los usuarios de las organizaciones de confianza, pueden unirse a la reunión directamente sin tener que esperar en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-134">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="69b6b-135">Los usuarios anónimos esperan en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="69b6b-136">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="69b6b-136">**Everyone in your organization**</span></span>    |<span data-ttu-id="69b6b-137">Los usuarios autenticados en la organización, incluidos los usuarios invitados, pueden unirse a la reunión directamente sin tener que esperar en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-137">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="69b6b-138">Los usuarios de organizaciones de confianza y los usuarios anónimos aguardan en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-138">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="69b6b-139">Esta configuración es la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69b6b-139">This is the default setting.</span></span>           |
|<span data-ttu-id="69b6b-140">**Solo organizador**</span><span class="sxs-lookup"><span data-stu-id="69b6b-140">**Organizer only**</span></span>    |<span data-ttu-id="69b6b-141">Solo los organizadores de la reunión se pueden unir a la reunión directamente sin tener que esperar en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-141">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="69b6b-142">Todos los usuarios, incluidos los usuarios autenticados de la organización, los invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="69b6b-142">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="69b6b-143">Permitir que los usuarios de acceso telefónico omitan la sala de espera</span><span class="sxs-lookup"><span data-stu-id="69b6b-143">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="69b6b-144">Esta es una directiva por organizador.</span><span class="sxs-lookup"><span data-stu-id="69b6b-144">This is a per-organizer policy.</span></span> <span data-ttu-id="69b6b-145">Esta opción controla si las personas que llaman por teléfono se unen a la reunión directamente o si aguardan en la sala de espera, independientemente de la configuración de **Admitir participantes automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="69b6b-145">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="69b6b-146">Esta configuración está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69b6b-146">By default, this setting is turned off.</span></span> <span data-ttu-id="69b6b-147">Cuando esta configuración está desactivada, los usuarios de acceso telefónico local esperarán en la sala de espera hasta que un usuario de la organización se una a la reunión con un cliente de Teams y los admita.</span><span class="sxs-lookup"><span data-stu-id="69b6b-147">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="69b6b-148">Cuando esta opción está activada, los usuarios de marcado se unirán automáticamente a la reunión cuando un usuario de la organización se una.</span><span class="sxs-lookup"><span data-stu-id="69b6b-148">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="69b6b-149">Si un usuario de marcado se une a la reunión antes de que lo haga un usuario de la organización, el primero aguardará en la sala de espera hasta que el usuario de la organización se incorpore a la reunión con un cliente de Teams y le acepte.</span><span class="sxs-lookup"><span data-stu-id="69b6b-149">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="69b6b-150">Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y las reuniones anteriores en las que el usuario no haya modificado las opciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="69b6b-150">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="69b6b-151">Activar subtítulos en directo</span><span class="sxs-lookup"><span data-stu-id="69b6b-151">Enable live captions</span></span>

<span data-ttu-id="69b6b-152">Esta configuración es una directiva por usuario y se aplica durante una reunión.</span><span class="sxs-lookup"><span data-stu-id="69b6b-152">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="69b6b-153">Esta configuración controla si la opción **Activar los subtítulos en directo** está disponible para que el usuario active y desactive los subtítulos en directo en las reuniones a las que asista.</span><span class="sxs-lookup"><span data-stu-id="69b6b-153">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![Captura de pantalla que muestra la opción Activar subtítulos en directo](media/meeting-policies-live-captions.png)

|<span data-ttu-id="69b6b-155">Valor de configuración</span><span class="sxs-lookup"><span data-stu-id="69b6b-155">Setting value</span></span> |<span data-ttu-id="69b6b-156">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="69b6b-156">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="69b6b-157">**Deshabilitados pero el usuario puede invalidarlos**</span><span class="sxs-lookup"><span data-stu-id="69b6b-157">**Disabled but the user can override**</span></span>     | <span data-ttu-id="69b6b-158">Los subtítulos en directo no se activan automáticamente durante una reunión.</span><span class="sxs-lookup"><span data-stu-id="69b6b-158">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="69b6b-159">El usuario verá la opción **Activar subtítulos en directo** en el menú de desbordamiento **(...)** para activarlos.</span><span class="sxs-lookup"><span data-stu-id="69b6b-159">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="69b6b-160">Esta configuración es la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69b6b-160">This is the default setting.</span></span> |
|<span data-ttu-id="69b6b-161">**Deshabilitado**</span><span class="sxs-lookup"><span data-stu-id="69b6b-161">**Disabled**</span></span>     | <span data-ttu-id="69b6b-162">Durante una reunión, los subtítulos en directo se deshabilitan para el usuario.</span><span class="sxs-lookup"><span data-stu-id="69b6b-162">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="69b6b-163">El usuario no tiene la opción de activarlos.</span><span class="sxs-lookup"><span data-stu-id="69b6b-163">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="69b6b-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="69b6b-164"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="69b6b-165">Permitir el chat en las reuniones</span><span class="sxs-lookup"><span data-stu-id="69b6b-165">Allow chat in meetings</span></span>

<span data-ttu-id="69b6b-166">Esta configuración es una configuración por participante.</span><span class="sxs-lookup"><span data-stu-id="69b6b-166">This setting is a per-participant setting.</span></span> <span data-ttu-id="69b6b-167">Esta configuración controla si se permite el chat de reunión en la reunión del usuario.</span><span class="sxs-lookup"><span data-stu-id="69b6b-167">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="69b6b-168"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="69b6b-168"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="69b6b-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="69b6b-169">Related topics</span></span>

- [<span data-ttu-id="69b6b-170">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="69b6b-170">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="69b6b-171">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="69b6b-171">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="69b6b-172">Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess</span><span class="sxs-lookup"><span data-stu-id="69b6b-172">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)

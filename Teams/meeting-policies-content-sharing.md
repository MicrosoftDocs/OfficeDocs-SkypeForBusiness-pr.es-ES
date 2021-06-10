---
title: Administrar directivas de reunión para compartir contenido
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
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de directiva de reunión en Teams para el uso compartido de contenido.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598772"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="b0f91-103">Configuración de la directiva de reunión. Uso compartido de contenido</span><span class="sxs-lookup"><span data-stu-id="b0f91-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="b0f91-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f91-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="b0f91-105">En este artículo se describen las siguientes opciones de directiva de reunión relacionadas con el uso compartido de contenido:</span><span class="sxs-lookup"><span data-stu-id="b0f91-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="b0f91-106">Modo de uso compartido de pantalla</span><span class="sxs-lookup"><span data-stu-id="b0f91-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="b0f91-107">Permitir a un participante ceder o solicitar el control</span><span class="sxs-lookup"><span data-stu-id="b0f91-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="b0f91-108">Permitir a un participante externo ceder o solicitar el control</span><span class="sxs-lookup"><span data-stu-id="b0f91-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="b0f91-109">Permitir uso compartido en PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b0f91-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="b0f91-110">Permitir pizarra</span><span class="sxs-lookup"><span data-stu-id="b0f91-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="b0f91-111">Permitir notas compartidas</span><span class="sxs-lookup"><span data-stu-id="b0f91-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="b0f91-112">Modo de uso compartido de la pantalla</span><span class="sxs-lookup"><span data-stu-id="b0f91-112">Screen sharing mode</span></span>

<span data-ttu-id="b0f91-113">Esta configuración es una combinación de directivas por organizador y por usuario.</span><span class="sxs-lookup"><span data-stu-id="b0f91-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="b0f91-114">Esta configuración controla si el escritorio y el uso compartido de ventanas están permitidos en la reunión del usuario.</span><span class="sxs-lookup"><span data-stu-id="b0f91-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="b0f91-115">Los participantes de la reunión a los que no se les ha asignado ninguna directiva (por ejemplo, los participantes anónimos, invitados, B2B y federados) heredan la directiva del organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="b0f91-116">Valor de configuración</span><span class="sxs-lookup"><span data-stu-id="b0f91-116">Setting value</span></span> |<span data-ttu-id="b0f91-117">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="b0f91-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="b0f91-118">**Toda la pantalla**</span><span class="sxs-lookup"><span data-stu-id="b0f91-118">**Entire screen**</span></span>    | <span data-ttu-id="b0f91-119">Se permiten en la reunión el uso compartido de escritorio completo y de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b0f91-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="b0f91-120">**Aplicación única**</span><span class="sxs-lookup"><span data-stu-id="b0f91-120">**Single application**</span></span>   | <span data-ttu-id="b0f91-121">El uso compartido de aplicaciones se permite en la reunión</span><span class="sxs-lookup"><span data-stu-id="b0f91-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="b0f91-122">**Deshabilitado**</span><span class="sxs-lookup"><span data-stu-id="b0f91-122">**Disabled**</span></span>     |<span data-ttu-id="b0f91-123">El uso compartido de la pantalla y el uso compartido de aplicaciones se desactivaron en la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="b0f91-124">Veamos el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0f91-124">Let's look at the following example.</span></span>

|<span data-ttu-id="b0f91-125">Usuario</span><span class="sxs-lookup"><span data-stu-id="b0f91-125">User</span></span> |<span data-ttu-id="b0f91-126">Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="b0f91-126">Meeting policy</span></span> |<span data-ttu-id="b0f91-127">Modo de uso compartido de la pantalla</span><span class="sxs-lookup"><span data-stu-id="b0f91-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b0f91-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="b0f91-128">Daniela</span></span>  | <span data-ttu-id="b0f91-129">Global</span><span class="sxs-lookup"><span data-stu-id="b0f91-129">Global</span></span>   | <span data-ttu-id="b0f91-130">Toda la pantalla</span><span class="sxs-lookup"><span data-stu-id="b0f91-130">Entire screen</span></span> |
|<span data-ttu-id="b0f91-131">Amanda</span><span class="sxs-lookup"><span data-stu-id="b0f91-131">Amanda</span></span>   | <span data-ttu-id="b0f91-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b0f91-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="b0f91-133">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="b0f91-133">Disabled</span></span> |

<span data-ttu-id="b0f91-134">Las reuniones hospedadas por Daniela permiten a los participantes de la reunión compartir toda la pantalla o una aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="b0f91-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="b0f91-135">Si Amanda se une a la reunión de Daniela, Amanda no puede compartir su pantalla ni una aplicación específica, ya que esta configuración de directiva está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="b0f91-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="b0f91-136">En las reuniones hospedadas por Amanda no se permite a nadie compartir su pantalla o una sola aplicación, independientemente de la directiva de modo de uso compartido de la pantalla que se les asignó.</span><span class="sxs-lookup"><span data-stu-id="b0f91-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="b0f91-137">Por lo tanto, Daniela no puede compartir su pantalla ni una sola aplicación en las reuniones de Amanda.</span><span class="sxs-lookup"><span data-stu-id="b0f91-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="b0f91-138">Actualmente, los usuarios no pueden reproducir vídeo ni compartir su pantalla en una reunión de Teams si usan Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="b0f91-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="b0f91-139">Permitir a un participante ceder o solicitar el control</span><span class="sxs-lookup"><span data-stu-id="b0f91-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="b0f91-140">Esta configuración es una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="b0f91-140">This setting is a per-user policy.</span></span> <span data-ttu-id="b0f91-141">Esta configuración controla si el usuario puede ceder el control de la ventana o del escritorio compartido a otros participantes de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="b0f91-142">Para ceder el control, pase el cursor por la parte superior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="b0f91-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="b0f91-143">Si esta configuración está activada para el usuario, la opción **Ceder el control** se mostrará en la barra superior de una sesión compartida.</span><span class="sxs-lookup"><span data-stu-id="b0f91-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![Captura de pantalla que muestra la opción Ceder el control](media/meeting-policies-give-control.png)

<span data-ttu-id="b0f91-145">Si la configuración está desactivada para el usuario, la opción **Ceder el control** no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="b0f91-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![Captura de pantalla que muestra que la opción Ceder el control no está disponible](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="b0f91-147">Veamos el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0f91-147">Let's look at the following example.</span></span>

|<span data-ttu-id="b0f91-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="b0f91-148">User</span></span> |<span data-ttu-id="b0f91-149">Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="b0f91-149">Meeting policy</span></span>  |<span data-ttu-id="b0f91-150">Permitir a un participante ceder o solicitar el control</span><span class="sxs-lookup"><span data-stu-id="b0f91-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b0f91-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="b0f91-151">Daniela</span></span>   | <span data-ttu-id="b0f91-152">Global</span><span class="sxs-lookup"><span data-stu-id="b0f91-152">Global</span></span>   | <span data-ttu-id="b0f91-153">Activado</span><span class="sxs-lookup"><span data-stu-id="b0f91-153">On</span></span>       |
|<span data-ttu-id="b0f91-154">Babek</span><span class="sxs-lookup"><span data-stu-id="b0f91-154">Babek</span></span>    | <span data-ttu-id="b0f91-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b0f91-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b0f91-156">Desactivado</span><span class="sxs-lookup"><span data-stu-id="b0f91-156">Off</span></span>   |

<span data-ttu-id="b0f91-157">Daniela puede dar el control del escritorio o ventana compartidos a otros participantes en una reunión organizada por Babek.</span><span class="sxs-lookup"><span data-stu-id="b0f91-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="b0f91-158">Sin embargo, Babek no puede ceder el control a otros participantes.</span><span class="sxs-lookup"><span data-stu-id="b0f91-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="b0f91-159">Si desea usar PowerShell para controlar quién puede ceder el control o aceptar solicitudes de control, use el cmdlet AllowParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="b0f91-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="b0f91-160">Para ceder y tomar el control del contenido compartido durante el uso compartido, ambas partes deben usar el cliente de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="b0f91-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="b0f91-161">El control no es compatible cuando cualquiera de las partes ejecuta Teams en un explorador.</span><span class="sxs-lookup"><span data-stu-id="b0f91-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="b0f91-162">Esto se debe a una limitación técnica que planeamos solucionar.</span><span class="sxs-lookup"><span data-stu-id="b0f91-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="b0f91-163">Permitir a un participante externo ceder o solicitar el control</span><span class="sxs-lookup"><span data-stu-id="b0f91-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="b0f91-164">Esta configuración es una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="b0f91-164">This setting is a per-user policy.</span></span> <span data-ttu-id="b0f91-165">Si una organización ha establecido esta directiva para un usuario no controla lo que los participantes externos pueden hacer, independientemente de lo que haya establecido el organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="b0f91-166">Lo que controla este parámetro es si los participantes externos pueden recibir o solicitar el control de la pantalla que comparten, en función de lo que la persona que comparte haya establecido en las directivas de reuniones de su organización.</span><span class="sxs-lookup"><span data-stu-id="b0f91-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="b0f91-167">Los participantes externos en reuniones de Teams se pueden categorizar de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b0f91-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="b0f91-168">Usuario anónimo</span><span class="sxs-lookup"><span data-stu-id="b0f91-168">Anonymous user</span></span>
- <span data-ttu-id="b0f91-169">Usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="b0f91-169">Guest users</span></span>  
- <span data-ttu-id="b0f91-170">Usuario B2B</span><span class="sxs-lookup"><span data-stu-id="b0f91-170">B2B user</span></span>
- <span data-ttu-id="b0f91-171">Usuario federado</span><span class="sxs-lookup"><span data-stu-id="b0f91-171">Federated user</span></span>  

<span data-ttu-id="b0f91-172">Que los usuarios federados puedan ceder el control a los usuarios externos mientras realicen un uso compartido se controla mediante la configuración **Permitir a un participante externo ceder o solicitar el control** de su organización.</span><span class="sxs-lookup"><span data-stu-id="b0f91-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="b0f91-173">Si desea usar PowerShell para controlar si los participantes externos pueden ceder el control o aceptar solicitudes de control, use el cmdlet AllowExternalParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="b0f91-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="b0f91-174">Permitir uso compartido de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b0f91-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="b0f91-175">Esta es una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="b0f91-175">This is a per-user policy.</span></span> <span data-ttu-id="b0f91-176">Esta configuración controla si el usuario puede compartir diapositivas de PowerPoint en una reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="b0f91-177">Los usuarios externos, incluidos los usuarios anónimos, invitados y federados, heredan la directiva del organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="b0f91-178">Veamos el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0f91-178">Let's look at the following example.</span></span>

|<span data-ttu-id="b0f91-179">Usuario</span><span class="sxs-lookup"><span data-stu-id="b0f91-179">User</span></span> |<span data-ttu-id="b0f91-180">Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="b0f91-180">Meeting policy</span></span>  |<span data-ttu-id="b0f91-181">Permitir uso compartido de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b0f91-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b0f91-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="b0f91-182">Daniela</span></span>   | <span data-ttu-id="b0f91-183">Global</span><span class="sxs-lookup"><span data-stu-id="b0f91-183">Global</span></span>   | <span data-ttu-id="b0f91-184">Activado</span><span class="sxs-lookup"><span data-stu-id="b0f91-184">On</span></span>       |
|<span data-ttu-id="b0f91-185">Amanda</span><span class="sxs-lookup"><span data-stu-id="b0f91-185">Amanda</span></span>   | <span data-ttu-id="b0f91-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b0f91-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b0f91-187">Desactivado</span><span class="sxs-lookup"><span data-stu-id="b0f91-187">Off</span></span>   |

<span data-ttu-id="b0f91-188">Amanda no puede compartir los conjuntos de diapositivas de PowerPoint en las reuniones aunque sea la organizadora.</span><span class="sxs-lookup"><span data-stu-id="b0f91-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="b0f91-189">Daniela puede compartir conjuntos de diapositivas de PowerPoint incluso si la reunión está organizada por Amanda.</span><span class="sxs-lookup"><span data-stu-id="b0f91-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="b0f91-190">Amanda puede ver los conjuntos de diapositivas de PowerPoint compartidos por otros usuarios de la reunión, aunque no pueda compartir conjuntos de diapositivas de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="b0f91-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="b0f91-191">Permitir pizarra</span><span class="sxs-lookup"><span data-stu-id="b0f91-191">Allow whiteboard</span></span>

<span data-ttu-id="b0f91-192">Esta configuración es una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="b0f91-192">This setting is a per-user policy.</span></span> <span data-ttu-id="b0f91-193">Esta configuración controla si un usuario puede compartir la pizarra en una reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="b0f91-194">Los usuarios externos, incluidos los usuarios anónimos, B2B y federados, heredan la directiva del organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="b0f91-195">Veamos el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0f91-195">Let's look at the following example.</span></span>

|<span data-ttu-id="b0f91-196">Usuario</span><span class="sxs-lookup"><span data-stu-id="b0f91-196">User</span></span> |<span data-ttu-id="b0f91-197">Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="b0f91-197">Meeting policy</span></span>  |<span data-ttu-id="b0f91-198">Permitir pizarra</span><span class="sxs-lookup"><span data-stu-id="b0f91-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b0f91-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="b0f91-199">Daniela</span></span>   | <span data-ttu-id="b0f91-200">Global</span><span class="sxs-lookup"><span data-stu-id="b0f91-200">Global</span></span>   | <span data-ttu-id="b0f91-201">Activado</span><span class="sxs-lookup"><span data-stu-id="b0f91-201">On</span></span>       |
|<span data-ttu-id="b0f91-202">Amanda</span><span class="sxs-lookup"><span data-stu-id="b0f91-202">Amanda</span></span>   | <span data-ttu-id="b0f91-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b0f91-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b0f91-204">Desactivado</span><span class="sxs-lookup"><span data-stu-id="b0f91-204">Off</span></span>   |

<span data-ttu-id="b0f91-205">Amanda no puede compartir la pizarra en una reunión, aunque sea la organizadora de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="b0f91-206">Daniela puede compartir la pizarra incluso si la reunión está organizada por Amanda.</span><span class="sxs-lookup"><span data-stu-id="b0f91-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="b0f91-207">Permitir notas compartidas</span><span class="sxs-lookup"><span data-stu-id="b0f91-207">Allow shared notes</span></span>

<span data-ttu-id="b0f91-208">Esta configuración es una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="b0f91-208">This setting is a per-user policy.</span></span> <span data-ttu-id="b0f91-209">Esta configuración controla si un usuario puede crear y compartir notas en una reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="b0f91-210">Los usuarios externos, incluidos los usuarios anónimos, B2B y federados, heredan la directiva del organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="b0f91-211">Actualmente, la pestaña **Notas de la reunión** solo es compatible con reuniones que tienen menos de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="b0f91-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="b0f91-212">Veamos el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0f91-212">Let's look at the following example.</span></span>

|<span data-ttu-id="b0f91-213">Usuario</span><span class="sxs-lookup"><span data-stu-id="b0f91-213">User</span></span> |<span data-ttu-id="b0f91-214">Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="b0f91-214">Meeting policy</span></span>  |<span data-ttu-id="b0f91-215">Permitir notas compartidas</span><span class="sxs-lookup"><span data-stu-id="b0f91-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b0f91-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="b0f91-216">Daniela</span></span>   | <span data-ttu-id="b0f91-217">Global</span><span class="sxs-lookup"><span data-stu-id="b0f91-217">Global</span></span>   | <span data-ttu-id="b0f91-218">Activado</span><span class="sxs-lookup"><span data-stu-id="b0f91-218">On</span></span>       |
|<span data-ttu-id="b0f91-219">Amanda</span><span class="sxs-lookup"><span data-stu-id="b0f91-219">Amanda</span></span>   | <span data-ttu-id="b0f91-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b0f91-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="b0f91-221">Desactivado</span><span class="sxs-lookup"><span data-stu-id="b0f91-221">Off</span></span> |

<span data-ttu-id="b0f91-222">Daniela puede tomar notas en las reuniones de Amanda, pero Amanda no puede tomar notas en ninguna reunión.</span><span class="sxs-lookup"><span data-stu-id="b0f91-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="b0f91-223">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b0f91-223">Related topics</span></span>

- [<span data-ttu-id="b0f91-224">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="b0f91-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b0f91-225">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="b0f91-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="b0f91-226">Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess</span><span class="sxs-lookup"><span data-stu-id="b0f91-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)

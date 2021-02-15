---
title: Experiencia de reunión de solo vista
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la experiencia de reunión solo vista de Teams para administradores, presentadores y asistentes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237460"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="562d1-103">Experiencia de reunión solo para la vista de Teams</span><span class="sxs-lookup"><span data-stu-id="562d1-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="562d1-104">La experiencia de reunión de solo lectura estará disponible a principios de marzo de 2021.</span><span class="sxs-lookup"><span data-stu-id="562d1-104">View-only meeting experience will be available in early March 2021.</span></span>

> [!Note]
> <span data-ttu-id="562d1-105">Hemos aumentado temporalmente la experiencia de solo vista para 20 000 asistentes, pero revertiremos la asistencia a 10 000 asistentes el 30 de junio de 2021.</span><span class="sxs-lookup"><span data-stu-id="562d1-105">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="562d1-106">Microsoft Teams permite que hasta 10 000 asistentes se unan a una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="562d1-106">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="562d1-107">Una vez que se haya alcanzado la capacidad de la reunión principal, se unirán otros asistentes con una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="562d1-107">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="562d1-108">Los asistentes que se unan a la reunión en primer lugar, hasta la capacidad de la reunión, recibirán la experiencia de reunión completa de Teams.</span><span class="sxs-lookup"><span data-stu-id="562d1-108">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="562d1-109">Pueden compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.</span><span class="sxs-lookup"><span data-stu-id="562d1-109">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="562d1-110">Los asistentes que se unan después de alcanzar la capacidad principal de la reunión tendrán una experiencia de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="562d1-110">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="562d1-111">Tenemos soporte móvil completo para Android y iOS para que un asistente se una.</span><span class="sxs-lookup"><span data-stu-id="562d1-111">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="562d1-112">El límite actual para el número de personas que pueden chatear y llamar a una reunión es 300 en EE. UU. y 250 en GCC, GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="562d1-112">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="562d1-113">La experiencia de solo vista está habilitada de forma predeterminada para cualquier organizador que tenga SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="562d1-113">The view-only experience is enabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="562d1-114">No es necesaria ninguna configuración o configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="562d1-114">No further configuration or setup is required.</span></span>

### <a name="disable-teams-view-only-experience"></a><span data-ttu-id="562d1-115">Deshabilitar la experiencia de solo lectura de Teams</span><span class="sxs-lookup"><span data-stu-id="562d1-115">Disable Teams view-only experience</span></span>

<span data-ttu-id="562d1-116">Los administradores pueden deshabilitar la experiencia de solo vista con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="562d1-116">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="562d1-117">En el futuro, también será posible que los administradores deshabilite la experiencia de solo lectura en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="562d1-117">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="562d1-118">Impacto para los usuarios</span><span class="sxs-lookup"><span data-stu-id="562d1-118">Impact to users</span></span>

<span data-ttu-id="562d1-119">La experiencia de un usuario variará en función de varios factores.</span><span class="sxs-lookup"><span data-stu-id="562d1-119">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="562d1-120">Cuando se haya alcanzado la capacidad de la reunión principal, un asistente no podrá unirse a la reunión si se cumple alguna de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="562d1-120">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="562d1-121">Un administrador ha deshabilitado la experiencia de solo vista de Teams.</span><span class="sxs-lookup"><span data-stu-id="562d1-121">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="562d1-122">El asistente no tiene permiso para omitir la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="562d1-122">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="562d1-123">Cuando se haya alcanzado la capacidad de la reunión principal, el organizador y los presentadores de la reunión verán un banner que les informará de que se ha alcanzado la capacidad de la reunión y que los nuevos asistentes se unirán a un asistente de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="562d1-123">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![El cliente de Teams y los desordenes de banner para organizadores y presentadores](media/chat-and-banner-message.png)

<span data-ttu-id="562d1-125">Cuando se haya alcanzado la capacidad de la reunión principal, los asistentes a la reunión recibirán una información en la pantalla antes de unirse de que se unen en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="562d1-125">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![la pantalla de antes de unirse a Teams y el mensaje para los participantes que les indica que se unirán en modo de solo lectura](media/view-only-pre-join-screen.png)

<span data-ttu-id="562d1-127">Si hay espacio, un usuario siempre se unirá a la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="562d1-127">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="562d1-128">Si la reunión principal alcanza la capacidad, y uno o más asistentes abandonan la reunión principal, la reunión principal tiene capacidad disponible.</span><span class="sxs-lookup"><span data-stu-id="562d1-128">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="562d1-129">Los asistentes que se unan (o vuelvan a unirse) a la reunión se unirán a la reunión principal hasta que llegue de nuevo a su capacidad.</span><span class="sxs-lookup"><span data-stu-id="562d1-129">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="562d1-130">Los asistentes que se encuentran en la experiencia de solo lectura no se promoverán automáticamente a la reunión principal y actualmente no pueden promoverse manualmente a la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="562d1-130">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="562d1-131">Si los roles de moderador/asistente no se han establecido, los espacios en la reunión principal se rellenan en función de su nombre.</span><span class="sxs-lookup"><span data-stu-id="562d1-131">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="562d1-132">Una vez que se haya alcanzado la capacidad de reunión, todos los demás usuarios se unirán con una experiencia de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="562d1-132">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="562d1-133">Impacto para los presentadores de la reunión</span><span class="sxs-lookup"><span data-stu-id="562d1-133">Impact to meeting presenters</span></span>

<span data-ttu-id="562d1-134">Reservaremos espacio en la reunión normal para los usuarios indicados explícitamente como presentadores en las opciones de la reunión.</span><span class="sxs-lookup"><span data-stu-id="562d1-134">We'll reserve space in the normal meeting for users explicitly indicated as presenters in the meeting options.</span></span> <span data-ttu-id="562d1-135">Si un moderador deja la reunión y, posteriormente, se une de nuevo a la reunión, se le permite entrar en la reunión como moderador.</span><span class="sxs-lookup"><span data-stu-id="562d1-135">If a presenter leaves and then later rejoins the meeting, they'll be let into the meeting as a presenter.</span></span>

<span data-ttu-id="562d1-136">Entre las limitaciones para los presentadores de reuniones se incluyen:</span><span class="sxs-lookup"><span data-stu-id="562d1-136">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="562d1-137">No tendrá ninguna información sobre el asistente de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="562d1-137">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="562d1-138">No se admite e-discovery para los asistentes solo para visualización.</span><span class="sxs-lookup"><span data-stu-id="562d1-138">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="562d1-139">Los usuarios no pueden ver solo a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="562d1-139">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="562d1-140">No puede quitar un asistente de solo vista de la reunión.</span><span class="sxs-lookup"><span data-stu-id="562d1-140">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="562d1-141">El número de asistentes solo reflejará las personas de la reunión y no las personas de la sala de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="562d1-141">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="562d1-142">Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="562d1-142">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="562d1-143">Experiencia para asistentes que solo pueden ver</span><span class="sxs-lookup"><span data-stu-id="562d1-143">Experience for view-only attendees</span></span>

<span data-ttu-id="562d1-144">La experiencia de solo vista de Teams permite a los asistentes:</span><span class="sxs-lookup"><span data-stu-id="562d1-144">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="562d1-145">Escuche a los participantes de la reunión principal de Teams.</span><span class="sxs-lookup"><span data-stu-id="562d1-145">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="562d1-146">Vea la fuente de vídeo del orador activo (si el orador activo comparte vídeo).</span><span class="sxs-lookup"><span data-stu-id="562d1-146">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="562d1-147">Ver el contenido que se comparte con la función compartir escritorio.</span><span class="sxs-lookup"><span data-stu-id="562d1-147">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="562d1-148">El asistente que solo ve no podrá experimentar las siguientes opciones en las reuniones:</span><span class="sxs-lookup"><span data-stu-id="562d1-148">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="562d1-149">Únase a la reunión si el asistente no tiene permiso para omitir la sala de espera en función de las directivas u opciones de la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="562d1-149">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="562d1-150">Únase a la sala de desbordamiento a través de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="562d1-150">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="562d1-151">Únase a la sala de desbordamiento a través de Microsoft Teams Room system o a través de los servicios cloud Video Interoperabilidad (CVI).</span><span class="sxs-lookup"><span data-stu-id="562d1-151">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="562d1-152">Únase a la sala de desbordamiento a través de la aplicación móvil Android de Teams.</span><span class="sxs-lookup"><span data-stu-id="562d1-152">Join the Overflow Room via the Teams Android mobile app.</span></span>
- <span data-ttu-id="562d1-153">Comparta su audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="562d1-153">Share their audio or video.</span></span>
- <span data-ttu-id="562d1-154">Ver o participar en el chat de la reunión.</span><span class="sxs-lookup"><span data-stu-id="562d1-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="562d1-155">Vea la fuente de vídeo de los participantes de la reunión a menos que sea el orador activo.</span><span class="sxs-lookup"><span data-stu-id="562d1-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="562d1-156">Vea los archivos de PowerPoint que se comparten con la funcionalidad de Uso compartido nativo de PowerPoint o con recursos compartidos de aplicaciones individuales (aparte del uso compartido de escritorio).</span><span class="sxs-lookup"><span data-stu-id="562d1-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="562d1-157">Limitaciones de características de solo vista</span><span class="sxs-lookup"><span data-stu-id="562d1-157">View-only feature limitations</span></span>

- <span data-ttu-id="562d1-158">Los asistentes que solo ven los subtítulos en directo, independientemente de la configuración de los subtítulos en directo para esa reunión.</span><span class="sxs-lookup"><span data-stu-id="562d1-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="562d1-159">En este momento, solo se admiten subtítulos en inglés.</span><span class="sxs-lookup"><span data-stu-id="562d1-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="562d1-160">Los asistentes solo para visualización serán compatibles con la tecnología de streaming.</span><span class="sxs-lookup"><span data-stu-id="562d1-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="562d1-161">Los asistentes de solo vista no se incluirán en el informe de asistencia.</span><span class="sxs-lookup"><span data-stu-id="562d1-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="562d1-162">Solo los asistentes a la vista tendrán una única experiencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="562d1-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="562d1-163">Pueden ver el orador activo o el contenido que se comparte, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="562d1-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="562d1-164">Actualmente no se admiten diseños  **de galería,** **galería grande** o modo conjunto para los asistentes que solo pueden verlos.</span><span class="sxs-lookup"><span data-stu-id="562d1-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="562d1-165">Los asistentes que solo pueden ver no tendrán la misma latencia que un asistente normal.</span><span class="sxs-lookup"><span data-stu-id="562d1-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="562d1-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="562d1-166"><sup>1</sup></span></span>

  <span data-ttu-id="562d1-167"><sup>1</sup> Los asistentes que solo pueden ver estarán en una demora de audio y vídeo de 30 segundos en la reunión.</span><span class="sxs-lookup"><span data-stu-id="562d1-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="562d1-168">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="562d1-168">Related topics</span></span>

- [<span data-ttu-id="562d1-169">Complemento de comunicaciones avanzado para Teams</span><span class="sxs-lookup"><span data-stu-id="562d1-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="562d1-170">Especificaciones y límites de Teams</span><span class="sxs-lookup"><span data-stu-id="562d1-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

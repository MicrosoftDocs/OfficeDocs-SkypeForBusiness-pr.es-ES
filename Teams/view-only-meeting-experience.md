---
title: Experiencia de reunión solo vista
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875060"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="015f6-103">Experiencia de reunión solo vista de Teams</span><span class="sxs-lookup"><span data-stu-id="015f6-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="015f6-104">Las transmisiones solo vistas están disponibles en Microsoft 365 E3/E5 y Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="015f6-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="015f6-105">Esta característica se habilitará el 1 de marzo de 2021 como desactivado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="015f6-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="015f6-106">La característica de Microsoft 365 Government Community Cloud (GCC) comenzará a realizarse a finales de marzo de 2021.</span><span class="sxs-lookup"><span data-stu-id="015f6-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="015f6-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span><span class="sxs-lookup"><span data-stu-id="015f6-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="015f6-108">Debe cambiar la directiva predeterminada después de esa fecha si desea que la característica sea predeterminada.</span><span class="sxs-lookup"><span data-stu-id="015f6-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="015f6-109">Use PowerShell para habilitar la directiva `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` .</span><span class="sxs-lookup"><span data-stu-id="015f6-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="015f6-110">Si su reunión o seminario web alcanza la capacidad, Teams escalará sin problemas para dar cabida a una experiencia de difusión solo para 10 000 personas.</span><span class="sxs-lookup"><span data-stu-id="015f6-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="015f6-111">Además, durante este tiempo de mayor trabajo remoto, aproveche las transmisiones de más de 20.000 personas hasta finales de este año.</span><span class="sxs-lookup"><span data-stu-id="015f6-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="015f6-112">Microsoft Teams permite que hasta 10 000 asistentes se unan a una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="015f6-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="015f6-113">Una vez que se haya alcanzado la capacidad de la reunión principal, los asistentes adicionales se unirán con una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="015f6-114">Los asistentes que se unan a la reunión primero, hasta la capacidad de la reunión, recibirán toda la experiencia de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="015f6-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="015f6-115">Pueden compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.</span><span class="sxs-lookup"><span data-stu-id="015f6-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="015f6-116">Los asistentes que se unan después de alcanzar la capacidad principal de la reunión tendrán una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="015f6-117">Tenemos soporte móvil completo para Android e iOS para que un asistente se una.</span><span class="sxs-lookup"><span data-stu-id="015f6-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="015f6-118">El límite actual para el número de personas que pueden chatear y llamar a una reunión es de 300 en WW y 250 en GCC, GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="015f6-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="015f6-119">La experiencia de solo visualización está deshabilitada de forma predeterminada para cualquier organizador que tenga SKU de E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="015f6-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="015f6-120">No se requiere ninguna configuración o configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="015f6-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="015f6-121">Deshabilitar la experiencia de solo vista de Teams</span><span class="sxs-lookup"><span data-stu-id="015f6-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="015f6-122">Los administradores pueden deshabilitar la experiencia de solo visualización con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="015f6-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="015f6-123">En el futuro, también será posible que los administradores deshabilite la experiencia de solo vista en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="015f6-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="015f6-124">Impacto para los usuarios</span><span class="sxs-lookup"><span data-stu-id="015f6-124">Impact to users</span></span>

<span data-ttu-id="015f6-125">La experiencia de un usuario variará en función de varios factores.</span><span class="sxs-lookup"><span data-stu-id="015f6-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="015f6-126">Cuando se haya alcanzado la capacidad de la reunión principal, los asistentes no podrán unirse a la reunión si alguna de las siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="015f6-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="015f6-127">Un administrador ha deshabilitado la experiencia de solo vista de Teams.</span><span class="sxs-lookup"><span data-stu-id="015f6-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="015f6-128">El asistente no tiene permiso para omitir la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="015f6-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="015f6-129">Cuando se haya alcanzado la capacidad de la reunión principal, el organizador de la reunión y los presentadores verán una pancarta en la que se les informará de que se ha alcanzado la capacidad de la reunión y de que los nuevos asistentes se unirán a un asistente de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![el mensaje de cliente y pancarta de Teams para organizadores y presentadores](media/chat-and-banner-message.png)

<span data-ttu-id="015f6-131">Cuando se haya alcanzado la capacidad de la reunión principal, se informará a los asistentes de la reunión en la pantalla anterior a la unirse de que se unen en modo de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![la pantalla de pre unirse a Teams y el mensaje para los participantes que les indica que se unirán en modo de solo vista](media/view-only-pre-join-screen.png)

<span data-ttu-id="015f6-133">Si hay espacio, un usuario siempre se unirá a la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="015f6-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="015f6-134">Si la reunión principal alcanza la capacidad y uno o varios asistentes abandonan la reunión principal, la reunión principal tiene capacidad disponible.</span><span class="sxs-lookup"><span data-stu-id="015f6-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="015f6-135">Los asistentes que se unan a la reunión (o vuelvan a unirse) se unirán a la reunión principal hasta que llegue de nuevo a su capacidad.</span><span class="sxs-lookup"><span data-stu-id="015f6-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="015f6-136">Los asistentes que se encuentran en la experiencia de solo visualización no se promoverán automáticamente a la reunión principal y actualmente no se pueden promover manualmente a la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="015f6-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="015f6-137">Si no se han establecido los roles de moderador o asistente, los espacios de la reunión principal se rellenan por primera vez.</span><span class="sxs-lookup"><span data-stu-id="015f6-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="015f6-138">Una vez que se haya alcanzado la capacidad de la reunión, todos los demás usuarios se unirán con una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="015f6-139">Impacto para los presentadores de la reunión</span><span class="sxs-lookup"><span data-stu-id="015f6-139">Impact to meeting presenters</span></span>

<span data-ttu-id="015f6-140">Entre las limitaciones para los presentadores de reuniones se incluyen:</span><span class="sxs-lookup"><span data-stu-id="015f6-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="015f6-141">No tendrá información sobre el asistente de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="015f6-142">No se admite la detección electrónica para los asistentes solo para la vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="015f6-143">Los usuarios no pueden ver los asistentes solo vistas.</span><span class="sxs-lookup"><span data-stu-id="015f6-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="015f6-144">No puede quitar un asistente de solo vista de la reunión.</span><span class="sxs-lookup"><span data-stu-id="015f6-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="015f6-145">El recuento de asistentes solo reflejará las personas de la reunión y no las personas de la sala de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="015f6-146">Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="015f6-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="015f6-147">Experiencia para asistentes solo vistas</span><span class="sxs-lookup"><span data-stu-id="015f6-147">Experience for view-only attendees</span></span>

<span data-ttu-id="015f6-148">La experiencia de solo vista de Teams permite a los asistentes:</span><span class="sxs-lookup"><span data-stu-id="015f6-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="015f6-149">Escuche a los participantes en la reunión principal de Teams.</span><span class="sxs-lookup"><span data-stu-id="015f6-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="015f6-150">Vea la fuente de vídeo del altavoz activo (si el orador activo está compartiendo vídeo).</span><span class="sxs-lookup"><span data-stu-id="015f6-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="015f6-151">Vea el contenido que se comparte con la funcionalidad compartir escritorio.</span><span class="sxs-lookup"><span data-stu-id="015f6-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="015f6-152">El asistente de solo vista no podrá experimentar las siguientes opciones en las reuniones:</span><span class="sxs-lookup"><span data-stu-id="015f6-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="015f6-153">Únase a la reunión si el asistente no tiene permiso para omitir la sala de espera en función de las opciones o directivas de la sala de espera establecidas.</span><span class="sxs-lookup"><span data-stu-id="015f6-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="015f6-154">Únase a la sala de solo vista con audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="015f6-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="015f6-155">Únase a la sala de solo vista con el sistema de sala de Microsoft Teams o con los servicios de interoperabilidad de vídeo en la nube (CVI).</span><span class="sxs-lookup"><span data-stu-id="015f6-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="015f6-156">Comparta su audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="015f6-156">Share their audio or video.</span></span>
- <span data-ttu-id="015f6-157">Ver o participar en el chat de la reunión.</span><span class="sxs-lookup"><span data-stu-id="015f6-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="015f6-158">Vea la fuente de vídeo de los participantes de la reunión a menos que el participante sea el orador activo.</span><span class="sxs-lookup"><span data-stu-id="015f6-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="015f6-159">Vea Archivos de PowerPoint que se comparten con la funcionalidad de PowerPoint de uso compartido nativo o recursos compartidos de aplicaciones individuales (aparte del uso compartido de escritorio).</span><span class="sxs-lookup"><span data-stu-id="015f6-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="015f6-160">Limitaciones de características solo vistas</span><span class="sxs-lookup"><span data-stu-id="015f6-160">View-only feature limitations</span></span>

- <span data-ttu-id="015f6-161">Los asistentes de solo visualización siempre verán los subtítulos en directo, independientemente de la configuración de los subtítulos en directo para esa reunión.</span><span class="sxs-lookup"><span data-stu-id="015f6-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="015f6-162">Solo se admiten los subtítulos en inglés en este momento.</span><span class="sxs-lookup"><span data-stu-id="015f6-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="015f6-163">Los asistentes solo para la vista serán compatibles con la tecnología de streaming.</span><span class="sxs-lookup"><span data-stu-id="015f6-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="015f6-164">Los asistentes de solo visualización no se incluirán en el informe de asistencia.</span><span class="sxs-lookup"><span data-stu-id="015f6-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="015f6-165">Los asistentes solo con vista tendrán una única experiencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="015f6-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="015f6-166">Pueden ver el orador activo o el contenido que se comparte, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="015f6-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="015f6-167">Actualmente no se admiten diseños  de **Galería,** Galería **grande** o Modo conjunto para los asistentes que solo pueden ver.</span><span class="sxs-lookup"><span data-stu-id="015f6-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="015f6-168">Los asistentes solo vistas no tendrán la misma latencia que un asistente normal.</span><span class="sxs-lookup"><span data-stu-id="015f6-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="015f6-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="015f6-169"><sup>1</sup></span></span>

  <span data-ttu-id="015f6-170"><sup>1 Los</sup> asistentes solo vistos tendrán un retraso de vídeo y audio de 30 segundos en la reunión.</span><span class="sxs-lookup"><span data-stu-id="015f6-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

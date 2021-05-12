---
title: Experiencia de reunión de solo vista
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la experiencia de reunión de solo vista de Teams para administradores, presentadores y asistentes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76137c0ebfe73c6ba500a0dbcdc8ee1a01de85fc
ms.sourcegitcommit: 242561bfc12504614633539ca696b91dfc890b92
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52328562"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="521c7-103">Experiencia de reunión de solo vista para Teams</span><span class="sxs-lookup"><span data-stu-id="521c7-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="521c7-104">Las difusiones de solo vista están disponibles en Microsoft 365 E3/E5 y Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="521c7-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="521c7-105">Esta característica se habilitará el 1 de marzo de 2021 como desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="521c7-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="521c7-106">La característica de Microsoft 365 Government Community Cloud (GCC) comenzará a implantarse a finales de marzo de 2021.</span><span class="sxs-lookup"><span data-stu-id="521c7-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="521c7-107">Government Community Cloud High (GCCH) y el Departamento de Defensa (DoD) se implementarán en una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="521c7-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="521c7-108">Debe cambiar la directiva predeterminada después de esa fecha si quiere que la característica esté ACTIVADA de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="521c7-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="521c7-109">Use PowerShell para habilitar la directiva `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="521c7-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="521c7-110">Si la reunión o el seminario web alcanzan su capacidad máxima, Teams escalará sin problemas para dar cabida a una experiencia de difusión de solo vista de 10 000 personas.</span><span class="sxs-lookup"><span data-stu-id="521c7-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="521c7-111">Además, en estos tiempos de aumento del trabajo remoto, le ofrecemos hasta finales de año la opción de difusiones de hasta 20 000 personas.</span><span class="sxs-lookup"><span data-stu-id="521c7-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="521c7-112">Microsoft Teams permite un máximo de 10 000 asistentes en una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="521c7-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="521c7-113">Una vez que se haya alcanzado la capacidad de la reunión principal (que es cuando 1000 usuarios entran en una reunión), los asistentes adicionales se unirán con una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-113">After the capacity of the main meeting has been reached (which is when 1000 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="521c7-114">Los asistentes que se unan a la reunión en primer lugar, hasta la capacidad de la reunión principal, recibirán la experiencia Teams reunión.</span><span class="sxs-lookup"><span data-stu-id="521c7-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="521c7-115">Podrán compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.</span><span class="sxs-lookup"><span data-stu-id="521c7-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="521c7-116">Los asistentes que se unan después de alcanzar la capacidad máxima de la reunión principal tendrán una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="521c7-117">Los asistentes podrán unirse a la experiencia de solo visualización a través de escritorio, web y Teams móvil (Android e iOS).</span><span class="sxs-lookup"><span data-stu-id="521c7-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="521c7-118">La capacidad límite actual de la "reunión principal" o, en otras palabras, el número de usuarios totalmente interactivos es 1000 e incluye GCC.</span><span class="sxs-lookup"><span data-stu-id="521c7-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 1000 and includes GCC.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="521c7-119">Teams de experiencia de solo vista</span><span class="sxs-lookup"><span data-stu-id="521c7-119">Teams view-only experience controls</span></span>

<span data-ttu-id="521c7-120">Puede habilitar la experiencia de solo vista con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="521c7-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="521c7-121">Para deshabilitar la experiencia de solo vista, también puede usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="521c7-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="521c7-122">En el futuro, podrá habilitar o deshabilitar la experiencia de solo vista en el centro de administración Teams vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="521c7-123">Impacto en los usuarios</span><span class="sxs-lookup"><span data-stu-id="521c7-123">Impact to users</span></span>

<span data-ttu-id="521c7-124">La experiencia de un usuario puede variar en función de varios factores.</span><span class="sxs-lookup"><span data-stu-id="521c7-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="521c7-125">Cuando se alcance la capacidad máxima de la reunión principal, un asistente no podrá unirse a la reunión si se cumple alguno de estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="521c7-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="521c7-126">Un administrador ha deshabilitado la Teams solo vista para el organizador o para todo el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="521c7-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="521c7-127">El asistente de solo vista no puede omitir la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="521c7-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="521c7-128">Como ejemplo, si un organizador de una  reunión elige que solo personas de mi organización omitan la sala de espera y un asistente que está fuera de la organización intenta unirse como asistente de solo vista, no podrá unirse.</span><span class="sxs-lookup"><span data-stu-id="521c7-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="521c7-129">Cuando se haya alcanzado la capacidad de la reunión principal, el organizador de la reunión y los presentadores verán una pancarta en la que se les informará de que los nuevos asistentes se unirán como asistentes de solo visualización.</span><span class="sxs-lookup"><span data-stu-id="521c7-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![el cliente y el mensaje de banner de Teams para organizadores y presentadores](media/chat-and-banner-message.png)

<span data-ttu-id="521c7-131">Cuando se alcance la capacidad máxima de la reunión principal, se informará a los asistentes a la reunión en una pantalla previa de que se encuentran en modo de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![la pantalla previa a unirse a la reunión de Teams y el mensaje para los participantes donde se les indica que se unen en modo de solo vista](media/view-only-pre-join-screen.png)

<span data-ttu-id="521c7-133">Siempre que haya espacio, un usuario podrá unirse a la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="521c7-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="521c7-134">Si la reunión principal alcanza su capacidad máxima y uno o más asistentes la dejan, esta tendrá de nuevo capacidad disponible.</span><span class="sxs-lookup"><span data-stu-id="521c7-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="521c7-135">Los asistentes que se unan (o vuelvan a unirse) entonces a la reunión, podrán hacerlo hasta que llegue de nuevo a su capacidad máxima.</span><span class="sxs-lookup"><span data-stu-id="521c7-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="521c7-136">Los asistentes que se encuentran en la experiencia de solo visualización no se promoverán automáticamente a la reunión principal y no se pueden promover manualmente a la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="521c7-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="521c7-137">Si se han establecido roles de moderador y asistente y un moderador intenta unirse a una reunión después de que la reunión principal haya alcanzado la capacidad, se unirán como asistentes de solo vista y tendrán las mismas limitaciones que otros asistentes de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="521c7-138">Soporte técnico para garantizar que todos los presentadores se unan a la reunión principal se llevará a cabo más adelante.</span><span class="sxs-lookup"><span data-stu-id="521c7-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="521c7-139">El organizador siempre tendrá garantizado el espacio en la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="521c7-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="521c7-140">Impacto para los presentadores y organizadores de la reunión</span><span class="sxs-lookup"><span data-stu-id="521c7-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="521c7-141">Entre las limitaciones para los organizadores y los organizadores de la reunión se incluyen:</span><span class="sxs-lookup"><span data-stu-id="521c7-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="521c7-142">No tendrá información sobre el asistente de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="521c7-143">eDiscovery no es compatible para los asistentes de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="521c7-144">Los usuarios de la reunión principal no pueden ver a los asistentes de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="521c7-145">No puede quitar a un asistente de solo vista de la reunión.</span><span class="sxs-lookup"><span data-stu-id="521c7-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="521c7-146">El recuento de asistentes solo reflejará las personas de la reunión principal y no las personas de la sala de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="521c7-147">Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="521c7-148">Experiencia para asistentes de solo vista</span><span class="sxs-lookup"><span data-stu-id="521c7-148">Experience for view-only attendees</span></span>

<span data-ttu-id="521c7-149">La experiencia de solo vista de Teams permite a los asistentes:</span><span class="sxs-lookup"><span data-stu-id="521c7-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="521c7-150">Escuchar a los participantes de la reunión principal de Teams.</span><span class="sxs-lookup"><span data-stu-id="521c7-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="521c7-151">Consultar la fuente de vídeo del orador activo (si este comparte vídeo).</span><span class="sxs-lookup"><span data-stu-id="521c7-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="521c7-152">Vea el contenido que se comparte con la funcionalidad compartir escritorio o pantalla.</span><span class="sxs-lookup"><span data-stu-id="521c7-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="521c7-153">El asistente de solo vista no podrá experimentar las siguientes opciones en las reuniones:</span><span class="sxs-lookup"><span data-stu-id="521c7-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="521c7-154">Unirse a la reunión si el asistente no tiene permiso para omitir la sala de espera según las directivas u opciones de sala de espera establecidas.</span><span class="sxs-lookup"><span data-stu-id="521c7-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="521c7-155">Unirse a la sala de solo vista con Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="521c7-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="521c7-156">Únase a la sala de solo vista con Salas de Microsoft Teams o con los servicios de interoperabilidad de vídeo en la nube (CVI).</span><span class="sxs-lookup"><span data-stu-id="521c7-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="521c7-157">Compartir su audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="521c7-157">Share their audio or video.</span></span>
- <span data-ttu-id="521c7-158">Ver el chat de reunión o participar en él.</span><span class="sxs-lookup"><span data-stu-id="521c7-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="521c7-159">Ver la fuente de vídeo de los participantes de la reunión a menos que el participante sea el orador activo.</span><span class="sxs-lookup"><span data-stu-id="521c7-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="521c7-160">Vea PowerPoint que se comparten con la funcionalidad PowerPoint Live o recursos compartidos de aplicaciones individuales (distintos del uso compartido de pantalla o escritorio).</span><span class="sxs-lookup"><span data-stu-id="521c7-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="521c7-161">Levante la mano en la reunión.</span><span class="sxs-lookup"><span data-stu-id="521c7-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="521c7-162">Enviar o ver reacciones.</span><span class="sxs-lookup"><span data-stu-id="521c7-162">Send or see reactions.</span></span>
- <span data-ttu-id="521c7-163">Interactúe con cualquier aplicación 3P que se integre en la Teams, incluidos sondeos.</span><span class="sxs-lookup"><span data-stu-id="521c7-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="521c7-164">Limitaciones de características de solo vista</span><span class="sxs-lookup"><span data-stu-id="521c7-164">View-only feature limitations</span></span>

- <span data-ttu-id="521c7-165">Los asistentes de solo visualización solo podrán ver los subtítulos en directo en escritorio y web.</span><span class="sxs-lookup"><span data-stu-id="521c7-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="521c7-166">Actualmente, solo se admiten subtítulos en inglés.</span><span class="sxs-lookup"><span data-stu-id="521c7-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="521c7-167">La tecnología de streaming respaldará a los asistentes de solo vista</span><span class="sxs-lookup"><span data-stu-id="521c7-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="521c7-168">Los asistentes de solo vista no se incluirán en el informe de asistencia.</span><span class="sxs-lookup"><span data-stu-id="521c7-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="521c7-169">Los asistentes de solo vista tendrán una sola experiencia en vídeo.</span><span class="sxs-lookup"><span data-stu-id="521c7-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="521c7-170">O bien podrán ver al orador activo o podrán ver el contenido que se comparte, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="521c7-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="521c7-171">Actualmente, no se admite el modo **Galería**, **Galería grande** o **Modo conferencia** para los asistentes de solo vista.</span><span class="sxs-lookup"><span data-stu-id="521c7-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="521c7-172">Los asistentes de solo vista no tendrán la misma latencia que los asistentes normales.</span><span class="sxs-lookup"><span data-stu-id="521c7-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="521c7-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="521c7-173"><sup>1</sup></span></span>

  <span data-ttu-id="521c7-174"><sup>1</sup> Los asistentes de solo vista se reunirán con un retraso de audio y vídeo de 30 segundos en la reunión.</span><span class="sxs-lookup"><span data-stu-id="521c7-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

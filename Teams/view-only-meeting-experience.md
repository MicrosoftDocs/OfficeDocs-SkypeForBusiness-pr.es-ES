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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875060"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="24a3f-103">Experiencia de reunión de solo vista para Teams</span><span class="sxs-lookup"><span data-stu-id="24a3f-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="24a3f-104">Las difusiones de solo vista están disponibles en Microsoft 365 E3/E5 y Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="24a3f-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="24a3f-105">Esta característica se habilitará el 1 de marzo de 2021 como desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="24a3f-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="24a3f-106">La característica de Microsoft 365 Government Community Cloud (GCC) comenzará a implantarse a finales de marzo de 2021.</span><span class="sxs-lookup"><span data-stu-id="24a3f-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="24a3f-107">Government Community Cloud High (GCCH) y el Departamento de Defensa (DoD) se implementarán en una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="24a3f-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="24a3f-108">Debe cambiar la directiva predeterminada después de esa fecha si quiere que la característica esté ACTIVADA de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="24a3f-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="24a3f-109">Use PowerShell para habilitar la directiva `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="24a3f-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="24a3f-110">Si la reunión o el seminario web alcanzan su capacidad máxima, Teams escalará sin problemas para dar cabida a una experiencia de difusión de solo vista de 10 000 personas.</span><span class="sxs-lookup"><span data-stu-id="24a3f-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="24a3f-111">Además, en estos tiempos de aumento del trabajo remoto, le ofrecemos hasta finales de año la opción de difusiones de hasta 20 000 personas.</span><span class="sxs-lookup"><span data-stu-id="24a3f-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="24a3f-112">Microsoft Teams permite un máximo de 10 000 asistentes en una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="24a3f-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="24a3f-113">Si se alcanza este límite en la reunión principal, los asistentes adicionales se unirán con una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="24a3f-114">Los asistentes que se unan a la reunión antes de alcanzar su capacidad máxima, disfrutarán de la experiencia completa de la reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="24a3f-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="24a3f-115">Podrán compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.</span><span class="sxs-lookup"><span data-stu-id="24a3f-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="24a3f-116">Los asistentes que se unan después de alcanzar la capacidad máxima de la reunión principal tendrán una experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="24a3f-117">Tenemos compatibilidad completa con dispositivos móviles Android e iOS para que un asistente se una.</span><span class="sxs-lookup"><span data-stu-id="24a3f-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="24a3f-118">El límite actual para el número de personas que pueden chatear y llamar a una reunión es de 300 en todo el mundo y 250 en GCC, GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="24a3f-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="24a3f-119">La experiencia de solo vista está deshabilitada de forma predeterminada para cualquier organizador que tenga SKU de E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="24a3f-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="24a3f-120">No es necesario realizar ninguna configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="24a3f-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="24a3f-121">Deshabilitar solo vista en Teams</span><span class="sxs-lookup"><span data-stu-id="24a3f-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="24a3f-122">Los administradores pueden deshabilitar solo vista con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24a3f-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="24a3f-123">En el futuro, también se les permitirá hacerlo desde el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="24a3f-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="24a3f-124">Impacto en los usuarios</span><span class="sxs-lookup"><span data-stu-id="24a3f-124">Impact to users</span></span>

<span data-ttu-id="24a3f-125">La experiencia de un usuario puede variar en función de varios factores.</span><span class="sxs-lookup"><span data-stu-id="24a3f-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="24a3f-126">Cuando se alcance la capacidad máxima de la reunión principal, un asistente no podrá unirse a la reunión si se cumple alguno de estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="24a3f-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="24a3f-127">Un administrador ha deshabilitado la experiencia de solo vista de Teams.</span><span class="sxs-lookup"><span data-stu-id="24a3f-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="24a3f-128">El asistente no tiene permiso para omitir la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="24a3f-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="24a3f-129">Cuando se alcance la capacidad máxima de la reunión principal, se informará de ello al organizador de la reunión y a los presentadores con una pancarta en la que también se les indicará que los nuevos asistentes se unirán a un asistente de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![el cliente y el mensaje de banner de Teams para organizadores y presentadores](media/chat-and-banner-message.png)

<span data-ttu-id="24a3f-131">Cuando se alcance la capacidad máxima de la reunión principal, se informará a los asistentes a la reunión en una pantalla previa de que se encuentran en modo de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![la pantalla previa a unirse a la reunión de Teams y el mensaje para los participantes donde se les indica que se unen en modo de solo vista](media/view-only-pre-join-screen.png)

<span data-ttu-id="24a3f-133">Siempre que haya espacio, un usuario podrá unirse a la reunión principal.</span><span class="sxs-lookup"><span data-stu-id="24a3f-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="24a3f-134">Si la reunión principal alcanza su capacidad máxima y uno o más asistentes la dejan, esta tendrá de nuevo capacidad disponible.</span><span class="sxs-lookup"><span data-stu-id="24a3f-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="24a3f-135">Los asistentes que se unan (o vuelvan a unirse) entonces a la reunión, podrán hacerlo hasta que llegue de nuevo a su capacidad máxima.</span><span class="sxs-lookup"><span data-stu-id="24a3f-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="24a3f-136">No se transferirá a los asistentes en modo solo vista a la reunión principal automáticamente y, actualmente, tampoco se les puede transferir manualmente.</span><span class="sxs-lookup"><span data-stu-id="24a3f-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="24a3f-137">Si no se han establecido roles de moderador o asistente, los espacios de la reunión principal se ocuparán por orden de llegada.</span><span class="sxs-lookup"><span data-stu-id="24a3f-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="24a3f-138">Una vez se haya alcanzado la capacidad máxima de la reunión, el resto de los usuarios se unirán en modo solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="24a3f-139">Impacto para los presentadores de reuniones</span><span class="sxs-lookup"><span data-stu-id="24a3f-139">Impact to meeting presenters</span></span>

<span data-ttu-id="24a3f-140">Estas son las limitaciones para los presentadores de reuniones:</span><span class="sxs-lookup"><span data-stu-id="24a3f-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="24a3f-141">No tendrá información sobre el asistente de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="24a3f-142">eDiscovery no es compatible para los asistentes de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="24a3f-143">Los usuarios no pueden ver a los asistentes de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="24a3f-144">No puede quitar a un asistente de solo vista de la reunión.</span><span class="sxs-lookup"><span data-stu-id="24a3f-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="24a3f-145">El número de asistentes solo contará a las personas presentes en la reunión y no a las que estén en la sala de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="24a3f-146">Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="24a3f-147">Experiencia para asistentes de solo vista</span><span class="sxs-lookup"><span data-stu-id="24a3f-147">Experience for view-only attendees</span></span>

<span data-ttu-id="24a3f-148">La experiencia de solo vista de Teams permite a los asistentes:</span><span class="sxs-lookup"><span data-stu-id="24a3f-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="24a3f-149">Escuchar a los participantes de la reunión principal de Teams.</span><span class="sxs-lookup"><span data-stu-id="24a3f-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="24a3f-150">Consultar la fuente de vídeo del orador activo (si este comparte vídeo).</span><span class="sxs-lookup"><span data-stu-id="24a3f-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="24a3f-151">Ver el contenido que se comparte con la funcionalidad de compartir el escritorio.</span><span class="sxs-lookup"><span data-stu-id="24a3f-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="24a3f-152">El asistente de solo vista no podrá experimentar las siguientes opciones en las reuniones:</span><span class="sxs-lookup"><span data-stu-id="24a3f-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="24a3f-153">Unirse a la reunión si el asistente no tiene permiso para omitir la sala de espera según las directivas u opciones de sala de espera establecidas.</span><span class="sxs-lookup"><span data-stu-id="24a3f-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="24a3f-154">Unirse a la sala de solo vista con Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="24a3f-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="24a3f-155">Unirse a la sala de solo vista con el sistema de Sala de Microsoft Teams o los servicios de Interoperabilidad de Vídeo en la Nube (CVI).</span><span class="sxs-lookup"><span data-stu-id="24a3f-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="24a3f-156">Compartir su audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="24a3f-156">Share their audio or video.</span></span>
- <span data-ttu-id="24a3f-157">Ver el chat de reunión o participar en él.</span><span class="sxs-lookup"><span data-stu-id="24a3f-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="24a3f-158">Ver la fuente de vídeo de los participantes de la reunión a menos que el participante sea el orador activo.</span><span class="sxs-lookup"><span data-stu-id="24a3f-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="24a3f-159">Ver los archivos de PowerPoint que se comparten con la funcionalidad de PowerPoint de recurso compartido nativo o con recursos compartidos de aplicaciones individuales (distintos al uso compartido de escritorio).</span><span class="sxs-lookup"><span data-stu-id="24a3f-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="24a3f-160">Limitaciones de características de solo vista</span><span class="sxs-lookup"><span data-stu-id="24a3f-160">View-only feature limitations</span></span>

- <span data-ttu-id="24a3f-161">Los asistentes de solo vista siempre verán los subtítulos en directo, independientemente de la configuración de los subtítulos en directo de esa reunión.</span><span class="sxs-lookup"><span data-stu-id="24a3f-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="24a3f-162">Actualmente, solo se admiten subtítulos en inglés.</span><span class="sxs-lookup"><span data-stu-id="24a3f-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="24a3f-163">La tecnología de streaming respaldará a los asistentes de solo vista</span><span class="sxs-lookup"><span data-stu-id="24a3f-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="24a3f-164">Los asistentes de solo vista no se incluirán en el informe de asistencia.</span><span class="sxs-lookup"><span data-stu-id="24a3f-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="24a3f-165">Los asistentes de solo vista tendrán una sola experiencia en vídeo.</span><span class="sxs-lookup"><span data-stu-id="24a3f-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="24a3f-166">O bien podrán ver al orador activo o podrán ver el contenido que se comparte, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="24a3f-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="24a3f-167">Actualmente, no se admite el modo **Galería**, **Galería grande** o **Modo conferencia** para los asistentes de solo vista.</span><span class="sxs-lookup"><span data-stu-id="24a3f-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="24a3f-168">Los asistentes de solo vista no tendrán la misma latencia que los asistentes normales.</span><span class="sxs-lookup"><span data-stu-id="24a3f-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="24a3f-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="24a3f-169"><sup>1</sup></span></span>

  <span data-ttu-id="24a3f-170"><sup>1</sup> Los asistentes de solo vista se reunirán con un retraso de audio y vídeo de 30 segundos en la reunión.</span><span class="sxs-lookup"><span data-stu-id="24a3f-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

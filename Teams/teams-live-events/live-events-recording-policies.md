---
title: Directivas de grabación de eventos en directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Obtenga información sobre las directivas de grabación de eventos en directo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8d25f37f94a514b83bd37e44d1b022bac064a839
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739660"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="dbcf4-103">Directivas de grabación de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbcf4-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="dbcf4-104">Tiene varias opciones para grabar un evento Microsoft Teams en directo.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="dbcf4-105">Las opciones de grabación se establecen con directivas de grabación.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="dbcf4-106">En este artículo se describen las distintas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-106">This article describes the various settings.</span></span>

<span data-ttu-id="dbcf4-107">Las opciones de grabación se establecen con el comando de PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dbcf4-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="dbcf4-108">Programación y comportamientos de opciones</span><span class="sxs-lookup"><span data-stu-id="dbcf4-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="dbcf4-109">Hay dos opciones de organizador al programar una grabación de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="dbcf4-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="dbcf4-110">Grabación disponible para productores y presentadores</span><span class="sxs-lookup"><span data-stu-id="dbcf4-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="dbcf4-111">Archivo de grabación: Proporciona un archivo de grabación que los productores y los presentadores pueden descargar una vez que haya terminado el evento.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="dbcf4-112">Grabación disponible para los asistentes</span><span class="sxs-lookup"><span data-stu-id="dbcf4-112">Recording available for attendees</span></span>

  - <span data-ttu-id="dbcf4-113">DVR: Una grabadora de vídeo digital (DVR) permite a los asistentes rebobinar y pausar durante el evento</span><span class="sxs-lookup"><span data-stu-id="dbcf4-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="dbcf4-114">VOD: Un vídeo a petición (VOD) permite a los asistentes ver una vez que el evento ha terminado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="dbcf4-115">Configuración de directiva de grabación de difusión</span><span class="sxs-lookup"><span data-stu-id="dbcf4-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="dbcf4-116">Como parte de la directiva de difusión, hay una configuración que puede activar o desactivar para activar o desactivar la grabación de un evento en directo.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="dbcf4-117">Grabación disponible para productores y presentadores</span><span class="sxs-lookup"><span data-stu-id="dbcf4-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="dbcf4-118">Grabación disponible para los asistentes</span><span class="sxs-lookup"><span data-stu-id="dbcf4-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="dbcf4-119">Grabar siempre</span><span class="sxs-lookup"><span data-stu-id="dbcf4-119">Always record</span></span>               | <span data-ttu-id="dbcf4-120">Deshabilitado y seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-120">Disabled and selected</span></span>                                | <span data-ttu-id="dbcf4-121">Habilitado y seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-121">Enabled and selected</span></span>         |
| <span data-ttu-id="dbcf4-122">Organizador puede grabar o no</span><span class="sxs-lookup"><span data-stu-id="dbcf4-122">Organizer can record or not</span></span> | <span data-ttu-id="dbcf4-123">Habilitado y seleccionado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="dbcf4-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="dbcf4-124">Habilitado y seleccionado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="dbcf4-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="dbcf4-125">Nunca grabar</span><span class="sxs-lookup"><span data-stu-id="dbcf4-125">Never record</span></span>               | <span data-ttu-id="dbcf4-126">Deshabilitado y no seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-126">Disabled and not selected</span></span>                            | <span data-ttu-id="dbcf4-127">Deshabilitado y no seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="dbcf4-128">Storage y el comportamiento de persistencia</span><span class="sxs-lookup"><span data-stu-id="dbcf4-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="dbcf4-129">Opción</span><span class="sxs-lookup"><span data-stu-id="dbcf4-129">Option</span></span>                                       | <span data-ttu-id="dbcf4-130">Estado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-130">State</span></span>   | <span data-ttu-id="dbcf4-131">DVR</span><span class="sxs-lookup"><span data-stu-id="dbcf4-131">DVR</span></span>                                                   | <span data-ttu-id="dbcf4-132">VOD</span><span class="sxs-lookup"><span data-stu-id="dbcf4-132">VOD</span></span>                                                     | <span data-ttu-id="dbcf4-133">Grabación</span><span class="sxs-lookup"><span data-stu-id="dbcf4-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="dbcf4-134">Grabación disponible para los asistentes</span><span class="sxs-lookup"><span data-stu-id="dbcf4-134">Recording available for attendees</span></span> | <span data-ttu-id="dbcf4-135">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-135">Selected</span></span>     | <span data-ttu-id="dbcf4-136">DVR está disponible y el Azure Media Services (AMS) se almacena durante 180 días</span><span class="sxs-lookup"><span data-stu-id="dbcf4-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="dbcf4-137">Los asistentes pueden acceder al evento y verlo</span><span class="sxs-lookup"><span data-stu-id="dbcf4-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="dbcf4-138">No seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-138">Not Selected</span></span> | <span data-ttu-id="dbcf4-139">DVR está disponible y el activo de AMS se almacena durante 180 días</span><span class="sxs-lookup"><span data-stu-id="dbcf4-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="dbcf4-140">Los asistentes no án acceso al evento una vez que se ha terminado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="dbcf4-141">Deshabilitado (no seleccionado)</span><span class="sxs-lookup"><span data-stu-id="dbcf4-141">Disabled (Not selected)</span></span>|<span data-ttu-id="dbcf4-142">DVR está disponible y el activo de AMS se elimina después del evento</span><span class="sxs-lookup"><span data-stu-id="dbcf4-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="dbcf4-143">Los asistentes no án acceso al evento una vez que se ha terminado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="dbcf4-144">Grabación disponible para productores y presentadores</span><span class="sxs-lookup"><span data-stu-id="dbcf4-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="dbcf4-145">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="dbcf4-146">Se crea y almacena un MP4</span><span class="sxs-lookup"><span data-stu-id="dbcf4-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="dbcf4-147">No seleccionado</span><span class="sxs-lookup"><span data-stu-id="dbcf4-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="dbcf4-148">No se crea ningún archivo</span><span class="sxs-lookup"><span data-stu-id="dbcf4-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="dbcf4-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dbcf4-149">Related topics</span></span>

- [<span data-ttu-id="dbcf4-150">¿Qué son los eventos en directo de Teams?</span><span class="sxs-lookup"><span data-stu-id="dbcf4-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="dbcf4-151">Planear eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="dbcf4-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="dbcf4-152">Establecer la configuración de eventos en directo de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbcf4-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="dbcf4-153">Teams de reuniones en la nube</span><span class="sxs-lookup"><span data-stu-id="dbcf4-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)

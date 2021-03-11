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
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615179"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="12806-103">Directivas de grabación de eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12806-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="12806-104">Tiene varias opciones para grabar un evento en directo de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="12806-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="12806-105">Las opciones de grabación se establecen con directivas de grabación.</span><span class="sxs-lookup"><span data-stu-id="12806-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="12806-106">En este artículo se describen las distintas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="12806-106">This article describes the various settings.</span></span>

<span data-ttu-id="12806-107">Las opciones de grabación se establecen con el comando de PowerShell [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="12806-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="12806-108">Programación y comportamientos de opciones</span><span class="sxs-lookup"><span data-stu-id="12806-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="12806-109">Hay dos opciones de organizador al programar una grabación de eventos en directo:</span><span class="sxs-lookup"><span data-stu-id="12806-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="12806-110">Grabación disponible para productores y presentadores</span><span class="sxs-lookup"><span data-stu-id="12806-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="12806-111">Archivo de grabación: Proporciona un archivo de grabación que los productores y los presentadores pueden descargar una vez que haya terminado el evento.</span><span class="sxs-lookup"><span data-stu-id="12806-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="12806-112">Grabación disponible para los asistentes</span><span class="sxs-lookup"><span data-stu-id="12806-112">Recording available for attendees</span></span>

  - <span data-ttu-id="12806-113">DVR: Una grabadora de vídeo digital (DVR) permite a los asistentes rebobinar y pausar durante el evento</span><span class="sxs-lookup"><span data-stu-id="12806-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="12806-114">VOD: Un vídeo a petición (VOD) permite a los asistentes ver una vez que el evento ha terminado</span><span class="sxs-lookup"><span data-stu-id="12806-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="12806-115">Configuración de directiva de grabación de difusión</span><span class="sxs-lookup"><span data-stu-id="12806-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="12806-116">Como parte de la directiva de difusión, hay una configuración que puede activar o desactivar para activar o desactivar la grabación de un evento en directo.</span><span class="sxs-lookup"><span data-stu-id="12806-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="12806-117">Grabación disponible para productores y presentadores</span><span class="sxs-lookup"><span data-stu-id="12806-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="12806-118">Grabación disponible para los asistentes</span><span class="sxs-lookup"><span data-stu-id="12806-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="12806-119">Grabar siempre</span><span class="sxs-lookup"><span data-stu-id="12806-119">Always record</span></span>               | <span data-ttu-id="12806-120">Deshabilitado y seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-120">Disabled and selected</span></span>                                | <span data-ttu-id="12806-121">Deshabilitado y seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-121">Disabled and selected</span></span>         |
| <span data-ttu-id="12806-122">Organizador puede grabar o no</span><span class="sxs-lookup"><span data-stu-id="12806-122">Organizer can record or not</span></span> | <span data-ttu-id="12806-123">Habilitado y no seleccionado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="12806-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="12806-124">Habilitado y no seleccionado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="12806-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="12806-125">Nunca grabar</span><span class="sxs-lookup"><span data-stu-id="12806-125">Never record</span></span>               | <span data-ttu-id="12806-126">Deshabilitado y no seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-126">Disabled and not selected</span></span>                            | <span data-ttu-id="12806-127">Deshabilitado y no seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-127">Disabled and not selected</span></span>      |

<span data-ttu-id="12806-128">Cuando la directiva se establece en **Registro siempre,** la página de directiva tiene las siguientes opciones seleccionadas:</span><span class="sxs-lookup"><span data-stu-id="12806-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="12806-129">![configuración de directiva de eventos en directo](../media/live-event-recording-policy.png "Captura de pantalla de la configuración de la directiva de eventos en directo en el centro de administración de Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="12806-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="12806-130">Comportamiento de almacenamiento y persistencia</span><span class="sxs-lookup"><span data-stu-id="12806-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="12806-131">Opción</span><span class="sxs-lookup"><span data-stu-id="12806-131">Option</span></span>                                       | <span data-ttu-id="12806-132">Estado</span><span class="sxs-lookup"><span data-stu-id="12806-132">State</span></span>   | <span data-ttu-id="12806-133">DVR</span><span class="sxs-lookup"><span data-stu-id="12806-133">DVR</span></span>                                                   | <span data-ttu-id="12806-134">VOD</span><span class="sxs-lookup"><span data-stu-id="12806-134">VOD</span></span>                                                     | <span data-ttu-id="12806-135">Grabación</span><span class="sxs-lookup"><span data-stu-id="12806-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="12806-136">Grabación disponible para productores y presentadores</span><span class="sxs-lookup"><span data-stu-id="12806-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="12806-137">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-137">Selected</span></span>     | <span data-ttu-id="12806-138">DVR está disponible y el activo de Azure Media Services (AMS) se almacena durante 180 días</span><span class="sxs-lookup"><span data-stu-id="12806-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="12806-139">Los asistentes pueden acceder al evento y verlo</span><span class="sxs-lookup"><span data-stu-id="12806-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="12806-140">No seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-140">Not Selected</span></span> | <span data-ttu-id="12806-141">DVR está disponible y el activo de AMS se almacena durante 180 días</span><span class="sxs-lookup"><span data-stu-id="12806-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="12806-142">Los asistentes no án acceso al evento una vez que se ha terminado</span><span class="sxs-lookup"><span data-stu-id="12806-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="12806-143">Deshabilitado (no seleccionado)</span><span class="sxs-lookup"><span data-stu-id="12806-143">Disabled (Not selected)</span></span>|<span data-ttu-id="12806-144">DVR está disponible y el activo de AMS se elimina después del evento</span><span class="sxs-lookup"><span data-stu-id="12806-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="12806-145">Los asistentes no án acceso al evento una vez que se ha terminado</span><span class="sxs-lookup"><span data-stu-id="12806-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="12806-146">Grabación disponible para productores y presentadores</span><span class="sxs-lookup"><span data-stu-id="12806-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="12806-147">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="12806-148">Se crea y almacena un MP4</span><span class="sxs-lookup"><span data-stu-id="12806-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="12806-149">No seleccionado</span><span class="sxs-lookup"><span data-stu-id="12806-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="12806-150">No se crea ningún archivo</span><span class="sxs-lookup"><span data-stu-id="12806-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="12806-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="12806-151">Related topics</span></span>

- [<span data-ttu-id="12806-152">¿Qué son los eventos en directo de Teams?</span><span class="sxs-lookup"><span data-stu-id="12806-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="12806-153">Planear eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="12806-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="12806-154">Establecer la configuración de eventos en directo de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12806-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="12806-155">Grabación de reuniones en la nube de Teams</span><span class="sxs-lookup"><span data-stu-id="12806-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)

---
title: Administración de directivas de eventos en directo en los equipos
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.liveevents.policies
description: Obtenga información sobre las directivas de eventos en directo de los equipos y cómo usarlas para administrar la configuración para los usuarios de la organización que mantenga los eventos en directo.
ms.openlocfilehash: b02f8de8accd0baff5f87af8682eab486866acb5
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354351"
---
# <a name="manage-live-events-policies-in-teams"></a><span data-ttu-id="ad7c6-103">Administración de directivas de eventos en directo en los equipos</span><span class="sxs-lookup"><span data-stu-id="ad7c6-103">Manage live events policies in Teams</span></span>

<span data-ttu-id="ad7c6-104">Las directivas de eventos en directo de los equipos se usan para controlar las personas de su organización pueden contener eventos en directo y las características que están disponibles en los eventos que se crean.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-104">Teams live events policies are used to control who in your organization can hold live events and the features that are available in the events that they create.</span></span> <span data-ttu-id="ad7c6-105">Después de crear una directiva, asignar a un usuario o grupos de usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-105">After you create a policy, assign it to a user or groups of users in your organization.</span></span> 

- <span data-ttu-id="ad7c6-106">**Nombre** Esto es el nombre de la directiva que aparece en la página de directivas de eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-106">**Name** This is the name of the policy that appears on the live events policies page.</span></span> <span data-ttu-id="ad7c6-107">No puede superar los 64 caracteres o tienen todos los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-107">It can't be longer than 64 characters or have any special characters.</span></span>  
- <span data-ttu-id="ad7c6-108">**Descripción** Se usa para agregar una descripción simplificada de la directiva.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-108">**Description** Use this to add a friendly description for the policy.</span></span> 
- <span data-ttu-id="ad7c6-109">**Permitir programación** Activar Esto permite a los usuarios de su organización crear y programar eventos en directo en los equipos.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-109">**Allow scheduling** Turning this on lets users in your organization create and schedule live events in Teams.</span></span>  
- <span data-ttu-id="ad7c6-110">**Transcripción de permitir para los asistentes** Activar Esto permite a los asistentes de evento en directo ver los títulos en tiempo real y traducción durante el evento.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-110">**Allow transcription for attendees** Turning this on enables live event attendees to see real-time captions and translation during the event.</span></span> 
- <span data-ttu-id="ad7c6-111">**Que pueden unir a eventos en directo programados**</span><span class="sxs-lookup"><span data-stu-id="ad7c6-111">**Who can join scheduled live events**</span></span>
    - <span data-ttu-id="ad7c6-112">**Todos los usuarios** Los usuarios pueden crear eventos en directo que todos, incluidas las personas fuera de la organización, pueden asistir a.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-112">**Everyone** Users can create live events that everyone, including people outside your organization, can attend.</span></span>  
    - <span data-ttu-id="ad7c6-113">**Todas las personas de la organización** Los usuarios pueden crear eventos en directo que pueden asistir sólo las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-113">**Everyone in the organization** Users can create live events that only people in your organization can attend.</span></span> 
    - <span data-ttu-id="ad7c6-114">**Usuarios o grupos específicos** Los usuarios pueden crear eventos en directo que sólo determinados usuarios o grupos de la organización pueden asistir a.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-114">**Specific users or groups** Users can create live events that only specific users or groups in your organization can attend.</span></span> 
- <span data-ttu-id="ad7c6-115">**Configuración de grabación** Esta configuración solo se puede aplicar para eventos que se producen con reuniones de los equipos, también conocida como inicio rápido live eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-115">**Recording setting** This setting can only be applied to live events that are produced using Teams meetings, also known as quick start live events.</span></span>  
    - <span data-ttu-id="ad7c6-116">**Registrar siempre** Siempre se registran los eventos en directo creados por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-116">**Always record** The live events created by users are always recorded.</span></span> <span data-ttu-id="ad7c6-117">Después de que el evento es a través de, los miembros del equipo de evento pueden descargar la grabación y los asistentes pueden verla el evento.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-117">After the event is over, event team members can download the recording and attendees can watch the event.</span></span> 
    - <span data-ttu-id="ad7c6-118">**Nunca registrar** Nunca se registran los eventos en directo creados por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-118">**Never record** The live events created by users are never recorded.</span></span>
    - <span data-ttu-id="ad7c6-119">**Puede registrar el organizador o no** Los usuarios pueden decidir si va a registrar el evento en directo.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-119">**Organizer can record or not** Users can decide whether to record the live event.</span></span> <span data-ttu-id="ad7c6-120">Si está registrado, después de que el evento es a través de, los miembros del equipo de evento pueden descargar la grabación y los asistentes pueden verla el evento.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-120">If it is recorded, after the event is over, event team members can download the recording and attendees can watch the event.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="ad7c6-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ad7c6-121">Related topics</span></span>
- [<span data-ttu-id="ad7c6-122">¿Cuáles son los equipos de eventos en directo?</span><span class="sxs-lookup"><span data-stu-id="ad7c6-122">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="ad7c6-123">Plan para los equipos eventos en directo</span><span class="sxs-lookup"><span data-stu-id="ad7c6-123">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="ad7c6-124">Configurar para los equipos de eventos en directo</span><span class="sxs-lookup"><span data-stu-id="ad7c6-124">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="ad7c6-125">Configurar los equipos eventos en directo</span><span class="sxs-lookup"><span data-stu-id="ad7c6-125">Configure Teams live events</span></span>](configure-teams-live-events.md)

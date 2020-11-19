---
title: 'Inicio rápido de administrador: Reuniones y eventos en directo en Microsoft Teams'
ms.reviewer: ''
description: Una guía de inicio rápido para que los administradores obtengan las respectivas licencias, implementen y configuren reuniones en línea y eventos en directo en Microsoft Teams.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- enabler-strategic
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 22626e14a9c6c6187949e5e770b2cdd22c20027b
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130631"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="afdd2-103">Inicio rápido de administrador: Reuniones y eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afdd2-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="afdd2-p101">Hay dos maneras de reunirse con Microsoft Teams: reuniones y eventos en directo. Este artículo le ayudará a implementarlo más rápidamente y a configurar las reuniones y los eventos en directo de tu organización.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p101">There are 2 ways to meet in Microsoft Teams - meetings and live events. Use this article to quickly roll out and configure meetings and live events for your organization.</span></span>

> [!Note]
> <span data-ttu-id="afdd2-106">Para obtener más información sobre cómo configurar rápidamente las reuniones y los eventos de Teams en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="afdd2-106">For details about quickly configuring Teams meetings and events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

 - <span data-ttu-id="afdd2-p102">Las **reuniones** en Teams incluyen audio, vídeo y pantalla compartida para más de 300 personas. Se trata de una de las maneras clave de colaborar en Teams y no necesita ser miembro de ninguna organización (¡ni tampoco tener una cuenta en Teams!) para reunirte por Teams, pues únicamente tendrá que buscar la invitación para seguir las instrucciones de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p102">**Meetings** in Teams include audio, video, and screen sharing for up to 300 people. They're one of the key ways to collaborate in Teams. And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span>

 - <span data-ttu-id="afdd2-p103">**Eventos en directo** es una extensión de las reuniones de Teams que le permiten programar y producir eventos que se transmiten a grandes contactos en línea, hasta 10 000 personas. Si necesita reunir a más de 300 personas, hazclo en un evento en directo.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p103">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people. If you need a meeting for more than 300 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="afdd2-112">Obtenga licencias para reuniones y eventos en directo</span><span class="sxs-lookup"><span data-stu-id="afdd2-112">Get licenses for meetings and live events</span></span>

<span data-ttu-id="afdd2-p104">Cualquiera puede participar en una reunión o un evento en directo en Teams de panera gratuita y sin ninguna licencia. Los asistentes se unen a las reuniones y los eventos en directo en Teams haciendo clic en el botón **Unirse** de Teams o de la invitación a la reunión. El audio forma parte de las reuniones en Teams, pero si quieres que la gente pueda acceder a la reunión marcando un número por teléfono, tendrá que darles su número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p104">Anyone can attend a Teams meeting or public live event for free - no license is required. Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation. Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span>

<span data-ttu-id="afdd2-p105">Quienes vayan a organizar, programar y ser los anfitriones de reuniones o eventos en directo necesitarán una de las licencias de Microsoft 365 u Office 365 que aparecen en la siguiente tabla. Si ya ha usado Teams, probablemente tenga la licencia que necesita para organizar e invitar a otros a reuniones y eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p105">For the people who will organize, schedule, and host meetings or live events, they'll need one of the Microsoft 365 or Office 365 licenses listed in the table below. If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span>

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="Tabla con las licencias necesarias para reuniones o eventos en directo en Teams":::

> <span data-ttu-id="afdd2-119"><sup>1</sup>  Los organizadores de las reuniones deben tener una [licencia del complemento de audioconferencia](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para enviar una invitación que incluya una conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="afdd2-119"><sup>1</sup>  Meeting organizers need to have an [Audio Conferencing add-on license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) to send an invite that includes dial-in conferencing.</span></span>
>
> <span data-ttu-id="afdd2-p106"><sup>2</sup> La llamada de acceso telefónico de la reunión [**a través de un** número de teléfono](set-up-the-call-me-feature-for-your-users.md) requiere que los organizadores tengan una licencia E5 o una [licencia del complemento de audioconferencia](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). También es posible que se necesite un [plan de marcado](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="afdd2-p106"><sup>2</sup>  Meeting dial out to a [**Call me at** number](set-up-the-call-me-feature-for-your-users.md) requires organizers to have an E5 or [Audio Conference add-in license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). A [dial plan](what-are-dial-plans.md) may also be needed.</span></span>

<span data-ttu-id="afdd2-122">Para más información sobre las licencias, consulte [Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="afdd2-122">To learn more about licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="afdd2-123">Asegúrese de que la red esté disponible</span><span class="sxs-lookup"><span data-stu-id="afdd2-123">Make sure your network's ready</span></span>

<span data-ttu-id="afdd2-p107">Si ya preparó su red cuando implementó Microsoft 365 u Office 365, probablemente y lo tenga todo listo. En cualquier caso, y especialmente si va a implementar Teams en poco tiempo con su primera carga de trabajo de Office 365 para admitir a **trabajadores remotos**, lea [Preparar la red de su organización para implementar Teams](prepare-network.md) para asegurarse de que estará preparado.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p107">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set. In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="afdd2-126">Reuniones y conferencias</span><span class="sxs-lookup"><span data-stu-id="afdd2-126">Meetings and conferencing</span></span>

- <span data-ttu-id="afdd2-p108">Como administrador, establecerá la [configuración de la reunión](meeting-settings-in-teams.md) para cada persona. Luego usará las [directivas de las reuniones](meeting-policies-in-teams.md) para controlar la disponibilidad (y la ausencia de disponibilidad) de las características de las reuniones para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p108">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone. Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span>

- <span data-ttu-id="afdd2-129">Para más información sobre la administración de la grabación de reuniones, consulte [Grabación de reuniones en la nube de Teams](cloud-recording.md).</span><span class="sxs-lookup"><span data-stu-id="afdd2-129">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="afdd2-p109">Si es la primera vez que sus usuarios participan en las reuniones de Teams comparta con ellos la formación para [Administrar reuniones](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4). Extraiga del repositorio nuestro curso en línea guiado por un instructor, [Celebre reuniones efectivas con Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span><span class="sxs-lookup"><span data-stu-id="afdd2-p109">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them. Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="afdd2-132">Para más información sobre cómo administrar las opciones de la reunión, lea [Cambiar la configuración de los participantes de la reunión de Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span><span class="sxs-lookup"><span data-stu-id="afdd2-132">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="afdd2-p110">No se olvide de [administrar los dispositivos de los usuarios](device-management.md): teléfonos, auriculares, cámaras. Para obtener las últimas noticias e información actualizada sobre los equipos certificados de Teams, entre en [Dispositivos de Teams](https://office.com/teamsdevices).</span><span class="sxs-lookup"><span data-stu-id="afdd2-p110">Don't forget about [managing your users' devices](device-management.md) - phones, headsets, cameras. To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="afdd2-135">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="afdd2-135">Live events</span></span>

- <span data-ttu-id="afdd2-p111">Al igual que en las reuniones, usted, el administrador, deberá [configurar los eventos en directo](teams-live-events/configure-teams-live-events.md) para todos los usuarios. Luego, configure (y asigne) las [directivas del evento en directo](teams-live-events/set-up-for-teams-live-events.md) para controlar lo que los usuarios (no) pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="afdd2-p111">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone. Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="afdd2-138">Asegúrese de que los productores y organizadores de sus eventos en directo estén formados. Envíelos a [Introducción a los eventos en directo](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span><span class="sxs-lookup"><span data-stu-id="afdd2-138">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="afdd2-139">Si es nuevo en los eventos en directo, consulte [¿Qué son los eventos en directo de Teams?](teams-live-events/what-are-teams-live-events.md) y [Planificar los eventos en directo de Teams](teams-live-events/plan-for-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="afdd2-139">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="afdd2-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="afdd2-140">Related topics</span></span>

[<span data-ttu-id="afdd2-141">Reuniones y conferencias a través de Teams</span><span class="sxs-lookup"><span data-stu-id="afdd2-141">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="afdd2-142">Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afdd2-142">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="afdd2-143">Eventos en directo en Yammer</span><span class="sxs-lookup"><span data-stu-id="afdd2-143">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="afdd2-144">Especificaciones y límites de Teams</span><span class="sxs-lookup"><span data-stu-id="afdd2-144">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="afdd2-145">Comunidad técnica de Microsoft: eventos en directo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="afdd2-145">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)

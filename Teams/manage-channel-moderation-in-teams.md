---
title: Configurar y administrar la moderación del canal
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a configurar canales para moderar en Microsoft Teams, incluido cómo agregar miembros del equipo como moderadores de canales.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822900"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="830b9-103">Configurar y administrar la moderación de canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="830b9-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="830b9-104">En Microsoft Teams, los propietarios de equipos pueden activar la moderación de un canal estándar para controlar quién puede iniciar nuevas publicaciones y responder a publicaciones en ese canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="830b9-105">Los propietarios de equipo también pueden agregar miembros del equipo como moderadores.</span><span class="sxs-lookup"><span data-stu-id="830b9-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="830b9-106">Es posible que el propietario de un equipo no tenga la experiencia necesaria en el nivel del canal para la mejor moderación del canal de soporte.</span><span class="sxs-lookup"><span data-stu-id="830b9-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="830b9-107">Al permitir que determinados miembros del equipo puedan moderar un canal, la responsabilidad de administrar el contenido y el contexto dentro de un canal se comparte entre los propietarios del equipo y los moderadores de canales.</span><span class="sxs-lookup"><span data-stu-id="830b9-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="830b9-108">Por ejemplo, el propietario de un equipo puede agregar propietarios de la empresa o propietarios de contenido como moderadores, lo que le permite controlar el uso compartido de información en ese canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="830b9-109">La moderación de canales está disponible para los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="830b9-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="830b9-110">No está disponible para el canal General ni para los canales privados.</span><span class="sxs-lookup"><span data-stu-id="830b9-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="830b9-111">¿Qué puede hacer un moderador de canal?</span><span class="sxs-lookup"><span data-stu-id="830b9-111">What can a channel moderator do?</span></span>

<span data-ttu-id="830b9-112">Los moderadores de canales pueden:</span><span class="sxs-lookup"><span data-stu-id="830b9-112">Channel moderators can:</span></span>

- <span data-ttu-id="830b9-113">Inicie nuevas publicaciones en el canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-113">Start new posts in the channel.</span></span> <span data-ttu-id="830b9-114">Cuando la moderación está activada para un canal, solo los moderadores pueden iniciar nuevas publicaciones en ese canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="830b9-115">Agregue y quite miembros del equipo como moderadores de un canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="830b9-116">Tenga en cuenta que, de forma predeterminada, los propietarios de los equipos son moderadores de canales y no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="830b9-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="830b9-117">Controle si los miembros del equipo pueden responder a los mensajes del canal existentes y si los bots y conectores pueden enviar mensajes del canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="830b9-118">Escenarios</span><span class="sxs-lookup"><span data-stu-id="830b9-118">Scenarios</span></span>

<span data-ttu-id="830b9-119">A continuación se muestran algunos ejemplos de cómo su organización puede usar la moderación de canales en Teams.</span><span class="sxs-lookup"><span data-stu-id="830b9-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="830b9-120">Usar un canal como canal de anuncio</span><span class="sxs-lookup"><span data-stu-id="830b9-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="830b9-121">El equipo de marketing usa un canal específico para compartir los anuncios clave del proyecto y las entregas.</span><span class="sxs-lookup"><span data-stu-id="830b9-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="830b9-122">A veces, los miembros del equipo publican contenido en el canal que pertenece más adecuadamente a otros canales.</span><span class="sxs-lookup"><span data-stu-id="830b9-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="830b9-123">El propietario del equipo quiere restringir el uso compartido de información en el canal a solo anuncios para que los miembros del equipo puedan usar ese canal para mantenerse al tanto de lo que es importante.</span><span class="sxs-lookup"><span data-stu-id="830b9-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="830b9-124">En este escenario, el propietario del equipo agrega los responsables de marketing como moderadores para que puedan publicar anuncios en el canal y desactiva la posibilidad de que los miembros del equipo respondan a mensajes en ese canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="830b9-125">Usar un canal para discusiones de clase en Teams para el sector educativo</span><span class="sxs-lookup"><span data-stu-id="830b9-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="830b9-126">En Teams para el educación, un profesor de ciencia desea usar un canal para involucrar a los alumnos en discusiones centradas en temas específicos del aula.</span><span class="sxs-lookup"><span data-stu-id="830b9-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="830b9-127">En este escenario, el profesor permite que sus asistentes de enseñanza modere el canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="830b9-128">Los asistentes de enseñanza pueden crear nuevas publicaciones para iniciar e impulsar discusiones con los alumnos.</span><span class="sxs-lookup"><span data-stu-id="830b9-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="830b9-129">Administrar la moderación del canal</span><span class="sxs-lookup"><span data-stu-id="830b9-129">Manage channel moderation</span></span>

<span data-ttu-id="830b9-130">En Teams, vaya al canal, haga clic en **Más opciones...**  >  **Administrar canal.**</span><span class="sxs-lookup"><span data-stu-id="830b9-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="830b9-131">Desde aquí puede activar y desactivar la moderación, agregar miembros del equipo como moderadores y establecer las preferencias.</span><span class="sxs-lookup"><span data-stu-id="830b9-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="830b9-132">La moderación de canales es una configuración por canal.</span><span class="sxs-lookup"><span data-stu-id="830b9-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="830b9-133">No hay ninguna configuración de nivel de inquilino para la moderación de canales.</span><span class="sxs-lookup"><span data-stu-id="830b9-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="830b9-134">Si quiere que agreguemos una configuración de moderación de canal de nivel de inquilino, preséntela a [UserVoice de Teams.](https://microsoftteams.uservoice.com/)</span><span class="sxs-lookup"><span data-stu-id="830b9-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="830b9-136">Activar o desactivar la moderación de un canal</span><span class="sxs-lookup"><span data-stu-id="830b9-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="830b9-137">La moderación está desactivada de forma predeterminada, lo que significa que la configuración habitual del canal se aplica a los propietarios del equipo y a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="830b9-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="830b9-138">Por ejemplo, puede restringir las nuevas publicaciones solo a los miembros del equipo o permitir que todos los usuarios, incluidos los invitados, inicien nuevas publicaciones.</span><span class="sxs-lookup"><span data-stu-id="830b9-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="830b9-139">Para activar la moderación de un canal, en **Moderación de canal,** haga clic **en Activar.**</span><span class="sxs-lookup"><span data-stu-id="830b9-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="830b9-140">Cuando la moderación de canales está en marcha, solo los moderadores pueden iniciar nuevas publicaciones.</span><span class="sxs-lookup"><span data-stu-id="830b9-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="830b9-141">Agregar o quitar moderadores de canal</span><span class="sxs-lookup"><span data-stu-id="830b9-141">Add or remove channel moderators</span></span>

<span data-ttu-id="830b9-142">En **¿Quiénes son los moderadores?** Haga clic en **Administrar** y, a continuación, agregue o quite miembros del equipo como moderadores.</span><span class="sxs-lookup"><span data-stu-id="830b9-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="830b9-143">Los propietarios del equipo y los moderadores pueden agregar y quitar otros moderadores.</span><span class="sxs-lookup"><span data-stu-id="830b9-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="830b9-144">Establecer permisos de miembros del equipo</span><span class="sxs-lookup"><span data-stu-id="830b9-144">Set team member permissions</span></span>

<span data-ttu-id="830b9-145">En **Permisos de los miembros del** equipo, active las casillas situadas junto a las actividades que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="830b9-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="830b9-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="830b9-146">Related topics</span></span>

- [<span data-ttu-id="830b9-147">Información general de los equipos y canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="830b9-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)

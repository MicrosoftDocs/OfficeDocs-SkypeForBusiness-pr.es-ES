---
title: Configurar y administrar la moderación de canales en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a configurar canales para moderación en Microsoft Teams, lo que incluye cómo agregar miembros del equipo como moderadores de canales.
ms.openlocfilehash: 333f0b43c3d703ddd2746bcae0af760228c9fa6e
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2019
ms.locfileid: "35804898"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="1451c-103">Configurar y administrar la moderación de canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1451c-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="1451c-104">En Microsoft Teams, los propietarios del equipo pueden activar la moderación de un canal para controlar quién puede iniciar publicaciones nuevas y responder a las entradas de ese canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-104">In Microsoft Teams, team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="1451c-105">Los propietarios del equipo también pueden agregar miembros del equipo como moderadores.</span><span class="sxs-lookup"><span data-stu-id="1451c-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="1451c-106">Es posible que el propietario de un equipo no tenga experiencia en el nivel de canal para mejorar la moderación del canal de soporte.</span><span class="sxs-lookup"><span data-stu-id="1451c-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="1451c-107">Al permitir que los miembros del equipo sean moderadores de un canal, la responsabilidad de administrar el contenido y el contexto dentro de un canal se comparte entre los propietarios del equipo y los moderadores de los canales.</span><span class="sxs-lookup"><span data-stu-id="1451c-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="1451c-108">Por ejemplo, el propietario de un equipo puede Agregar propietarios de negocios o propietarios de contenido como moderadores, lo que les permite controlar el uso compartido de información en ese canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="1451c-109">¿Qué puede hacer un moderador de canal?</span><span class="sxs-lookup"><span data-stu-id="1451c-109">What can a channel moderator do?</span></span>

<span data-ttu-id="1451c-110">Los moderadores de canal pueden:</span><span class="sxs-lookup"><span data-stu-id="1451c-110">Channel moderators can:</span></span>

- <span data-ttu-id="1451c-111">Inicie nuevas publicaciones en el canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-111">Start new posts in the channel.</span></span> <span data-ttu-id="1451c-112">Cuando la moderación está activada para un canal, solo los moderadores pueden iniciar publicaciones nuevas en ese canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-112">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="1451c-113">Agregar y quitar miembros del equipo como moderadores de un canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-113">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="1451c-114">Tenga en cuenta que, de forma predeterminada, los propietarios del equipo son moderadores de canal y no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="1451c-114">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="1451c-115">Controle si los miembros del equipo pueden responder a los mensajes de canal existentes y si los bots y los conectores pueden enviar mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-115">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="1451c-116">Escenarios</span><span class="sxs-lookup"><span data-stu-id="1451c-116">Scenarios</span></span>

<span data-ttu-id="1451c-117">Estos son algunos ejemplos de cómo su organización puede usar la moderación de canales en Teams.</span><span class="sxs-lookup"><span data-stu-id="1451c-117">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="1451c-118">Usar un canal como canal de anuncios</span><span class="sxs-lookup"><span data-stu-id="1451c-118">Use a channel as an announcement channel</span></span>

<span data-ttu-id="1451c-119">El equipo de marketing usa un canal específico para compartir los anuncios y las entregas clave del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1451c-119">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="1451c-120">A veces, los miembros del equipo publican contenido en el canal que pertenece de forma más adecuada a otros canales.</span><span class="sxs-lookup"><span data-stu-id="1451c-120">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="1451c-121">El propietario del equipo desea restringir la información que se comparte en el canal solo a los anuncios, de modo que los miembros del equipo puedan usar ese canal para mantenerse al día de lo importante.</span><span class="sxs-lookup"><span data-stu-id="1451c-121">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="1451c-122">En este escenario, el propietario del equipo agrega los responsables de marketing como moderadores para que puedan publicar anuncios en el canal y desactivar la posibilidad de que los miembros del equipo puedan responder a los mensajes de ese canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-122">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="1451c-123">Usar un canal para discusiones de clase en Teams para el ámbito educativo</span><span class="sxs-lookup"><span data-stu-id="1451c-123">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="1451c-124">En Teams para el ámbito educativo, un profesor de ciencia desea usar un canal para atraer a los alumnos en debates específicos sobre temas específicos del aula.</span><span class="sxs-lookup"><span data-stu-id="1451c-124">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="1451c-125">En este escenario, el profesor permite a los asistentes de la enseñanza moderar el canal.</span><span class="sxs-lookup"><span data-stu-id="1451c-125">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="1451c-126">Los asistentes de enseñanza pueden crear nuevos mensajes para iniciar y realizar debates con los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="1451c-126">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="1451c-127">Administrar la moderación de canales</span><span class="sxs-lookup"><span data-stu-id="1451c-127">Manage channel moderation</span></span>

<span data-ttu-id="1451c-128">En Teams, vaya al canal, haga clic en **más opciones...**  >  **Administrar canal**.</span><span class="sxs-lookup"><span data-stu-id="1451c-128">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="1451c-129">Desde aquí puede activar y desactivar la moderación, agregar miembros del equipo como moderadores y establecer preferencias.</span><span class="sxs-lookup"><span data-stu-id="1451c-129">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

![Manage-Channel-Moderation-in-Teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="1451c-131">Activar o desactivar la moderación de un canal</span><span class="sxs-lookup"><span data-stu-id="1451c-131">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="1451c-132">De forma predeterminada, la moderación está desactivada y puede restringir las publicaciones nuevas solo a los miembros del equipo o permitir que todos los usuarios, incluidos los invitados, inicien publicaciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="1451c-132">By default, moderation is off and you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="1451c-133">Para activar la moderación para un canal, en moderación de **canales**, haga clic **en activar**.</span><span class="sxs-lookup"><span data-stu-id="1451c-133">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="1451c-134">Cuando la moderación de canales está activada, solo los moderadores pueden iniciar publicaciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="1451c-134">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="1451c-135">Agregar o quitar moderadores de canal</span><span class="sxs-lookup"><span data-stu-id="1451c-135">Add or remove channel moderators</span></span>

<span data-ttu-id="1451c-136">En **¿quién es el moderador?**, haga clic en **administrar**y, a continuación, agregue o quite miembros del equipo como moderadores.</span><span class="sxs-lookup"><span data-stu-id="1451c-136">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="1451c-137">Los propietarios del equipo y los moderadores pueden agregar y quitar otros moderadores.</span><span class="sxs-lookup"><span data-stu-id="1451c-137">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="1451c-138">Establecer permisos de los miembros del equipo</span><span class="sxs-lookup"><span data-stu-id="1451c-138">Set team member permissions</span></span>

<span data-ttu-id="1451c-139">En **permisos**de los miembros del equipo, active las casillas de verificación junto a las actividades que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="1451c-139">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1451c-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1451c-140">Related topics</span></span>

- [<span data-ttu-id="1451c-141">Información general de los equipos y canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1451c-141">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
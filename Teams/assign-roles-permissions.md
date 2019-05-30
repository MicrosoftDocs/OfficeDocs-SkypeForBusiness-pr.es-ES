---
title: Asignar miembros y propietarios de equipo en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493805"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="ea6a0-103">Asignar miembros y propietarios de equipo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea6a0-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ea6a0-p101">Dentro de Microsoft Teams hay dos roles: **Propietario** y **Miembro**. De forma predeterminada, el usuario que crea un equipo tiene el estado Propietario. Si se crea un equipo a partir de un grupo de Office 365 existente, los permisos se heredan.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-p101">Within Microsoft Teams there are two user roles: **Owner** and **Member**. By default, a user who creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="ea6a0-107">En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:</span><span class="sxs-lookup"><span data-stu-id="ea6a0-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="ea6a0-108">Propietario de equipo</span><span class="sxs-lookup"><span data-stu-id="ea6a0-108">Team Owner</span></span> | <span data-ttu-id="ea6a0-109">Integrante de grupo</span><span class="sxs-lookup"><span data-stu-id="ea6a0-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="ea6a0-110">**Crear un equipo**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-110">**Create team**</span></span>          |    <span data-ttu-id="ea6a0-111">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="ea6a0-112">No</span><span class="sxs-lookup"><span data-stu-id="ea6a0-112">No</span></span>      |
|          <span data-ttu-id="ea6a0-113">**Abandonar equipo**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-113">**Leave team**</span></span>           |    <span data-ttu-id="ea6a0-114">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-114">Yes</span></span>     |     <span data-ttu-id="ea6a0-115">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-115">Yes</span></span>     |
|  <span data-ttu-id="ea6a0-116">**Editar nombre o descripción del equipo**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="ea6a0-117">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-117">Yes</span></span>     |     <span data-ttu-id="ea6a0-118">No</span><span class="sxs-lookup"><span data-stu-id="ea6a0-118">No</span></span>      |
|          <span data-ttu-id="ea6a0-119">**Eliminar equipo**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-119">**Delete team**</span></span>          |    <span data-ttu-id="ea6a0-120">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-120">Yes</span></span>     |     <span data-ttu-id="ea6a0-121">No</span><span class="sxs-lookup"><span data-stu-id="ea6a0-121">No</span></span>      |
|          <span data-ttu-id="ea6a0-122">**Agregar canal**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-122">**Add channel**</span></span>          |    <span data-ttu-id="ea6a0-123">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-123">Yes</span></span>     |    <span data-ttu-id="ea6a0-124">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="ea6a0-125">**Editar nombre o descripción del canal**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="ea6a0-126">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-126">Yes</span></span>     |    <span data-ttu-id="ea6a0-127">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="ea6a0-128">**Eliminar canal**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-128">**Delete channel**</span></span>         |    <span data-ttu-id="ea6a0-129">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-129">Yes</span></span>     |    <span data-ttu-id="ea6a0-130">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="ea6a0-131">**Agregar miembros**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-131">**Add members**</span></span>          |  <span data-ttu-id="ea6a0-132">Sí<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="ea6a0-133">No<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="ea6a0-134">**Solicitud para agregar miembros**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-134">**Request to add members**</span></span>          |  <span data-ttu-id="ea6a0-135">N/D</span><span class="sxs-lookup"><span data-stu-id="ea6a0-135">N/A</span></span>   |     <span data-ttu-id="ea6a0-136">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="ea6a0-137">**Agregar fichas**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-137">**Add tabs**</span></span>            |    <span data-ttu-id="ea6a0-138">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-138">Yes</span></span>     |    <span data-ttu-id="ea6a0-139">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="ea6a0-140">**Agregar conectores**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-140">**Add connectors**</span></span>         |    <span data-ttu-id="ea6a0-141">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-141">Yes</span></span>     |    <span data-ttu-id="ea6a0-142">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="ea6a0-143">**Agregar bots**</span><span class="sxs-lookup"><span data-stu-id="ea6a0-143">**Add bots**</span></span>            |    <span data-ttu-id="ea6a0-144">Sí</span><span class="sxs-lookup"><span data-stu-id="ea6a0-144">Yes</span></span>     |    <span data-ttu-id="ea6a0-145">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea6a0-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="ea6a0-146"><sup>1</sup> Los propietarios del equipo pueden crear equipos a no ser que se les haya quitado el permiso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="ea6a0-147">Consulte "Permisos para crear equipos" más abajo.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="ea6a0-148"><sup>2</sup> Un propietario puede desactivar estos elementos a nivel de equipo, en cuyo caso, los miembros no tendrían acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="ea6a0-149"><sup>3</sup> Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado de propietario.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="ea6a0-150">El propietario también puede degradar su propio estado a miembro.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="ea6a0-151"><sup>4</sup> Los miembros del equipo pueden agregar otros miembros a un equipo público.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="ea6a0-152"><sup>5</sup> Aunque un miembro del equipo no puede agregar directamente miembros a un equipo privado, puede solicitar que se añada a una persona a un equipo del que ya es miembro.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="ea6a0-153">Cuando un miembro solicita que se añada a una persona a un equipo, los propietarios del equipo reciben una alerta de que tienen una solicitud pendiente que pueden aceptar o denegar.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="ea6a0-154">Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="ea6a0-155">Un equipo puede tener hasta 100 propietarios.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="ea6a0-156">Se recomienda tener al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo se evita que algunos grupos se queden huérfanos si el único propietario deja la organización.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="ea6a0-157">Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="ea6a0-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="ea6a0-158">Permisos para crear equipos</span><span class="sxs-lookup"><span data-stu-id="ea6a0-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="ea6a0-159">De manera predeterminada, todos los usuarios que tengan un buzón de correo en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, para crear equipos dentro de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="ea6a0-160">Puede ejercer un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de grupos de Office 365 si delega la creación de grupos y los derechos de administración en un conjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="ea6a0-161">Para ver más información, consulte [Administrar quién puede crear Grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="ea6a0-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Un icono que representa un punto de decisión](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="ea6a0-163">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="ea6a0-163">Decision Point</span></span>         |<span data-ttu-id="ea6a0-164">¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="ea6a0-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Un icono que representa los pasos siguientes](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="ea6a0-166">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="ea6a0-166">Next Steps</span></span>         |<span data-ttu-id="ea6a0-167">Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.</span><span class="sxs-lookup"><span data-stu-id="ea6a0-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |

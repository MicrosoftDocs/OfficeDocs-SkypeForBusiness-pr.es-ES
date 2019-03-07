---
title: Asignar miembros y propietarios de equipo en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
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
ms.openlocfilehash: 4887cb129242473da46a611c4f873e79384e5e32
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460343"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="1c4e0-103">Asignar miembros y propietarios de equipo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c4e0-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="1c4e0-104">En Microsoft Teams existen dos roles de usuario: **propietario** y **miembros**.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="1c4e0-105">De forma predeterminada, un usuario que crea un nuevo equipo se concede el estado de propietario.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="1c4e0-106">Si se crea un equipo de un grupo de 365 existente de Office, los permisos se heredan.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="1c4e0-107">En la tabla siguiente muestra la diferencia de permisos entre un propietario y un miembro.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="1c4e0-108">Propietario de equipo</span><span class="sxs-lookup"><span data-stu-id="1c4e0-108">Team Owner</span></span> | <span data-ttu-id="1c4e0-109">Miembro de equipo</span><span class="sxs-lookup"><span data-stu-id="1c4e0-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="1c4e0-110">**Crear equipo**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-110">**Create team**</span></span>          |    <span data-ttu-id="1c4e0-111">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="1c4e0-112">No</span><span class="sxs-lookup"><span data-stu-id="1c4e0-112">No</span></span>      |
|          <span data-ttu-id="1c4e0-113">**Abandonar equipo**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-113">**Leave team**</span></span>           |    <span data-ttu-id="1c4e0-114">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-114">Yes</span></span>     |     <span data-ttu-id="1c4e0-115">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-115">Yes</span></span>     |
|  <span data-ttu-id="1c4e0-116">**Editar nombre o descripción del equipo**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="1c4e0-117">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-117">Yes</span></span>     |     <span data-ttu-id="1c4e0-118">No</span><span class="sxs-lookup"><span data-stu-id="1c4e0-118">No</span></span>      |
|          <span data-ttu-id="1c4e0-119">**Eliminar equipo**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-119">**Delete team**</span></span>          |    <span data-ttu-id="1c4e0-120">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-120">Yes</span></span>     |     <span data-ttu-id="1c4e0-121">No</span><span class="sxs-lookup"><span data-stu-id="1c4e0-121">No</span></span>      |
|          <span data-ttu-id="1c4e0-122">**Agregar canal**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-122">**Add channel**</span></span>          |    <span data-ttu-id="1c4e0-123">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-123">Yes</span></span>     |    <span data-ttu-id="1c4e0-124">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="1c4e0-125">**Editar nombre o descripción del canal**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="1c4e0-126">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-126">Yes</span></span>     |    <span data-ttu-id="1c4e0-127">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="1c4e0-128">**Eliminar canal**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-128">**Delete channel**</span></span>         |    <span data-ttu-id="1c4e0-129">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-129">Yes</span></span>     |    <span data-ttu-id="1c4e0-130">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="1c4e0-131">**Agregar miembros**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-131">**Add members**</span></span>          |  <span data-ttu-id="1c4e0-132">Sí<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="1c4e0-133">No</span><span class="sxs-lookup"><span data-stu-id="1c4e0-133">No</span></span>      |
|           <span data-ttu-id="1c4e0-134">**Agregar fichas**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-134">**Add tabs**</span></span>            |    <span data-ttu-id="1c4e0-135">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-135">Yes</span></span>     |    <span data-ttu-id="1c4e0-136">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-136">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="1c4e0-137">**Agregar conectores**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-137">**Add connectors**</span></span>         |    <span data-ttu-id="1c4e0-138">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-138">Yes</span></span>     |    <span data-ttu-id="1c4e0-139">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-139">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="1c4e0-140">**Agregar bots**</span><span class="sxs-lookup"><span data-stu-id="1c4e0-140">**Add bots**</span></span>            |    <span data-ttu-id="1c4e0-141">Sí</span><span class="sxs-lookup"><span data-stu-id="1c4e0-141">Yes</span></span>     |    <span data-ttu-id="1c4e0-142">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1c4e0-142">Yes<sup>2</sup></span></span>|

<span data-ttu-id="1c4e0-143"><sup>1</sup> los propietarios de equipo pueden crear equipos a menos que ha ha restringido de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-143"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="1c4e0-144">Vea "Permisos para crear los equipos" más adelante.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-144">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="1c4e0-145"><sup>2</sup> estos elementos se pueden desactivar un propietario en un nivel de equipo, en cuyo caso los miembros no tienen acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-145"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="1c4e0-146"><sup>3</sup> después de agregar a un miembro a un equipo, un propietario también puede ascender a un miembro al estado de propietario.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-146"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="1c4e0-147">También es posible para un propietario disminuir el nivel de su propio estado para un miembro.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-147">It is also possible for an owner to demote their own status to a member.</span></span>



> [!NOTE]
> <span data-ttu-id="1c4e0-148">Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-148">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="1c4e0-149">Un equipo puede tener hasta 100 propietarios.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-149">A team can have up to 100 owners.</span></span> <span data-ttu-id="1c4e0-150">Se recomienda tener al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo se evita que algunos grupos se queden huérfanos si el único propietario deja la organización.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-150">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="1c4e0-151">Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="1c4e0-151">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="1c4e0-152">Permisos para crear equipos</span><span class="sxs-lookup"><span data-stu-id="1c4e0-152">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="1c4e0-153">De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, un equipo dentro de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-153">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="1c4e0-154">Puede tener un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de nuevos grupos de Office 365 mediante la delegación de la creación del grupo y derechos de administración a un conjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-154">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="1c4e0-155">Para obtener instrucciones, vea [administrar quién puede crear grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="1c4e0-155">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Icono de Punto de decisión.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="1c4e0-157">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="1c4e0-157">Decision Point</span></span>         |<span data-ttu-id="1c4e0-158">¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="1c4e0-158">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icono de Siguientes pasos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="1c4e0-160">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="1c4e0-160">Next Steps</span></span>         |<span data-ttu-id="1c4e0-161">Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.</span><span class="sxs-lookup"><span data-stu-id="1c4e0-161">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |

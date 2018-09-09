---
title: Asignar roles y permisos en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: da4bae93a35775141c246145e1375e73963ec120
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892701"
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="17a04-103">Asignar roles y permisos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17a04-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="17a04-p101">Dentro de Microsoft Teams hay dos roles: **Propietario** y **Miembro**. De forma predeterminada, el usuario que crea un equipo tiene el estado Propietario. Si se crea un equipo a partir de un grupo de Office 365 existente, los permisos se heredan.</span><span class="sxs-lookup"><span data-stu-id="17a04-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="17a04-107">En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:</span><span class="sxs-lookup"><span data-stu-id="17a04-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="17a04-108">Propietario de equipo</span><span class="sxs-lookup"><span data-stu-id="17a04-108">Team Owner</span></span>  |<span data-ttu-id="17a04-109">Miembro de equipo</span><span class="sxs-lookup"><span data-stu-id="17a04-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="17a04-110">**Crear equipo**</span><span class="sxs-lookup"><span data-stu-id="17a04-110">**Create team**</span></span>     |<span data-ttu-id="17a04-111">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-111">Yes</span></span>        |<span data-ttu-id="17a04-112">No</span><span class="sxs-lookup"><span data-stu-id="17a04-112">No</span></span>         |
|<span data-ttu-id="17a04-113">**Abandonar equipo**</span><span class="sxs-lookup"><span data-stu-id="17a04-113">**Leave team**</span></span>     |<span data-ttu-id="17a04-114">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-114">Yes</span></span>         |<span data-ttu-id="17a04-115">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-115">Yes</span></span>         |
|<span data-ttu-id="17a04-116">**Editar nombre o descripción del equipo**</span><span class="sxs-lookup"><span data-stu-id="17a04-116">**Edit team name/description**</span></span>      |<span data-ttu-id="17a04-117">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-117">Yes</span></span>         |<span data-ttu-id="17a04-118">No</span><span class="sxs-lookup"><span data-stu-id="17a04-118">No</span></span>         |
|<span data-ttu-id="17a04-119">**Eliminar equipo**</span><span class="sxs-lookup"><span data-stu-id="17a04-119">**Delete team**</span></span>      |<span data-ttu-id="17a04-120">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-120">Yes</span></span>         |<span data-ttu-id="17a04-121">No</span><span class="sxs-lookup"><span data-stu-id="17a04-121">No</span></span>         |
|<span data-ttu-id="17a04-122">**Agregar canal**</span><span class="sxs-lookup"><span data-stu-id="17a04-122">**Add channel**</span></span>      |<span data-ttu-id="17a04-123">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-123">Yes</span></span>         |<span data-ttu-id="17a04-124">Sí\*</span><span class="sxs-lookup"><span data-stu-id="17a04-124">Yes\*</span></span>         |
|<span data-ttu-id="17a04-125">**Editar nombre o descripción del canal**</span><span class="sxs-lookup"><span data-stu-id="17a04-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="17a04-126">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-126">Yes</span></span>         |<span data-ttu-id="17a04-127">Sí\*</span><span class="sxs-lookup"><span data-stu-id="17a04-127">Yes\*</span></span>         |
|<span data-ttu-id="17a04-128">**Eliminar canal**</span><span class="sxs-lookup"><span data-stu-id="17a04-128">**Delete channel**</span></span>      |<span data-ttu-id="17a04-129">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-129">Yes</span></span>         |<span data-ttu-id="17a04-130">Sí\*</span><span class="sxs-lookup"><span data-stu-id="17a04-130">Yes\*</span></span>         |
|<span data-ttu-id="17a04-131">**Agregar miembros**</span><span class="sxs-lookup"><span data-stu-id="17a04-131">**Add members**</span></span>      |<span data-ttu-id="17a04-132">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-132">Yes\*\*</span></span>         |<span data-ttu-id="17a04-133">No</span><span class="sxs-lookup"><span data-stu-id="17a04-133">No</span></span>         |
|<span data-ttu-id="17a04-134">**Agregar fichas**</span><span class="sxs-lookup"><span data-stu-id="17a04-134">**Add tabs**</span></span>      |<span data-ttu-id="17a04-135">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-135">Yes</span></span>         |<span data-ttu-id="17a04-136">Sí\*</span><span class="sxs-lookup"><span data-stu-id="17a04-136">Yes\*</span></span>         |
|<span data-ttu-id="17a04-137">**Agregar conectores**</span><span class="sxs-lookup"><span data-stu-id="17a04-137">**Add connectors**</span></span>      |<span data-ttu-id="17a04-138">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-138">Yes</span></span>         |<span data-ttu-id="17a04-139">Sí\*</span><span class="sxs-lookup"><span data-stu-id="17a04-139">Yes\*</span></span>         |
|<span data-ttu-id="17a04-140">**Agregar bots**</span><span class="sxs-lookup"><span data-stu-id="17a04-140">**Add bots**</span></span>      |<span data-ttu-id="17a04-141">Sí</span><span class="sxs-lookup"><span data-stu-id="17a04-141">Yes</span></span>         |<span data-ttu-id="17a04-142">Sí\*</span><span class="sxs-lookup"><span data-stu-id="17a04-142">Yes\*</span></span>         |
<span data-ttu-id="17a04-143">\* Un propietario puede desactivar estos elementos a nivel de equipo, en cuyo caso, los miembros no tendrían acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="17a04-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="17a04-p102">\*\*Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado Propietario. También es posible que un propietario disminuya su propio estado a Miembro.</span><span class="sxs-lookup"><span data-stu-id="17a04-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="17a04-146">Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos.</span><span class="sxs-lookup"><span data-stu-id="17a04-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="17a04-147">Un equipo puede tener hasta 100 propietarios.</span><span class="sxs-lookup"><span data-stu-id="17a04-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="17a04-148">Se recomienda tener al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo se evita que algunos grupos se queden huérfanos si el único propietario deja la organización.</span><span class="sxs-lookup"><span data-stu-id="17a04-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="17a04-149">Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="17a04-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="17a04-150">Permisos para crear equipos</span><span class="sxs-lookup"><span data-stu-id="17a04-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="17a04-151">De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, un equipo dentro de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17a04-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="17a04-152">Puede tener un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de nuevos grupos de Office 365 mediante la delegación de la creación del grupo y derechos de administración a un conjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="17a04-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="17a04-153">Para obtener instrucciones, vea [administrar quién puede crear grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="17a04-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Icono de Punto de decisión.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="17a04-155">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="17a04-155">Decision Point</span></span>         |<span data-ttu-id="17a04-156">¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="17a04-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icono de Siguientes pasos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="17a04-158">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="17a04-158">Next Steps</span></span>         |<span data-ttu-id="17a04-159">Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.</span><span class="sxs-lookup"><span data-stu-id="17a04-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |

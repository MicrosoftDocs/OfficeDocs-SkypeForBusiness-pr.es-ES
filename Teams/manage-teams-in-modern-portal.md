---
title: Administrar los equipos de Microsoft Teams & Skype para el centro de administración de negocio
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Obtenga información sobre cómo ver o actualizar los equipos en el Microsoft Teams & Skype para el centro de administración de negocio.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14ab474289e5a677e1125df7146ba7c5a6fc2ca1
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539060"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="590b4-103">Administrar los equipos de Microsoft Teams & Skype para el centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="590b4-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="590b4-104">Información general</span><span class="sxs-lookup"><span data-stu-id="590b4-104">Overview</span></span>

<span data-ttu-id="590b4-105">Como un administrador de TI, es posible que necesite vista o actualización de los equipos de su organización ha configurado para la colaboración o necesite para llevar a cabo las acciones de corrección, como la asignación de propietarios de los equipos sin dueño.</span><span class="sxs-lookup"><span data-stu-id="590b4-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="590b4-106">Puede administrar los equipos que se usan en la organización a través del módulo de PowerShell de los equipos de Microsoft y el Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="590b4-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="590b4-107">Para las capacidades de administración completa con estos dos conjuntos de herramientas, debe asegurarse de que se le asigna uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="590b4-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="590b4-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="590b4-108">Global Administrator</span></span>
- <span data-ttu-id="590b4-109">Administrador de servicios de Teams</span><span class="sxs-lookup"><span data-stu-id="590b4-109">Teams Service Administrator</span></span>

<span data-ttu-id="590b4-110">También debe asegurarse de que su cuenta se ha asignado una licencia de los equipos que no sean de prueba para la administración.</span><span class="sxs-lookup"><span data-stu-id="590b4-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="590b4-111">Como parte de un problema conocido, debe asegurarse de que su cuenta tiene sólo **una** función Administrador asignada.</span><span class="sxs-lookup"><span data-stu-id="590b4-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="590b4-112">Encontrará más información acerca de las funciones de administración en Microsoft Teams en [roles de administrador de utilizar equipos de Microsoft para administrar los equipos](using-admin-roles.md)y puede leer más información acerca de cómo usar los cmdlets de PowerShell para la administración de equipos en la [referencia del cmdlet de equipos de Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="590b4-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="590b4-113">En este artículo se proporciona una visión general de las herramientas de administración de equipos en el Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="590b4-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="590b4-114">Cuadrícula de visión general de los equipos</span><span class="sxs-lookup"><span data-stu-id="590b4-114">Teams overview grid</span></span>

<span data-ttu-id="590b4-115">Herramientas de administración de los equipos se encuentran en el nodo de **los equipos** en el Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="590b4-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="590b4-116">(En el centro de administración, seleccione **los equipos** > **administrar equipos**.) Cada equipo se respaldadas por un grupo de Office 365, y este nodo proporciona una vista de grupos que se han habilitado para los equipos de la organización de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="590b4-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="590b4-117">Estamos en el proceso de recuperación de información creado previamente equipos para asegurarse de que se mostrará en esta vista.</span><span class="sxs-lookup"><span data-stu-id="590b4-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Cuadrícula de visión general de los equipos](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="590b4-119">La cuadrícula muestra las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="590b4-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="590b4-120">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="590b4-120">**Team name**</span></span>
- <span data-ttu-id="590b4-121">**Canales** : un recuento de todos los canales en el equipo, incluido el canal General de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="590b4-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="590b4-122">**Los usuarios** : un recuento del total de usuarios, incluidos los propietarios, los invitados y miembros desde el inquilino.</span><span class="sxs-lookup"><span data-stu-id="590b4-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="590b4-123">**Los propietarios de** -un recuento de los propietarios de este equipo.</span><span class="sxs-lookup"><span data-stu-id="590b4-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="590b4-124">**Los invitados** - un recuento de los usuarios de invitado de Azure Active Directory B2B que son miembros de este equipo.</span><span class="sxs-lookup"><span data-stu-id="590b4-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="590b4-125">**Privacidad** - la AccessType del grupo de realizar la copia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="590b4-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="590b4-126">Buscar.</span><span class="sxs-lookup"><span data-stu-id="590b4-126">Search</span></span>

<span data-ttu-id="590b4-127">Búsqueda actualmente es compatible con la cadena "Comienza por" y busca en el campo **nombre del equipo** .</span><span class="sxs-lookup"><span data-stu-id="590b4-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="590b4-128">Editar</span><span class="sxs-lookup"><span data-stu-id="590b4-128">Edit</span></span>

<span data-ttu-id="590b4-129">Puede editar la configuración específica de equipo y grupo seleccionando un equipo de la cuadrícula y, a continuación, seleccionando el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="590b4-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Editar equipo](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="590b4-131">Perfiles de equipo</span><span class="sxs-lookup"><span data-stu-id="590b4-131">Team profile</span></span>

<span data-ttu-id="590b4-132">Puede navegar a la página de perfil de equipo de cualquier equipo de la cuadrícula de visión general de los equipos principal haciendo clic en el nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="590b4-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="590b4-133">La página de perfil de equipo muestra los miembros, los propietarios y los invitados que pertenecen al equipo (y su copia de grupo de Office 365), así como canales y la configuración del grupo.</span><span class="sxs-lookup"><span data-stu-id="590b4-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="590b4-134">Desde la página de perfil del equipo, se puede:</span><span class="sxs-lookup"><span data-stu-id="590b4-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="590b4-135">Agregar o quitar miembros y propietarios.</span><span class="sxs-lookup"><span data-stu-id="590b4-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="590b4-136">Agregar o quitar canales (tenga en cuenta que no se puede quitar el canal General).</span><span class="sxs-lookup"><span data-stu-id="590b4-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="590b4-137">Actualización del equipo y configuración de grupo.</span><span class="sxs-lookup"><span data-stu-id="590b4-137">Update team and group settings.</span></span>
 
![Perfiles de equipo](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="590b4-139">Realizar cambios en los equipos</span><span class="sxs-lookup"><span data-stu-id="590b4-139">Making changes to teams</span></span>

<span data-ttu-id="590b4-140">Puede cambiar los siguientes elementos de un equipo:</span><span class="sxs-lookup"><span data-stu-id="590b4-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="590b4-141">**Los usuarios en el equipo** , puede agregar o quitar miembros y promover o disminuir el nivel de los propietarios de</span><span class="sxs-lookup"><span data-stu-id="590b4-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="590b4-142">**Canales** : puede agregar nuevos canales o quitar canales existentes.</span><span class="sxs-lookup"><span data-stu-id="590b4-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="590b4-143">No se puede eliminar el canal "General" de forma predeterminada y una vez creados sólo se puede editar el nombre del canal, no descripción.</span><span class="sxs-lookup"><span data-stu-id="590b4-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="590b4-144">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="590b4-144">**Team name**</span></span>
- <span data-ttu-id="590b4-145">**Descripción de equipo**</span><span class="sxs-lookup"><span data-stu-id="590b4-145">**Team description**</span></span>
- <span data-ttu-id="590b4-146">**Privacidad del equipo** - público o privado</span><span class="sxs-lookup"><span data-stu-id="590b4-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="590b4-147">**Clasificación de equipo** - respaldados por sus clasificaciones de grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="590b4-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="590b4-148">**Configuración del miembro de equipo** : configuración de miembro de equipo seleccione</span><span class="sxs-lookup"><span data-stu-id="590b4-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="590b4-149">Se registran los cambios que realice en un equipo.</span><span class="sxs-lookup"><span data-stu-id="590b4-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="590b4-150">Si modifica la configuración de grupo (cambiar el nombre, descripción, foto, privacidad, clasificación o los miembros del equipo), estos cambios se expresarán a usted a través de la canalización de auditoría.</span><span class="sxs-lookup"><span data-stu-id="590b4-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="590b4-151">Si va a realizar acciones contra la configuración específica de los equipos, los cambios se realiza un seguimiento y se expresarán en el canal general del equipo.</span><span class="sxs-lookup"><span data-stu-id="590b4-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="590b4-152">Más información</span><span class="sxs-lookup"><span data-stu-id="590b4-152">Learn more</span></span>

[<span data-ttu-id="590b4-153">Referencia del cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="590b4-153">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="590b4-154">Roles de administrador en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="590b4-154">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->


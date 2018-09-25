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
ms.openlocfilehash: 1dbfddf2f9cfba12943b8b2e18326de1877e1de3
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018826"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="804bf-103">Administrar los equipos de Microsoft Teams & Skype para el centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="804bf-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="804bf-104">Información general</span><span class="sxs-lookup"><span data-stu-id="804bf-104">Overview</span></span>

<span data-ttu-id="804bf-105">Como un administrador de TI, es posible que necesite vista o actualización de los equipos de su organización ha configurado para la colaboración o necesite para llevar a cabo las acciones de corrección, como la asignación de propietarios de los equipos sin dueño.</span><span class="sxs-lookup"><span data-stu-id="804bf-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="804bf-106">Puede administrar los equipos que se usan en la organización a través del módulo de PowerShell de los equipos de Microsoft y el Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="804bf-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="804bf-107">Para las capacidades de administración completa con estos dos conjuntos de herramientas, debe asegurarse de que se le asigna uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="804bf-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="804bf-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="804bf-108">Global Administrator</span></span>
- <span data-ttu-id="804bf-109">Administrador de servicio de los equipos</span><span class="sxs-lookup"><span data-stu-id="804bf-109">Teams Service Administrator</span></span>

<span data-ttu-id="804bf-110">Encontrará más información acerca de las funciones de administración en Microsoft Teams [aquí](using-admin-roles.md), y pueden leer más información acerca de cómo usar los cmdlets de PowerShell para la administración de equipos en la [referencia del cmdlet de equipos de Microsoft](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="804bf-110">You can learn more about admin roles in Microsoft Teams [here](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="804bf-111">En este artículo se proporciona una visión general de las herramientas de administración de equipos en el Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="804bf-111">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="804bf-112">Cuadrícula de visión general de los equipos</span><span class="sxs-lookup"><span data-stu-id="804bf-112">Teams overview grid</span></span>

<span data-ttu-id="804bf-113">Herramientas de administración de los equipos se encuentran en el nodo de **los equipos** en el Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="804bf-113">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="804bf-114">(En el centro de administración, seleccione **los equipos** > **administrar equipos**.) Cada equipo se respaldadas por un grupo de Office 365, y este nodo proporciona una vista de todos los grupos que se han habilitado para los equipos de la organización de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="804bf-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of all groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Cuadrícula de visión general de los equipos](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="804bf-116">La cuadrícula muestra las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="804bf-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="804bf-117">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="804bf-117">**Team name**</span></span>
- <span data-ttu-id="804bf-118">**Canales** : un recuento de todos los canales en el equipo, incluido el canal General de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="804bf-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="804bf-119">**Los usuarios** : un recuento del total de usuarios, incluidos los propietarios, los invitados y miembros desde el inquilino.</span><span class="sxs-lookup"><span data-stu-id="804bf-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="804bf-120">**Los propietarios de** -un recuento de los propietarios de este equipo.</span><span class="sxs-lookup"><span data-stu-id="804bf-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="804bf-121">**Los invitados** - un recuento de los usuarios de invitado de Azure Active Directory B2B que son miembros de este equipo.</span><span class="sxs-lookup"><span data-stu-id="804bf-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="804bf-122">**Privacidad** - la AccessType del grupo de realizar la copia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="804bf-122">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="804bf-123">Buscar.</span><span class="sxs-lookup"><span data-stu-id="804bf-123">Search</span></span>

<span data-ttu-id="804bf-124">Búsqueda actualmente es compatible con la cadena "Comienza por" y busca en el campo **nombre del equipo** .</span><span class="sxs-lookup"><span data-stu-id="804bf-124">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="804bf-125">Editar.</span><span class="sxs-lookup"><span data-stu-id="804bf-125">Edit</span></span>

<span data-ttu-id="804bf-126">Puede editar la configuración específica de equipo y grupo seleccionando un equipo de la cuadrícula y, a continuación, seleccionando el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="804bf-126">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Editar equipo](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="804bf-128">Perfiles de equipo</span><span class="sxs-lookup"><span data-stu-id="804bf-128">Team profile</span></span>

<span data-ttu-id="804bf-129">Puede navegar a la página de perfil de equipo de cualquier equipo de la cuadrícula de visión general de los equipos principal haciendo clic en el nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="804bf-129">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="804bf-130">La página de perfil de equipo muestra los miembros, los propietarios y los invitados que pertenecen al equipo (y su copia de grupo de Office 365), así como canales y la configuración del grupo.</span><span class="sxs-lookup"><span data-stu-id="804bf-130">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="804bf-131">Desde la página de perfil del equipo, se puede:</span><span class="sxs-lookup"><span data-stu-id="804bf-131">From the team profile page, you can:</span></span>

- <span data-ttu-id="804bf-132">Agregar o quitar miembros y propietarios.</span><span class="sxs-lookup"><span data-stu-id="804bf-132">Add or remove members and owners.</span></span>
- <span data-ttu-id="804bf-133">Agregar o quitar canales (tenga en cuenta que no se puede quitar el canal General).</span><span class="sxs-lookup"><span data-stu-id="804bf-133">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="804bf-134">Actualización del equipo y configuración de grupo.</span><span class="sxs-lookup"><span data-stu-id="804bf-134">Update team and group settings.</span></span>
 
![Perfiles de equipo](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="804bf-136">Realizar cambios en los equipos</span><span class="sxs-lookup"><span data-stu-id="804bf-136">Making changes to teams</span></span>

<span data-ttu-id="804bf-137">Puede cambiar los siguientes elementos de un equipo:</span><span class="sxs-lookup"><span data-stu-id="804bf-137">You can change the following elements of a team:</span></span>
- <span data-ttu-id="804bf-138">**Los usuarios en el equipo** , puede agregar o quitar miembros y promover o disminuir el nivel de los propietarios de</span><span class="sxs-lookup"><span data-stu-id="804bf-138">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="804bf-139">**Canales** : puede agregar nuevos canales o quitar canales existentes.</span><span class="sxs-lookup"><span data-stu-id="804bf-139">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="804bf-140">No se puede eliminar el canal "General" de forma predeterminada y una vez creados sólo se puede editar el nombre del canal, no descripción.</span><span class="sxs-lookup"><span data-stu-id="804bf-140">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="804bf-141">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="804bf-141">**Team name**</span></span>
- <span data-ttu-id="804bf-142">**Descripción de equipo**</span><span class="sxs-lookup"><span data-stu-id="804bf-142">**Team description**</span></span>
- <span data-ttu-id="804bf-143">**Fotografía de equipo**</span><span class="sxs-lookup"><span data-stu-id="804bf-143">**Team photo**</span></span>
- <span data-ttu-id="804bf-144">**Privacidad del equipo** - público o privado</span><span class="sxs-lookup"><span data-stu-id="804bf-144">**Team privacy** - public or private</span></span>
- <span data-ttu-id="804bf-145">**Clasificación de equipo** - respaldados por sus clasificaciones de grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="804bf-145">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="804bf-146">**Configuración del miembro de equipo** : configuración de miembro de equipo seleccione</span><span class="sxs-lookup"><span data-stu-id="804bf-146">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="804bf-147">Se registran los cambios que realice en un equipo.</span><span class="sxs-lookup"><span data-stu-id="804bf-147">The changes that you make to a team are logged.</span></span> <span data-ttu-id="804bf-148">Si modifica la configuración de grupo (cambiar el nombre, descripción, foto, privacidad, clasificación o los miembros del equipo), estos cambios se expresarán a usted a través de la canalización de auditoría.</span><span class="sxs-lookup"><span data-stu-id="804bf-148">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="804bf-149">Si va a realizar acciones contra la configuración específica de los equipos, los cambios se realiza un seguimiento y se expresarán en el canal general del equipo.</span><span class="sxs-lookup"><span data-stu-id="804bf-149">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="804bf-150">Más información</span><span class="sxs-lookup"><span data-stu-id="804bf-150">Learn more</span></span>

[<span data-ttu-id="804bf-151">Referencia del cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="804bf-151">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="804bf-152">Roles de administrador en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="804bf-152">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->


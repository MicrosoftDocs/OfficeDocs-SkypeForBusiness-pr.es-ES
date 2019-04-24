---
title: Administrar los equipos en el centro de administración de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Obtenga información sobre cómo ver o actualizar los equipos en el centro de administración de Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202752"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="907b4-103">Administrar los equipos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="907b4-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="907b4-104">Información general</span><span class="sxs-lookup"><span data-stu-id="907b4-104">Overview</span></span>

<span data-ttu-id="907b4-105">Como un administrador de TI, es posible que necesite vista o actualización de los equipos de su organización ha configurado para la colaboración o necesite para llevar a cabo las acciones de corrección, como la asignación de propietarios de los equipos sin dueño.</span><span class="sxs-lookup"><span data-stu-id="907b4-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="907b4-106">Puede administrar los equipos que se usan en la organización a través del módulo de PowerShell de los equipos de Microsoft y el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="907b4-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="907b4-107">Para las capacidades de administración completa con estos dos conjuntos de herramientas, debe asegurarse de que se le asigna uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="907b4-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="907b4-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="907b4-108">Global Administrator</span></span>
- <span data-ttu-id="907b4-109">Administrador de servicios de Teams</span><span class="sxs-lookup"><span data-stu-id="907b4-109">Teams Service Administrator</span></span>

<span data-ttu-id="907b4-110">Encontrará más información acerca de las funciones de administración en los equipos de [los roles de administrador de utilizar equipos de Microsoft para administrar los equipos](using-admin-roles.md)y puede leer más información acerca de cómo usar los cmdlets de PowerShell para la administración de equipos en la [referencia del cmdlet de equipos de Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="907b4-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="907b4-111">En este artículo se proporciona una visión general de las herramientas de administración de equipos en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="907b4-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="907b4-112">Cuadrícula de visión general de los equipos</span><span class="sxs-lookup"><span data-stu-id="907b4-112">Teams overview grid</span></span>

<span data-ttu-id="907b4-113">Herramientas de administración de los equipos se encuentran en el nodo de **los equipos** en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="907b4-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="907b4-114">(En el centro de administración, seleccione **los equipos** > **administrar equipos**.) Cada equipo se respaldadas por un grupo de Office 365, y este nodo proporciona una vista de grupos que se han habilitado para los equipos de la organización de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="907b4-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Cuadrícula de visión general de los equipos](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="907b4-116">La cuadrícula muestra las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="907b4-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="907b4-117">**Nombre de equipo**</span><span class="sxs-lookup"><span data-stu-id="907b4-117">**Team name**</span></span>
- <span data-ttu-id="907b4-118">**Canales** : un recuento de todos los canales en el equipo, incluido el canal General de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="907b4-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="907b4-119">**Los usuarios** : un recuento del total de usuarios, incluidos los propietarios, los invitados y miembros desde el inquilino.</span><span class="sxs-lookup"><span data-stu-id="907b4-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="907b4-120">**Los propietarios de** -un recuento de los propietarios de este equipo.</span><span class="sxs-lookup"><span data-stu-id="907b4-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="907b4-121">**Los invitados** - un recuento de los usuarios de invitado de Azure Active Directory B2B que son miembros de este equipo.</span><span class="sxs-lookup"><span data-stu-id="907b4-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="907b4-122">**Privacidad** - la visibilidad/AccessType del grupo de realizar la copia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="907b4-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="907b4-123">**Estado** : el archivado o estado activo para este equipo.</span><span class="sxs-lookup"><span data-stu-id="907b4-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="907b4-124">Obtenga más información sobre el archivado de los equipos en el [archivo o la restauración de un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="907b4-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="907b4-125">**GroupID** - GroupID único del grupo de realizar la copia de Office 365</span><span class="sxs-lookup"><span data-stu-id="907b4-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="907b4-126">**Clasificación** - la clasificación (si se usan en la organización) que se asigna al grupo de realizar la copia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="907b4-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="907b4-127">Obtenga más información acerca de las clasificaciones en [crear clasificaciones para los grupos de Office en su organización](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="907b4-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="907b4-128">**Descripción** : la descripción para el grupo de realizar la copia de Office 365</span><span class="sxs-lookup"><span data-stu-id="907b4-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="907b4-129">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="907b4-129">Search</span></span>

<span data-ttu-id="907b4-130">Búsqueda actualmente es compatible con la cadena "Comienza por" y busca en el campo **nombre del equipo** .</span><span class="sxs-lookup"><span data-stu-id="907b4-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="907b4-131">Editar</span><span class="sxs-lookup"><span data-stu-id="907b4-131">Edit</span></span>

<span data-ttu-id="907b4-132">Puede editar la configuración específica de equipo y grupo seleccionando un equipo de la cuadrícula y, a continuación, seleccionando el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="907b4-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Editar equipo](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="907b4-134">Perfiles de equipo</span><span class="sxs-lookup"><span data-stu-id="907b4-134">Team profile</span></span>

<span data-ttu-id="907b4-135">Puede navegar a la página de perfil de equipo de cualquier equipo de la cuadrícula de visión general de los equipos principal haciendo clic en el nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="907b4-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="907b4-136">La página de perfil de equipo muestra los miembros, los propietarios y los invitados que pertenecen al equipo (y su copia de grupo de Office 365), así como canales y la configuración del grupo.</span><span class="sxs-lookup"><span data-stu-id="907b4-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="907b4-137">Desde la página de perfil del equipo, se puede:</span><span class="sxs-lookup"><span data-stu-id="907b4-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="907b4-138">Agregar o quitar miembros y propietarios.</span><span class="sxs-lookup"><span data-stu-id="907b4-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="907b4-139">Agregar o quitar canales (tenga en cuenta que no se puede quitar el canal General).</span><span class="sxs-lookup"><span data-stu-id="907b4-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="907b4-140">Actualización del equipo y configuración de grupo.</span><span class="sxs-lookup"><span data-stu-id="907b4-140">Update team and group settings.</span></span>
 
![Perfiles de equipo](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="907b4-142">Realizar cambios en los equipos</span><span class="sxs-lookup"><span data-stu-id="907b4-142">Making changes to teams</span></span>

<span data-ttu-id="907b4-143">Puede cambiar los siguientes elementos de un equipo:</span><span class="sxs-lookup"><span data-stu-id="907b4-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="907b4-144">**Los usuarios en el equipo** , puede agregar o quitar miembros y promover o disminuir el nivel de los propietarios de</span><span class="sxs-lookup"><span data-stu-id="907b4-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="907b4-145">**Canales** : puede agregar nuevos canales o quitar canales existentes.</span><span class="sxs-lookup"><span data-stu-id="907b4-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="907b4-146">No se puede eliminar el canal "General" de forma predeterminada y una vez creados sólo se puede editar el nombre del canal, no descripción.</span><span class="sxs-lookup"><span data-stu-id="907b4-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="907b4-147">**Nombre de equipo**</span><span class="sxs-lookup"><span data-stu-id="907b4-147">**Team name**</span></span>
- <span data-ttu-id="907b4-148">**Descripción de equipo**</span><span class="sxs-lookup"><span data-stu-id="907b4-148">**Team description**</span></span>
- <span data-ttu-id="907b4-149">**Privacidad del equipo** - público o privado</span><span class="sxs-lookup"><span data-stu-id="907b4-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="907b4-150">**Clasificación de equipo** - respaldados por sus clasificaciones de grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="907b4-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="907b4-151">**Configuración del miembro de equipo** : configuración de miembro de equipo seleccione</span><span class="sxs-lookup"><span data-stu-id="907b4-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="907b4-152">Otros cambios admitidos para los equipos</span><span class="sxs-lookup"><span data-stu-id="907b4-152">Other supported changes to teams</span></span>

- <span data-ttu-id="907b4-153">**Eliminar** - eliminación de un equipo es una eliminación temporalmente del equipo y el grupo correspondiente de Office 365.</span><span class="sxs-lookup"><span data-stu-id="907b4-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="907b4-154">Para restaurar un equipo eliminado por error, siga las instrucciones que aparecen en la [restauración de un grupo de 365 eliminado de Office](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="907b4-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="907b4-155">**Archivo** - archivado un equipo pone el equipo en modo de sólo lectura dentro de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="907b4-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="907b4-156">Como administrador, puede archivar y unarchive los equipos en nombre de la organización a través del portal de administración.</span><span class="sxs-lookup"><span data-stu-id="907b4-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="907b4-157">Se registran los cambios que realice en un equipo.</span><span class="sxs-lookup"><span data-stu-id="907b4-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="907b4-158">Si modifica la configuración de grupo (cambiar el nombre, descripción, foto, privacidad, clasificación o los miembros del equipo), estos cambios se expresarán a usted a través de la canalización de auditoría.</span><span class="sxs-lookup"><span data-stu-id="907b4-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="907b4-159">Si va a realizar acciones contra la configuración específica de los equipos, los cambios se realiza un seguimiento y se expresarán en el canal general del equipo.</span><span class="sxs-lookup"><span data-stu-id="907b4-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="907b4-160">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="907b4-160">Troubleshooting</span></span>

<span data-ttu-id="907b4-161">**Problema: Los equipos que faltan en la cuadrícula de visión general del equipo**</span><span class="sxs-lookup"><span data-stu-id="907b4-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="907b4-162">Al escribir el centro de administración de Microsoft Teams, debajo de la opción de **los equipos** faltan algunas de sus equipos desde la lista en la cuadrícula de visión general de los equipos.</span><span class="sxs-lookup"><span data-stu-id="907b4-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="907b4-163">**Causa**: este problema se produce cuando el equipo de perfil se incorrectamente (o no todavía) generó el sistema que puede dar lugar a una propiedad que faltan para que se reconozca.</span><span class="sxs-lookup"><span data-stu-id="907b4-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="907b4-164">**Solución: Establezca manualmente la propiedad en el valor correcto a través de MS Graph**</span><span class="sxs-lookup"><span data-stu-id="907b4-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="907b4-165">Reemplace **{groupid}** en la consulta para el GroupId real en cuestión, que se puede obtener a través de la Exchange Online powershell, con el cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como el atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="907b4-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="907b4-166">[El Explorador de gráfico](https://developer.microsoft.com/en-us/graph/graph-explorer) de acceso</span><span class="sxs-lookup"><span data-stu-id="907b4-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="907b4-167">Inicie sesión en el Explorador de gráfico en el menú de la izquierda</span><span class="sxs-lookup"><span data-stu-id="907b4-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="907b4-168">Cambie la línea de consulta para: revisión > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="907b4-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="907b4-169">Agregue el siguiente valor en el cuerpo de solicitud: {"resourceProvisioningOptions": ["equipo"]}</span><span class="sxs-lookup"><span data-stu-id="907b4-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="907b4-170">Ejecute la consulta en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="907b4-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="907b4-171">Confirme que el equipo correctamente aparece en el centro de administración de Microsoft Teams - información general del equipo</span><span class="sxs-lookup"><span data-stu-id="907b4-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="907b4-172">Más información</span><span class="sxs-lookup"><span data-stu-id="907b4-172">Learn more</span></span>

[<span data-ttu-id="907b4-173">Referencia del cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="907b4-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="907b4-174">Roles de administrador en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="907b4-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->


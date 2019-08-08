---
title: Administrar equipos en el Centro de administración de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin
description: Obtenga información sobre cómo ver o actualizar los equipos en el centro de administración de Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f495a9cc5b3bfb1fd270e85b2a1fb17bd5f11e68
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233357"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="419f3-103">Administrar equipos en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="419f3-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="419f3-104">Información general</span><span class="sxs-lookup"><span data-stu-id="419f3-104">Overview</span></span>

<span data-ttu-id="419f3-105">Como administrador de ti, es posible que necesite ver o actualizar los equipos que su organización ha configurado para la colaboración, o es posible que tenga que realizar acciones de corrección como asignar propietarios a equipos sin propietario.</span><span class="sxs-lookup"><span data-stu-id="419f3-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="419f3-106">Puede administrar los equipos que se usan en la organización a través del módulo Microsoft Teams PowerShell y el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="419f3-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="419f3-107">Para obtener capacidades de administración completas con estos dos conjuntos de herramientas, debe asegurarse de que tiene asignada una de las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="419f3-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="419f3-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="419f3-108">Global Administrator</span></span>
- <span data-ttu-id="419f3-109">Administrador de servicios de Teams</span><span class="sxs-lookup"><span data-stu-id="419f3-109">Teams Service Administrator</span></span>

<span data-ttu-id="419f3-110">Puede obtener más información sobre los roles de administrador en Teams en [usar los roles de administrador de Microsoft Teams para administrar equipos](using-admin-roles.md)y puede obtener más información sobre cómo usar los cmdlets de PowerShell para administrar equipos en la [Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="419f3-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="419f3-111">Este artículo proporciona una descripción general de las herramientas de administración de Teams en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="419f3-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="419f3-112">Cuadrícula de información general de Teams</span><span class="sxs-lookup"><span data-stu-id="419f3-112">Teams overview grid</span></span>

<span data-ttu-id="419f3-113">Las herramientas de administración para Teams \*\*\*\* se encuentran en el nodo Teams del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="419f3-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="419f3-114">(En el centro de administración, seleccione **Teams** > **Manage Teams**). Cada equipo está respaldado por un grupo de Office 365, y este nodo proporciona una vista de los grupos que se han habilitado en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="419f3-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Captura de pantalla de la cuadrícula de información general de Teams](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="419f3-116">La cuadrícula muestra las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="419f3-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="419f3-117">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="419f3-117">**Team name**</span></span>
- <span data-ttu-id="419f3-118">**Canales** : un recuento de todos los canales del equipo, incluido el canal general predeterminado.</span><span class="sxs-lookup"><span data-stu-id="419f3-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="419f3-119">**Usuarios** : un recuento de total de usuarios, incluidos los propietarios, los invitados y los miembros de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="419f3-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="419f3-120">**Propietarios** : un recuento de propietarios de este equipo.</span><span class="sxs-lookup"><span data-stu-id="419f3-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="419f3-121">**Invitados** : un recuento de usuarios invitados B2B de Azure Active Directory que son miembros de este equipo.</span><span class="sxs-lookup"><span data-stu-id="419f3-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="419f3-122">**Privacidad** : la visibilidad/AccessType del grupo de respaldo de la oficina de 365.</span><span class="sxs-lookup"><span data-stu-id="419f3-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="419f3-123">**Estado** : el estado de archivo o activo de este equipo.</span><span class="sxs-lookup"><span data-stu-id="419f3-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="419f3-124">Obtenga más información sobre el archivado de Teams en el [archivo o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="419f3-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="419f3-125">**GROUPID** : el GROUPID exclusivo del grupo de respaldo de la oficina de 365</span><span class="sxs-lookup"><span data-stu-id="419f3-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="419f3-126">**Clasificación** : la clasificación (si se usa en su organización) asignada al grupo de copia de seguridad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="419f3-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="419f3-127">Obtenga más información acerca de las clasificaciones en [crear clasificaciones para los grupos de Office de su organización](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="419f3-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="419f3-128">**Descripción** : la descripción establecida para el grupo de copia de seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="419f3-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="419f3-129">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="419f3-129">Search</span></span>

<span data-ttu-id="419f3-130">La búsqueda es compatible actualmente con la cadena "comienza con" y busca en el campo de **nombre de equipo** .</span><span class="sxs-lookup"><span data-stu-id="419f3-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="419f3-131">Editar</span><span class="sxs-lookup"><span data-stu-id="419f3-131">Edit</span></span>

<span data-ttu-id="419f3-132">Puede editar la configuración específica del grupo y del equipo seleccionando un equipo de la cuadrícula y seleccionando el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="419f3-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Captura de pantalla de las opciones de editar equipo](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="419f3-134">Perfil de equipo</span><span class="sxs-lookup"><span data-stu-id="419f3-134">Team profile</span></span>

<span data-ttu-id="419f3-135">Puede ir a la página de Perfil de equipo de cualquier equipo desde la cuadrícula de información general de equipos principales haciendo clic en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="419f3-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="419f3-136">En la página Perfil de equipo se muestran los miembros, los propietarios y los invitados que pertenecen al equipo (y su grupo de O365 que respalda), así como los canales y la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="419f3-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="419f3-137">En la página Perfil de equipo, puede:</span><span class="sxs-lookup"><span data-stu-id="419f3-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="419f3-138">Agregar o quitar miembros y propietarios.</span><span class="sxs-lookup"><span data-stu-id="419f3-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="419f3-139">Agregar o quitar canales (tenga en cuenta que no puede quitar el canal general).</span><span class="sxs-lookup"><span data-stu-id="419f3-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="419f3-140">Actualizar la configuración del equipo y el grupo.</span><span class="sxs-lookup"><span data-stu-id="419f3-140">Update team and group settings.</span></span>
 
![Captura de pantalla de un perfil de equipo de ejemplo](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="419f3-142">Realizar cambios en los equipos</span><span class="sxs-lookup"><span data-stu-id="419f3-142">Making changes to teams</span></span>

<span data-ttu-id="419f3-143">Puede cambiar los siguientes elementos de un equipo:</span><span class="sxs-lookup"><span data-stu-id="419f3-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="419f3-144">**Usuarios del equipo** : puede Agregar o quitar miembros, y promover o disminuir el nivel de propietarios.</span><span class="sxs-lookup"><span data-stu-id="419f3-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="419f3-145">**Canales** : puede Agregar canales nuevos o quitar los canales existentes.</span><span class="sxs-lookup"><span data-stu-id="419f3-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="419f3-146">No puedes eliminar el canal "general" predeterminado y, una vez que lo hayas creado, solo podrás modificar el nombre del canal, no una descripción.</span><span class="sxs-lookup"><span data-stu-id="419f3-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="419f3-147">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="419f3-147">**Team name**</span></span>
- <span data-ttu-id="419f3-148">**Descripción del equipo**</span><span class="sxs-lookup"><span data-stu-id="419f3-148">**Team description**</span></span>
- <span data-ttu-id="419f3-149">**Privacidad del equipo** : pública o privada</span><span class="sxs-lookup"><span data-stu-id="419f3-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="419f3-150">**Clasificación de equipo** : respaldado por las clasificaciones de grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="419f3-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="419f3-151">**Configuración de miembro del equipo** : seleccionar configuración de miembro del equipo</span><span class="sxs-lookup"><span data-stu-id="419f3-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="419f3-152">Otros cambios admitidos en los equipos</span><span class="sxs-lookup"><span data-stu-id="419f3-152">Other supported changes to teams</span></span>

- <span data-ttu-id="419f3-153">**Eliminar** : la eliminación de un equipo es una eliminación parcial del equipo y del grupo de Office 365 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="419f3-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="419f3-154">Para restaurar un equipo eliminado por error, siga las instrucciones de [restaurar un grupo de Office 365 eliminado](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="419f3-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="419f3-155">**Archivo** : archivar un equipo pone el equipo en modo de solo lectura dentro de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="419f3-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="419f3-156">Como administrador, puede archivar y desarchivar Teams en nombre de su organización a través del portal de administración.</span><span class="sxs-lookup"><span data-stu-id="419f3-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="419f3-157">Se registran los cambios que realice en un equipo.</span><span class="sxs-lookup"><span data-stu-id="419f3-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="419f3-158">Si va a modificar la configuración del grupo (cambiar el nombre, la descripción, la foto, la privacidad, la clasificación o los miembros del equipo), estos cambios se le atribuyen a través de la canalización de auditoría.</span><span class="sxs-lookup"><span data-stu-id="419f3-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="419f3-159">Si va a realizar acciones con la configuración específica de Teams, se hará un seguimiento de los cambios y se les atribuye en el canal general del equipo.</span><span class="sxs-lookup"><span data-stu-id="419f3-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="419f3-160">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="419f3-160">Troubleshooting</span></span>

<span data-ttu-id="419f3-161">**Problema: falta Teams en la cuadrícula de información general de equipo**</span><span class="sxs-lookup"><span data-stu-id="419f3-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="419f3-162">Al entrar en el centro de administración de Microsoft Teams \*\*\*\* , en la opción de Teams, algunos de sus equipos no aparecen en la lista de la cuadrícula de información general de Teams.</span><span class="sxs-lookup"><span data-stu-id="419f3-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="419f3-163">**Causa**: este problema se produce cuando el sistema no ha sobrearchivado (o todavía no ha sido creado por el equipo), lo que puede llevar a que falte una propiedad para que lo reconozca.</span><span class="sxs-lookup"><span data-stu-id="419f3-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="419f3-164">**Solución: establezca manualmente la propiedad en el valor correcto a través de MS Graph.**</span><span class="sxs-lookup"><span data-stu-id="419f3-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="419f3-165">Reemplace **{GROUPID}** en la consulta del GROUPID real en cuestión, que puede obtener a través de Exchange Online PowerShell, con el cmdlet **"[Get-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como el atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="419f3-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="419f3-166">[Explorador de gráficos](https://developer.microsoft.com/en-us/graph/graph-explorer) de Access</span><span class="sxs-lookup"><span data-stu-id="419f3-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="419f3-167">Iniciar sesión en el explorador de gráficos en el menú de la izquierda</span><span class="sxs-lookup"><span data-stu-id="419f3-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="419f3-168">Cambiar la línea de consulta a: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="419f3-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="419f3-169">Agregue el valor siguiente en el cuerpo de la solicitud: {"resourceProvisioningOptions": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="419f3-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="419f3-170">Ejecute la consulta en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="419f3-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="419f3-171">Confirmar que el equipo aparece correctamente en el centro de administración de Microsoft Teams: información general del equipo</span><span class="sxs-lookup"><span data-stu-id="419f3-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="419f3-172">Más información</span><span class="sxs-lookup"><span data-stu-id="419f3-172">Learn more</span></span>

[<span data-ttu-id="419f3-173">Referencia del cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="419f3-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="419f3-174">Roles de administrador en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="419f3-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->


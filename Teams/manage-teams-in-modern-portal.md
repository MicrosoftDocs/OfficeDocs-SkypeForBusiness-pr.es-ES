---
title: Administrar equipos en el centro de administración de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Obtenga información sobre cómo ver o actualizar los equipos en el centro de administración de Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fea7081ee66cbd7b103f4292f577aaf5d841e11
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "37571939"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2ba04-103">Administrar equipos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ba04-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="2ba04-104">Información general</span><span class="sxs-lookup"><span data-stu-id="2ba04-104">Overview</span></span>

<span data-ttu-id="2ba04-105">Como administrador, es posible que tenga que ver o actualizar los equipos en los que la organización configuró la colaboración, o es posible que tenga que realizar acciones de corrección, como asignar propietarios a equipos sin propietario.</span><span class="sxs-lookup"><span data-stu-id="2ba04-105">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="2ba04-106">Puede administrar los equipos que se usan en la organización a través del módulo Microsoft Teams PowerShell y el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba04-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="2ba04-107">Para obtener capacidades de administración completas con estos dos conjuntos de herramientas, debe asegurarse de que tiene asignada una de las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="2ba04-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="2ba04-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="2ba04-108">Global Administrator</span></span>
- <span data-ttu-id="2ba04-109">Administrador de servicios de Teams</span><span class="sxs-lookup"><span data-stu-id="2ba04-109">Teams Service Administrator</span></span>

<span data-ttu-id="2ba04-110">Puede obtener más información sobre los roles de administrador en Teams en [usar los roles de administrador de Microsoft Teams para administrar equipos](using-admin-roles.md)y puede obtener más información sobre cómo usar los cmdlets de PowerShell para administrar equipos en la [Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="2ba04-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>

<span data-ttu-id="2ba04-111">Este artículo proporciona una descripción general de las herramientas de administración de Teams en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba04-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="2ba04-112">Cuadrícula de información general de Teams</span><span class="sxs-lookup"><span data-stu-id="2ba04-112">Teams overview grid</span></span>

<span data-ttu-id="2ba04-113">Las herramientas de administración para Teams se encuentran en el nodo **Teams** del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba04-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2ba04-114">(En el centro de administración, seleccione **Teams** > **Manage Teams**). Cada equipo está respaldado por un grupo de Office 365, y este nodo proporciona una vista de los grupos que se han habilitado en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba04-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Captura de pantalla de la cuadrícula de información general de Teams](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="2ba04-116">La cuadrícula muestra las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2ba04-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="2ba04-117">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="2ba04-117">**Team name**</span></span>
- <span data-ttu-id="2ba04-118">**Canales** : un recuento de todos los canales del equipo, incluido el canal general predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2ba04-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="2ba04-119">**Miembros del equipo** : un recuento de total de usuarios, incluidos los propietarios, los invitados y los miembros de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="2ba04-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="2ba04-120">**Propietarios** : un recuento de propietarios de este equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="2ba04-121">**Invitados** : un recuento de usuarios invitados B2B de Azure Active Directory que son miembros de este equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="2ba04-122">**Privacidad** : la visibilidad/AccessType del grupo de respaldo de la oficina de 365.</span><span class="sxs-lookup"><span data-stu-id="2ba04-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="2ba04-123">**Estado** : el estado de archivo o activo de este equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="2ba04-124">Obtenga más información sobre el archivado de Teams en [archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="2ba04-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="2ba04-125">**Descripción** : la descripción del grupo de copia de seguridad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ba04-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="2ba04-126">**Clasificación** : la clasificación (si se usa en su organización) asignada al grupo de copia de seguridad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ba04-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="2ba04-127">Obtenga más información acerca de las clasificaciones en [crear clasificaciones para los grupos de Office de su organización](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="2ba04-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="2ba04-128">**GROUPID** : el único GROUPID del grupo de respaldo de la oficina de 365.</span><span class="sxs-lookup"><span data-stu-id="2ba04-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="2ba04-129">Si no ve todas estas propiedades en la cuadrícula, haga clic en el icono **Editar columnas** .</span><span class="sxs-lookup"><span data-stu-id="2ba04-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="2ba04-130">En el panel **Editar columnas** , puede usar el botón de alternancia para activar o desactivar las columnas de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="2ba04-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="2ba04-131">Cuando haya terminado, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2ba04-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="2ba04-132">Suma</span><span class="sxs-lookup"><span data-stu-id="2ba04-132">Add</span></span>

<span data-ttu-id="2ba04-133">Para agregar un nuevo equipo, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2ba04-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="2ba04-134">En el panel **Agregar un nuevo equipo** , asigne un nombre y una descripción al equipo, establezca si desea convertirlo en un equipo público o privado, y establezca la clasificación.</span><span class="sxs-lookup"><span data-stu-id="2ba04-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="2ba04-135">Editar</span><span class="sxs-lookup"><span data-stu-id="2ba04-135">Edit</span></span>

<span data-ttu-id="2ba04-136">Para editar la configuración específica del grupo y del equipo, seleccione el equipo haciendo clic a la izquierda del nombre del equipo y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2ba04-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="2ba04-137">Archivo</span><span class="sxs-lookup"><span data-stu-id="2ba04-137">Archive</span></span>

<span data-ttu-id="2ba04-138">Puede archivar un equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-138">You can archive a team.</span></span> <span data-ttu-id="2ba04-139">El archivado de un equipo pone al equipo en modo de solo lectura dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba04-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="2ba04-140">Como administrador, puede archivar y desarchivar Teams en nombre de su organización en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="2ba04-140">As an admin, you can archive and unarchive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="2ba04-141">Eliminar</span><span class="sxs-lookup"><span data-stu-id="2ba04-141">Delete</span></span>

<span data-ttu-id="2ba04-142">Eliminar un equipo es una eliminación parcial del equipo y el grupo de Office 365 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2ba04-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="2ba04-143">Para restaurar un equipo eliminado por error, siga las instrucciones de [restaurar un grupo eliminado de Office 365](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2ba04-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="2ba04-144">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="2ba04-144">Search</span></span>

<span data-ttu-id="2ba04-145">La búsqueda es compatible actualmente con la cadena "comienza con" y busca en el campo de **nombre de equipo** .</span><span class="sxs-lookup"><span data-stu-id="2ba04-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="2ba04-146">Perfil de equipo</span><span class="sxs-lookup"><span data-stu-id="2ba04-146">Team profile</span></span>

<span data-ttu-id="2ba04-147">Puede ir a la página de Perfil de equipo de cualquier equipo desde la cuadrícula de información general de equipos principales haciendo clic en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="2ba04-148">La página Perfil de equipo muestra los miembros, propietarios e invitados que pertenecen al equipo (y su grupo de copia de Office 365), así como los canales y la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="2ba04-149">En la página Perfil de equipo, puede:</span><span class="sxs-lookup"><span data-stu-id="2ba04-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="2ba04-150">Agregar o quitar miembros y propietarios.</span><span class="sxs-lookup"><span data-stu-id="2ba04-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="2ba04-151">Agregar o quitar canales (tenga en cuenta que no puede quitar el canal general).</span><span class="sxs-lookup"><span data-stu-id="2ba04-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="2ba04-152">Cambiar la configuración del equipo y el grupo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-152">Change team and group settings.</span></span>
 
![Captura de pantalla de un perfil de equipo de ejemplo](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="2ba04-154">Realizar cambios en los equipos</span><span class="sxs-lookup"><span data-stu-id="2ba04-154">Making changes to teams</span></span>

<span data-ttu-id="2ba04-155">En la página de perfil del equipo, puede cambiar los siguientes elementos de un equipo:</span><span class="sxs-lookup"><span data-stu-id="2ba04-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="2ba04-156">**Miembros** : agregar o quitar miembros y promover o disminuir el nivel de propietarios.</span><span class="sxs-lookup"><span data-stu-id="2ba04-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="2ba04-157">**Canales** : agregue canales nuevos y edite o elimine canales existentes.</span><span class="sxs-lookup"><span data-stu-id="2ba04-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="2ba04-158">Recuerde que no puede eliminar el canal general predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2ba04-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="2ba04-159">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="2ba04-159">**Team name**</span></span>
- <span data-ttu-id="2ba04-160">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2ba04-160">**Description**</span></span>
- <span data-ttu-id="2ba04-161">**Privacidad** : defina si el equipo es público o privado.</span><span class="sxs-lookup"><span data-stu-id="2ba04-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="2ba04-162">**Clasificación** : está respaldado por las clasificaciones de grupo de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ba04-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="2ba04-163">Elija **confidencial**, **muy confidencial**o **General**.</span><span class="sxs-lookup"><span data-stu-id="2ba04-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="2ba04-164">**Configuración de conversaciones** : establezca si los miembros pueden editar y eliminar los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="2ba04-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="2ba04-165">**Configuración de canales** : permite establecer si los miembros pueden crear nuevos canales y editar los existentes, así como agregar, editar y quitar pestañas, conectores y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2ba04-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="2ba04-166">Se registran los cambios que realice en un equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="2ba04-167">Si va a modificar la configuración de un grupo (cambiar el nombre, la descripción, la foto, la privacidad, la clasificación o los miembros del equipo), los cambios se atribuyen a través de la canalización de auditoría.</span><span class="sxs-lookup"><span data-stu-id="2ba04-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="2ba04-168">Si está realizando acciones con la configuración específica de Teams, se hace un seguimiento de los cambios y se les atribuye en el canal general del equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2ba04-169">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2ba04-169">Troubleshooting</span></span>

<span data-ttu-id="2ba04-170">**Problema: falta Teams en la cuadrícula de información general de equipo**</span><span class="sxs-lookup"><span data-stu-id="2ba04-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="2ba04-171">Algunos de sus equipos no están en la lista de equipos de la cuadrícula de información general de Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba04-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="2ba04-172">**Causa**: este problema se produce cuando el sistema no ha sobrearchivado (o todavía no ha sido creado por el equipo), lo que puede llevar a que falte una propiedad para que lo reconozca.</span><span class="sxs-lookup"><span data-stu-id="2ba04-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="2ba04-173">**Solución: establezca manualmente la propiedad en el valor correcto a través de MS Graph.**</span><span class="sxs-lookup"><span data-stu-id="2ba04-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="2ba04-174">Reemplace **{GROUPID}** en la consulta del GROUPID real en cuestión, que puede obtener a través de Exchange Online PowerShell, con el cmdlet **"[Get-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como el atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="2ba04-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="2ba04-175">[Explorador de gráficos](https://developer.microsoft.com/en-us/graph/graph-explorer)de Access.</span><span class="sxs-lookup"><span data-stu-id="2ba04-175">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).</span></span>

2. <span data-ttu-id="2ba04-176">Inicie sesión en el explorador de gráficos en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="2ba04-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="2ba04-177">Cambie la línea de consulta a: PATCH > v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}>.</span><span class="sxs-lookup"><span data-stu-id="2ba04-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="2ba04-178">Agregue el valor siguiente en el cuerpo de la solicitud: {"resourceProvisioningOptions": ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="2ba04-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="2ba04-179">Ejecute la consulta en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="2ba04-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="2ba04-180">Confirme que el equipo aparece correctamente en el centro de administración de Microsoft Teams: información general del equipo.</span><span class="sxs-lookup"><span data-stu-id="2ba04-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="2ba04-181">Más información</span><span class="sxs-lookup"><span data-stu-id="2ba04-181">Learn more</span></span>

- [<span data-ttu-id="2ba04-182">Referencia del cmdlet de Teams</span><span class="sxs-lookup"><span data-stu-id="2ba04-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="2ba04-183">Usar los roles de administrador de Teams para administrar equipos</span><span class="sxs-lookup"><span data-stu-id="2ba04-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="2ba04-184">Plan para la administración del ciclo de vida en Teams</span><span class="sxs-lookup"><span data-stu-id="2ba04-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)

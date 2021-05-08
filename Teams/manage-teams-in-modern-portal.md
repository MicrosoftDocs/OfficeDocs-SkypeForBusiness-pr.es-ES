---
title: Administrar equipos en el Centro de administración de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Obtenga información acerca de cómo ver o actualizar los equipos que su organización ha configurado para colaboración en el centro de administración de Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237546"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8f4d3-103">Administrar equipos en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f4d3-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="8f4d3-104">Información general</span><span class="sxs-lookup"><span data-stu-id="8f4d3-104">Overview</span></span>

<span data-ttu-id="8f4d3-105">Este artículo proporciona una descripción general de las herramientas de administración para equipos en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="8f4d3-106">Como administrador, es posible que tenga que ver o actualizar los equipos que la organización configuró para la colaboración, o es posible que tenga que llevar a cabo acciones de corrección, como la asignación de propietarios a equipos sin propietario.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="8f4d3-107">Puede administrar los equipos que se usan en la organización tanto en el módulo de PowerShell para Microsoft Teams como en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="8f4d3-108">Puede acceder al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="8f4d3-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="8f4d3-109">Para obtener todas las funciones de administración con estos dos conjuntos de herramientas, debe asegurarse de que tiene asignado uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f4d3-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="8f4d3-110">Administrador global</span><span class="sxs-lookup"><span data-stu-id="8f4d3-110">Global Administrator</span></span>
- <span data-ttu-id="8f4d3-111">Teams Administrador</span><span class="sxs-lookup"><span data-stu-id="8f4d3-111">Teams Administrator</span></span>

<span data-ttu-id="8f4d3-112">Puede obtener más información acerca de los roles de administrador en Teams en [Usar los roles de administrador de Microsoft Teams para administrar equipos](using-admin-roles.md) y puede ver más sobre cómo usar los cmdlets de PowerShell para administrar equipos en la [referencia de cmdlets de Microsoft Teams](/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="8f4d3-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="8f4d3-113">Información general de equipos</span><span class="sxs-lookup"><span data-stu-id="8f4d3-113">Teams overview grid</span></span>

<span data-ttu-id="8f4d3-114">Las herramientas de administración para equipos se encuentran en el nodo **Equipos** en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8f4d3-115">(En el centro de administración, seleccione **Teams**  >  **Administrar equipos).)** Cada equipo está a Microsoft 365 grupo y este nodo proporciona una vista de los grupos que se Microsoft Teams habilitados en su organización.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Captura de pantalla de la cuadrícula de información general de equipos](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="8f4d3-117">La cuadrícula muestra las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="8f4d3-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="8f4d3-118">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="8f4d3-118">**Team name**</span></span>
- <span data-ttu-id="8f4d3-119">**Canales**: es el número de todos los canales del equipo, incluido el canal General predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="8f4d3-120">**Miembros del equipo**: un recuento de los usuarios totales, incluidos los propietarios, los invitados y los miembros de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="8f4d3-121">**Propietarios**: un recuento de propietarios de este equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="8f4d3-122">**Invitados**: recuento de usuarios invitados de B2B de Azure Active Directory que son miembros de este equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="8f4d3-123">**Privacidad:** visibilidad/AccessType del grupo de Microsoft 365 copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="8f4d3-124">**Estado**: el estado Archivado o Activo de este equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="8f4d3-125">Obtenga más información sobre archivar equipos en [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="8f4d3-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="8f4d3-126">**Descripción:** la descripción del grupo de Microsoft 365 copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="8f4d3-127">**Clasificación:** la clasificación (si se usa en su organización) asignada al grupo de Microsoft 365 copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="8f4d3-128">Obtenga más información sobre las clasificaciones en [Crear clasificaciones para los grupos de Office de su organización](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="8f4d3-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="8f4d3-129">**GroupID:** el id. de grupo único del grupo Microsoft 365 copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="8f4d3-130">Si no ve todas estas propiedades en la cuadrícula, haga clic en el icono **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="8f4d3-131">En el panel **Editar columnas**, puede usar el botón de alternancia para activar o desactivar columnas en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="8f4d3-132">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="8f4d3-133">Agregar</span><span class="sxs-lookup"><span data-stu-id="8f4d3-133">Add</span></span>

<span data-ttu-id="8f4d3-134">Para agregar un nuevo equipo, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="8f4d3-135">En el panel **Agregar un nuevo equipo**, otorgue un nombre y una descripción al equipo, indique si quiere convertirlo en un equipo público o privado y establezca la clasificación.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="8f4d3-136">Los equipos recién creados se pueden administrar inmediatamente en el Centro de administración de Teams, a diferencia de la experiencia de otros clientes como, por ejemplo, Outlook.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="8f4d3-137">Editar </span><span class="sxs-lookup"><span data-stu-id="8f4d3-137">Edit</span></span>

<span data-ttu-id="8f4d3-138">Para editar configuraciones específicas de grupo y de equipo, seleccione el equipo haciendo clic a la izquierda del nombre de equipo y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="8f4d3-139">Archivar</span><span class="sxs-lookup"><span data-stu-id="8f4d3-139">Archive</span></span>

<span data-ttu-id="8f4d3-140">Puede archivar un equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-140">You can archive a team.</span></span> <span data-ttu-id="8f4d3-141">El archivado de un equipo convierte el equipo en modo de solo lectura en Teams.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="8f4d3-142">Como administrador, puede archivar y desarchivar equipos en nombre de su organización en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="8f4d3-143">Eliminar</span><span class="sxs-lookup"><span data-stu-id="8f4d3-143">Delete</span></span>

<span data-ttu-id="8f4d3-144">Eliminar un equipo es una eliminación suave del equipo y el grupo Microsoft 365 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="8f4d3-145">Para restaurar un equipo eliminado por error, siga las instrucciones de [Restaurar un grupo eliminado.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="8f4d3-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="8f4d3-146">Buscar </span><span class="sxs-lookup"><span data-stu-id="8f4d3-146">Search</span></span>

<span data-ttu-id="8f4d3-147">La búsqueda admite la cadena "Empieza por" y busca en el campo **Nombre del grupo**.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="8f4d3-148">Perfil de equipo</span><span class="sxs-lookup"><span data-stu-id="8f4d3-148">Team profile</span></span>

<span data-ttu-id="8f4d3-149">Puede ir a la página de perfil de equipo de cualquier equipo desde la cuadrícula principal de información general de equipos al hacer clic en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="8f4d3-150">La página de perfil del equipo muestra los miembros, propietarios e invitados que pertenecen al equipo (y su respaldo Microsoft 365 grupo), así como los canales y la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="8f4d3-151">En la página de perfil de equipo, puede:</span><span class="sxs-lookup"><span data-stu-id="8f4d3-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="8f4d3-152">Agregar o quitar miembros y propietarios.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="8f4d3-153">Agregar o quitar canales (tenga en cuenta que no se puede quitar el canal General).</span><span class="sxs-lookup"><span data-stu-id="8f4d3-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="8f4d3-154">Cambiar la configuración de grupo y equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-154">Change team and group settings.</span></span>
 
![Captura de pantalla de un perfil de equipo de ejemplo](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="8f4d3-156">Realizar cambios en los equipos</span><span class="sxs-lookup"><span data-stu-id="8f4d3-156">Making changes to teams</span></span>

<span data-ttu-id="8f4d3-157">En la página de perfil del equipo, puede cambiar los siguientes elementos de un equipo:</span><span class="sxs-lookup"><span data-stu-id="8f4d3-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="8f4d3-158">**Miembros**: agregue o elimine miembros y aumente o disminuya el nivel de los propietarios.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="8f4d3-159">**Canales**: agregue nuevos canales, y edite o elimine canales existentes.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="8f4d3-160">Recuerde que no puede eliminar el canal General predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="8f4d3-161">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="8f4d3-161">**Team name**</span></span>
- <span data-ttu-id="8f4d3-162">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8f4d3-162">**Description**</span></span>
- <span data-ttu-id="8f4d3-163">**Privacidad**: establezca si el equipo es público o privado.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="8f4d3-164">**Clasificación:** esto está a Microsoft 365 clasificaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="8f4d3-165">Elija **Confidencial**, **Extremadamente confidencial** o **General**.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="8f4d3-166">**Configuración de conversaciones**: establezca si los miembros pueden editar y eliminar los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="8f4d3-167">**Configuración de canales**: establezca si los miembros pueden crear nuevos canales y editar los existentes, y agregar, editar y quitar fichas, conectores y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="8f4d3-168">Los cambios realizados en un equipo se registran.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="8f4d3-169">Si va a modificar la configuración de un grupo (cambiar el nombre, la descripción, la foto, la privacidad, la clasificación o los miembros del equipo), los cambios se le atribuyen en la canalización de auditoría.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="8f4d3-170">Si lleva a cabo acciones en configuraciones específicas de Teams, se realiza un seguimiento de los cambios y se le atribuyen en el canal General del equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8f4d3-171">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="8f4d3-171">Troubleshooting</span></span>

<span data-ttu-id="8f4d3-172">**Problema: faltan equipos en la cuadrícula de información general de equipo**</span><span class="sxs-lookup"><span data-stu-id="8f4d3-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="8f4d3-173">Algunos de los equipos no están en la lista de equipos de la cuadrícula información general de equipos.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="8f4d3-174">**Causa**: este problema se produce cuando el sistema ha creado el perfil del equipo de forma incorrecta (o aún no se ha completado), lo que puede provocar que falte alguna propiedad para que se reconozca.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="8f4d3-175">**Resolución: configure manualmente la propiedad en el valor correcto mediante MS Graph**</span><span class="sxs-lookup"><span data-stu-id="8f4d3-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="8f4d3-176">Reemplace **{groupid}** en la consulta para el GroupId real en cuestión, que puede obtener mediante el PowerShell de Exchange Online con el cmdlet **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"**, como el atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="8f4d3-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="8f4d3-177">Acceder a [Probador de Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="8f4d3-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="8f4d3-178">Inicie sesión en el Probador de Graph en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="8f4d3-179">Cambie la línea de consulta a: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="8f4d3-180">Agregue el siguiente valor en el cuerpo de la solicitud: {"resourceProvisioningOptions": ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="8f4d3-181">Ejecute la consulta en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="8f4d3-182">Confirme que el equipo se muestra correctamente en el centro de administración de Microsoft Teams: información general de equipo.</span><span class="sxs-lookup"><span data-stu-id="8f4d3-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="8f4d3-183">Más información</span><span class="sxs-lookup"><span data-stu-id="8f4d3-183">Learn more</span></span>

- [<span data-ttu-id="8f4d3-184">Referencia de cmdlet para Teams</span><span class="sxs-lookup"><span data-stu-id="8f4d3-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="8f4d3-185">Usar roles de administrador de Teams para administrar equipos</span><span class="sxs-lookup"><span data-stu-id="8f4d3-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="8f4d3-186">Plan para la administración del ciclo de vida en Teams</span><span class="sxs-lookup"><span data-stu-id="8f4d3-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
---
title: Archivar o eliminar un equipo en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: En este artículo, obtendrá información sobre cómo archivar o eliminar permanentemente un equipo en Microsoft Teams.
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
ms.openlocfilehash: da2d330986ca2fd924df75e0fcae6fc4388c5d48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120842"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="0c373-103">Archivar o eliminar un equipo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c373-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="0c373-104">Con el tiempo, es posible que un equipo creado en Microsoft Teams se quede fuera de uso o que desee archivar o eliminar un equipo al final de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c373-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="0c373-105">Si es un administrador de Microsoft Teams, siga los pasos de este artículo para archivar o eliminar un equipo que ya no se necesita.</span><span class="sxs-lookup"><span data-stu-id="0c373-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="0c373-106">Cuando archiva un equipo, toda la actividad del equipo cesa.</span><span class="sxs-lookup"><span data-stu-id="0c373-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="0c373-107">El archivado de un equipo también archiva canales privados en el equipo y sus colecciones de sitios asociadas.</span><span class="sxs-lookup"><span data-stu-id="0c373-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="0c373-108">Sin embargo, puede seguir agregando o quitando los miembros de, y aún podrá ver todas las actividades del equipo en canales, archivos y chats estándar y privados.</span><span class="sxs-lookup"><span data-stu-id="0c373-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="0c373-109">Al eliminar un equipo, se elimina también la actividad de equipo en canales estándar y privados (y colecciones de sitios asociadas), archivos y charlas.</span><span class="sxs-lookup"><span data-stu-id="0c373-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c373-110">Los equipos archivados se pueden reactivar, pero no puede restaurar directamente un equipo que se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="0c373-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="0c373-111">Considere la posibilidad de archivar el equipo en primer lugar y, a continuación, posponga la eliminación hasta que esté seguro de que ya no necesita el equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="0c373-112">Archivar un equipo</span><span class="sxs-lookup"><span data-stu-id="0c373-112">Archive a team</span></span>

<span data-ttu-id="0c373-113">Siga estos pasos para archivar un equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="0c373-114">Debe ser administrador de servicio de Teams para realizar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="0c373-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="0c373-115">Consulte [Usar roles de administrador de Teams para administrar Teams](./using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.</span><span class="sxs-lookup"><span data-stu-id="0c373-115">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="0c373-116">En el centro de administración, seleccione **Teams**.</span><span class="sxs-lookup"><span data-stu-id="0c373-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="0c373-117">Para que seleccione un equipo, haga clic en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="0c373-118">Seleccione **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="0c373-118">Select **Archive**.</span></span> <span data-ttu-id="0c373-119">Aparecerá el siguiente mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c373-119">The following message will appear.</span></span>

    ![Captura de pantalla del mensaje del archivo de Teams](media/teams-archive-message.png)

4. <span data-ttu-id="0c373-121">Para evitar que las personas editen el contenido en el sitio de SharePoint y la pestaña de la Wiki asociada con el equipo, seleccione **Hacer que el sitio de SharePoint sea de solo lectura para los miembros del equipo**.</span><span class="sxs-lookup"><span data-stu-id="0c373-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="0c373-122">(Los propietarios de Teams seguirán pudiendo editar este contenido)</span><span class="sxs-lookup"><span data-stu-id="0c373-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="0c373-123">Seleccione **archivo** archivar el equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="0c373-124">El estado del equipo cambiará a **Archivados**.</span><span class="sxs-lookup"><span data-stu-id="0c373-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="0c373-125">Haga que un equipo archivado se active</span><span class="sxs-lookup"><span data-stu-id="0c373-125">Make an archived team active</span></span>

<span data-ttu-id="0c373-126">Siga estos pasos para volver a activar un equipo archivado.</span><span class="sxs-lookup"><span data-stu-id="0c373-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="0c373-127">En el centro de administración, seleccione **Teams**.</span><span class="sxs-lookup"><span data-stu-id="0c373-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="0c373-128">Para que seleccione un equipo, haga clic en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="0c373-129">Seleccione **Unarchivar**.</span><span class="sxs-lookup"><span data-stu-id="0c373-129">Select **Unarchive**.</span></span> <span data-ttu-id="0c373-130">El estado del equipo cambiará a **Activo**.</span><span class="sxs-lookup"><span data-stu-id="0c373-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="0c373-131">Eliminar un equipo</span><span class="sxs-lookup"><span data-stu-id="0c373-131">Delete a team</span></span>

<span data-ttu-id="0c373-132">Si el equipo no va a necesitar el futuro, puede eliminarlo en lugar de archivarlo.</span><span class="sxs-lookup"><span data-stu-id="0c373-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="0c373-133">Para eliminar un grupo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0c373-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="0c373-134">En el centro de administración, seleccione **Teams**.</span><span class="sxs-lookup"><span data-stu-id="0c373-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="0c373-135">Para que seleccione un equipo, haga clic en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="0c373-136">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0c373-136">Select **Delete**.</span></span> <span data-ttu-id="0c373-137">Aparecerá un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="0c373-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="0c373-138">Seleccione **Eliminar** para eliminar permanentemente el equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="0c373-139">Restaurar un equipo eliminado</span><span class="sxs-lookup"><span data-stu-id="0c373-139">Restore a deleted team</span></span>

<span data-ttu-id="0c373-140">Siga estos pasos para restaurar un equipo eliminado mediante la restauración del grupo de Microsoft 365 que esté asociado al equipo.</span><span class="sxs-lookup"><span data-stu-id="0c373-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="0c373-141">Restaurar el grupo de Microsoft 365 para un equipo restaura el contenido del equipo, incluidas las pestañas, canales estándar y canales privados y sus colecciones de sitios asociadas.</span><span class="sxs-lookup"><span data-stu-id="0c373-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="0c373-142">De forma predeterminada, un grupo eliminado de Microsoft 365 se conserva durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="0c373-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="0c373-143">Este periodo de 30 días se llama "eliminación parcial", ya que puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="0c373-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="0c373-144">Para obtener más información, consulte [restaurar un grupo eliminado](/microsoft-365/admin/create-groups/restore-deleted-group).</span><span class="sxs-lookup"><span data-stu-id="0c373-144">To learn more, see [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="0c373-145">Instalar el módulo AzureADPreview</span><span class="sxs-lookup"><span data-stu-id="0c373-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="0c373-146">Abra Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="0c373-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="0c373-147">Si tiene instalada una versión anterior del módulo AzureADPreview o el módulo AzureAD, desinstálela mediante la ejecución de uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0c373-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="0c373-148">Para instalar la última versión del módulo AzureADPreview, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c373-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="0c373-149">Restaurar el grupo de Microsoft 365 eliminado</span><span class="sxs-lookup"><span data-stu-id="0c373-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="0c373-150">Para conectarse a Azure AD, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c373-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="0c373-151">Cuando se le solicite, inicie sesión con su cuenta de administrador y su contraseña.</span><span class="sxs-lookup"><span data-stu-id="0c373-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="0c373-152">Ejecute lo siguiente para mostrar una lista de todos los grupos de Microsoft 365 eliminados de forma suave que siguen en un período de retención de 30 días.</span><span class="sxs-lookup"><span data-stu-id="0c373-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="0c373-153">Use el parámetro **-All $True** si tiene una gran cantidad de grupos.</span><span class="sxs-lookup"><span data-stu-id="0c373-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="0c373-154">Busque el grupo que quiera restaurar y, después, tome nota de la ID.</span><span class="sxs-lookup"><span data-stu-id="0c373-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="0c373-155">Ejecute lo siguiente para restaurar el grupo, donde [id.] es el ID. de grupo.</span><span class="sxs-lookup"><span data-stu-id="0c373-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="0c373-156">Ejecute lo siguiente para comprobar si el grupo se ha restaurado correctamente, donde [id.] es el ID. de grupo.</span><span class="sxs-lookup"><span data-stu-id="0c373-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="0c373-157">Se pueden tardar hasta 24 horas en completarse el proceso de restauración, tras lo cual el equipo y el contenido asociados al equipo, incluidos pestañas y canales, se muestran en equipos.</span><span class="sxs-lookup"><span data-stu-id="0c373-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
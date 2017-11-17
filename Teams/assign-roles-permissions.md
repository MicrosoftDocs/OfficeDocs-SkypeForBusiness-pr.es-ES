---
title: "Asignar roles y permisos en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9cc8a72cdabacb76638acb689c6622642c524c8e
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="ea670-103">Asignar roles y permisos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea670-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="ea670-p101">Dentro de Microsoft Teams hay dos roles: **Propietario** y **Miembro**. De forma predeterminada, el usuario que crea un equipo tiene el estado Propietario. Si se crea un equipo a partir de un grupo de Office 365 existente, los permisos se heredan.</span><span class="sxs-lookup"><span data-stu-id="ea670-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="ea670-107">En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:</span><span class="sxs-lookup"><span data-stu-id="ea670-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="ea670-108">Propietario de equipo</span><span class="sxs-lookup"><span data-stu-id="ea670-108">Team Owner</span></span>  |<span data-ttu-id="ea670-109">Miembro de equipo</span><span class="sxs-lookup"><span data-stu-id="ea670-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ea670-110">**Crear equipo**</span><span class="sxs-lookup"><span data-stu-id="ea670-110">**Create team**</span></span>     |<span data-ttu-id="ea670-111">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-111">Yes</span></span>        |<span data-ttu-id="ea670-112">No</span><span class="sxs-lookup"><span data-stu-id="ea670-112">No</span></span>         |
|<span data-ttu-id="ea670-113">**Abandonar equipo**</span><span class="sxs-lookup"><span data-stu-id="ea670-113">**Leave team**</span></span>     |<span data-ttu-id="ea670-114">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-114">Yes</span></span>         |<span data-ttu-id="ea670-115">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-115">Yes</span></span>         |
|<span data-ttu-id="ea670-116">**Editar nombre o descripción del equipo**</span><span class="sxs-lookup"><span data-stu-id="ea670-116">**Edit team name/description**</span></span>      |<span data-ttu-id="ea670-117">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-117">Yes</span></span>         |<span data-ttu-id="ea670-118">No</span><span class="sxs-lookup"><span data-stu-id="ea670-118">No</span></span>         |
|<span data-ttu-id="ea670-119">**Eliminar equipo**</span><span class="sxs-lookup"><span data-stu-id="ea670-119">**Delete team**</span></span>      |<span data-ttu-id="ea670-120">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-120">Yes</span></span>         |<span data-ttu-id="ea670-121">No</span><span class="sxs-lookup"><span data-stu-id="ea670-121">No</span></span>         |
|<span data-ttu-id="ea670-122">**Agregar canal**</span><span class="sxs-lookup"><span data-stu-id="ea670-122">**Add channel**</span></span>      |<span data-ttu-id="ea670-123">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-123">Yes</span></span>         |<span data-ttu-id="ea670-124">Sí*</span><span class="sxs-lookup"><span data-stu-id="ea670-124">Yes*</span></span>         |
|<span data-ttu-id="ea670-125">**Editar nombre o descripción del canal**</span><span class="sxs-lookup"><span data-stu-id="ea670-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="ea670-126">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-126">Yes</span></span>         |<span data-ttu-id="ea670-127">Sí*</span><span class="sxs-lookup"><span data-stu-id="ea670-127">Yes*</span></span>         |
|<span data-ttu-id="ea670-128">**Eliminar canal**</span><span class="sxs-lookup"><span data-stu-id="ea670-128">**Delete channel**</span></span>      |<span data-ttu-id="ea670-129">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-129">Yes</span></span>         |<span data-ttu-id="ea670-130">Sí*</span><span class="sxs-lookup"><span data-stu-id="ea670-130">Yes*</span></span>         |
|<span data-ttu-id="ea670-131">**Agregar miembros**</span><span class="sxs-lookup"><span data-stu-id="ea670-131">**Add members**</span></span>      |<span data-ttu-id="ea670-132">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-132">Yes**</span></span>         |<span data-ttu-id="ea670-133">No</span><span class="sxs-lookup"><span data-stu-id="ea670-133">No</span></span>         |
|<span data-ttu-id="ea670-134">**Agregar fichas**</span><span class="sxs-lookup"><span data-stu-id="ea670-134">**Add tabs**</span></span>      |<span data-ttu-id="ea670-135">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-135">Yes</span></span>         |<span data-ttu-id="ea670-136">Sí*</span><span class="sxs-lookup"><span data-stu-id="ea670-136">Yes*</span></span>         |
|<span data-ttu-id="ea670-137">**Agregar conectores**</span><span class="sxs-lookup"><span data-stu-id="ea670-137">**Add connectors**</span></span>      |<span data-ttu-id="ea670-138">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-138">Yes</span></span>         |<span data-ttu-id="ea670-139">Sí*</span><span class="sxs-lookup"><span data-stu-id="ea670-139">Yes*</span></span>         |
|<span data-ttu-id="ea670-140">**Agregar bots**</span><span class="sxs-lookup"><span data-stu-id="ea670-140">**Add bots**</span></span>      |<span data-ttu-id="ea670-141">Sí</span><span class="sxs-lookup"><span data-stu-id="ea670-141">Yes</span></span>         |<span data-ttu-id="ea670-142">Sí*</span><span class="sxs-lookup"><span data-stu-id="ea670-142">Yes*</span></span>         |
<span data-ttu-id="ea670-143">\* Un propietario puede desactivar estos elementos a nivel de equipo, en cuyo caso, los miembros no tendrían acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="ea670-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="ea670-p102">\*\*Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado Propietario. También es posible que un propietario disminuya su propio estado a Miembro.</span><span class="sxs-lookup"><span data-stu-id="ea670-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>

| | |
|---------|---------|
|![Icono de bombilla.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br><span data-ttu-id="ea670-147">Nota</span><span class="sxs-lookup"><span data-stu-id="ea670-147">Note</span></span>     |<span data-ttu-id="ea670-p103">Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos. Un equipo puede tener hasta 10 propietarios.</span><span class="sxs-lookup"><span data-stu-id="ea670-p103">Owners can make other members owners in the View teams option. A team can have up to 10 owners.</span></span>         |

<a name="permissions-to-create-teams"></a><span data-ttu-id="ea670-150">Permisos para crear equipos</span><span class="sxs-lookup"><span data-stu-id="ea670-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="ea670-p104">De manera predeterminada, todos los usuarios que tengan una casilla de correo en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, para crear equipos dentro de Microsoft Teams. Puede ejercer un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de grupos de Office 365 si delega la creación de grupos y los derechos de administración en un conjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ea670-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="ea670-153">Si su organización está interesada en hacer esto, puede encontrar instrucciones sobre las tareas que se deben realizar a continuación.</span><span class="sxs-lookup"><span data-stu-id="ea670-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="ea670-154">Identifique o cree un grupo de seguridad de usuarios que tendrán permisos delegados para crear grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea670-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="ea670-p105">a.  **Acción:** Establezca un grupo de seguridad en Office 365 para poder agregar usuarios que puedan crear grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea670-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="ea670-p106">B. Para obtener más información, consulte [Crear, editar o eliminar un grupo de seguridad en el centro de administración de Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="ea670-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="ea670-159">Compruebe que está habilitado el control de toda la empresa para que los usuarios creen grupos.</span><span class="sxs-lookup"><span data-stu-id="ea670-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="ea670-p107">a.  **Acción:** Ejecute el siguiente script de PowerShell y compruebe que el parámetro UsersPermissiontoCreateGroupsEnabled esté establecido en **True**.</span><span class="sxs-lookup"><span data-stu-id="ea670-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="ea670-162">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="ea670-162">Connect-MsolService</span></span>

    <span data-ttu-id="ea670-163">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="ea670-163">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="ea670-164">b.</span><span class="sxs-lookup"><span data-stu-id="ea670-164">b.</span></span>  <span data-ttu-id="ea670-165">Si no es verdadero, ejecute el cmdlet Set-MsolCompanySettings **para establecerlo en True**.</span><span class="sxs-lookup"><span data-stu-id="ea670-165">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="ea670-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="ea670-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="ea670-p109">c. Para obtener más información, consulte: [Administrar la creación de grupos de Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span><span class="sxs-lookup"><span data-stu-id="ea670-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="ea670-169">Establecer la configuración de grupos de Office 365 para que solo los grupos de seguridad identificados tengan permisos para crear grupos</span><span class="sxs-lookup"><span data-stu-id="ea670-169">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="ea670-p110">a.  **Acción:** Cree un objeto de configuración de grupos que contenga las opciones de configuración del grupo al que se le asignarán permisos delegados para crear grupos.</span><span class="sxs-lookup"><span data-stu-id="ea670-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="ea670-172">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="ea670-172">Connect-AzureAD</span></span>

    <span data-ttu-id="ea670-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="ea670-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="ea670-174">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="ea670-174">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="ea670-175">$setting["EnableGroupCreation"] = "false"</span><span class="sxs-lookup"><span data-stu-id="ea670-175">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="ea670-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span><span class="sxs-lookup"><span data-stu-id="ea670-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="ea670-177">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="ea670-177">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="ea670-p111">b. Para obtener más información, consulte: [Administrar la creación de grupos de Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="ea670-p111">b. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![Icono de Punto de decisión.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="ea670-181">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="ea670-181">Decision Point</span></span>         |<span data-ttu-id="ea670-182">¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="ea670-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icono de Siguientes pasos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="ea670-184">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="ea670-184">Next Steps</span></span>         |<span data-ttu-id="ea670-185">Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.</span><span class="sxs-lookup"><span data-stu-id="ea670-185">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |

---
title: Administrar directivas de Teams en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de Teams en su organización para controlar qué pueden hacer los usuarios en Teams y en los canales.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 02c7258ebc316d5e08c77698e18935eb51b5b43d
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998818"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="ed6a1-103">Administrar directivas de Teams en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed6a1-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="ed6a1-104">Como administrador, puede usar las directivas de Teams en Microsoft Teams para controlar lo que los usuarios de su organización pueden hacer en Teams y en los canales.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="ed6a1-105">Por ejemplo, puede establecer si los usuarios podrán detectar equipos privados en los resultados de búsqueda y en la galería de equipos y si los usuarios pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="ed6a1-106">Para administrar las directivas de Teams, vaya a **Teams** > **Policies** en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ed6a1-107">Puede usar la directiva global (opción predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="ed6a1-108">Los usuarios de la organización obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="ed6a1-109">Puede editar la directiva global o crear y asignar una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="ed6a1-110">Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="ed6a1-111">Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="ed6a1-112">Después de modificar la directiva global o asignar una directiva, los cambios pueden tardar hasta 24 horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="ed6a1-113">Crear una directiva de Teams personalizada</span><span class="sxs-lookup"><span data-stu-id="ed6a1-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="ed6a1-114">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a** > **directivas de Teams**Teams.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="ed6a1-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-115">Click **Add**.</span></span>
3. <span data-ttu-id="ed6a1-116">Escriba un nombre y una descripción para la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-116">Enter a name and description for the policy.</span></span>

    ![Captura de pantalla de la configuración de directiva de Teams](media/teams-policies.png)
4. <span data-ttu-id="ed6a1-118">Elija la configuración que desee:</span><span class="sxs-lookup"><span data-stu-id="ed6a1-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="ed6a1-119">**Descubrir equipos privados**:<a name="discoverteams"> </a> Active esta opción para permitir que los usuarios detecten equipos privados en los resultados de búsqueda y en la galería de equipos.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="ed6a1-120">**Crear canales privados**: <a name="createchannels"> </a>Active esta opción para permitir a los usuarios crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="ed6a1-121">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="ed6a1-122">Editar una directiva de Teams</span><span class="sxs-lookup"><span data-stu-id="ed6a1-122">Edit a teams policy</span></span>

<span data-ttu-id="ed6a1-123">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="ed6a1-124">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a** > **directivas de Teams**Teams.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="ed6a1-125">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="ed6a1-126">Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="ed6a1-127">Asignar una directiva de Teams personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="ed6a1-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="ed6a1-128">Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a uno o más usuarios o el módulo de PowerShell de Skype empresarial para asignar una directiva personalizada a grupos de usuarios, como un grupo de seguridad o un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="ed6a1-129">Asignar una directiva de Teams personalizada a un usuario</span><span class="sxs-lookup"><span data-stu-id="ed6a1-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="ed6a1-130">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="ed6a1-131">Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="ed6a1-132">En **directivas de Teams**, seleccione la Directiva que desea asignar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="ed6a1-133">Para asignar una directiva de Teams personalizada a varios usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="ed6a1-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="ed6a1-134">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed6a1-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="ed6a1-135">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a** > **directivas de Teams**Teams.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="ed6a1-136">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="ed6a1-137">Seleccione **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="ed6a1-138">En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="ed6a1-139">Repita este paso para cada usuario que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="ed6a1-140">Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="ed6a1-141">Asignar una directiva de Teams personalizada a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="ed6a1-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="ed6a1-142">Es posible que desee asignar una directiva personalizada de Teams a varios usuarios que ya haya identificado.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="ed6a1-143">Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="ed6a1-144">Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="ed6a1-145">Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed6a1-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="ed6a1-146">En este ejemplo, asignamos una directiva de Teams denominada Directiva de marketing Teams a todos los usuarios del grupo mercadotecnia de contoso.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="ed6a1-147">Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="ed6a1-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="ed6a1-148">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-148">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="ed6a1-149">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-149">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="ed6a1-150">Asignar todos los usuarios del grupo a una directiva de equipos en particular.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="ed6a1-151">En este ejemplo, se trata de una política de Teams.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-151">In this example, it's Marketing Teams Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="ed6a1-152">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed6a1-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ed6a1-153">Related topics</span></span>

- [<span data-ttu-id="ed6a1-154">Administrar la detección de equipos privados en Teams</span><span class="sxs-lookup"><span data-stu-id="ed6a1-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="ed6a1-155">Canales privados en Teams</span><span class="sxs-lookup"><span data-stu-id="ed6a1-155">Private channels in Teams</span></span>](private-channels.md)

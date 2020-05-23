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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: ce387ec406a9ccfd6ee45a67f2613a45c219f21f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349704"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="ddd3e-103">Administrar directivas de Teams en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ddd3e-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="ddd3e-104">Como administrador, puede usar las directivas de Teams en Microsoft Teams para controlar lo que los usuarios de su organización pueden hacer en Teams y en los canales.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="ddd3e-105">Por ejemplo, puede establecer si los usuarios podrán detectar equipos privados en los resultados de búsqueda y en la galería de equipos y si los usuarios pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="ddd3e-106">Para administrar las directivas de Teams, vaya a **Teams**  >  **Policies** en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ddd3e-107">Puede usar la directiva global (predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="ddd3e-108">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="ddd3e-109">Puede editar la directiva global o crear y asignar una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="ddd3e-110">Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="ddd3e-111">Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="ddd3e-112">Después de modificar la directiva global o asignar una directiva, los cambios pueden demorar algunas horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-112">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="ddd3e-113">Crear una directiva de Teams personalizada</span><span class="sxs-lookup"><span data-stu-id="ddd3e-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="ddd3e-114">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a**  >  **directivas de Teams**Teams.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="ddd3e-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-115">Click **Add**.</span></span>
3. <span data-ttu-id="ddd3e-116">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-116">Enter a name and description for the policy.</span></span>

    ![Captura de pantalla de la configuración de directiva de Teams](media/teams-policies.png)
4. <span data-ttu-id="ddd3e-118">Elija la configuración que desee:</span><span class="sxs-lookup"><span data-stu-id="ddd3e-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="ddd3e-119">**Descubrir equipos privados**:<a name="discoverteams"> </a> Active esta opción para permitir que los usuarios detecten equipos privados en los resultados de búsqueda y en la galería de equipos.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="ddd3e-120">**Crear canales privados**: <a name="createchannels"> </a>Active esta opción para permitir a los usuarios crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="ddd3e-121">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="ddd3e-122">Editar una directiva de Teams</span><span class="sxs-lookup"><span data-stu-id="ddd3e-122">Edit a teams policy</span></span>

<span data-ttu-id="ddd3e-123">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="ddd3e-124">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a**  >  **directivas de Teams**Teams.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="ddd3e-125">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="ddd3e-126">Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="ddd3e-127">Asignar una directiva de Teams personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="ddd3e-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="ddd3e-128">Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a uno o más usuarios o el módulo de PowerShell de Skype empresarial para asignar una directiva personalizada a grupos de usuarios, como un grupo de seguridad o un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="ddd3e-129">Asignar una directiva de Teams personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="ddd3e-129">Assign a custom teams policy to users</span></span>

<span data-ttu-id="ddd3e-130">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="ddd3e-130">To assign a policy to one user:</span></span>

1. <span data-ttu-id="ddd3e-131">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-131">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="ddd3e-132">Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-132">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="ddd3e-133">En **directivas de Teams**, seleccione la Directiva que desea asignar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-133">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="ddd3e-134">Para asignar una directiva a varios usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="ddd3e-134">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="ddd3e-135">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, busque los usuarios o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="ddd3e-136">En la columna **&#x2713;** (marca), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-136">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="ddd3e-137">Para seleccionar todos los usuarios, haga clic en el &#x2713; (marca de verificación) en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-137">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="ddd3e-138">Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-138">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="ddd3e-139">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ddd3e-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="ddd3e-140">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a**  >  **directivas de Teams**Teams.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-140">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="ddd3e-141">Haga clic a la izquierda del nombre de la directiva para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="ddd3e-142">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="ddd3e-143">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="ddd3e-144">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="ddd3e-145">Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-145">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="ddd3e-146">Asignar una directiva de Teams personalizada a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="ddd3e-146">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="ddd3e-147">Es posible que desee asignar una directiva personalizada de Teams a varios usuarios que ya haya identificado.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-147">You may want to assign a custom teams policy to multiple users that you've already identified.</span></span> <span data-ttu-id="ddd3e-148">Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-148">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="ddd3e-149">Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-149">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="ddd3e-150">Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ddd3e-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="ddd3e-151">En este ejemplo, asignamos una directiva de Teams denominada Directiva de marketing Teams a todos los usuarios del grupo mercadotecnia de contoso.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-151">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="ddd3e-152">Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="ddd3e-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="ddd3e-153">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-153">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="ddd3e-154">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-154">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="ddd3e-155">Asignar todos los usuarios del grupo a una directiva de equipos en particular.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-155">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="ddd3e-156">En este ejemplo, se trata de una política de Teams.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-156">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="ddd3e-157">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ddd3e-157">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ddd3e-158">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ddd3e-158">Related topics</span></span>

- [<span data-ttu-id="ddd3e-159">Administrar la detección de equipos privados en Teams</span><span class="sxs-lookup"><span data-stu-id="ddd3e-159">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="ddd3e-160">Canales privados en Teams</span><span class="sxs-lookup"><span data-stu-id="ddd3e-160">Private channels in Teams</span></span>](private-channels.md)
- [<span data-ttu-id="ddd3e-161">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="ddd3e-161">Assign policies to your users in Teams</span></span>](assign-policies.md)

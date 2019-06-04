---
title: Administrar directivas de permisos de aplicación en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga más información sobre las directivas de permisos de aplicaciones en Microsoft Teams y cómo usarlas para controlar qué aplicaciones están disponibles para los usuarios de su organización.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: fac559fb492155af9953beb74c2fac1526f01432
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681924"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="62838-103">Administrar directivas de permisos de aplicación en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="62838-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> <span data-ttu-id="62838-104">Para obtener el método de administración de aplicaciones actual en Microsoft Teams, vea [administrar la configuración de Microsoft Teams para su organización](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span><span class="sxs-lookup"><span data-stu-id="62838-104">For the current method of managing apps in Microsoft Teams, see [Manage Microsoft Teams settings for your organization](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span></span>

<span data-ttu-id="62838-105">Como administrador, puede usar las directivas de permisos de aplicaciones para controlar qué aplicaciones están disponibles para los usuarios de Microsoft Teams de su organización.</span><span class="sxs-lookup"><span data-stu-id="62838-105">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="62838-106">Puede permitir o bloquear todas las aplicaciones o aplicaciones específicas publicadas por Microsoft, terceros y su organización.</span><span class="sxs-lookup"><span data-stu-id="62838-106">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="62838-107">Cuando bloquea una aplicación, los usuarios no pueden instalarla desde la tienda de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-107">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="62838-108">Administre las directivas de permisos de aplicaciones en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="62838-109">Puede aplicar la configuración de toda la organización, usar la directiva global (predeterminada para toda la organización) y crear y asignar directivas personalizadas a usuarios individuales o a usuarios de un grupo.</span><span class="sxs-lookup"><span data-stu-id="62838-109">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![Captura de pantalla de la Directiva de permisos de aplicaciones](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="62838-111">Los usuarios de la organización obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="62838-111">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="62838-112">La configuración de la aplicación en toda la organización reemplaza la directiva global y las directivas personalizadas que cree y asigne a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="62838-112">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="62838-113">Supongamos, por ejemplo, que desea bloquear todas las aplicaciones de terceros y permitir aplicaciones específicas de Microsoft para el equipo de RRHH de su organización.</span><span class="sxs-lookup"><span data-stu-id="62838-113">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="62838-114">Crearía una directiva personalizada denominada Directiva de permisos de aplicaciones de RRHH, establecerla para que bloquee y permitir las aplicaciones que quiera y, después, asignarla a los usuarios del equipo de RRHH.</span><span class="sxs-lookup"><span data-stu-id="62838-114">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="62838-115">Administrar la configuración de la aplicación en toda la organización</span><span class="sxs-lookup"><span data-stu-id="62838-115">Manage org-wide app settings</span></span>

<span data-ttu-id="62838-116">Use la configuración de la aplicación en toda la organización para controlar qué aplicaciones están disponibles en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="62838-116">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="62838-117">La configuración de la aplicación en toda la organización rige el comportamiento de todos los usuarios y anula cualquier otra directiva de permisos de aplicación asignada a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="62838-117">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="62838-118">La configuración de la aplicación en toda la organización se aplicará inmediatamente y podrá usarlas para controlar aplicaciones malintencionadas o problemáticas.</span><span class="sxs-lookup"><span data-stu-id="62838-118">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="62838-119">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos**de la **aplicación** > Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-119">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="62838-120">Seleccione **configuración de toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="62838-120">Select **Org-wide settings**.</span></span> <span data-ttu-id="62838-121">Puede establecer la configuración que desee en el panel.</span><span class="sxs-lookup"><span data-stu-id="62838-121">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="62838-122">![Captura de pantalla de la configuración de la aplicación de toda la organización](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="62838-122">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="62838-123">En **aplicaciones de terceros**, desactive o Active esta configuración para controlar el acceso a las aplicaciones de terceros:</span><span class="sxs-lookup"><span data-stu-id="62838-123">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="62838-124">**Permitir aplicaciones de terceros en Teams**: controla si los usuarios pueden usar aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="62838-124">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="62838-125">**Permitir que todas las aplicaciones de terceros se publiquen en la tienda de forma predeterminada**: controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams se encuentran disponibles automáticamente en Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-125">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="62838-126">Solo puede establecer esta opción si permite aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="62838-126">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="62838-127">En **aplicaciones personalizadas**, desactive o desactive la **opción permitir la interacción con aplicaciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="62838-127">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="62838-128">Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas (transferidas).</span><span class="sxs-lookup"><span data-stu-id="62838-128">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="62838-129">Tenga en cuenta que esto es diferente de permitir que los \*\* usuarios carguen aplicaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="62838-129">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="62838-130">En **aplicaciones bloqueadas**, busque y agregue las aplicaciones que desea bloquear en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="62838-130">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="62838-131">Puede elegir aplicaciones del catálogo de aplicaciones de inquilino o de la tienda de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-131">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="62838-132">Haga clic en **Guardar** para que la configuración de la aplicación de toda la organización surta efecto.</span><span class="sxs-lookup"><span data-stu-id="62838-132">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="62838-133">Crear una directiva de permisos de aplicaciones personalizada</span><span class="sxs-lookup"><span data-stu-id="62838-133">Create a custom app permission policy</span></span>

<span data-ttu-id="62838-134">Si desea controlar las aplicaciones que están disponibles para los distintos grupos de usuarios de su organización, cree y asigne una o varias directivas de permisos de aplicaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="62838-134">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="62838-135">Puede crear y asignar directivas personalizadas distintas basándose en si las aplicaciones son publicadas por Microsoft, por terceros o por su organización.</span><span class="sxs-lookup"><span data-stu-id="62838-135">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="62838-136">Es importante saber que después de crear una directiva personalizada, no puede cambiarla si las aplicaciones de terceros se deshabilitan en la configuración de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="62838-136">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="62838-137">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos**de la **aplicación** > Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-137">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="62838-138">Seleccione **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="62838-138">Select **New policy**.</span></span>
    <span data-ttu-id="62838-139">![Captura de pantalla de nueva Directiva de permisos de aplicación](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="62838-139">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="62838-140">Escriba un nombre descriptivo para la Directiva.</span><span class="sxs-lookup"><span data-stu-id="62838-140">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="62838-141">En aplicaciones de **Microsoft**, **aplicaciones**de terceros y **aplicaciones de inquilino**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="62838-141">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="62838-142">**Permitir todas las aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="62838-142">**Allow all apps**</span></span>
    - <span data-ttu-id="62838-143">**Permitir aplicaciones específicas y bloquear a todos los demás**</span><span class="sxs-lookup"><span data-stu-id="62838-143">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="62838-144">**Bloquear aplicaciones específicas y permitir a todos los demás**</span><span class="sxs-lookup"><span data-stu-id="62838-144">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="62838-145">**Bloquear todas las aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="62838-145">**Block all apps**</span></span>

5. <span data-ttu-id="62838-146">Si seleccionó **permitir aplicaciones específicas y bloquear a otras personas**, agregue las aplicaciones que quiera permitir:</span><span class="sxs-lookup"><span data-stu-id="62838-146">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="62838-147">Seleccione **permitir aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="62838-147">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="62838-148">Busque las aplicaciones que desea permitir y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="62838-148">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="62838-149">Los resultados de la búsqueda se filtran para el publicador de la aplicación (aplicaciones de**Microsoft**, **aplicaciones de terceros**o **aplicaciones de inquilino**).</span><span class="sxs-lookup"><span data-stu-id="62838-149">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="62838-150">Cuando haya elegido la lista de aplicaciones, haga clic en **permitir**.</span><span class="sxs-lookup"><span data-stu-id="62838-150">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="62838-151">De forma similar, si seleccionaste **bloquear aplicaciones específicas y permitir a todos los demás**, busca y agrega las aplicaciones que deseas bloquear.</span><span class="sxs-lookup"><span data-stu-id="62838-151">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="62838-152">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="62838-152">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="62838-153">Editar una directiva de permisos de aplicación</span><span class="sxs-lookup"><span data-stu-id="62838-153">Edit an app permission policy</span></span>

<span data-ttu-id="62838-154">Puede usar el centro de administración de Microsoft Teams para editar una directiva, incluyendo la directiva global (opción predeterminada de toda la organización) y las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="62838-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="62838-155">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos**de la **aplicación** > Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-155">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="62838-156">Seleccione la Directiva que desea editar.</span><span class="sxs-lookup"><span data-stu-id="62838-156">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="62838-157">Desde aquí, realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="62838-157">From here, make the changes that you want.</span></span> <span data-ttu-id="62838-158">Puede administrar la configuración basándose en el editor de la aplicación y agregar y quitar aplicaciones en función de la configuración permitir o bloquear.</span><span class="sxs-lookup"><span data-stu-id="62838-158">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="62838-159">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="62838-159">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="62838-160">Asignar una directiva de permisos de aplicación personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="62838-160">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="62838-161">Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a usuarios individuales o el módulo de PowerShell de Skype empresarial para asignar una directiva personalizada a varios usuarios, como todos los usuarios de un grupo de seguridad o de un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="62838-161">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62838-162">Le recomendamos usar PowerShell solo para asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="62838-162">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="62838-163">Use el centro de administración de Microsoft Teams para crear, editar y administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="62838-163">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="62838-164">Asignar una directiva de permisos de aplicación personalizada a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="62838-164">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="62838-165">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="62838-165">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="62838-166">Junto a **directivas asignadas**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="62838-166">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="62838-167">En **Directiva de permisos de aplicaciones**, seleccione la Directiva de permisos de aplicación que desea asignar y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="62838-167">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![App-Setup-Permission-Assign-Policy. png](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="62838-169">También puede asignar una directiva de permisos de aplicaciones a uno o más usuarios de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="62838-169">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="62838-170">Vaya al **Centro** > de administración de Microsoft Teams**directivas de permisos**de**aplicaciones** > de Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-170">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="62838-171">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="62838-171">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="62838-172">Seleccione **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="62838-172">Select **Manage users**.</span></span>
4. <span data-ttu-id="62838-173">En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="62838-173">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="62838-174">Repita este paso para cada usuario que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="62838-174">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="62838-175">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="62838-175">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="62838-176">Asignar una directiva de permisos de aplicación personalizada a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="62838-176">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="62838-177">Es posible que desee asignar una directiva de permisos de aplicación personalizada a varios usuarios que ya haya identificado.</span><span class="sxs-lookup"><span data-stu-id="62838-177">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="62838-178">Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="62838-178">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="62838-179">Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="62838-179">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="62838-180">Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62838-180">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="62838-181">En este ejemplo, asignamos una directiva de permisos de aplicaciones personalizada denominada Directiva de permisos de aplicaciones de RRHH a todos los usuarios del grupo de proyectos de RRHH de Contoso Pharmaceuticals.</span><span class="sxs-lookup"><span data-stu-id="62838-181">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="62838-182">Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="62838-182">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="62838-183">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="62838-183">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="62838-184">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="62838-184">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="62838-185">Asignar todos los usuarios del grupo a una directiva de permisos de la aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="62838-185">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="62838-186">En este ejemplo, es la Directiva de permisos de la aplicación de RRHH.</span><span class="sxs-lookup"><span data-stu-id="62838-186">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="62838-187">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="62838-187">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="62838-188">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="62838-188">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="62838-189">Trabajar con directivas de permisos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="62838-189">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="62838-190">¿Puedo controlar las aplicaciones de línea de negocio (LOB)?</span><span class="sxs-lookup"><span data-stu-id="62838-190">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="62838-191">Sí, puede usar las directivas de permisos de aplicaciones para controlar el despliegue y la distribución de aplicaciones personalizadas (LOB).</span><span class="sxs-lookup"><span data-stu-id="62838-191">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="62838-192">¿Cómo se relacionan las directivas de permisos de aplicaciones con las aplicaciones fijas y las directivas de configuración de aplicaciones?</span><span class="sxs-lookup"><span data-stu-id="62838-192">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="62838-193">Puede usar las directivas de configuración de la aplicación junto con directivas de permisos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="62838-193">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="62838-194">Las aplicaciones previamente ancladas se seleccionan en el conjunto de aplicaciones habilitadas para un usuario.</span><span class="sxs-lookup"><span data-stu-id="62838-194">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="62838-195">Además, si un usuario tiene una directiva de permisos de la aplicación que bloquea una aplicación en la Directiva de configuración de la aplicación, esa aplicación no aparecerá en Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-195">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="62838-196">¿Puedo usar directivas de permisos de aplicaciones para restringir la carga de aplicaciones personalizadas (también conocidas como de prueba de prueba)?</span><span class="sxs-lookup"><span data-stu-id="62838-196">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="62838-197">Para obtener más información sobre cómo restringir la carga de aplicaciones personalizadas, consulte [administrar las directivas y la configuración de la aplicación personalizada en Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="62838-197">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="62838-198">¿Cuánto tiempo se tarda en aplicar los cambios de Directiva?</span><span class="sxs-lookup"><span data-stu-id="62838-198">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="62838-199">Después de modificar la directiva global o de asignar una directiva a los usuarios, los cambios pueden tardar hasta 24 horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="62838-199">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="62838-200">La configuración de la aplicación en toda la organización surte efecto de inmediato.</span><span class="sxs-lookup"><span data-stu-id="62838-200">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="62838-201">¿El bloqueo de una aplicación se aplica a los clientes móviles de Teams?</span><span class="sxs-lookup"><span data-stu-id="62838-201">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="62838-202">Sí, cuando bloquea una aplicación, dicha aplicación se bloquea en todos los clientes de Teams.</span><span class="sxs-lookup"><span data-stu-id="62838-202">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="62838-203">Experiencia de usuario</span><span class="sxs-lookup"><span data-stu-id="62838-203">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="62838-204">¿Qué es una experiencia de usuario cuando se bloquea una aplicación?</span><span class="sxs-lookup"><span data-stu-id="62838-204">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="62838-205">Los usuarios no pueden interactuar con una aplicación bloqueada ni con sus funciones, como bots, pestañas y extensiones de mensajería.</span><span class="sxs-lookup"><span data-stu-id="62838-205">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="62838-206">En un contexto compartido, como un chat de grupo o de equipo, los bots pueden enviar mensajes a todos los participantes de ese contexto.</span><span class="sxs-lookup"><span data-stu-id="62838-206">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="62838-207">Teams indica al usuario Cuándo se bloquea una aplicación.</span><span class="sxs-lookup"><span data-stu-id="62838-207">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="62838-208">Por ejemplo, cuando una aplicación está bloqueada, los usuarios no pueden realizar ninguna de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="62838-208">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="62838-209">Agregar la aplicación personalmente o a un chat o un equipo</span><span class="sxs-lookup"><span data-stu-id="62838-209">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="62838-210">Enviar mensajes al bot de la aplicación</span><span class="sxs-lookup"><span data-stu-id="62838-210">Send messages to the app’s bot</span></span>
- <span data-ttu-id="62838-211">Realizar acciones de botón que envían información a la aplicación, como mensajes accionables</span><span class="sxs-lookup"><span data-stu-id="62838-211">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="62838-212">Ver la pestaña de la aplicación</span><span class="sxs-lookup"><span data-stu-id="62838-212">View the app’s tab</span></span>
- <span data-ttu-id="62838-213">Configurar conectores para recibir notificaciones</span><span class="sxs-lookup"><span data-stu-id="62838-213">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="62838-214">Usar la extensión de mensajería de la aplicación</span><span class="sxs-lookup"><span data-stu-id="62838-214">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="62838-215">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="62838-215">Related topics</span></span>
- [<span data-ttu-id="62838-216">Configurar la administración para aplicaciones en Teams</span><span class="sxs-lookup"><span data-stu-id="62838-216">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="62838-217">Administrar directivas de configuración de aplicación en Teams</span><span class="sxs-lookup"><span data-stu-id="62838-217">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="62838-218">Administrar configuración y directivas de aplicación personalizadas en Teams</span><span class="sxs-lookup"><span data-stu-id="62838-218">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)

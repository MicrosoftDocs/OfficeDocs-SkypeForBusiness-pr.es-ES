---
title: Administrar directivas de configuración de aplicación en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
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
description: Obtenga información sobre cómo usar y administrar las directivas de configuración de aplicaciones en Microsoft Teams para los usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145927"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="abf8f-103">Administrar directivas de configuración de aplicación en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="abf8f-104">Como administrador, puede usar las directivas de configuración de la aplicación para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="abf8f-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="abf8f-105">Personalice Teams para destacar las aplicaciones más importantes para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="abf8f-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="abf8f-106">Elija las aplicaciones que desea anclar y establezca el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="abf8f-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="abf8f-107">Anclar aplicaciones le permite presentar las aplicaciones que los usuarios de su organización necesitan, incluidas las aplicaciones creadas por terceros o por desarrolladores de su organización.</span><span class="sxs-lookup"><span data-stu-id="abf8f-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="abf8f-108">Controle si los usuarios pueden anclar aplicaciones a Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="abf8f-109">Instale aplicaciones en nombre de los usuarios **(en versión preliminar).**</span><span class="sxs-lookup"><span data-stu-id="abf8f-109">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="abf8f-110">Al iniciar Teams, puede elegir qué aplicaciones se instalan de forma predeterminada para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="abf8f-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="abf8f-111">Tenga en cuenta que los usuarios pueden instalar aplicaciones por su cuenta si la [directiva](teams-app-permission-policies.md) de permisos de aplicación asignada a ellos lo permite.</span><span class="sxs-lookup"><span data-stu-id="abf8f-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="abf8f-112">Las aplicaciones se anclan a la barra de aplicaciones, que se encuentra en la parte lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams (iOS y Android).</span><span class="sxs-lookup"><span data-stu-id="abf8f-112">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="abf8f-113">Cliente de escritorio de Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-113">Teams desktop client</span></span>  |<span data-ttu-id="abf8f-114">Cliente móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-114">Teams mobile client</span></span> |
|---------|---------|
|![El cliente de escritorio de Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![El cliente móvil de Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="abf8f-117">Para ver las aplicaciones preinstaladas, en la barra de aplicaciones, los usuarios **seleccionan... Más aplicaciones en** los clientes web y de escritorio de Teams, y deslice el dedo hacia arriba en los clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="abf8f-117">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="abf8f-118">Administre las directivas de configuración de aplicaciones en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-118">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="abf8f-119">Use la directiva global (predeterminada para toda la organización) o cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="abf8f-119">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="abf8f-120">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="abf8f-120">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="abf8f-121">Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.</span><span class="sxs-lookup"><span data-stu-id="abf8f-121">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="abf8f-122">Edite la configuración de la directiva global para incluir las aplicaciones que desee.</span><span class="sxs-lookup"><span data-stu-id="abf8f-122">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="abf8f-123">Para personalizar Teams para distintos grupos de usuarios de su organización, cree y asigne una o más directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="abf8f-123">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![la página Directivas de configuración de aplicaciones](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="abf8f-125">Si tiene Teams para el ámbito educativo, es importante saber que la aplicación Tareas está anclada de forma predeterminada en la directiva global aunque actualmente no la vea en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="abf8f-125">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="abf8f-126">Será la cuarta aplicación de la lista de aplicaciones ancladas en los clientes de Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-126">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="abf8f-127">Crear una directiva de configuración de aplicación personalizada</span><span class="sxs-lookup"><span data-stu-id="abf8f-127">Create a custom app setup policy</span></span>

<span data-ttu-id="abf8f-128">Puede usar el Centro de administración de Microsoft Teams para crear una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="abf8f-128">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="abf8f-129">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a directivas **de configuración de aplicaciones**  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="abf8f-130">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="abf8f-130">Select **Add**.</span></span>

   ![la página Agregar directivas de configuración de aplicaciones](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="abf8f-132">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="abf8f-132">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="abf8f-133">Active o desactive Cargar **aplicaciones personalizadas,** dependiendo de si quiere permitir que los usuarios carguen aplicaciones personalizadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-133">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="abf8f-134">No puede cambiar esta configuración si la opción Permitir aplicaciones de terceros **está** desactivada en la configuración de aplicaciones para toda [la organización.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="abf8f-134">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="abf8f-135">Active o desactive Permitir **anclar** usuarios, dependiendo de si quiere permitir que los usuarios personalicen su barra de aplicaciones anclar aplicaciones a ella.</span><span class="sxs-lookup"><span data-stu-id="abf8f-135">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="abf8f-136">La  configuración Permitir anclación de usuarios está disponible en el Centro de administración de Teams en entornos de Microsoft 365 Government Community Cloud (GCC), pero actualmente no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="abf8f-136">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="abf8f-137">Para instalar aplicaciones para usuarios **(en versión preliminar),** realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="abf8f-137">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="abf8f-138">En **Aplicaciones instaladas,** seleccione **Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-138">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="abf8f-139">En el **panel Agregar aplicaciones instaladas,** busque las aplicaciones que quiere instalar automáticamente para los usuarios al iniciar Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-139">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="abf8f-140">También puede filtrar aplicaciones por directiva de permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="abf8f-140">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="abf8f-141">Cuando haya elegido la lista de aplicaciones, seleccione **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-141">When you've chosen your list of apps, select **Add**.</span></span>

       ![el panel Agregar aplicaciones instaladas](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="abf8f-143">Para anclar aplicaciones, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abf8f-143">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="abf8f-144">En **Aplicaciones ancladas,** seleccione **Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-144">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="abf8f-145">En el **panel Agregar aplicaciones ancladas,** busque las aplicaciones que desea agregar y, a continuación, **seleccione Agregar.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-145">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="abf8f-146">También puede filtrar aplicaciones por directiva de permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="abf8f-146">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="abf8f-147">Cuando haya elegido la lista de aplicaciones que desea anclar, seleccione **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-147">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![el panel Agregar aplicaciones ancladas](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="abf8f-149">Organice las aplicaciones en el orden en que desea que aparezcan en Teams y, a continuación, seleccione **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-149">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![la sección de aplicaciones ancladas](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="abf8f-151">Editar una directiva de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="abf8f-151">Edit an app setup policy</span></span>

<span data-ttu-id="abf8f-152">Puede usar el Centro de administración de Microsoft Teams para editar una directiva, incluidas las directivas globales (predeterminadas para toda la organización) y las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="abf8f-152">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="abf8f-153">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a directivas **de configuración de aplicaciones**  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="abf8f-154">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="abf8f-154">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="abf8f-155">A partir de aquí, realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="abf8f-155">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="abf8f-156">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="abf8f-156">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="abf8f-157">Asignar una directiva de configuración de aplicación personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="abf8f-157">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="abf8f-158">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="abf8f-158">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="abf8f-159">Trabajar con directivas de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="abf8f-159">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="abf8f-160">Las directivas de configuración integradas de aplicaciones se incluyen en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-160">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="abf8f-161">**Global (predeterminado para toda** la organización): esta directiva predeterminada se aplica a todos los usuarios de su organización, a menos que asigne otra directiva.</span><span class="sxs-lookup"><span data-stu-id="abf8f-161">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="abf8f-162">Edite la directiva global para anclar aplicaciones que sean más importantes para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="abf8f-162">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="abf8f-163">**FrontlineWorker:** esta directiva es para Los Trabajadores de frontline workers.</span><span class="sxs-lookup"><span data-stu-id="abf8f-163">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="abf8f-164">Puede asignarlo a los Trabajadores de primera línea de su organización.</span><span class="sxs-lookup"><span data-stu-id="abf8f-164">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="abf8f-165">Es importante saber que, al igual que las directivas personalizadas que crea, tiene que asignar la directiva a los usuarios para que la configuración esté activa.</span><span class="sxs-lookup"><span data-stu-id="abf8f-165">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="abf8f-166">Para obtener más información, vaya a la sección Asignar una directiva de configuración [de aplicación personalizada a](#assign-a-custom-app-setup-policy-to-users) los usuarios de este artículo.</span><span class="sxs-lookup"><span data-stu-id="abf8f-166">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="abf8f-167">¿Por qué no puedo encontrar una aplicación en el panel Agregar aplicaciones ancladas?</span><span class="sxs-lookup"><span data-stu-id="abf8f-167">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="abf8f-168">No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="abf8f-168">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="abf8f-169">Es posible que algunas aplicaciones no admitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="abf8f-169">Some apps may not support this functionality.</span></span> <span data-ttu-id="abf8f-170">Para buscar aplicaciones que se pueden anclar, busque la aplicación en el panel Agregar aplicaciones **ancladas.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-170">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="abf8f-171">Las fichas que tienen un ámbito personal (pestañas estáticas) y los bots se pueden anclar al cliente de escritorio de Teams y estas aplicaciones están disponibles en el panel Agregar aplicaciones **ancladas.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-171">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="abf8f-172">Tenga en cuenta que la tienda de aplicaciones de Teams enumera todas las aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-172">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="abf8f-173">El **panel Agregar aplicaciones ancladas** incluye solo las aplicaciones que se pueden anclar a Teams a través de una directiva.</span><span class="sxs-lookup"><span data-stu-id="abf8f-173">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="abf8f-174">Soy el administrador de Teams para el sector educativo. ¿Qué necesito saber sobre las directivas de configuración de aplicaciones en Teams para el sector educativo?</span><span class="sxs-lookup"><span data-stu-id="abf8f-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="abf8f-175">La aplicación Llamadas no está disponible en Teams para el sector educativo.</span><span class="sxs-lookup"><span data-stu-id="abf8f-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="abf8f-176">Al crear una nueva directiva de configuración de aplicaciones personalizada, la aplicación Llamadas se muestra en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="abf8f-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="abf8f-177">Sin embargo, la aplicación no está anclada a los clientes de Teams y los usuarios de Teams para el sector educativo no verán la aplicación Llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="abf8f-178">Cuántas aplicaciones ancladas se pueden agregar a una directiva</span><span class="sxs-lookup"><span data-stu-id="abf8f-178">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="abf8f-179">Como mínimo, deben anclarse dos aplicaciones a los clientes móviles de Teams (iOS y Android).</span><span class="sxs-lookup"><span data-stu-id="abf8f-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="abf8f-180">Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de directiva y, en su lugar, seguirán usando la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="abf8f-180">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="abf8f-181">No hay límite en el número de aplicaciones ancladas que puede agregar a una directiva.</span><span class="sxs-lookup"><span data-stu-id="abf8f-181">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="abf8f-182">¿Cuánto tiempo se requiere para que los cambios de directivas sumen efecto?</span><span class="sxs-lookup"><span data-stu-id="abf8f-182">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="abf8f-183">Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="abf8f-183">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="abf8f-184">Experiencia de usuario</span><span class="sxs-lookup"><span data-stu-id="abf8f-184">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="abf8f-185">¿Cómo pueden ver los usuarios todas sus aplicaciones ancladas en Teams?</span><span class="sxs-lookup"><span data-stu-id="abf8f-185">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="abf8f-186">Para ver todas las aplicaciones que están ancladas para un usuario, es posible que los usuarios tengan que hacer lo siguiente según el número de aplicaciones instaladas y el tamaño de la ventana del cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-186">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="abf8f-187">Cliente de escritorio de Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-187">Teams desktop client</span></span> |<span data-ttu-id="abf8f-188">Cliente móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-188">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="abf8f-189">En la barra de aplicaciones del lateral de Teams, **seleccione... Más aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="abf8f-189">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="abf8f-190">En la barra de aplicaciones cerca de la parte inferior de Teams, deslice el dedo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="abf8f-190">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Más aplicaciones en el cliente de escritorio de Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![más aplicaciones en el cliente móvil de Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="abf8f-193">Qué necesito saber sobre la experiencia móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-193">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="abf8f-194">Los clientes móviles de Teams (iOS y Android) actualmente no admiten aplicaciones personales con pestañas estáticas.</span><span class="sxs-lookup"><span data-stu-id="abf8f-194">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="abf8f-195">Según las aplicaciones establecidas en la directiva, es posible que las aplicaciones ancladas al cliente de escritorio de Teams no aparezcan en los clientes móviles de Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-195">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="abf8f-196">Los bots personales seguirán apareciendo en el chat en clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="abf8f-196">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="abf8f-197">Con los clientes móviles de Teams, los usuarios verán las aplicaciones principales de Teams, como Actividad, Chat y Teams, y puede anclar algunas aplicaciones de terceros de Microsoft, como Turnos.</span><span class="sxs-lookup"><span data-stu-id="abf8f-197">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="abf8f-198">¿Los usuarios pueden cambiar el orden de las aplicaciones ancladas a través de una directiva?</span><span class="sxs-lookup"><span data-stu-id="abf8f-198">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="abf8f-199">Los usuarios pueden cambiar el orden de sus aplicaciones ancladas en clientes móviles y de escritorio de Teams si la opción Permitir anclamiento de usuarios está activada. </span><span class="sxs-lookup"><span data-stu-id="abf8f-199">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="abf8f-200">Los usuarios no pueden cambiar el orden de sus aplicaciones ancladas en los clientes web de Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-200">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="abf8f-201">¿Tiene prioridad la anclación de usuario?</span><span class="sxs-lookup"><span data-stu-id="abf8f-201">Does user pinning take precedence</span></span>

<span data-ttu-id="abf8f-202">Si la directiva de configuración de la aplicación asignada al usuario cambia para bloquear la anclación de aplicaciones de usuario, Teams quita todas las aplicaciones ancladas a la barra de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="abf8f-202">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="abf8f-203">Si la directiva se cambia para permitir la anclación de aplicaciones de usuario, los usuarios deben volver a anclar sus aplicaciones ancladas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="abf8f-203">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="abf8f-204">Aplicaciones personalizadas de Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-204">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="abf8f-205">Mi organización creó una aplicación personalizada de Teams y la publicó, ya sea en AppSource o en el catálogo de aplicaciones del espacio empresarial, pero el icono de la aplicación no se muestra de la forma esperada cuando la aplicación se ancla a la barra de la aplicación en Teams.</span><span class="sxs-lookup"><span data-stu-id="abf8f-205">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="abf8f-206">¿Cómo puedo solucionarlo?</span><span class="sxs-lookup"><span data-stu-id="abf8f-206">How do I fix it</span></span>

<span data-ttu-id="abf8f-207">Asegúrese de seguir las directrices del logotipo antes de enviar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="abf8f-207">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="abf8f-208">Para obtener más información, vea [Envío de panel de lista de comprobación de vendedores.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="abf8f-208">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="abf8f-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="abf8f-209">Related topics</span></span>

[<span data-ttu-id="abf8f-210">Configurar la administración para aplicaciones en Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-210">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="abf8f-211">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="abf8f-211">Assign policies to your users in Teams</span></span>](assign-policies.md)

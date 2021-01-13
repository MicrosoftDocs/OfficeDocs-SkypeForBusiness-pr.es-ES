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
ms.openlocfilehash: 7d5a2c70eae9227b550e1e435634a6a8773be39c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821120"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="da050-103">Administrar directivas de configuración de aplicación en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da050-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="da050-104">Si habilitó la configuración de la aplicación para toda la **organización,** Permitir la interacción con aplicaciones personalizadas, es posible que todavía no vea las directivas de configuración de aplicaciones en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="da050-105">Se está ejecutando actualmente y estará disponible próximamente en su organización.</span><span class="sxs-lookup"><span data-stu-id="da050-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="da050-106">Como administrador, puede usar las directivas de configuración de la aplicación para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="da050-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="da050-107">Personalice Teams para destacar las aplicaciones más importantes para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="da050-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="da050-108">Elija las aplicaciones que desea anclar y establezca el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="da050-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="da050-109">Anclar aplicaciones le permite mostrar las aplicaciones que los usuarios de su organización necesitan, incluidas las aplicaciones creadas por terceros o por desarrolladores de su organización.</span><span class="sxs-lookup"><span data-stu-id="da050-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="da050-110">Controle si los usuarios pueden anclar aplicaciones a Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="da050-111">Instale aplicaciones en nombre de los usuarios **(en versión preliminar).**</span><span class="sxs-lookup"><span data-stu-id="da050-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="da050-112">Al iniciar Teams, puede elegir qué aplicaciones se instalan de forma predeterminada para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="da050-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="da050-113">Tenga en cuenta que los usuarios pueden instalar aplicaciones por su cuenta si la [directiva](teams-app-permission-policies.md) de permisos de aplicación asignada a ellos lo permite.</span><span class="sxs-lookup"><span data-stu-id="da050-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="da050-114">Las aplicaciones se anclan a la barra de aplicaciones, que se encuentra en la parte lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams (iOS y Android).</span><span class="sxs-lookup"><span data-stu-id="da050-114">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="da050-115">Cliente de escritorio de Teams</span><span class="sxs-lookup"><span data-stu-id="da050-115">Teams desktop client</span></span>  |<span data-ttu-id="da050-116">Cliente móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="da050-116">Teams mobile client</span></span> |
|---------|---------|
|![El cliente de escritorio de Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![El cliente móvil de Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="da050-119">Para ver las aplicaciones preinstaladas, en la barra de aplicaciones, los usuarios **seleccionan... Más aplicaciones en** los clientes web y de escritorio de Teams, y deslice el dedo hacia arriba en los clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="da050-119">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="da050-120">Administre las directivas de configuración de aplicaciones en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-120">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="da050-121">Use la directiva global (predeterminada para toda la organización) o cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="da050-121">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="da050-122">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="da050-122">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="da050-123">Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.</span><span class="sxs-lookup"><span data-stu-id="da050-123">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="da050-124">Edite la configuración de la directiva global para incluir las aplicaciones que desee.</span><span class="sxs-lookup"><span data-stu-id="da050-124">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="da050-125">Para personalizar Teams para distintos grupos de usuarios de su organización, cree y asigne una o más directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="da050-125">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![la página Directivas de configuración de aplicaciones](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="da050-127">Si tiene Teams para el ámbito educativo, es importante saber que la aplicación Tareas está anclada de forma predeterminada en la directiva global aunque actualmente no la vea en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="da050-127">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="da050-128">Será la cuarta aplicación de la lista de aplicaciones ancladas en los clientes de Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-128">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="da050-129">Crear una directiva de configuración de aplicación personalizada</span><span class="sxs-lookup"><span data-stu-id="da050-129">Create a custom app setup policy</span></span>

<span data-ttu-id="da050-130">Puede usar el Centro de administración de Microsoft Teams para crear una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="da050-130">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="da050-131">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a directivas **de configuración** de aplicaciones  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="da050-132">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="da050-132">Select **Add**.</span></span>

   ![la página Agregar directivas de configuración de aplicaciones](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="da050-134">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="da050-134">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="da050-135">Active o desactive Cargar **aplicaciones personalizadas,** dependiendo de si quiere permitir que los usuarios carguen aplicaciones personalizadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-135">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="da050-136">No puede cambiar esta configuración si la opción Permitir aplicaciones de terceros **está** desactivada en la configuración de la aplicación para toda [la organización.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="da050-136">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="da050-137">Active o desactive Permitir **anclar** usuarios, dependiendo de si quiere permitir que los usuarios personalicen su barra de aplicaciones anclar aplicaciones a ella.</span><span class="sxs-lookup"><span data-stu-id="da050-137">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="da050-138">La  configuración Permitir anclación de usuarios está disponible en el Centro de administración de Teams en entornos de Microsoft 365 Government Community Cloud (GCC), pero actualmente no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="da050-138">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="da050-139">Para instalar aplicaciones para usuarios **(en versión preliminar),** realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="da050-139">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="da050-140">En **Aplicaciones instaladas,** seleccione **Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="da050-140">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="da050-141">En el **panel Agregar aplicaciones instaladas,** busque las aplicaciones que quiere instalar automáticamente para los usuarios al iniciar Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="da050-142">También puede filtrar aplicaciones por directiva de permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="da050-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="da050-143">Cuando haya elegido la lista de aplicaciones, seleccione **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="da050-143">When you've chosen your list of apps, select **Add**.</span></span>

       ![el panel Agregar aplicaciones instaladas](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="da050-145">Para anclar aplicaciones, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da050-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="da050-146">En **Aplicaciones ancladas,** seleccione **Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="da050-146">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="da050-147">En el **panel Agregar aplicaciones ancladas,** busque las aplicaciones que desea agregar y, a continuación, **seleccione Agregar.**</span><span class="sxs-lookup"><span data-stu-id="da050-147">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="da050-148">También puede filtrar aplicaciones por directiva de permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="da050-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="da050-149">Cuando haya elegido la lista de aplicaciones que desea anclar, seleccione **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="da050-149">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![el panel Agregar aplicaciones ancladas](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="da050-151">Organice las aplicaciones en el orden en que desea que aparezcan en Teams y, a continuación, seleccione **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="da050-151">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![la sección de aplicaciones ancladas](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="da050-153">Editar una directiva de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="da050-153">Edit an app setup policy</span></span>

<span data-ttu-id="da050-154">Puede usar el Centro de administración de Microsoft Teams para editar una directiva, incluidas las directivas globales (predeterminadas para toda la organización) y las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="da050-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="da050-155">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a directivas **de configuración** de aplicaciones  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="da050-156">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="da050-156">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="da050-157">A partir de aquí, realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="da050-157">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="da050-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="da050-158">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="da050-159">Asignar una directiva de configuración de aplicación personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="da050-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="da050-160">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="da050-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="da050-161">Trabajar con directivas de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="da050-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="da050-162">Las directivas de configuración integradas de aplicaciones se incluyen en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da050-162">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="da050-163">**Global (predeterminado para** toda la organización): esta directiva predeterminada se aplica a todos los usuarios de su organización, a menos que asigne otra directiva.</span><span class="sxs-lookup"><span data-stu-id="da050-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="da050-164">Edite la directiva global para anclar aplicaciones que sean más importantes para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="da050-164">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="da050-165">**FirstLineWorker:** esta directiva es para Firstline Workers.</span><span class="sxs-lookup"><span data-stu-id="da050-165">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="da050-166">Puede asignarlo a los Firstline Workers de su organización.</span><span class="sxs-lookup"><span data-stu-id="da050-166">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="da050-167">Es importante saber que, al igual que las directivas personalizadas que crea, tiene que asignar la directiva a los usuarios para que la configuración esté activa.</span><span class="sxs-lookup"><span data-stu-id="da050-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="da050-168">Para obtener más información, vaya a la sección Asignar una directiva de [configuración de aplicación personalizada a](#assign-a-custom-app-setup-policy-to-users) los usuarios de este artículo.</span><span class="sxs-lookup"><span data-stu-id="da050-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="da050-169">¿Por qué no puedo encontrar una aplicación en el panel Agregar aplicaciones ancladas?</span><span class="sxs-lookup"><span data-stu-id="da050-169">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="da050-170">No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="da050-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="da050-171">Es posible que algunas aplicaciones no admitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="da050-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="da050-172">Para buscar aplicaciones que se pueden anclar, busque la aplicación en el panel Agregar **aplicaciones ancladas.**</span><span class="sxs-lookup"><span data-stu-id="da050-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="da050-173">Las fichas que tienen un ámbito personal (pestañas estáticas) y los bots se pueden anclar al cliente de escritorio de Teams y estas aplicaciones están disponibles en el panel Agregar aplicaciones **ancladas.**</span><span class="sxs-lookup"><span data-stu-id="da050-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="da050-174">Tenga en cuenta que la tienda de aplicaciones de Teams enumera todas las aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-174">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="da050-175">El **panel Agregar aplicaciones ancladas** incluye solo las aplicaciones que se pueden anclar a Teams a través de una directiva.</span><span class="sxs-lookup"><span data-stu-id="da050-175">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="da050-176">Soy el administrador de Teams para el sector educativo. Qué necesito saber sobre las directivas de configuración de aplicaciones en Teams para el sector educativo</span><span class="sxs-lookup"><span data-stu-id="da050-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="da050-177">La aplicación Llamadas no está disponible en Teams para el sector educativo.</span><span class="sxs-lookup"><span data-stu-id="da050-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="da050-178">Al crear una nueva directiva de configuración de aplicaciones personalizada, la aplicación Llamadas se muestra en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="da050-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="da050-179">Sin embargo, la aplicación no está anclada a los clientes de Teams y los usuarios de Teams para el sector educativo no verán la aplicación Llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="da050-180">Cuántas aplicaciones ancladas se pueden agregar a una directiva</span><span class="sxs-lookup"><span data-stu-id="da050-180">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="da050-181">Como mínimo, deben anclarse dos aplicaciones a los clientes móviles de Teams (iOS y Android).</span><span class="sxs-lookup"><span data-stu-id="da050-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="da050-182">Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de directiva y, en su lugar, seguirán usando la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="da050-182">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="da050-183">No hay límite en el número de aplicaciones ancladas que puede agregar a una directiva.</span><span class="sxs-lookup"><span data-stu-id="da050-183">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="da050-184">¿Cuánto tiempo se requiere para que los cambios de directivas sumen efecto?</span><span class="sxs-lookup"><span data-stu-id="da050-184">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="da050-185">Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="da050-185">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="da050-186">Experiencia de usuario</span><span class="sxs-lookup"><span data-stu-id="da050-186">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="da050-187">¿Cómo pueden los usuarios ver todas sus aplicaciones ancladas en Teams?</span><span class="sxs-lookup"><span data-stu-id="da050-187">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="da050-188">Para ver todas las aplicaciones que están ancladas para un usuario, es posible que los usuarios tengan que hacer lo siguiente según el número de aplicaciones instaladas y el tamaño de la ventana del cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-188">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="da050-189">Cliente de escritorio de Teams</span><span class="sxs-lookup"><span data-stu-id="da050-189">Teams desktop client</span></span> |<span data-ttu-id="da050-190">Cliente móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="da050-190">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="da050-191">En la barra de aplicaciones del lateral de Teams, **seleccione... Más aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="da050-191">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="da050-192">En la barra de aplicaciones cerca de la parte inferior de Teams, deslice el dedo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="da050-192">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Más aplicaciones en el cliente de escritorio de Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![más aplicaciones en el cliente móvil de Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="da050-195">¿Qué necesito saber sobre la experiencia móvil de Teams?</span><span class="sxs-lookup"><span data-stu-id="da050-195">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="da050-196">Los clientes móviles de Teams (iOS y Android) no admiten actualmente aplicaciones personales con pestañas estáticas.</span><span class="sxs-lookup"><span data-stu-id="da050-196">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="da050-197">Según las aplicaciones establecidas en la directiva, es posible que las aplicaciones ancladas al cliente de escritorio de Teams no aparezcan en los clientes móviles de Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-197">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="da050-198">Los bots personales seguirán apareciendo en el chat en clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="da050-198">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="da050-199">Con los clientes móviles de Teams, los usuarios verán las aplicaciones principales de Teams, como Actividad, Chat y Teams, y puede anclar algunas aplicaciones de terceros de Microsoft, como Turnos.</span><span class="sxs-lookup"><span data-stu-id="da050-199">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="da050-200">¿Los usuarios pueden cambiar el orden de las aplicaciones ancladas a través de una directiva?</span><span class="sxs-lookup"><span data-stu-id="da050-200">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="da050-201">Los usuarios pueden cambiar el orden de sus aplicaciones ancladas en clientes móviles y de escritorio de Teams si la opción Permitir anclamiento de usuarios está activada. </span><span class="sxs-lookup"><span data-stu-id="da050-201">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="da050-202">Los usuarios no pueden cambiar el orden de sus aplicaciones ancladas en los clientes web de Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-202">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="da050-203">¿Tiene prioridad la anclación de usuario?</span><span class="sxs-lookup"><span data-stu-id="da050-203">Does user pinning take precedence</span></span>

<span data-ttu-id="da050-204">Si la directiva de configuración de la aplicación asignada al usuario cambia para bloquear la anclación de aplicaciones de usuario, Teams quita todas las aplicaciones ancladas a la barra de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="da050-204">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="da050-205">Si la directiva se cambia para permitir la anclación de aplicaciones de usuario, los usuarios deben volver a anclar sus aplicaciones ancladas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="da050-205">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="da050-206">Aplicaciones personalizadas de Teams</span><span class="sxs-lookup"><span data-stu-id="da050-206">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="da050-207">Mi organización creó una aplicación personalizada de Teams y la publicó, ya sea en AppSource o en el catálogo de aplicaciones del espacio empresarial, pero el icono de la aplicación no aparece como se esperaba cuando la aplicación se ancla a la barra de la aplicación en Teams.</span><span class="sxs-lookup"><span data-stu-id="da050-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="da050-208">¿Cómo puedo solucionarlo?</span><span class="sxs-lookup"><span data-stu-id="da050-208">How do I fix it</span></span>

<span data-ttu-id="da050-209">Asegúrese de seguir las directrices del logotipo antes de enviar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da050-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="da050-210">Para obtener más información, vea [Envío de panel de lista de comprobación de vendedores.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="da050-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="da050-211">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="da050-211">Related topics</span></span>

[<span data-ttu-id="da050-212">Configurar la administración para aplicaciones en Teams</span><span class="sxs-lookup"><span data-stu-id="da050-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="da050-213">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="da050-213">Assign policies to your users in Teams</span></span>](assign-policies.md)

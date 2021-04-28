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
description: Obtenga información sobre cómo usar y administrar directivas de configuración de aplicaciones en Microsoft Teams para los usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059204"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="749a9-103">Administrar directivas de configuración de aplicación en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="749a9-104">Como administrador, puede usar directivas de configuración de aplicaciones para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="749a9-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="749a9-105">Personalice Teams para destacar las aplicaciones más importantes para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="749a9-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="749a9-106">Elige las aplicaciones para anclar y establecer el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="749a9-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="749a9-107">Las aplicaciones ancladas le permiten mostrar las aplicaciones que necesitan los usuarios de su organización, incluidas las aplicaciones creadas por terceros o por desarrolladores de su organización.</span><span class="sxs-lookup"><span data-stu-id="749a9-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="749a9-108">Controle si los usuarios pueden anclar aplicaciones a Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="749a9-109">Instale aplicaciones en nombre de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="749a9-109">Install apps on behalf of users.</span></span> <span data-ttu-id="749a9-110">Al iniciar Teams, puede elegir qué aplicaciones están instaladas de forma predeterminada para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="749a9-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="749a9-111">Tenga en cuenta que los usuarios [](teams-app-permission-policies.md) aún pueden instalar aplicaciones si la directiva de permisos de la aplicación que se les ha asignado lo permite.</span><span class="sxs-lookup"><span data-stu-id="749a9-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="749a9-112">Para las aplicaciones instaladas por los administradores, los usuarios no pueden desinstalar esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="749a9-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="749a9-113">Las aplicaciones se anclan a la barra de aplicaciones, que es la barra del lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams (iOS y Android).</span><span class="sxs-lookup"><span data-stu-id="749a9-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="749a9-114">Cliente de escritorio de Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-114">Teams desktop client</span></span>  |<span data-ttu-id="749a9-115">Cliente móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-115">Teams mobile client</span></span> |
|---------|---------|
|![El cliente de escritorio de Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![El cliente móvil de Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="749a9-118">Para ver las aplicaciones instaladas por los administradores, en la barra de aplicaciones, los usuarios seleccionan **... Más aplicaciones en** los clientes web y de escritorio de Teams y deslice el dedo hacia arriba en los clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="749a9-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="749a9-119">Puede administrar directivas de configuración de aplicaciones en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="749a9-120">Use la directiva global (predeterminada para toda la organización) o cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="749a9-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="749a9-121">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="749a9-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="749a9-122">Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.</span><span class="sxs-lookup"><span data-stu-id="749a9-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="749a9-123">Edita la configuración de la directiva global para incluir las aplicaciones que desee.</span><span class="sxs-lookup"><span data-stu-id="749a9-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="749a9-124">Para personalizar Teams para diferentes grupos de usuarios de su organización, cree y asigne una o más directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="749a9-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![la página Directivas de configuración de aplicaciones](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="749a9-126">Si tiene Teams para el ámbito educativo, es importante saber que la aplicación Asignaciones está anclada de forma predeterminada en la directiva global aunque actualmente no la vea en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="749a9-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="749a9-127">Será la cuarta aplicación de la lista de aplicaciones ancladas en clientes de Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="749a9-128">Crear una directiva de configuración de aplicaciones personalizada</span><span class="sxs-lookup"><span data-stu-id="749a9-128">Create a custom app setup policy</span></span>

<span data-ttu-id="749a9-129">Puede usar el Centro de administración de Microsoft Teams para crear una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="749a9-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="749a9-130">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de configuración **de aplicaciones**  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="749a9-131">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="749a9-131">Select **Add**.</span></span>

   ![página Agregar directivas de configuración de aplicaciones](media/app-setup-policies-add.png)

3. <span data-ttu-id="749a9-133">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="749a9-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="749a9-134">Activa o desactiva **Cargar** aplicaciones personalizadas, dependiendo de si quieres permitir que los usuarios carguen aplicaciones personalizadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="749a9-135">No puede cambiar esta configuración si Permitir aplicaciones **de terceros** está desactivada en la configuración de la aplicación para toda [la organización.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="749a9-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="749a9-136">Activa o desactiva **Permitir** anclación de usuario, dependiendo de si quieres permitir que los usuarios personalicen su barra de aplicaciones anclando aplicaciones a ella.</span><span class="sxs-lookup"><span data-stu-id="749a9-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="749a9-137">La **configuración** Permitir anclación de usuario está disponible en el Centro de administración de Teams en entornos de Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High y DoD), pero actualmente no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="749a9-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="749a9-138">Para instalar aplicaciones para los usuarios, realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="749a9-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="749a9-139">En **Aplicaciones instaladas,** seleccione **Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="749a9-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="749a9-140">En el **panel Agregar aplicaciones instaladas,** busque las aplicaciones que desea instalar automáticamente para los usuarios al iniciar Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="749a9-141">También puede filtrar aplicaciones por directiva de permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="749a9-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="749a9-142">Cuando haya elegido la lista de aplicaciones, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="749a9-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![el panel Agregar aplicaciones instaladas](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="749a9-144">Para anclar aplicaciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="749a9-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="749a9-145">En **Aplicaciones ancladas,** selecciona **Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="749a9-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="749a9-146">En el **panel Agregar aplicaciones** ancladas, busque las aplicaciones que desea agregar y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="749a9-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="749a9-147">También puede filtrar aplicaciones por directiva de permisos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="749a9-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="749a9-148">Cuando haya elegido la lista de aplicaciones para anclar, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="749a9-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![el panel Agregar aplicaciones ancladas](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="749a9-150">Organice las aplicaciones en el orden en que quiera que aparezcan en Teams y, a continuación, seleccione **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="749a9-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![la sección Aplicaciones ancladas](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="749a9-152">Editar una directiva de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="749a9-152">Edit an app setup policy</span></span>

<span data-ttu-id="749a9-153">Puede usar el Centro de administración de Microsoft Teams para editar una directiva, incluida la directiva global (predeterminada para toda la organización) y las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="749a9-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="749a9-154">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de configuración **de aplicaciones**  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="749a9-155">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="749a9-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="749a9-156">A partir de aquí, realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="749a9-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="749a9-157">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="749a9-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="749a9-158">Asignar una directiva de configuración de aplicación personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="749a9-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="749a9-159">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="749a9-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="749a9-160">Trabajar con directivas de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="749a9-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="749a9-161">Qué directivas de configuración de aplicaciones integradas se incluyen en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="749a9-162">**Global (predeterminado para toda** la organización): esta directiva predeterminada se aplica a todos los usuarios de su organización a menos que asigne otra directiva.</span><span class="sxs-lookup"><span data-stu-id="749a9-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="749a9-163">Edite la directiva global para anclar aplicaciones que sean más importantes para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="749a9-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="749a9-164">**FrontlineWorker:** esta directiva es para trabajadores de frontline.</span><span class="sxs-lookup"><span data-stu-id="749a9-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="749a9-165">Puede asignarlo a Trabajadores de frontline de su organización.</span><span class="sxs-lookup"><span data-stu-id="749a9-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="749a9-166">Es importante saber que, al igual que las directivas personalizadas que cree, tiene que asignar la directiva a los usuarios para que la configuración esté activa.</span><span class="sxs-lookup"><span data-stu-id="749a9-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="749a9-167">Para obtener más información, vaya a la sección Asignar una directiva de configuración [de aplicación personalizada a](#assign-a-custom-app-setup-policy-to-users) los usuarios de este artículo.</span><span class="sxs-lookup"><span data-stu-id="749a9-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="749a9-168">¿Por qué no puedo encontrar una aplicación en el panel Agregar aplicaciones ancladas?</span><span class="sxs-lookup"><span data-stu-id="749a9-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="749a9-169">No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="749a9-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="749a9-170">Es posible que algunas aplicaciones no admitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="749a9-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="749a9-171">Para buscar aplicaciones que se pueden anclar, busque la aplicación en el panel Agregar aplicaciones **ancladas.**</span><span class="sxs-lookup"><span data-stu-id="749a9-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="749a9-172">Las pestañas que tienen un ámbito personal (pestañas estáticas) y bots se pueden anclar al cliente de escritorio de Teams y estas aplicaciones están disponibles en el panel Agregar aplicaciones **ancladas.**</span><span class="sxs-lookup"><span data-stu-id="749a9-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="749a9-173">Tenga en cuenta que la tienda de aplicaciones de Teams enumera todas las aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="749a9-174">El **panel Agregar aplicaciones ancladas** solo incluye las aplicaciones que se pueden anclar a Teams a través de una directiva.</span><span class="sxs-lookup"><span data-stu-id="749a9-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="749a9-175">Soy administrador de Teams for Education. ¿Qué necesito saber sobre las directivas de configuración de aplicaciones en Teams para el sector educativo?</span><span class="sxs-lookup"><span data-stu-id="749a9-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="749a9-176">La aplicación Llamadas no está disponible en Teams para el sector educativo.</span><span class="sxs-lookup"><span data-stu-id="749a9-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="749a9-177">Al crear una nueva directiva de configuración de aplicaciones personalizada, la aplicación Llamadas se muestra en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="749a9-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="749a9-178">Sin embargo, la aplicación no está anclada a clientes de Teams y los usuarios de Teams para el sector educativo no verán la aplicación Llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="749a9-179">Cuántas aplicaciones ancladas se pueden agregar a una directiva</span><span class="sxs-lookup"><span data-stu-id="749a9-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="749a9-180">Un mínimo de dos aplicaciones deben estar ancladas a los clientes móviles de Teams (iOS y Android).</span><span class="sxs-lookup"><span data-stu-id="749a9-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="749a9-181">Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de directiva y, en su lugar, seguirán usando la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="749a9-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="749a9-182">No hay ningún límite en el número de aplicaciones ancladas que puede agregar a una directiva.</span><span class="sxs-lookup"><span data-stu-id="749a9-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="749a9-183">¿Cuánto tiempo se necesita para que los cambios de directiva entren en vigor?</span><span class="sxs-lookup"><span data-stu-id="749a9-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="749a9-184">Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="749a9-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="749a9-185">Experiencia de usuario</span><span class="sxs-lookup"><span data-stu-id="749a9-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="749a9-186">Cómo pueden los usuarios ver todas sus aplicaciones ancladas en Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="749a9-187">Para ver todas las aplicaciones ancladas para un usuario, es posible que los usuarios tengan que hacer lo siguiente en función del número de aplicaciones instaladas y del tamaño de la ventana del cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="749a9-188">Cliente de escritorio de Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-188">Teams desktop client</span></span> |<span data-ttu-id="749a9-189">Cliente móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="749a9-190">En la barra de aplicaciones del lado de Teams, selecciona **... Más aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="749a9-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="749a9-191">En la barra de aplicaciones cerca de la parte inferior de Teams, deslice el dedo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="749a9-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Más aplicaciones en el cliente de escritorio de Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![más aplicaciones en el cliente móvil de Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="749a9-194">¿Qué necesito saber sobre la experiencia móvil de Teams?</span><span class="sxs-lookup"><span data-stu-id="749a9-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="749a9-195">Los clientes móviles de Teams (iOS y Android) admiten aplicaciones personales con pestañas estáticas.</span><span class="sxs-lookup"><span data-stu-id="749a9-195">The Teams mobile clients (iOS and Android) support personal apps with static tabs.</span></span> <span data-ttu-id="749a9-196">Las aplicaciones ancladas al cliente de escritorio de Teams aparecerán en los clientes móviles de Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-196">Apps pinned to the Teams desktop client will appear in the Teams mobile clients.</span></span> <span data-ttu-id="749a9-197">Los bots personales aparecerán en Chat en clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="749a9-197">Personal bots will appear in Chat on mobile clients.</span></span>

<span data-ttu-id="749a9-198">Las aplicaciones de terceros (que se pueden descargar desde la Tienda Teams) deben aprobarse antes de que se muestren en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="749a9-198">Third-party apps (which can be downloaded from Teams Store) need to be approved before they show up on mobile.</span></span> <span data-ttu-id="749a9-199">Si un administrador ancla una aplicación, que no ha sido aprobada por Microsoft para Móviles, se mostrará en el escritorio de Teams, pero no se mostrará en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="749a9-199">If an admin pins an app, which is unapproved by Microsoft for Mobile, it will show up on the Teams Desktop, but not show up on mobile.</span></span> <span data-ttu-id="749a9-200">Vea [Clientes móviles](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="749a9-200">See [Mobile clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) for more information.</span></span>

<span data-ttu-id="749a9-201">Con los clientes móviles de Teams, los usuarios verán las aplicaciones principales de Teams, como Actividad, Chat y Teams, y puede anclar algunas aplicaciones de primer nivel de Microsoft, como Turnos.</span><span class="sxs-lookup"><span data-stu-id="749a9-201">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="749a9-202">¿Pueden los usuarios cambiar el orden de las aplicaciones ancladas a través de una directiva?</span><span class="sxs-lookup"><span data-stu-id="749a9-202">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="749a9-203">Los usuarios pueden cambiar el orden de sus aplicaciones ancladas en clientes móviles y de escritorio de Teams si la **opción** Permitir anclar usuarios está activada.</span><span class="sxs-lookup"><span data-stu-id="749a9-203">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="749a9-204">Los usuarios no pueden cambiar el orden de sus aplicaciones ancladas en clientes web de Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-204">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="749a9-205">¿Tiene prioridad la anclación de usuario?</span><span class="sxs-lookup"><span data-stu-id="749a9-205">Does user pinning take precedence</span></span>

<span data-ttu-id="749a9-206">Los anclares de administrador siempre tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="749a9-206">Admin pins always take precedence.</span></span> <span data-ttu-id="749a9-207">Si la **opción Permitir anclación de** usuario está activada, los usuarios conservarán sus aplicaciones ancladas debajo de las aplicaciones ancladas por el administrador.</span><span class="sxs-lookup"><span data-stu-id="749a9-207">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="749a9-208">Si la **opción** Permitir anclación de usuario está desactivada, los usuarios perderán sus pasadores preexistentes y solo las aplicaciones ancladas por el administrador estarán presentes en la barra de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="749a9-208">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="749a9-209">Aplicaciones personalizadas de Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-209">Custom Teams apps</span></span>

<span data-ttu-id="749a9-210">Mi organización creó una aplicación personalizada de Teams y la publicó, ya sea en AppSource o en el catálogo de aplicaciones de inquilino, pero el icono de la aplicación no se muestra como se esperaba cuando la aplicación está anclada a la barra de aplicaciones en Teams.</span><span class="sxs-lookup"><span data-stu-id="749a9-210">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="749a9-211">¿Cómo puedo corregirlo?</span><span class="sxs-lookup"><span data-stu-id="749a9-211">How do I fix it</span></span>

<span data-ttu-id="749a9-212">Asegúrese de que sigue las directrices del logotipo antes de enviar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="749a9-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="749a9-213">Para obtener más información, vea [Envío de lista de comprobación del panel de vendedores.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="749a9-213">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="749a9-214">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="749a9-214">Related topics</span></span>

[<span data-ttu-id="749a9-215">Configurar la administración para aplicaciones en Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-215">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="749a9-216">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="749a9-216">Assign policies to your users in Teams</span></span>](assign-policies.md)

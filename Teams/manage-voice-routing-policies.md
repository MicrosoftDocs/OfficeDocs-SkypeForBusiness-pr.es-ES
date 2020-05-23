---
title: Administrar directivas de enrutamiento de voz en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a crear y administrar directivas de enrutamiento de voz en Microsoft Teams.
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350194"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="04ff4-103">Administrar directivas de enrutamiento de voz en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04ff4-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="04ff4-104">Si ha implementado el [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md) en su organización, puede usar las directivas de enrutamiento de voz para permitir que los usuarios de Teams y Skype empresarial online reciban y realicen llamadas telefónicas a la red de telefonía pública conmutada (RTC) con su infraestructura de telefonía local.</span><span class="sxs-lookup"><span data-stu-id="04ff4-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="04ff4-105">Una directiva de enrutamiento de voz es un contenedor de registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="04ff4-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="04ff4-106">Para crear y administrar directivas de enrutamiento de voz, **vaya a**  >  **directivas de enrutamiento** de voz de voz en el centro de administración de Microsoft Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04ff4-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="04ff4-107">Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="04ff4-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="04ff4-108">Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="04ff4-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="04ff4-109">Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="04ff4-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="04ff4-110">Es importante saber que asignar una directiva de enrutamiento de voz a un usuario no les permite realizar llamadas RTC en Teams.</span><span class="sxs-lookup"><span data-stu-id="04ff4-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="04ff4-111">También tendrá que habilitar el enrutamiento directo del usuario para el sistema telefónico y completar otros pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="04ff4-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="04ff4-112">Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="04ff4-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="04ff4-113">Crear una directiva de enrutamiento de voz personalizada</span><span class="sxs-lookup"><span data-stu-id="04ff4-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="04ff4-114">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04ff4-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="04ff4-115">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de enrutamiento de voz de **voz**  >  **Voice routing policies**y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="04ff4-116">![Captura de pantalla de la página Agregar Directiva de enrutamiento de voz en el centro de administración de Microsoft Teams](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="04ff4-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="04ff4-117">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="04ff4-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="04ff4-118">En **registros de uso de RTC**, haga clic en **Agregar uso de RTC**y, a continuación, seleccione los registros que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="04ff4-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="04ff4-119">Si necesita crear un registro de uso de RTC nuevo, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="04ff4-120">Si ha agregado varios registros de uso de RTC, organícelos en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="04ff4-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="04ff4-121">Cuando haya terminado, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="04ff4-122">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="04ff4-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="04ff4-123">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="04ff4-123">Using PowerShell</span></span>

<span data-ttu-id="04ff4-124">Vea [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="04ff4-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="04ff4-125">Editar una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="04ff4-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="04ff4-126">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04ff4-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="04ff4-127">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="04ff4-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="04ff4-128">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de enrutamiento de voz**de voz.</span><span class="sxs-lookup"><span data-stu-id="04ff4-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="04ff4-129">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="04ff4-130">Haga clic en **Agregar o quitar registros de uso de RTC**, realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="04ff4-131">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="04ff4-131">Using PowerShell</span></span>

<span data-ttu-id="04ff4-132">Consulte [set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="04ff4-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="04ff4-133">Asignar una directiva de enrutamiento de voz personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="04ff4-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="04ff4-134">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04ff4-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="04ff4-135">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="04ff4-135">To assign a policy to one user:</span></span>

1. <span data-ttu-id="04ff4-136">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="04ff4-136">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="04ff4-137">Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-137">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="04ff4-138">En **Directiva de enrutamiento de voz**, seleccione la Directiva que desea asignar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-138">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="04ff4-139">Para asignar una directiva a varios usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="04ff4-139">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="04ff4-140">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, busque los usuarios o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="04ff4-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="04ff4-141">En la columna **&#x2713;** (marca), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="04ff4-141">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="04ff4-142">Para seleccionar todos los usuarios, haga clic en el &#x2713; (marca de verificación) en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="04ff4-142">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="04ff4-143">Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-143">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="04ff4-144">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04ff4-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="04ff4-145">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de enrutamiento de voz**de voz.</span><span class="sxs-lookup"><span data-stu-id="04ff4-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="04ff4-146">Haga clic a la izquierda del nombre de la directiva para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="04ff4-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="04ff4-147">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="04ff4-148">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="04ff4-149">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="04ff4-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="04ff4-150">Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="04ff4-150">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="04ff4-151">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="04ff4-151">Using PowerShell</span></span>

<span data-ttu-id="04ff4-152">Consulte [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="04ff4-152">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="04ff4-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="04ff4-153">Related topics</span></span>

- [<span data-ttu-id="04ff4-154">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="04ff4-154">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="04ff4-155">Configurar el enrutamiento de voz para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="04ff4-155">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="04ff4-156">Habilitar enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="04ff4-156">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="04ff4-157">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="04ff4-157">Assign policies to your users in Teams</span></span>](assign-policies.md)

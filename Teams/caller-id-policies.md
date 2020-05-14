---
title: Administrar directivas de identificación de llamadas en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar y administrar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas de los usuarios de su organización.
ms.openlocfilehash: a4dbdbac0922bb475f47447a3cf8b2d0f001909c
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224258"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="ed451-103">Administrar directivas de identificación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed451-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="ed451-104">Como administrador, puede usar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas (también conocida como identificador de línea de llamada).</span><span class="sxs-lookup"><span data-stu-id="ed451-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="ed451-105">De forma predeterminada, se puede ver el número de teléfono de los usuarios de Teams cuando hacen una llamada a un teléfono PSTN y el número de teléfono de los autores de llamadas RTC se puede ver al llamar a un usuario de Teams.</span><span class="sxs-lookup"><span data-stu-id="ed451-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="ed451-106">Puede usar las directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de equipos de su organización o impedir que se muestre un número entrante.</span><span class="sxs-lookup"><span data-stu-id="ed451-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="ed451-107">Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar la identificación de llamadas para mostrar el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed451-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="ed451-108">Para administrar las directivas de identificación de llamadas, **Voice**vaya a  >  **directivas de identificación de llamadas** de voz en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ed451-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ed451-109">Puede usar la directiva global (predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed451-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="ed451-110">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed451-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="ed451-111">Puede editar la directiva global o crear y asignar una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed451-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="ed451-112">Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="ed451-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="ed451-113">Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="ed451-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="ed451-114">Crear una directiva de identificación de llamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="ed451-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="ed451-115">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="ed451-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="ed451-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ed451-116">Click **Add**.</span></span> <br>
<span data-ttu-id="ed451-117">![Captura de pantalla de la nueva página de la Directiva de identificación de llamadas en el centro de administración](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ed451-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="ed451-118">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="ed451-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="ed451-119">Desde aquí, elija la configuración que desee:</span><span class="sxs-lookup"><span data-stu-id="ed451-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="ed451-120">**Bloquear la identificación de llamadas entrantes**: activa esta configuración para bloquear la identificación de llamadas entrantes de llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="ed451-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="ed451-121">**Invalidar la Directiva de identificación de llamadas**: activa esta configuración para permitir a los usuarios invalidar la configuración de la Directiva relativa a la presentación de su número a destinatarios o no.</span><span class="sxs-lookup"><span data-stu-id="ed451-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="ed451-122">Esto significa que los usuarios pueden elegir si deseas Mostrar la identificación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ed451-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="ed451-123">Para obtener más información, consulte [control del usuario final de la identificación de llamadas salientes](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="ed451-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="ed451-124">**Cambie la identificación de llamadas por**: establezca la identificación de llamadas que se va a mostrar para los usuarios seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ed451-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="ed451-125">**Número de usuario**: muestra el número de usuario.</span><span class="sxs-lookup"><span data-stu-id="ed451-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="ed451-126">**Número de servicio**: te permite establecer un número de teléfono de servicio para que se muestre como la identificación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ed451-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="ed451-127">**Anonymous**: muestra la identificación de llamadas como anónima.</span><span class="sxs-lookup"><span data-stu-id="ed451-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="ed451-128">**Reemplazar la identificación de llamadas por este número de servicio**: elige un número de servicio para reemplazar la identificación de llamadas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed451-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="ed451-129">Esta opción está disponible si seleccionaste **número de servicio** en **reemplazar la identificación de llamadas por**.</span><span class="sxs-lookup"><span data-stu-id="ed451-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="ed451-130">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="ed451-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="ed451-131">Editar una directiva de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="ed451-131">Edit a caller ID policy</span></span>

<span data-ttu-id="ed451-132">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="ed451-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="ed451-133">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="ed451-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="ed451-134">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ed451-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="ed451-135">Cambie la configuración que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed451-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="ed451-136">Asignar una directiva de identificación de llamadas personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="ed451-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="ed451-137">Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a uno o más usuarios o el módulo de PowerShell de Skype empresarial para asignar una directiva personalizada a grupos de usuarios, como un grupo de seguridad o un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="ed451-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="ed451-138">Asignar una directiva de identificador de línea de llamada personalizada a un usuario</span><span class="sxs-lookup"><span data-stu-id="ed451-138">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="ed451-139">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="ed451-139">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="ed451-140">Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ed451-140">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="ed451-141">En **Directiva de identificación de llamadas**, seleccione la Directiva que desea asignar y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed451-141">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="ed451-142">Asignar una directiva de identificador de línea de llamada personalizado a varios usuarios a la vez</span><span class="sxs-lookup"><span data-stu-id="ed451-142">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="ed451-143">Para asignar una directiva de identificador de línea de llamada personalizado a varios usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="ed451-143">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="ed451-144">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed451-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="ed451-145">Vaya a directivas de identificación de llamadas de voz del **centro de administración de Microsoft Teams**  >  **Voice**  >  **Caller ID policies**.</span><span class="sxs-lookup"><span data-stu-id="ed451-145">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="ed451-146">Haga clic a la izquierda del nombre de la directiva para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="ed451-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="ed451-147">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ed451-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="ed451-148">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ed451-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="ed451-149">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="ed451-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="ed451-150">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed451-150">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="ed451-151">Asignar una directiva de identificación de llamadas personalizada a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="ed451-151">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="ed451-152">Es posible que desee asignar una directiva personalizada a varios usuarios que ya haya identificado.</span><span class="sxs-lookup"><span data-stu-id="ed451-152">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="ed451-153">Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ed451-153">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="ed451-154">Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ed451-154">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="ed451-155">Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed451-155">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="ed451-156">En este ejemplo, asignamos una directiva de la tapa de la llamada personalizada denominada compatibilidad con la Directiva de identificación de llamadas a todos los usuarios del grupo soporte de contoso.</span><span class="sxs-lookup"><span data-stu-id="ed451-156">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="ed451-157">Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="ed451-157">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="ed451-158">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="ed451-158">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="ed451-159">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="ed451-159">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="ed451-160">Asignar todos los usuarios del grupo a una directiva determinada de identificación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ed451-160">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="ed451-161">En este ejemplo, es compatible con la Directiva de identificación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ed451-161">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="ed451-162">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ed451-162">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="ed451-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ed451-163">Related topics</span></span>

- [<span data-ttu-id="ed451-164">Nuevo: CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="ed451-164">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)


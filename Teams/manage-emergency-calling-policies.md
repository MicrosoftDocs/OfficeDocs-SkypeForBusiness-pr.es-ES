---
title: Administrar las directivas de llamadas de emergencia en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar las directivas de llamadas de emergencia en Microsoft Teams para definir qué sucede cuando un usuario de un equipo de su organización hace una llamada de emergencia.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98d6fb5eba98701cddccb808e5670fb34a00efbf
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539487"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="d6a96-103">Administrar las directivas de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6a96-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="d6a96-104">Si su organización usa [planes de llamadas](set-up-calling-plans.md) o el [enrutamiento directo de sistemas telefónicos](direct-routing-landing-page.md)implementados, puede usar directivas de llamadas de emergencia en Microsoft Teams para definir lo que sucede cuando un usuario de un equipo de su organización hace una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d6a96-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="d6a96-105">Puedes establecer a quién deseas notificar y cómo se les notifica cuando un usuario que tiene asignada la Directiva llama a servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d6a96-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="d6a96-106">Por ejemplo, puede configurar opciones de directiva para notificar automáticamente al escritorio de seguridad de su organización y hacer que escuchen llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d6a96-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="d6a96-107">Para administrar las directivas de llamadas de emergencia **Voice**, vaya a  >  **directivas de emergencia** de voz en el centro de administración de Microsoft Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6a96-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="d6a96-108">Las directivas se pueden asignar a los usuarios y a los [sitios de red](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d6a96-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="d6a96-109">Para los usuarios, puede usar la directiva global (opción predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d6a96-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="d6a96-110">Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6a96-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="d6a96-111">Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="d6a96-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="d6a96-112">Para los sitios de red, cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d6a96-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="d6a96-113">Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario y dicho usuario se encuentra en el sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="d6a96-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="d6a96-114">Crear una directiva de llamadas de emergencia personalizada</span><span class="sxs-lookup"><span data-stu-id="d6a96-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d6a96-115">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6a96-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="d6a96-116">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .</span><span class="sxs-lookup"><span data-stu-id="d6a96-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="d6a96-117">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-117">Click **Add**.</span></span>
3. <span data-ttu-id="d6a96-118">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="d6a96-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="d6a96-119">Establezca cómo desea notificar a los usuarios de su organización, normalmente el escritorio, Cuándo se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d6a96-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="d6a96-120">Para ello, en **modo de notificación**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d6a96-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="d6a96-121">**Enviar notificación solo**: se envía un mensaje de chat de equipo a los usuarios y grupos que especifique.</span><span class="sxs-lookup"><span data-stu-id="d6a96-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="d6a96-122">**En conferencia, pero**desactivado: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden escuchar (pero no participar) en la conversación entre el autor de la llamada y el operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="d6a96-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="d6a96-123">**Conferencias en y están** reactivadas (próximamente **)**: se envía un mensaje de chat de equipos a los usuarios y grupos que especifique y pueden reactivar el audio para escuchar y participar en la conversación entre el autor de la llamada y el operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="d6a96-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="d6a96-124">Si seleccionó el modo **de notificación está silenciado** en los **números para marcar para llamadas de emergencia** , puede escribir un número de teléfono RTC de un usuario o grupo al que llamar y unirse a la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d6a96-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="d6a96-125">Por ejemplo, escriba el número del escritorio de seguridad de su organización, que recibirá una llamada cuando se haga una llamada de emergencia y, después, podrá escuchar la llamada.</span><span class="sxs-lookup"><span data-stu-id="d6a96-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="d6a96-126">Busque y seleccione uno o más usuarios o grupos, como el escritorio de seguridad de su organización, para notificar cuando se realice una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d6a96-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="d6a96-127">La notificación se puede enviar a las direcciones de correo electrónico de los usuarios, los grupos de distribución y los grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d6a96-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="d6a96-128">Se puede notificar a un máximo de 50 usuarios.</span><span class="sxs-lookup"><span data-stu-id="d6a96-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="d6a96-129">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d6a96-130">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6a96-130">Using PowerShell</span></span>

<span data-ttu-id="d6a96-131">Vea [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d6a96-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="d6a96-132">Modificar una directiva de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="d6a96-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d6a96-133">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6a96-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d6a96-134">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="d6a96-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="d6a96-135">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .</span><span class="sxs-lookup"><span data-stu-id="d6a96-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="d6a96-136">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d6a96-137">Realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d6a96-138">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6a96-138">Using PowerShell</span></span>

<span data-ttu-id="d6a96-139">Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d6a96-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="d6a96-140">Asignar una directiva de llamadas de emergencia personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="d6a96-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d6a96-141">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6a96-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d6a96-142">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="d6a96-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="d6a96-143">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="d6a96-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d6a96-144">Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="d6a96-145">En **política de llamadas de emergencia**, seleccione la Directiva que desea asignar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="d6a96-146">Para asignar una directiva a varios usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="d6a96-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d6a96-147">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.</span><span class="sxs-lookup"><span data-stu-id="d6a96-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d6a96-148">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d6a96-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d6a96-149">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d6a96-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d6a96-150">Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="d6a96-151">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6a96-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d6a96-152">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .</span><span class="sxs-lookup"><span data-stu-id="d6a96-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="d6a96-153">Haga clic a la izquierda del nombre de la directiva para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="d6a96-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d6a96-154">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="d6a96-155">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d6a96-156">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="d6a96-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d6a96-157">Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6a96-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d6a96-158">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6a96-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="d6a96-159">Asignar una directiva de llamadas de emergencia personalizada a un usuario</span><span class="sxs-lookup"><span data-stu-id="d6a96-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="d6a96-160">Consulte [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d6a96-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="d6a96-161">Asignar una directiva de llamadas de emergencia personalizada a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="d6a96-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="d6a96-162">Es posible que desee asignar una directiva de llamadas de emergencia personalizada a varios usuarios que ya haya identificado.</span><span class="sxs-lookup"><span data-stu-id="d6a96-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="d6a96-163">Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d6a96-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="d6a96-164">Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6a96-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="d6a96-165">En este ejemplo, asignamos una directiva llamada Directiva de llamadas de emergencia de operaciones a todos los usuarios del grupo de operaciones de contoso.</span><span class="sxs-lookup"><span data-stu-id="d6a96-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="d6a96-166">Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="d6a96-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="d6a96-167">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="d6a96-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="d6a96-168">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="d6a96-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="d6a96-169">Asignar todos los usuarios del grupo a una directiva de equipos en particular.</span><span class="sxs-lookup"><span data-stu-id="d6a96-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="d6a96-170">En este ejemplo, es una directiva de enrutamiento de llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d6a96-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="d6a96-171">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d6a96-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="d6a96-172">Asignar una directiva de llamadas de emergencia personalizada a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="d6a96-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="d6a96-173">Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de llamadas de emergencia a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="d6a96-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="d6a96-174">En el ejemplo siguiente se muestra cómo asignar una directiva denominada política de llamadas de emergencia de Contoso 1 al sitio de Sitio1.</span><span class="sxs-lookup"><span data-stu-id="d6a96-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="d6a96-175">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d6a96-175">Related topics</span></span>

- [<span data-ttu-id="d6a96-176">Administrar directivas de enrutamiento de llamadas de emergencia en Teams</span><span class="sxs-lookup"><span data-stu-id="d6a96-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="d6a96-177">Información general de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="d6a96-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d6a96-178">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="d6a96-178">Assign policies to your users in Teams</span></span>](assign-policies.md)

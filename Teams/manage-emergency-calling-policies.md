---
title: Administrar directivas de llamadas de emergencia en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de llamadas de emergencia en Microsoft Teams para definir lo que sucede cuando un usuario Teams de su organización realiza una llamada de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120571"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="cf4f5-103">Administrar directivas de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf4f5-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="cf4f5-104">Si su [](set-up-calling-plans.md) organización usa planes de llamadas o enrutamiento directo implementado [Sistema telefónico](direct-routing-landing-page.md), puede usar directivas de llamadas de emergencia en Microsoft Teams para definir lo que sucede cuando un usuario de Teams de su organización realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="cf4f5-105">Puede establecer a quién notificar y cómo se les notifica cuando un usuario al que se le asigna la directiva llama a los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="cf4f5-106">Por ejemplo, puede configurar la configuración de directiva para notificar automáticamente al servicio de seguridad de su organización y hacer que escuche las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="cf4f5-107">Para administrar las directivas de llamadas de emergencia, vaya a Directivas de emergencia de voz en el centro Microsoft Teams de administración o mediante  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="cf4f5-108">Las directivas se pueden asignar a usuarios y sitios [de red.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cf4f5-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="cf4f5-109">Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="cf4f5-110">Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="cf4f5-111">Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiar el nombre ni eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="cf4f5-112">Para los sitios de red, cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="cf4f5-113">Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="cf4f5-114">Crear una directiva de llamadas de emergencia personalizada</span><span class="sxs-lookup"><span data-stu-id="cf4f5-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cf4f5-115">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf4f5-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="cf4f5-116">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Directivas de emergencia de voz y, a continuación, haga  >  clic en la pestaña **Directivas de** llamadas.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="cf4f5-117">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-117">Click **Add**.</span></span>
3. <span data-ttu-id="cf4f5-118">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="cf4f5-119">Establezca cómo quiere notificar a los usuarios de su organización, normalmente el escritorio de seguridad, cuando se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="cf4f5-120">Para ello, en **Modo de notificación,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cf4f5-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="cf4f5-121">**Enviar solo notificación:** se envía un Teams de chat a los usuarios y grupos que especifique.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="cf4f5-122">**Conferencia en** silenciada y no se puede activar: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden escuchar (pero no participar) en la conversación entre el autor de la llamada y el operador psap.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="cf4f5-123">**Conferencia en** silenciada pero que puede activar: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y que pueden activar para escuchar y participar en la conversación entre el autor de la llamada y el operador de PSAP.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="cf4f5-124">Si seleccionó cualquiera  de los modos conferencia  en modo de notificación silenciada, en el cuadro Números para marcar para las notificaciones de llamadas de emergencia, puede escribir un número de teléfono RTC de un usuario o grupo para llamar y unirse a la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="cf4f5-125">Por ejemplo, escriba el número del servicio de seguridad de su organización, que recibirá una llamada cuando se haga una llamada de emergencia y, a continuación, podrá escuchar la llamada.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="cf4f5-126">El teléfono RTC no se puede desmutar incluso cuando el modo está establecido en Conferencia en silenciado, pero pueden **desenmuteer**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="cf4f5-127">Busque y seleccione uno o varios usuarios o grupos, como el escritorio de seguridad de su organización, para notificar cuando se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="cf4f5-128">La notificación se puede enviar a direcciones de correo electrónico de usuarios, grupos de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="cf4f5-129">Se puede notificar un máximo de 50 usuarios.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="cf4f5-130">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cf4f5-131">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf4f5-131">Using PowerShell</span></span>

<span data-ttu-id="cf4f5-132">Vea [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="cf4f5-132">See [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="cf4f5-133">Editar una directiva de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="cf4f5-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cf4f5-134">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf4f5-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="cf4f5-135">Puede editar la directiva global o las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="cf4f5-136">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Directivas de emergencia de voz y, a continuación, haga  >  clic en la pestaña **Directivas de** llamadas.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="cf4f5-137">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="cf4f5-138">Realice los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cf4f5-139">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf4f5-139">Using PowerShell</span></span>

<span data-ttu-id="cf4f5-140">Vea [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="cf4f5-140">See [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="cf4f5-141">Asignar una directiva de llamadas de emergencia personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="cf4f5-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="cf4f5-142">Vea también [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="cf4f5-142">See also [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="cf4f5-143">Asignar una directiva de llamadas de emergencia personalizada a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="cf4f5-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="cf4f5-144">Use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de llamadas de emergencia a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-144">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="cf4f5-145">En el ejemplo siguiente se muestra cómo asignar una directiva denominada Directiva de llamadas de emergencia contoso 1 al sitio de Sitio1.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="cf4f5-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cf4f5-146">Related topics</span></span>

[<span data-ttu-id="cf4f5-147">Administrar directivas de enrutamiento de llamadas de emergencia en Teams</span><span class="sxs-lookup"><span data-stu-id="cf4f5-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="cf4f5-148">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="cf4f5-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="cf4f5-149">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="cf4f5-149">Assign policies to your users in Teams</span></span>](assign-policies.md)
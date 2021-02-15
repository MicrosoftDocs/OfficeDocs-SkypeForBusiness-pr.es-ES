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
description: Aprenda a usar y administrar las directivas de llamadas de emergencia en Microsoft Teams para definir lo que ocurre cuando un usuario de Teams de su organización realiza una llamada de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973144"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="e0b02-103">Administrar directivas de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0b02-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="e0b02-104">Si su [](set-up-calling-plans.md) organización usa planes de llamadas o enrutamiento directo de sistema telefónico [implementado,](direct-routing-landing-page.md)puede usar directivas de llamadas de emergencia en Microsoft Teams para definir lo que ocurre cuando un usuario de Teams de su organización realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e0b02-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="e0b02-105">Puede establecer a quién notificar y cómo se le notificará cuando un usuario asignado a la directiva llame a los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e0b02-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="e0b02-106">Por ejemplo, puede configurar las opciones de directiva para notificar automáticamente al servicio de seguridad de su organización y que escuche en llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e0b02-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="e0b02-107">Para administrar las directivas de llamadas de emergencia, vaya a directivas **de** emergencia de voz en el Centro de administración de Microsoft Teams o  >   use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0b02-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="e0b02-108">Las directivas se pueden asignar a usuarios y sitios [de red.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e0b02-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="e0b02-109">Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e0b02-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e0b02-110">Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="e0b02-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e0b02-111">Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiarle el nombre ni eliminarla.</span><span class="sxs-lookup"><span data-stu-id="e0b02-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="e0b02-112">Para sitios de red, puede crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e0b02-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="e0b02-113">Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red invalidará la directiva que se asignó al usuario.</span><span class="sxs-lookup"><span data-stu-id="e0b02-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="e0b02-114">Crear una directiva de llamadas de emergencia personalizada</span><span class="sxs-lookup"><span data-stu-id="e0b02-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e0b02-115">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0b02-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e0b02-116">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y haga clic en la  >  pestaña **Directivas de** llamadas.</span><span class="sxs-lookup"><span data-stu-id="e0b02-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e0b02-117">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e0b02-117">Click **Add**.</span></span>
3. <span data-ttu-id="e0b02-118">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="e0b02-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e0b02-119">Configure cómo quiere notificar a las personas de su organización(normalmente el servicio de seguridad) cuando se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e0b02-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="e0b02-120">Para ello, en **modo de notificación,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e0b02-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="e0b02-121">**Enviar solo notificación:** se envía un mensaje de chat de Teams a los usuarios y grupos que especifique.</span><span class="sxs-lookup"><span data-stu-id="e0b02-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="e0b02-122">Conferencias silenciadas y sin poder activar el **sonido:** se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y estos pueden escuchar (pero no participar) la conversación entre el autor de la llamada y el operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="e0b02-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="e0b02-123">**Con** conferencias silenciadas, pero pueden activarlo: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden activar el sonido para escuchar y participar en la conversación entre el autor de la llamada y el operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="e0b02-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="e0b02-124">Si seleccionó cualquiera  de las dos **conferencias** en modos de notificación silenciados, en el cuadro Números para marcar para las notificaciones de llamadas de emergencia, puede introducir un número de teléfono RTC de un usuario o grupo para llamar y unirse a la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e0b02-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="e0b02-125">Por ejemplo, escriba el número del servicio de seguridad de su organización, que recibirá una llamada cuando se haga una llamada de emergencia y podrá escuchar la llamada.</span><span class="sxs-lookup"><span data-stu-id="e0b02-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="e0b02-126">El teléfono RTC no se puede activar ni siquiera cuando el modo está establecido en Conferencia **silenciada, pero puede activarlo.**</span><span class="sxs-lookup"><span data-stu-id="e0b02-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="e0b02-127">Busque y seleccione uno o varios usuarios o grupos, como el servicio de seguridad de su organización, para notificar cuando se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e0b02-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="e0b02-128">La notificación se puede enviar a direcciones de correo electrónico de usuarios, grupos de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e0b02-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="e0b02-129">Se puede notificar a un máximo de 50 usuarios.</span><span class="sxs-lookup"><span data-stu-id="e0b02-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="e0b02-130">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e0b02-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e0b02-131">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0b02-131">Using PowerShell</span></span>

<span data-ttu-id="e0b02-132">Consulte [New-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e0b02-132">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="e0b02-133">Editar una directiva de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="e0b02-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e0b02-134">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0b02-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e0b02-135">Puede editar la directiva global o las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="e0b02-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="e0b02-136">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y haga clic en la  >  pestaña **Directivas de** llamadas.</span><span class="sxs-lookup"><span data-stu-id="e0b02-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e0b02-137">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e0b02-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e0b02-138">Realice los cambios que desee y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="e0b02-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e0b02-139">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0b02-139">Using PowerShell</span></span>

<span data-ttu-id="e0b02-140">Consulte [Set-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e0b02-140">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="e0b02-141">Asignar una directiva de llamadas de emergencia personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="e0b02-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="e0b02-142">Vea también [Grant-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e0b02-142">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="e0b02-143">Asignar una directiva de llamadas de emergencia personalizada a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="e0b02-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="e0b02-144">Use el [cmdlet Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de llamadas de emergencia a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e0b02-144">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="e0b02-145">En el ejemplo siguiente se muestra cómo asignar una directiva denominada Directiva de llamadas de emergencia 1 de Contoso al sitio Sitio1.</span><span class="sxs-lookup"><span data-stu-id="e0b02-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="e0b02-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e0b02-146">Related topics</span></span>

[<span data-ttu-id="e0b02-147">Administrar directivas de enrutamiento de llamadas de emergencia en Teams</span><span class="sxs-lookup"><span data-stu-id="e0b02-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="e0b02-148">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="e0b02-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="e0b02-149">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="e0b02-149">Assign policies to your users in Teams</span></span>](assign-policies.md)

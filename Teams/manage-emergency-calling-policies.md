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
ms.openlocfilehash: 12d2e114a53c47e6c938c6c2cb4bf3cb83c81180
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938439"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="be116-103">Administrar las directivas de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be116-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="be116-104">Si su organización usa [planes de llamadas](set-up-calling-plans.md) o el [enrutamiento directo de sistemas telefónicos](direct-routing-landing-page.md)implementados, puede usar directivas de llamadas de emergencia en Microsoft Teams para definir lo que sucede cuando un usuario de un equipo de su organización hace una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="be116-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="be116-105">Puedes establecer a quién deseas notificar y cómo se les notifica cuando un usuario que tiene asignada la Directiva llama a servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="be116-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="be116-106">Por ejemplo, puede configurar opciones de directiva para notificar automáticamente al escritorio de seguridad de su organización y hacer que escuchen llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="be116-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="be116-107">Para administrar las directivas de llamadas de emergencia **Voice**, vaya a  >  **directivas de emergencia** de voz en el centro de administración de Microsoft Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be116-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="be116-108">Las directivas se pueden asignar a los usuarios y a los [sitios de red](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="be116-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="be116-109">Para los usuarios, puede usar la directiva global (opción predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="be116-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="be116-110">Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="be116-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="be116-111">Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="be116-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="be116-112">Para los sitios de red, cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="be116-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="be116-113">Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario y dicho usuario se encuentra en el sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="be116-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="be116-114">Crear una directiva de llamadas de emergencia personalizada</span><span class="sxs-lookup"><span data-stu-id="be116-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="be116-115">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be116-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="be116-116">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .</span><span class="sxs-lookup"><span data-stu-id="be116-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="be116-117">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="be116-117">Click **Add**.</span></span>
3. <span data-ttu-id="be116-118">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="be116-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="be116-119">Establezca cómo desea notificar a los usuarios de su organización, normalmente el escritorio, Cuándo se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="be116-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="be116-120">Para ello, en **modo de notificación**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="be116-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="be116-121">**Enviar notificación solo**: se envía un mensaje de chat de equipo a los usuarios y grupos que especifique.</span><span class="sxs-lookup"><span data-stu-id="be116-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="be116-122">**En conferencia, pero**desactivado: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden escuchar (pero no participar) en la conversación entre el autor de la llamada y el operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="be116-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="be116-123">**Conferencias en y están** reactivadas (próximamente **)**: se envía un mensaje de chat de equipos a los usuarios y grupos que especifique y pueden reactivar el audio para escuchar y participar en la conversación entre el autor de la llamada y el operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="be116-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="be116-124">Si seleccionó el modo **de notificación está silenciado** en los **números para marcar para llamadas de emergencia** , puede escribir un número de teléfono RTC de un usuario o grupo al que llamar y unirse a la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="be116-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="be116-125">Por ejemplo, escriba el número del escritorio de seguridad de su organización, que recibirá una llamada cuando se haga una llamada de emergencia y, después, podrá escuchar la llamada.</span><span class="sxs-lookup"><span data-stu-id="be116-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="be116-126">Busque y seleccione uno o más usuarios o grupos, como el escritorio de seguridad de su organización, para notificar cuando se realice una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="be116-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="be116-127">La notificación se puede enviar a las direcciones de correo electrónico de los usuarios, los grupos de distribución y los grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="be116-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="be116-128">Se puede notificar a un máximo de 50 usuarios.</span><span class="sxs-lookup"><span data-stu-id="be116-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="be116-129">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="be116-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="be116-130">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="be116-130">Using PowerShell</span></span>

<span data-ttu-id="be116-131">Vea [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="be116-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="be116-132">Modificar una directiva de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="be116-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="be116-133">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be116-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="be116-134">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="be116-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="be116-135">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .</span><span class="sxs-lookup"><span data-stu-id="be116-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="be116-136">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="be116-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="be116-137">Realice los cambios que desee y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="be116-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="be116-138">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="be116-138">Using PowerShell</span></span>

<span data-ttu-id="be116-139">Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="be116-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="be116-140">Asignar una directiva de llamadas de emergencia personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="be116-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="be116-141">Consulte también [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="be116-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="be116-142">Asignar una directiva de llamadas de emergencia personalizada a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="be116-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="be116-143">Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de llamadas de emergencia a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="be116-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="be116-144">En el ejemplo siguiente se muestra cómo asignar una directiva denominada política de llamadas de emergencia de Contoso 1 al sitio de Sitio1.</span><span class="sxs-lookup"><span data-stu-id="be116-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="be116-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="be116-145">Related topics</span></span>

[<span data-ttu-id="be116-146">Administrar directivas de enrutamiento de llamadas de emergencia en Teams</span><span class="sxs-lookup"><span data-stu-id="be116-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="be116-147">Información general de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="be116-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="be116-148">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="be116-148">Assign policies to your users in Teams</span></span>](assign-policies.md)

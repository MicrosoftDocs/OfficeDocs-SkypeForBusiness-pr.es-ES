---
title: Administrar directivas de enrutamiento de llamadas de emergencia
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar números de emergencia y especificar cómo se enrutar las llamadas de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096184"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="6a43b-103">Administrar directivas de enrutamiento de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a43b-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="6a43b-104">Si ha implementado [](direct-routing-landing-page.md) enrutamiento directo del sistema telefónico en su organización, puede usar directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar números de emergencia y especificar cómo se enruten las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="6a43b-105">Una directiva de enrutamiento de llamadas de emergencia determina si los servicios de emergencia mejorados están habilitados para los usuarios a los que se les asignó la directiva, los números usados para llamar a servicios de emergencia (por ejemplo, 911 en Estados Unidos) y cómo se enrutar las llamadas a los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="6a43b-106">Para administrar las directivas de enrutamiento de llamadas de emergencia, vaya a Directivas de emergencia de voz en el Centro de administración de Microsoft Teams o  >   mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a43b-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="6a43b-107">Las directivas se pueden asignar a usuarios y sitios [de red.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6a43b-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="6a43b-108">Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6a43b-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="6a43b-109">Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="6a43b-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6a43b-110">Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiar el nombre ni eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="6a43b-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="6a43b-111">Para los sitios de red, cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6a43b-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="6a43b-112">Si asignó una directiva de enrutamiento de llamadas de emergencia a un sitio de red y a un usuario y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="6a43b-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="6a43b-113">Crear una directiva de enrutamiento de llamadas de emergencia personalizada</span><span class="sxs-lookup"><span data-stu-id="6a43b-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6a43b-114">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a43b-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6a43b-115">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y, a continuación, haga clic en la pestaña Directivas  >  de **enrutamiento de** llamadas.</span><span class="sxs-lookup"><span data-stu-id="6a43b-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="6a43b-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6a43b-116">Click **Add**.</span></span>
3. <span data-ttu-id="6a43b-117">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="6a43b-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="6a43b-118">Para habilitar las llamadas de emergencia dinámicas, active **Llamadas de emergencia dinámicas.**</span><span class="sxs-lookup"><span data-stu-id="6a43b-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="6a43b-119">Cuando las llamadas de emergencia dinámicas están habilitadas, Teams recupera información de directiva y ubicación del servicio e incluye esa información como parte de la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="6a43b-120">Defina uno o varios números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="6a43b-121">Para ello, en **Números de emergencia,** haga clic **en Agregar** y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a43b-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="6a43b-122">**Cadena de marcado de emergencia:** escriba la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="6a43b-123">Esta cadena de marcado indica que una llamada es una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="6a43b-124">Para enrutamiento directo, nos estamos alejando de los clientes de Teams que envían llamadas de emergencia con un "+" delante de la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="6a43b-125">Hasta que se complete la transición, el patrón de ruta de voz para que coincida con una cadena de marcado de emergencia debe asegurarse de que se realiza una coincidencia para las cadenas que tienen y no tienen un "+" anterior, como 911 y +911.</span><span class="sxs-lookup"><span data-stu-id="6a43b-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="6a43b-126">Por ejemplo, ^ \\ +?911 o .\*.</span><span class="sxs-lookup"><span data-stu-id="6a43b-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="6a43b-127">**Máscara de marcado de** emergencia: para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="6a43b-128">Una máscara de marcado es el número que desea traducir al valor de la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="6a43b-129">Esto permite que se marquen números de emergencia alternativos y que la llamada llegue a los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="6a43b-130">Por ejemplo, agregue 112 como máscara de marcado de emergencia, que es el número de servicio de emergencia de la mayor parte de Europa, y 911 como cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6a43b-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="6a43b-131">Es posible que un usuario de Teams de Europa que está de visita no sepa que el 911 es el número de emergencia en Estados Unidos y, cuando marca el 112, la llamada se realiza al 911.</span><span class="sxs-lookup"><span data-stu-id="6a43b-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="6a43b-132">Para definir varias máscaras de marcado, separe cada valor por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="6a43b-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="6a43b-133">Por ejemplo, 112;212.</span><span class="sxs-lookup"><span data-stu-id="6a43b-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="6a43b-134">**Registro de uso rtc:** seleccione el registro de uso de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="6a43b-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="6a43b-135">El registro de uso de RTC se usa para determinar qué ruta se usa para enrutar llamadas de emergencia de usuarios autorizados a usarlas.</span><span class="sxs-lookup"><span data-stu-id="6a43b-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="6a43b-136">La ruta asociada con este uso debe apuntar a un tronco del Protocolo de inicio de sesión (SIP) dedicado a las llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al Punto de respuesta de seguridad pública (PSAP) más próximo.</span><span class="sxs-lookup"><span data-stu-id="6a43b-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a43b-137">Las cadenas de marcado y las máscaras de marcado deben ser únicas dentro de una directiva.</span><span class="sxs-lookup"><span data-stu-id="6a43b-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="6a43b-138">Esto significa que, para una directiva, puede definir varios números de emergencia y puede establecer varias máscaras de marcado para una cadena de marcado, pero cada cadena de marcado y máscara de marcado solo debe usarse una vez.</span><span class="sxs-lookup"><span data-stu-id="6a43b-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="6a43b-139">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a43b-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6a43b-140">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a43b-140">Using PowerShell</span></span>

<span data-ttu-id="6a43b-141">Vea [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="6a43b-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="6a43b-142">Editar una directiva de enrutamiento de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="6a43b-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6a43b-143">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a43b-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6a43b-144">Puede editar la directiva global o las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="6a43b-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="6a43b-145">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y, a continuación, haga clic en la pestaña Directivas  >  de **enrutamiento de** llamadas.</span><span class="sxs-lookup"><span data-stu-id="6a43b-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="6a43b-146">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6a43b-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6a43b-147">Realice los cambios que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="6a43b-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6a43b-148">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a43b-148">Using PowerShell</span></span>

<span data-ttu-id="6a43b-149">Vea [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="6a43b-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="6a43b-150">Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="6a43b-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="6a43b-151">Vea también [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="6a43b-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="6a43b-152">Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="6a43b-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="6a43b-153">Use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de enrutamiento de llamadas de emergencia a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="6a43b-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="6a43b-154">En este ejemplo se muestra cómo asignar una directiva denominada Directiva de enrutamiento de llamadas de emergencia 1 al sitio de Sitio1.</span><span class="sxs-lookup"><span data-stu-id="6a43b-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="6a43b-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6a43b-155">Related topics</span></span>

[<span data-ttu-id="6a43b-156">Administrar directivas de llamadas de emergencia en Teams</span><span class="sxs-lookup"><span data-stu-id="6a43b-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="6a43b-157">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="6a43b-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="6a43b-158">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="6a43b-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
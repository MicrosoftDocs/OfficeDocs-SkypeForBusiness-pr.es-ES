---
title: Administrar directivas de enrutamiento de llamadas de emergencia
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar y administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar los números de emergencia y especificar cómo se enrutarán las llamadas de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 67ef3bb5700c223f3057ef0ba44c9df07a2e7be6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217701"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="85ada-103">Administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85ada-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="85ada-104">Si ha implementado el [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md) en su organización, puede usar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar los números de emergencia y especificar cómo se enrutan las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="85ada-105">Una política de enrutamiento de llamadas determina si se habilitan los servicios de emergencia mejorados para los usuarios que tienen asignada la Directiva, los números que se usan para llamar a servicios de emergencia (por ejemplo, 911 en Estados Unidos) y cómo se enrutan las llamadas a servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="85ada-106">Para administrar las directivas de enrutamiento de llamadas de **Voice**emergencia, vaya a  >  **directivas de emergencia** de voz en el centro de administración de Microsoft Teams o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85ada-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="85ada-107">Las directivas se pueden asignar a los usuarios y a los [sitios de red](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="85ada-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="85ada-108">Para los usuarios, puede usar la directiva global (opción predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="85ada-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="85ada-109">Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="85ada-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="85ada-110">Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="85ada-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="85ada-111">Para los sitios de red, cree y asigne directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="85ada-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="85ada-112">Si asignó una directiva de enrutamiento de llamadas de emergencia a un sitio de red y a un usuario y dicho usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red reemplaza la que está asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="85ada-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="85ada-113">Crear una directiva de enrutamiento de llamadas de emergencia personalizada</span><span class="sxs-lookup"><span data-stu-id="85ada-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="85ada-114">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85ada-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="85ada-115">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de enrutamiento de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="85ada-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="85ada-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="85ada-116">Click **Add**.</span></span>
3. <span data-ttu-id="85ada-117">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="85ada-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="85ada-118">Para habilitar las llamadas de emergencia dinámicas, activa las **llamadas de emergencia dinámicas**.</span><span class="sxs-lookup"><span data-stu-id="85ada-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="85ada-119">Cuando se habilitan las llamadas de emergencia dinámicas, Teams recupera la información de directivas y ubicaciones del servicio e incluye esa información como parte de la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="85ada-120">Defina uno o más números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="85ada-121">Para hacerlo, en **números de emergencia**, haga clic en **Agregar**y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85ada-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="85ada-122">**Cadena de marcado de emergencia**: escriba la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="85ada-123">Esta cadena de marcado indica que una llamada es una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="85ada-124">Para el enrutamiento directo, estamos pasando de los clientes de Teams a través de una llamada de emergencia con un "+" delante de la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="85ada-125">Hasta que se complete la transición, el patrón de enrutamiento de voz que se corresponda con una cadena de marcado de emergencia debe garantizar que se realice una coincidencia con las cadenas que tengan y no tengan una "+" anterior, como 911 y + 911.</span><span class="sxs-lookup"><span data-stu-id="85ada-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="85ada-126">Por ejemplo, ^ \\ +? 911 o. \*.</span><span class="sxs-lookup"><span data-stu-id="85ada-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="85ada-127">**Máscara de marcado de emergencia**: para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="85ada-128">Una máscara de marcado es el número que desea traducir en el valor de la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="85ada-129">Esto permite que se marquen números de emergencia alternativos y que la llamada tenga acceso a los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="85ada-130">Por ejemplo, agrega 112 como máscara de marcado de emergencia, que es el número de servicio de emergencia para la mayoría de Europa y 911 como la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="85ada-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="85ada-131">Un usuario de equipos de Europa que visita puede no saber que 911 es el número de emergencia en los Estados Unidos y cuando marca 112, la llamada se realiza a 911.</span><span class="sxs-lookup"><span data-stu-id="85ada-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="85ada-132">Para definir varias máscaras de marcado, separe cada valor por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="85ada-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="85ada-133">Por ejemplo, 112; 212.</span><span class="sxs-lookup"><span data-stu-id="85ada-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="85ada-134">**Registro de uso de RTC**: seleccione el registro de uso de la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="85ada-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="85ada-135">El registro de uso de RTC se usa para determinar qué ruta se usa para enrutar llamadas de emergencia de los usuarios autorizados a usarlos.</span><span class="sxs-lookup"><span data-stu-id="85ada-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="85ada-136">La ruta asociada con este uso debe apuntar a un tronco de protocolo de inicio de sesión (SIP) dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que dirige las llamadas de emergencia al punto de respuesta de seguridad pública más cercano (PSAP).</span><span class="sxs-lookup"><span data-stu-id="85ada-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="85ada-137">Las cadenas de marcado y las máscaras de marcado deben ser únicas dentro de una directiva.</span><span class="sxs-lookup"><span data-stu-id="85ada-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="85ada-138">Esto significa que, para una directiva, puede definir varios números de emergencia y puede establecer varias máscaras de marcado para una cadena de marcado, pero cada cadena de marcado y máscara de marcado debe usarse solo una vez.</span><span class="sxs-lookup"><span data-stu-id="85ada-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="85ada-139">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="85ada-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="85ada-140">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="85ada-140">Using PowerShell</span></span>

<span data-ttu-id="85ada-141">Vea [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="85ada-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="85ada-142">Modificar una política de enrutamiento de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="85ada-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="85ada-143">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85ada-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="85ada-144">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="85ada-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="85ada-145">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de enrutamiento de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="85ada-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="85ada-146">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="85ada-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="85ada-147">Realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="85ada-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="85ada-148">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="85ada-148">Using PowerShell</span></span>

<span data-ttu-id="85ada-149">Consulte [set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="85ada-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="85ada-150">Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="85ada-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="85ada-151">Consulte también [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="85ada-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="85ada-152">Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="85ada-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="85ada-153">Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de enrutamiento de llamadas de emergencia a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="85ada-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="85ada-154">Este ejemplo muestra cómo asignar una directiva denominada Directiva de enrutamiento de llamadas de emergencia 1 al sitio de Sitio1.</span><span class="sxs-lookup"><span data-stu-id="85ada-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="85ada-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="85ada-155">Related topics</span></span>

[<span data-ttu-id="85ada-156">Administrar las directivas de llamadas de emergencia en Teams</span><span class="sxs-lookup"><span data-stu-id="85ada-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="85ada-157">Información general de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="85ada-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="85ada-158">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="85ada-158">Assign policies to your users in Teams</span></span>](assign-policies.md)

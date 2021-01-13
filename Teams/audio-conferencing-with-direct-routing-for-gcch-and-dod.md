---
title: Audioconferencia con enrutamiento directo, M.C.CH y DoD
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: El administrador puede obtener información sobre cómo usar audioconferencia con enrutamiento directo en entornos GCCH y DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 818b36e379532e361fd3991b002bc899156af056
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812920"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="cc16e-103">Audioconferencia con enrutamiento directo para GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="cc16e-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="cc16e-104">Las audioconferencias con enrutamiento directo para GCC High y DoD permiten a los participantes unirse a las reuniones de Teams en su organización de GCC High o DoD con un dispositivo telefónico.</span><span class="sxs-lookup"><span data-stu-id="cc16e-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="cc16e-105">Es posible que los participantes de la reunión prefieran usar un dispositivo telefónico para unirse a reuniones de Teams en situaciones como cuando la conectividad a Internet es limitada o cuando los usuarios están de viaje y no tienen acceso a Teams.</span><span class="sxs-lookup"><span data-stu-id="cc16e-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="cc16e-106">Los participantes pueden elegir entre unirse a las reuniones mediante marcado en un número de teléfono de acceso telefónico local para su organización o haciendo que la reunión llame a su dispositivo de teléfono.</span><span class="sxs-lookup"><span data-stu-id="cc16e-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="cc16e-107">Con las audioconferencias con enrutamiento directo para GCC High y DoD, su organización usa sus propios números como números de teléfono de acceso telefónico local y todas las llamadas a las llamadas a los dispositivos telefónicos se enruta a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="cc16e-108">Para habilitar el servicio, las organizaciones necesitan configurar el enrutamiento directo y los números de teléfono que se pueden usar como números de teléfono de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="cc16e-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="cc16e-109">El requisito de usar enrutamiento directo es diferente del servicio de Audioconferencia que se ofrece a organizaciones que no son GCC High y que no son DoD donde Microsoft proporciona los números de teléfono de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="cc16e-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="cc16e-110">Implementar Audioconferencia con enrutamiento directo para GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="cc16e-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="cc16e-111">Paso 1: Obtener Audioconferencia con enrutamiento directo para licencias GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="cc16e-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="cc16e-112">Para usar Audioconferencia en GCC High o DoD, su organización y los usuarios de su organización necesitan tener asignada una licencia de Audioconferencia con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="cc16e-113">Estas son las licencias que necesita para habilitar audioconferencia con enrutamiento directo para GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="cc16e-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="cc16e-114">GCC High: Una licencia de Audioconferencia - Inquilino de GCC High para su organización y Audioconferencia - licencias de GCC High para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="cc16e-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="cc16e-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span><span class="sxs-lookup"><span data-stu-id="cc16e-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="cc16e-116">Se requiere una licencia de espacio empresarial y al menos una licencia de usuario para habilitar el servicio.</span><span class="sxs-lookup"><span data-stu-id="cc16e-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="cc16e-117">No puede habilitar el servicio solo con la licencia del inquilino o solo con licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="cc16e-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="cc16e-118">Para obtener licencias de servicio para su inquilino y los usuarios de su organización, póngase en contacto con el equipo de cuentas.</span><span class="sxs-lookup"><span data-stu-id="cc16e-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc16e-119">No se puede habilitar a los usuarios para Audioconferencia con enrutamiento directo hasta que no se configuren los números de teléfono de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="cc16e-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="cc16e-120">Le recomendamos que no asigne audioconferencias con enrutamiento directo para licencias GCC High o DoD a los usuarios hasta que configure los números de teléfono de acceso telefónico local como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="cc16e-121">Paso 2: Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="cc16e-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="cc16e-122">Para configurar enrutamiento directo, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc16e-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="cc16e-123">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="cc16e-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="cc16e-124">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="cc16e-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="cc16e-125">Al configurar enrutamiento directo, recuerde usar los FQDN y los puertos específicos de GCC High o DoD que se describen en estos dos artículos.</span><span class="sxs-lookup"><span data-stu-id="cc16e-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="cc16e-126">Paso 3: Configurar los números de teléfono de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="cc16e-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="cc16e-127">Los números de teléfono de acceso telefónico local son los que están asociados a su puente de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="cc16e-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="cc16e-128">Los participantes usan estos números para unirse a reuniones programadas por los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="cc16e-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="cc16e-129">Estos números también se incluyen en las invitaciones a reuniones de los usuarios que programan reuniones en su organización y en la página "Buscar un número local".</span><span class="sxs-lookup"><span data-stu-id="cc16e-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="cc16e-130">Definir números de teléfono de servicio en el inquilino</span><span class="sxs-lookup"><span data-stu-id="cc16e-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="cc16e-131">Puede usar el cmdlet de PowerShell New-csHybridTelephoneNumber para definir los números de teléfono de servicio del inquilino que se pueden usar para enrutar llamadas al servicio de Audioconferencia a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="cc16e-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc16e-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="cc16e-133">Asignar los números de teléfono de servicio al puente de Audioconferencia de su organización</span><span class="sxs-lookup"><span data-stu-id="cc16e-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="cc16e-134">Puede asignar números de teléfono de servicio al puente de Audioconferencia de su organización mediante el cmdlet Register-csOnlineDialInConferencingServiceNumber PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc16e-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="cc16e-135">Puede ver el id. de su puente de audioconferencia con Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="cc16e-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="cc16e-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc16e-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="cc16e-137">Paso 4: Definir una directiva global de enrutamiento de voz para habilitar el enrutamiento de llamadas salientes desde reuniones</span><span class="sxs-lookup"><span data-stu-id="cc16e-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="cc16e-138">El enrutamiento de las llamadas salientes realizadas a la RTC desde reuniones organizadas por los usuarios de su organización está definido por la directiva global de enrutamiento de voz de su organización.</span><span class="sxs-lookup"><span data-stu-id="cc16e-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="cc16e-139">Si su organización tiene definida una directiva global de enrutamiento de voz, compruebe que la directiva global de enrutamiento de voz permite que las llamadas salientes a la RTC se inicien desde reuniones organizadas por los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="cc16e-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="cc16e-140">Si su organización no tiene definida una directiva global de enrutamiento de voz, tendrá que definir una para habilitar el enrutamiento de llamadas salientes a la RTC desde reuniones organizadas por los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="cc16e-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="cc16e-141">Tenga en cuenta que la directiva global de enrutamiento de voz de su organización también se aplica a las llamadas uno a uno realizadas a RTC por los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="cc16e-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="cc16e-142">Si las llamadas uno a uno a la RTC están habilitadas para los usuarios de su organización, asegúrese de que la directiva global de enrutamiento de voz cumple las necesidades de su organización para ambos tipos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="cc16e-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="cc16e-143">Location-Based implementación de Microsoft 365 Government Community Cloud (GCC) High o DoD.</span><span class="sxs-lookup"><span data-stu-id="cc16e-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="cc16e-144">Al habilitar Audioconferencia, compruebe que no haya usuarios de Audioconferencia en GCC High ni en los entornos doD habilitados para el Location-Based voz.</span><span class="sxs-lookup"><span data-stu-id="cc16e-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="cc16e-145">Definir una directiva global de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="cc16e-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="cc16e-146">Para definir una directiva global de enrutamiento de voz, defina un uso de RTC, una ruta de voz, una directiva de enrutamiento de voz y asigne la nueva directiva de enrutamiento de voz como directiva global de enrutamiento de voz de su organización.</span><span class="sxs-lookup"><span data-stu-id="cc16e-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="cc16e-147">En los pasos siguientes se describe cómo definir una nueva directiva global de enrutamiento de voz para una organización sin una.</span><span class="sxs-lookup"><span data-stu-id="cc16e-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="cc16e-148">Si su organización ya tiene definidas directivas de enrutamiento de voz, compruebe que la siguiente configuración no entre en conflicto con las directivas de enrutamiento de voz existentes de la organización.</span><span class="sxs-lookup"><span data-stu-id="cc16e-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="cc16e-149">Para crear un nuevo uso de RTC en una sesión de PowerShell remota en Skype Empresarial Online, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cc16e-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="cc16e-150">Para obtener información adicional, [vea Set-CsOnlinePstnUsage.](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)</span><span class="sxs-lookup"><span data-stu-id="cc16e-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="cc16e-151">Para crear una nueva ruta de voz, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc16e-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="cc16e-152">Al definir una nueva ruta de voz para su organización, especifique una o varias de las puertas de enlace RTC en línea definidas para su organización durante la configuración del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="cc16e-153">El patrón de números especifica qué llamadas se enrutarán a través de la lista especificada de puertas de enlace en función del número de teléfono de destino de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cc16e-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="cc16e-154">En el ejemplo anterior, las llamadas a cualquier destino del mundo coincidirán con la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="cc16e-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="cc16e-155">Si desea restringir los números de teléfono que se pueden marcar desde las reuniones de usuarios de su organización, puede cambiar el patrón de números para que la ruta de voz coincida solo con los patrones de número de los destinos permitidos.</span><span class="sxs-lookup"><span data-stu-id="cc16e-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="cc16e-156">Tenga en cuenta que si no hay rutas de voz que coincidan con el patrón de número del número de teléfono de destino de una llamada determinada, la llamada no se enruta.</span><span class="sxs-lookup"><span data-stu-id="cc16e-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="cc16e-157">Para obtener información adicional, [vea New-CsOnlineVoiceRoute.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)</span><span class="sxs-lookup"><span data-stu-id="cc16e-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="cc16e-158">Para crear una nueva directiva de enrutamiento de voz, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc16e-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="cc16e-159">Si se definen varios usos de RTC en la directiva de enrutamiento de voz, se evaluarán en el orden en que se definen.</span><span class="sxs-lookup"><span data-stu-id="cc16e-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="cc16e-160">Se recomienda que los usos de RTC se definan en el orden más específico de los más genéricos en términos de los patrones de número de las rutas de voz asociadas con los usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="cc16e-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="cc16e-161">Por ejemplo, si se definió un uso de RTC para enrutar llamadas a Estados Unidos y se definió otro uso de RTC para enrutar llamadas a cualquier otra ubicación del mundo, el uso de RTC para llamadas a Estados Unidos debería aparecer en la directiva de enrutamiento de voz antes del uso de RTC para enrutar las llamadas a cualquier otra ubicación del mundo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="cc16e-162">Para obtener más información, [consulte New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="cc16e-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="cc16e-163">Para asignar la nueva ruta de voz a la directiva global de enrutamiento de voz de su organización, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc16e-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="cc16e-164">Para obtener más información, [consulte Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="cc16e-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="cc16e-165">Una vez definida la directiva global de enrutamiento de voz, las llamadas salientes realizadas desde reuniones organizadas por los usuarios de su organización se evaluarán en función de las rutas de voz asociadas a los usos de RTC de la directiva global de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="cc16e-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="cc16e-166">Las llamadas salientes se enrutarán según la primera ruta de voz que coincida con el patrón de número del número de teléfono marcado.</span><span class="sxs-lookup"><span data-stu-id="cc16e-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="cc16e-167">Paso 5: Asignar audioconferencia con enrutamiento directo para licencias GCC High o DoD a los usuarios</span><span class="sxs-lookup"><span data-stu-id="cc16e-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="cc16e-168">Para asignar audioconferencias con enrutamiento directo para licencias GCC High o DoD a un usuario, consulte [Asignar licencias a usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="cc16e-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="cc16e-169">Paso 6: (Opcional) Ver una lista de números de Audioconferencia en Teams</span><span class="sxs-lookup"><span data-stu-id="cc16e-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="cc16e-170">Para ver la lista de números de Audioconferencia de su organización, vaya a Ver una lista de números de [Audioconferencia en Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="cc16e-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="cc16e-171">Paso 7: (Opcional) Establecer los idiomas del operador automático para los números de acceso telefónico de audioconferencia de su organización</span><span class="sxs-lookup"><span data-stu-id="cc16e-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="cc16e-172">Para cambiar los idiomas de los números de acceso telefónico local de Audioconferencia de su organización, vea Establecer los idiomas del operador automático para [Audioconferencia en Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="cc16e-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="cc16e-173">Paso 8: (Opcional) Cambiar la configuración del puente de audioconferencia de su organización</span><span class="sxs-lookup"><span data-stu-id="cc16e-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="cc16e-174">Para cambiar la configuración del puente de audioconferencia de su organización, vea Cambiar la configuración de un puente de [Audioconferencia.](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="cc16e-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="cc16e-175">Paso 9: (opcional) Establecer los números de teléfono incluidos en las invitaciones de reunión de los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="cc16e-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="cc16e-176">Para cambiar el conjunto de números de teléfono que se incluyen en las invitaciones de reunión de los usuarios es su organización, consulte Establecer los números de teléfono incluidos en las invitaciones [en Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="cc16e-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="cc16e-177">Capacidades de Audioconferencia no admitidas en Audioconferencia con enrutamiento directo para GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="cc16e-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="cc16e-178">Las siguientes son funciones de Audioconferencia que no son compatibles con Audioconferencia con enrutamiento directo para GCC High y DoD:</span><span class="sxs-lookup"><span data-stu-id="cc16e-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="cc16e-179">Notificaciones de entrada y salida con la grabación de nombres.</span><span class="sxs-lookup"><span data-stu-id="cc16e-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="cc16e-180">Para las audioconferencias con enrutamiento directo, las notificaciones de entrada y salida se reproducen en la reunión como tonos.</span><span class="sxs-lookup"><span data-stu-id="cc16e-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="cc16e-181">Directivas de restricción de llamadas salientes para Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="cc16e-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="cc16e-182">Los controles de nivel de usuario para restringir las llamadas salientes no se aplican a las llamadas salientes de reunión enrutadas a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="cc16e-183">Deshabilite el uso de números gratuitos para el organizador específico de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="cc16e-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="cc16e-184">Los controles a nivel de usuario para restringir el uso de números gratuitos para unirse a las reuniones de su organización no se aplican a las llamadas enrutadas a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="cc16e-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="cc16e-185">Enviar correos electrónicos de notificación a los usuarios cuando cambie su configuración.</span><span class="sxs-lookup"><span data-stu-id="cc16e-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="cc16e-186">Los correos electrónicos de notificación de Audioconferencia no son compatibles con Audioconferencia con enrutamiento directo para GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="cc16e-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>

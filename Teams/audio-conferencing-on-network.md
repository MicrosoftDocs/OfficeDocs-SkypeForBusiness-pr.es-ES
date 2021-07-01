---
title: Conferencias en red para audioconferencias
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: A continuación se describen las conferencias en red para audioconferencias.
ms.openlocfilehash: b7851bd2457debe8ee0de3144e24a15edb521222
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230567"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="98fe9-103">Conferencias en red para audioconferencias</span><span class="sxs-lookup"><span data-stu-id="98fe9-103">On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="98fe9-104">Las conferencias en red permiten a las organizaciones enviar llamadas de audioconferencia entrantes y salientes a números de acceso telefónico local de Microsoft mediante enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="98fe9-104">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="98fe9-105">Esta capacidad no está pensada para extender la compatibilidad de audioconferencias a números de acceso telefónico local de terceros.</span><span class="sxs-lookup"><span data-stu-id="98fe9-105">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="98fe9-106">Las conferencias en red no son compatibles si se usan para enrutar las llamadas entrantes al servicio de audioconferencia a través de números de teléfono de acceso telefónico local de terceros o llamadas salientes a la RTC desde el puente de audioconferencia de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98fe9-106">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="98fe9-107">En este artículo se describen los requisitos previos y los pasos de configuración necesarios para habilitar las conferencias en red para su organización.</span><span class="sxs-lookup"><span data-stu-id="98fe9-107">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98fe9-108">Las conferencias en red NO deben implementarse con ningún equipo de telefonía en india.</span><span class="sxs-lookup"><span data-stu-id="98fe9-108">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="98fe9-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="98fe9-109">Prerequisites</span></span>

<span data-ttu-id="98fe9-110">Antes de configurar conferencias en red, asegúrese de que su organización cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="98fe9-110">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="98fe9-111">Asegúrese de que todos los usuarios de su organización que estén habilitados o que estén habilitados para las audioconferencias usen Teams para todas las reuniones.</span><span class="sxs-lookup"><span data-stu-id="98fe9-111">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="98fe9-112">El enrutamiento de las llamadas de audioconferencia entrantes y salientes a través de conferencias en red solo es compatible con Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="98fe9-112">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="98fe9-113">Asigne licencias de conferencias de audio a todos los usuarios que usen conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="98fe9-113">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="98fe9-114">Configure el servicio de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="98fe9-114">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="98fe9-115">Para obtener más información, vea [Configurar audioconferencias para Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="98fe9-115">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="98fe9-116">Configure el controlador de borde de sesión (SBC) para enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="98fe9-116">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="98fe9-117">Para obtener más información, vea [Planear enrutamiento directo](direct-routing-plan.md) y Configurar enrutamiento [directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="98fe9-117">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="98fe9-118">Si está configurando enrutamiento directo solo para los fines de las audioconferencias, solo necesita completar "Paso 1: Conectar su SBC" para conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="98fe9-118">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="98fe9-119">Habilitar el enrutamiento de llamadas de acceso telefónico local a Las audioconferencias de Microsoft a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="98fe9-119">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="98fe9-120">Para enrutar las llamadas de acceso telefónico local realizadas por los usuarios locales al servicio de audioconferencia a través del enrutamiento directo, debe configurar reglas de enrutamiento adecuadas para los SBC y las Exchange(s) de sucursales privadas (PBX).</span><span class="sxs-lookup"><span data-stu-id="98fe9-120">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="98fe9-121">Debe configurar el equipamiento de telefonía de sus sitios para enrutar las llamadas a cualquier número de servicio del puente de conferencia de su organización a través de un tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="98fe9-121">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="98fe9-122">Puede encontrar los números de servicio en el centro de administración de Teams en Reuniones **-> Puentes** de conferencia o mediante el cmdlet de PowerShell de Skype Empresarial Online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="98fe9-122">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="98fe9-123">Para obtener información adicional, vea una lista de números [de audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="98fe9-123">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="98fe9-124">Esta característica no está disponible para los usuarios con la licencia de audioconferencia de pago por minuto.</span><span class="sxs-lookup"><span data-stu-id="98fe9-124">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="98fe9-125">Habilitar el enrutamiento de llamadas Teams llamadas de llamada de reunión mediante enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="98fe9-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="98fe9-126">Teams llamadas de acceso telefónico local de la reunión se inician desde una reunión de su organización a números RTC, incluidas las llamadas de llamada y las llamadas para que los nuevos participantes se unan a una reunión.</span><span class="sxs-lookup"><span data-stu-id="98fe9-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="98fe9-127">Para habilitar Teams de acceso telefónico local de una reunión mediante enrutamiento directo a usuarios en red, debe crear y asignar una directiva de enrutamiento de audioconferencia denominada "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="98fe9-127">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="98fe9-128">La directiva OnlineAudioConferencingRoutingPolicy equivale a CsOnlineVoiceRoutingPolicy para llamadas RTC 1:1 a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="98fe9-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="98fe9-129">La directiva OnlineAudioConferencingRoutingPolicy se puede administrar mediante los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="98fe9-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="98fe9-130">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="98fe9-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="98fe9-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="98fe9-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="98fe9-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="98fe9-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="98fe9-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="98fe9-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="98fe9-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="98fe9-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="98fe9-135">Para obtener más información sobre el enrutamiento para enrutamiento directo, vea [Configurar enrutamiento de voz para enrutamiento directo.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="98fe9-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="98fe9-136">Para habilitar el enrutamiento de llamadas de llamada de reunión a través de Enrutamiento directo, debe:</span><span class="sxs-lookup"><span data-stu-id="98fe9-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="98fe9-137">Configurar directivas de enrutamiento de audioconferencias</span><span class="sxs-lookup"><span data-stu-id="98fe9-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="98fe9-138">Configurar el enrutamiento en el equipo de telefonía de su organización</span><span class="sxs-lookup"><span data-stu-id="98fe9-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="98fe9-139">(Opcional) Configurar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="98fe9-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="98fe9-140">Las llamadas de llamada de Teams reuniones vienen del número de servicio predeterminado en el puente de conferencia.</span><span class="sxs-lookup"><span data-stu-id="98fe9-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="98fe9-141">Para obtener información adicional sobre el número de servicio predeterminado de su puente de audioconferencia, vea Cambiar los números de teléfono en el puente [de audioconferencia.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="98fe9-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="98fe9-142">Configurar directivas de enrutamiento de audioconferencias</span><span class="sxs-lookup"><span data-stu-id="98fe9-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="98fe9-143">La directiva de enrutamiento de audioconferencia OnlineAudioConferencingRoutingPolicy determina qué llamadas de acceso telefónico saliente de reunión se enruta a los troncos de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="98fe9-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="98fe9-144">Si está familiarizado con la directiva CsOnlineVoiceRoutingPolicy, esta directiva funciona de forma muy similar.</span><span class="sxs-lookup"><span data-stu-id="98fe9-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="98fe9-145">Para configurar las directivas de enrutamiento de audioconferencias, se necesitan los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="98fe9-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="98fe9-146">Crear usos de RTC</span><span class="sxs-lookup"><span data-stu-id="98fe9-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="98fe9-147">Configurar rutas de voz</span><span class="sxs-lookup"><span data-stu-id="98fe9-147">Configure voice routes</span></span>
3.  <span data-ttu-id="98fe9-148">Crear directivas de enrutamiento de voz de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="98fe9-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="98fe9-149">Asignar una directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="98fe9-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="98fe9-150">Crear usos de RTC</span><span class="sxs-lookup"><span data-stu-id="98fe9-150">Create PSTN usages</span></span>

<span data-ttu-id="98fe9-151">Los usos RTC son colecciones de rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="98fe9-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="98fe9-152">Cuando se inicia una llamada de acceso telefónico local desde la reunión de un organizador determinado, las rutas de voz se usarán para determinar la ruta de enrutamiento de la llamada en función de los usos RTC asociados al usuario a través de la directiva de enrutamiento de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="98fe9-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="98fe9-153">Puede crear un uso rtc mediante el cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="98fe9-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="98fe9-154">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98fe9-154">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="98fe9-155">Configurar rutas de voz</span><span class="sxs-lookup"><span data-stu-id="98fe9-155">Configure voice routes</span></span>

<span data-ttu-id="98fe9-156">Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada en función del número de teléfono que se marca desde una Teams reunión.</span><span class="sxs-lookup"><span data-stu-id="98fe9-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="98fe9-157">Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada determinada haciendo coincidir el número de teléfono marcado desde una reunión de Teams con un patrón regex.</span><span class="sxs-lookup"><span data-stu-id="98fe9-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="98fe9-158">Al crear una ruta de voz, la ruta debe estar asociada a uno o varios usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="98fe9-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="98fe9-159">Puede crear una ruta de voz y definir el regex y las puertas de enlace que se asociarán a la ruta de voz con el cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="98fe9-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="98fe9-160">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98fe9-160">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="98fe9-161">Crear directivas de enrutamiento de voz de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="98fe9-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="98fe9-162">Las directivas de enrutamiento de voz de audioconferencia determinan las posibles rutas que se pueden usar para enrutar una llamada procedente de las reuniones de un organizador en función del número de teléfono de destino de la llamada de acceso telefónico local de la reunión.</span><span class="sxs-lookup"><span data-stu-id="98fe9-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="98fe9-163">Las directivas de enrutamiento de voz de audioconferencia están asociadas a uno o varios usos de RTC, que a su vez determinan las posibles rutas que se van a intentar usar para las llamadas de acceso telefónico local de reunión de los organizadores asociados a la directiva.</span><span class="sxs-lookup"><span data-stu-id="98fe9-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="98fe9-164">Puede crear una directiva de enrutamiento de voz de audioconferencia mediante el cmdlet "New- CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="98fe9-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="98fe9-165">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98fe9-165">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="98fe9-166">Una vez asignada la directiva a un usuario y cuando se inicia una llamada de acceso telefónico local desde una de las reuniones del usuario, se evaluarán las rutas de voz en los usos rtc asociados al organizador a través de la directiva de enrutamiento de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="98fe9-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="98fe9-167">Si el destino de la llamada de acceso telefónico local de la reunión coincide con un regex en una de las rutas de voz asociadas al organizador, la llamada de acceso telefónico local de la reunión se dirigirá a la puerta de enlace RTC definida en la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="98fe9-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="98fe9-168">Si el destino de la llamada de salida de reunión no coincide con ninguna de las rutas de voz asociadas al organizador, Microsoft dirigirá la llamada de llamada de salida de la reunión.</span><span class="sxs-lookup"><span data-stu-id="98fe9-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="98fe9-169">Asignar una directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="98fe9-169">Assign a policy to your users</span></span>

<span data-ttu-id="98fe9-170">Una vez definidas las directivas de enrutamiento de audioconferencias, ahora puede asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="98fe9-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="98fe9-171">Una vez asignadas las directivas, se evaluarán las llamadas de acceso telefónico local de la reunión para determinar su ruta de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="98fe9-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="98fe9-172">Las directivas de enrutamiento de audioconferencia siempre se evalúan en función del organizador de la reunión, independientemente del usuario de la reunión que inicia una llamada de acceso telefónico local de la reunión.</span><span class="sxs-lookup"><span data-stu-id="98fe9-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="98fe9-173">Puede asignar una directiva de enrutamiento de voz de audioconferencia a un usuario mediante el cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="98fe9-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="98fe9-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98fe9-174">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="98fe9-175">Configurar el enrutamiento en el equipo de telefonía de su organización</span><span class="sxs-lookup"><span data-stu-id="98fe9-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="98fe9-176">En el equipo de telefonía de su organización, debe asegurarse de que las llamadas de acceso telefónico local de la reunión enrutadas a través del enrutamiento directo se enrutan al destino previsto en la red.</span><span class="sxs-lookup"><span data-stu-id="98fe9-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="98fe9-177">(Opcional) Configurar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="98fe9-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="98fe9-178">Un plan de marcado es un conjunto de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (normalmente, E.164) para fines de autorización de llamadas y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="98fe9-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="98fe9-179">De forma predeterminada, Teams usuarios pueden llamar a números RTC en formato E.164, es decir, + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="98fe9-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="98fe9-180">Sin embargo, los planes de marcado se pueden usar para permitir a los usuarios marcar números de teléfono en otros formatos, por ejemplo, extensiones de 4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="98fe9-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="98fe9-181">Si desea habilitar la marcación basada en extensiones a través de conferencias en red, puede configurar los planes de marcado para que coincidan con el patrón de marcado de extensión con los intervalos de número de teléfono del número de teléfono de su organización.</span><span class="sxs-lookup"><span data-stu-id="98fe9-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="98fe9-182">Para configurar planes de marcado, vea [Crear y administrar planes de marcado.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="98fe9-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="98fe9-183">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="98fe9-183">Related topics</span></span>



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
description: A continuación se describen las funciones De vista previa abierta para audioconferencias en red.
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637842"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="19437-103">Abrir vista previa de conferencias en red para audioconferencias</span><span class="sxs-lookup"><span data-stu-id="19437-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="19437-104">La vista previa abierta de conferencias en red está disponible para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="19437-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="19437-105">Las conferencias en red permiten a las organizaciones enviar llamadas de audioconferencia entrantes y salientes a números de acceso telefónico local de Microsoft mediante enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="19437-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="19437-106">Esta capacidad no está pensada para extender la compatibilidad de audioconferencias a números de acceso telefónico local de terceros.</span><span class="sxs-lookup"><span data-stu-id="19437-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="19437-107">Las conferencias en red no son compatibles si se usan para enrutar las llamadas entrantes al servicio de audioconferencia a través de números de teléfono de acceso telefónico local de terceros o llamadas salientes a la RTC desde el puente de audioconferencia de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19437-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="19437-108">En este artículo se describen los requisitos previos y los pasos de configuración necesarios para habilitar las conferencias en red para su organización.</span><span class="sxs-lookup"><span data-stu-id="19437-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19437-109">Las conferencias en red NO deben implementarse con ningún equipo de telefonía en india.</span><span class="sxs-lookup"><span data-stu-id="19437-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="19437-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="19437-110">Prerequisites</span></span>

<span data-ttu-id="19437-111">Antes de configurar conferencias en red, asegúrese de que su organización cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="19437-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="19437-112">Asegúrese de que todos los usuarios de su organización habilitados o habilitados para las audioconferencias usen Teams para todas las reuniones.</span><span class="sxs-lookup"><span data-stu-id="19437-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="19437-113">El enrutamiento de las llamadas de audioconferencia entrantes y salientes a través de conferencias en red solo es compatible con las reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="19437-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="19437-114">Asigne licencias de conferencias de audio a todos los usuarios que usen conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="19437-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="19437-115">Configure el servicio de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="19437-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="19437-116">Para obtener más información, vea [Configurar audioconferencias para Microsoft Teams.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="19437-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="19437-117">Configure el controlador de borde de sesión (SBC) para enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="19437-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="19437-118">Para obtener más información, vea [Planear enrutamiento directo](direct-routing-plan.md) y Configurar enrutamiento [directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="19437-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="19437-119">Si está configurando enrutamiento directo solo para los fines de las audioconferencias, solo necesita completar "Paso 1: Conectar su SBC" para conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="19437-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="19437-120">Habilitar el enrutamiento de llamadas de acceso telefónico local a Las audioconferencias de Microsoft a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="19437-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="19437-121">Para enrutar las llamadas de acceso telefónico local realizadas por los usuarios locales al servicio de audioconferencia a través del enrutamiento directo, debe configurar reglas de enrutamiento adecuadas para los SBC y los intercambios de sucursales privados (PBX).</span><span class="sxs-lookup"><span data-stu-id="19437-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="19437-122">Debe configurar el equipamiento de telefonía de sus sitios para enrutar las llamadas a cualquier número de servicio del puente de conferencia de su organización a través de un tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="19437-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="19437-123">Puede encontrar los números de servicio en el Centro de administración de Teams en Reuniones **-> Puentes** de conferencia o mediante el cmdlet de PowerShell de Skype Empresarial Online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="19437-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="19437-124">Para obtener información adicional, vea una lista de números [de audioconferencia en Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="19437-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="19437-125">Esta característica no está disponible para los usuarios con la licencia de audioconferencia de pago por minuto.</span><span class="sxs-lookup"><span data-stu-id="19437-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="19437-126">Habilitar el enrutamiento de llamadas de llamada de reunión de Teams a través de Enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="19437-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="19437-127">Las llamadas de acceso telefónico de reunión de Teams se inician desde una reunión de su organización a números RTC, incluidas las llamadas de llamada y las llamadas para llevar a nuevos participantes a una reunión.</span><span class="sxs-lookup"><span data-stu-id="19437-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="19437-128">Para habilitar el enrutamiento de acceso telefónico de reunión de Teams a través del enrutamiento directo a usuarios en red, debe crear y asignar una directiva de enrutamiento de audioconferencia denominada "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="19437-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="19437-129">La directiva OnlineAudioConferencingRoutingPolicy equivale a CsOnlineVoiceRoutingPolicy para llamadas RTC 1:1 a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="19437-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="19437-130">La directiva OnlineAudioConferencingRoutingPolicy se puede administrar mediante los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="19437-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="19437-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="19437-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="19437-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="19437-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="19437-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="19437-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="19437-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="19437-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="19437-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="19437-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="19437-136">Para obtener más información sobre el enrutamiento para enrutamiento directo, vea [Configurar enrutamiento de voz para enrutamiento directo.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="19437-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="19437-137">Para habilitar el enrutamiento de llamadas de llamada de reunión a través de Enrutamiento directo, debe:</span><span class="sxs-lookup"><span data-stu-id="19437-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="19437-138">Configurar directivas de enrutamiento de audioconferencias</span><span class="sxs-lookup"><span data-stu-id="19437-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="19437-139">Configurar el enrutamiento en el equipo de telefonía de su organización</span><span class="sxs-lookup"><span data-stu-id="19437-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="19437-140">(Opcional) Configurar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="19437-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="19437-141">Las llamadas de llamada de las reuniones de Teams vienen del número de servicio predeterminado en el puente de conferencia.</span><span class="sxs-lookup"><span data-stu-id="19437-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="19437-142">Para obtener información adicional sobre el número de servicio predeterminado de su puente de audioconferencia, vea Cambiar los números de teléfono en el puente [de audioconferencia.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="19437-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="19437-143">Configurar directivas de enrutamiento de audioconferencias</span><span class="sxs-lookup"><span data-stu-id="19437-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="19437-144">La directiva de enrutamiento de audioconferencia OnlineAudioConferencingRoutingPolicy determina qué llamadas de acceso telefónico saliente de reunión se enruta a los troncos de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="19437-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="19437-145">Si está familiarizado con la directiva CsOnlineVoiceRoutingPolicy, esta directiva funciona de forma muy similar.</span><span class="sxs-lookup"><span data-stu-id="19437-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="19437-146">Para configurar las directivas de enrutamiento de audioconferencias, se necesitan los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="19437-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="19437-147">Crear usos de RTC</span><span class="sxs-lookup"><span data-stu-id="19437-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="19437-148">Configurar rutas de voz</span><span class="sxs-lookup"><span data-stu-id="19437-148">Configure voice routes</span></span>
3.  <span data-ttu-id="19437-149">Crear directivas de enrutamiento de voz de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="19437-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="19437-150">Asignar una directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="19437-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="19437-151">Crear usos de RTC</span><span class="sxs-lookup"><span data-stu-id="19437-151">Create PSTN usages</span></span>

<span data-ttu-id="19437-152">Los usos RTC son colecciones de rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="19437-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="19437-153">Cuando se inicia una llamada de acceso telefónico local desde la reunión de un organizador determinado, las rutas de voz se usarán para determinar la ruta de enrutamiento de la llamada en función de los usos RTC asociados al usuario a través de la directiva de enrutamiento de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="19437-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="19437-154">Puede crear un uso rtc mediante el cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="19437-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="19437-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19437-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="19437-156">Configurar rutas de voz</span><span class="sxs-lookup"><span data-stu-id="19437-156">Configure voice routes</span></span>

<span data-ttu-id="19437-157">Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada en función del número de teléfono marcado desde una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="19437-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="19437-158">Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada determinada haciendo coincidir el número de teléfono marcado desde una reunión de Teams con un patrón regex.</span><span class="sxs-lookup"><span data-stu-id="19437-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="19437-159">Al crear una ruta de voz, la ruta debe estar asociada a uno o varios usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="19437-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="19437-160">Puede crear una ruta de voz y definir el regex y las puertas de enlace que se asociarán a la ruta de voz con el cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="19437-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="19437-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19437-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="19437-162">Crear directivas de enrutamiento de voz de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="19437-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="19437-163">Las directivas de enrutamiento de voz de audioconferencia determinan las posibles rutas que se pueden usar para enrutar una llamada procedente de las reuniones de un organizador en función del número de teléfono de destino de la llamada de acceso telefónico local de la reunión.</span><span class="sxs-lookup"><span data-stu-id="19437-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="19437-164">Las directivas de enrutamiento de voz de audioconferencia están asociadas a uno o varios usos de RTC, que a su vez determinan las posibles rutas que se van a intentar usar para las llamadas de acceso telefónico local de reunión de los organizadores asociados a la directiva.</span><span class="sxs-lookup"><span data-stu-id="19437-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="19437-165">Puede crear una directiva de enrutamiento de voz de audioconferencia mediante el cmdlet "New- CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="19437-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="19437-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19437-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="19437-167">Una vez asignada la directiva a un usuario y cuando se inicia una llamada de acceso telefónico local desde una de las reuniones del usuario, se evaluarán las rutas de voz en los usos rtc asociados al organizador a través de la directiva de enrutamiento de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="19437-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="19437-168">Si el destino de la llamada de acceso telefónico local de la reunión coincide con un regex en una de las rutas de voz asociadas al organizador, la llamada de acceso telefónico local de la reunión se dirigirá a la puerta de enlace RTC definida en la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="19437-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="19437-169">Si el destino de la llamada de salida de reunión no coincide con ninguna de las rutas de voz asociadas al organizador, Microsoft dirigirá la llamada de llamada de salida de la reunión.</span><span class="sxs-lookup"><span data-stu-id="19437-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="19437-170">Asignar una directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="19437-170">Assign a policy to your users</span></span>

<span data-ttu-id="19437-171">Una vez definidas las directivas de enrutamiento de audioconferencias, ahora puede asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="19437-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="19437-172">Una vez asignadas las directivas, se evaluarán las llamadas de acceso telefónico local de la reunión para determinar su ruta de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="19437-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="19437-173">Las directivas de enrutamiento de audioconferencia siempre se evalúan en función del organizador de la reunión, independientemente del usuario de la reunión que inicia una llamada de acceso telefónico local de la reunión.</span><span class="sxs-lookup"><span data-stu-id="19437-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="19437-174">Puede asignar una directiva de enrutamiento de voz de audioconferencia a un usuario mediante el cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="19437-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="19437-175">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19437-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="19437-176">Configurar el enrutamiento en el equipo de telefonía de su organización</span><span class="sxs-lookup"><span data-stu-id="19437-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="19437-177">En el equipo de telefonía de su organización, debe asegurarse de que las llamadas de acceso telefónico local de la reunión enrutadas a través del enrutamiento directo se enrutan al destino previsto en la red.</span><span class="sxs-lookup"><span data-stu-id="19437-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="19437-178">(Opcional) Configurar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="19437-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="19437-179">Un plan de marcado es un conjunto de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (normalmente, E.164) para fines de autorización de llamadas y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="19437-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="19437-180">De forma predeterminada, los usuarios de Teams pueden llamar a números RTC en formato E.164, es decir, + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="19437-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="19437-181">Sin embargo, los planes de marcado se pueden usar para permitir a los usuarios marcar números de teléfono en otros formatos, por ejemplo, extensiones de 4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="19437-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="19437-182">Si desea habilitar la marcación basada en extensiones a través de conferencias en red, puede configurar los planes de marcado para que coincidan con el patrón de marcado de extensión con los intervalos de número de teléfono del número de teléfono de su organización.</span><span class="sxs-lookup"><span data-stu-id="19437-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="19437-183">Para configurar planes de marcado, vea [Crear y administrar planes de marcado.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="19437-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="19437-184">Problemas conocidos en Open Preview</span><span class="sxs-lookup"><span data-stu-id="19437-184">Known issues in Open Preview</span></span>

<span data-ttu-id="19437-185">A continuación se muestra una lista de los problemas conocidos que están presentes actualmente en la versión de Open Preview de las conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="19437-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="19437-186">Microsoft está trabajando para solucionar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="19437-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="19437-187">Problema</span><span class="sxs-lookup"><span data-stu-id="19437-187">Issue</span></span> | <span data-ttu-id="19437-188">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="19437-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="19437-189">Las llamadas de acceso telefónico local con identificadores de llamadas anónimos u ocultos que se enruta a través de conferencias en red no se pueden conectar a la reunión.</span><span class="sxs-lookup"><span data-stu-id="19437-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="19437-190">Si es posible, establezca una configuración en su PBX o SBC para enviar siempre un identificador de llamada para las llamadas enrutadas a través de conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="19437-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="19437-191">En algunos casos, el mensaje de bienvenida que se reproduce para los usuarios al llamar al servicio ("Bienvenido al servicio de audioconferencia...") se trunca y los usuarios no escuchan la palabra "Bienvenido".</span><span class="sxs-lookup"><span data-stu-id="19437-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="19437-192">No hay soluciones alternativas para este problema en este momento.</span><span class="sxs-lookup"><span data-stu-id="19437-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="19437-193">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="19437-193">Related topics</span></span>



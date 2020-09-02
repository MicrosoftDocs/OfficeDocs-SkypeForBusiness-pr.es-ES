---
title: Conferencias en red para conferencias de audio
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: A continuación se describe la funcionalidad de Open Preview para las conferencias de audio en red.
ms.openlocfilehash: 3b33c67cc79f79d36cf2a11213dc934103b026fb
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321817"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="2542d-103">Abrir vista previa de conferencias en red para conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="2542d-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="2542d-104">La vista previa abierta de las conferencias en red está disponible para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="2542d-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="2542d-105">Conferencias en red permite a las organizaciones enviar llamadas de voz de audio entrantes y salientes a números de acceso telefónico de Microsoft mediante enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2542d-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="2542d-106">Esta funcionalidad no está pensada para extender el soporte técnico de las audioconferencias a los números de acceso telefónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="2542d-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="2542d-107">Las conferencias en red no son compatibles si se usa para enrutar llamadas entrantes al servicio de audioconferencia a través de números de teléfono de acceso telefónico local de terceros.</span><span class="sxs-lookup"><span data-stu-id="2542d-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="2542d-108">En este artículo se describen los requisitos previos y los pasos de configuración necesarios para habilitar las conferencias en la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="2542d-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2542d-109">Las conferencias en red no deben implementarse con ningún equipo de telefonía en la India.</span><span class="sxs-lookup"><span data-stu-id="2542d-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="2542d-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2542d-110">Prerequisites</span></span>

<span data-ttu-id="2542d-111">Antes de configurar las conferencias en red, asegúrese de que su organización cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="2542d-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="2542d-112">Asegúrese de que todos los usuarios de su organización que estén habilitados o que se habilitarán para las conferencias de audio están en el modo solo de Teams.</span><span class="sxs-lookup"><span data-stu-id="2542d-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are in Teams Only mode.</span></span> <span data-ttu-id="2542d-113">El enrutamiento de llamadas entrantes y salientes de conferencias de audio a través de conferencias en red solo es compatible con las reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="2542d-113">The routing of inbound and outboud Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="2542d-114">Asigne licencias de audioconferencia a todos los usuarios que vayan a usar conferencias en la red.</span><span class="sxs-lookup"><span data-stu-id="2542d-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="2542d-115">Configure el servicio audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="2542d-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="2542d-116">Para obtener más información, consulte [configurar audioconferencias para Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2542d-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="2542d-117">Configure el controlador de borde de sesión (SBC) para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2542d-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="2542d-118">Para obtener más información, consulte [planear el enrutamiento directo](direct-routing-plan.md) y [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="2542d-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="2542d-119">Si está configurando el enrutamiento directo solo para fines de audioconferencia, solo necesita completar el paso 1: conectar su SBC "para las conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="2542d-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="2542d-120">Habilitar el enrutamiento de llamadas de acceso telefónico para conferencias de audio de Microsoft a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2542d-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="2542d-121">Para enrutar las llamadas de acceso telefónico realizadas por los usuarios locales en el servicio de audioconferencia mediante enrutamiento directo, debe configurar las reglas de enrutamiento apropiadas para sus PBX y las Exchange (s) privadas (PBX).</span><span class="sxs-lookup"><span data-stu-id="2542d-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="2542d-122">Debe configurar el equipo de telefonía de sus sitios para que enrute las llamadas a cualquier número de servicio del puente de conferencia de su organización a través de un tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2542d-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="2542d-123">Puede encontrar los números de servicio en el centro de administración de Teams en **reuniones-> puentes de conferencia** o mediante el cmdlet de PowerShell de Skype empresarial online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="2542d-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="2542d-124">Para obtener más información, consulte una lista de [números de audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2542d-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>


## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="2542d-125">Habilitar el enrutamiento de las llamadas de llamada de reunión de los equipos mediante enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2542d-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="2542d-126">Los equipos que reúnen las llamadas de acceso telefónico se inician desde una reunión de su organización a números RTC, incluidas las llamadas y llamadas en persona, y las llamadas para incluir a nuevos participantes en una reunión.</span><span class="sxs-lookup"><span data-stu-id="2542d-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="2542d-127">Para habilitar a los equipos el enrutamiento de marcado saliente mediante enrutamiento directo, debe crear y asignar una directiva de enrutamiento de audioconferencia denominada "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="2542d-127">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="2542d-128">La Directiva OnlineAudioConferencingRoutingPolicy es equivalente a la CsOnlineVoiceRoutingPolicy para llamadas RTC de 1:1 a través de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2542d-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="2542d-129">La Directiva OnlineAudioConferencingRoutingPolicy se puede administrar con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2542d-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="2542d-130">Nuevo: CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="2542d-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="2542d-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="2542d-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="2542d-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="2542d-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="2542d-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="2542d-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="2542d-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="2542d-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="2542d-135">Para obtener más información sobre el enrutamiento para enrutamiento directo, consulte [configurar el enrutamiento de voz para enrutamiento directo](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="2542d-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="2542d-136">Para habilitar el enrutamiento de llamadas de acceso telefónico de la reunión a través del enrutamiento directo, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2542d-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="2542d-137">Configurar directivas de enrutamiento de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2542d-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="2542d-138">Configurar el enrutamiento en el equipo de telefonía de su organización</span><span class="sxs-lookup"><span data-stu-id="2542d-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="2542d-139">Faculta Configurar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="2542d-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="2542d-140">Las llamadas de acceso telefónico de las reuniones de Teams provienen del número de servicio predeterminado del puente de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2542d-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="2542d-141">Para obtener más información sobre el número de servicio predeterminado de su puente de audioconferencia, consulte [cambiar los números de teléfono en el puente de audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="2542d-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="2542d-142">Configurar directivas de enrutamiento de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2542d-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="2542d-143">La Directiva de enrutamiento de audioconferencia OnlineAudioConferencingRoutingPolicy determina qué llamadas de llamada salientes de la reunión se enrutan a troncos de enrutamiento directos.</span><span class="sxs-lookup"><span data-stu-id="2542d-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="2542d-144">Si está familiarizado con la Directiva CsOnlineVoiceRoutingPolicy, esta directiva funciona de manera muy similar.</span><span class="sxs-lookup"><span data-stu-id="2542d-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="2542d-145">Para configurar las directivas de enrutamiento de audioconferencia, debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2542d-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="2542d-146">Crear usos de RTC</span><span class="sxs-lookup"><span data-stu-id="2542d-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="2542d-147">Configurar rutas de voz</span><span class="sxs-lookup"><span data-stu-id="2542d-147">Configure voice routes</span></span>
3.  <span data-ttu-id="2542d-148">Crear directivas de enrutamiento de voz de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2542d-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="2542d-149">Asignar una directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2542d-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="2542d-150">Crear usos de RTC</span><span class="sxs-lookup"><span data-stu-id="2542d-150">Create PSTN usages</span></span>

<span data-ttu-id="2542d-151">Los usos de RTC son colecciones de rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="2542d-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="2542d-152">Cuando se inicia una llamada de acceso telefónico desde la reunión de un organizador determinado, las rutas de voz se usarán para determinar la ruta de enrutamiento de la llamada en función de los usos de RTC asociados al usuario a través de la Directiva de enrutamiento de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="2542d-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="2542d-153">Puede crear un uso de RTC mediante el cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="2542d-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="2542d-154">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2542d-154">For Example:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="2542d-155">Configurar rutas de voz</span><span class="sxs-lookup"><span data-stu-id="2542d-155">Configure voice routes</span></span>

<span data-ttu-id="2542d-156">Las rutas de voz determinan la puerta de enlace PSTN que debe usarse para enrutar una llamada según el número de teléfono que se marca desde una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="2542d-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="2542d-157">Las rutas de voz determinan la puerta de enlace PSTN que debe usarse para enrutar una llamada determinada haciendo coincidir el número de teléfono marcado desde una reunión de Teams con un patrón de Regex.</span><span class="sxs-lookup"><span data-stu-id="2542d-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="2542d-158">Al crear una ruta de voz, la ruta debe estar asociada a uno o varios usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="2542d-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="2542d-159">Puede crear una ruta de voz y definir los regex y las puertas de enlace que se van a asociar a la ruta de voz mediante el cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="2542d-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="2542d-160">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2542d-160">For Example:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="2542d-161">Crear directivas de enrutamiento de voz de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2542d-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="2542d-162">Las directivas de enrutamiento de voz de audioconferencia determinan las rutas posibles que se pueden usar para enrutar una llamada originada desde las reuniones de un organizador basándose en el número de teléfono objetivo de la llamada de llamada de salida de la reunión.</span><span class="sxs-lookup"><span data-stu-id="2542d-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="2542d-163">Las directivas de enrutamiento de voz de audioconferencia están asociadas a uno o más usos de RTC, que a su vez determinan las rutas posibles que se intentarán usar para las llamadas de acceso telefónico de la reunión de los organizadores asociados a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="2542d-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="2542d-164">Puede crear una directiva de enrutamiento de voz de audioconferencia con el cmdlet "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="2542d-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="2542d-165">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2542d-165">For Example:</span></span>

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2542d-166">Una vez que se ha asignado la Directiva a un usuario, y cuando se inicia una llamada de acceso telefónico de la reunión desde una de las reuniones del usuario, se evaluarán las rutas de voz de los usos de RTC asociados al organizador a través de la Directiva de enrutamiento de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="2542d-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="2542d-167">Si el destino de la llamada de llamada de salida de la reunión coincide con un regex en una de las rutas de voz asociadas al organizador, la llamada de acceso telefónico de reunión se redirigirá a la puerta de enlace RTC definida en la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="2542d-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="2542d-168">Si el destino de la llamada de aceptación de la reunión no coincide con ninguna de las rutas de voz asociadas al organizador, Microsoft redirigirá la llamada de llamada de salida de la reunión.</span><span class="sxs-lookup"><span data-stu-id="2542d-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="2542d-169">Asignar una directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2542d-169">Assign a policy to your users</span></span>

<span data-ttu-id="2542d-170">Una vez definidas las directivas de enrutamiento de audioconferencia, ahora puede asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2542d-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="2542d-171">Una vez que se les asignan las directivas, las llamadas de llamada salientes de la reunión se evaluarán para determinar su ruta de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2542d-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="2542d-172">Las directivas de enrutamiento de audioconferencia siempre se evalúan según el organizador de la reunión, independientemente del usuario de la reunión que inicia una llamada de acceso telefónico de la reunión.</span><span class="sxs-lookup"><span data-stu-id="2542d-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="2542d-173">Puede asignar una directiva de enrutamiento de voz de audioconferencia a un usuario mediante el cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="2542d-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="2542d-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2542d-174">For example:</span></span>

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="2542d-175">Configurar el enrutamiento en el equipo de telefonía de su organización</span><span class="sxs-lookup"><span data-stu-id="2542d-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="2542d-176">En el equipo de telefonía de su organización, debe asegurarse de que las llamadas de acceso telefónico de la reunión enrutadas a través del enrutamiento directo se enruten al destino previsto.</span><span class="sxs-lookup"><span data-stu-id="2542d-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="2542d-177">Faculta Configurar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="2542d-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="2542d-178">Un plan de marcado es un conjunto de reglas de normalización que convierten los números de teléfono marcados por un usuario individual en un formato alternativo (por lo general, E. 164) para fines de autorización de llamadas y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2542d-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="2542d-179">De forma predeterminada, los usuarios de Teams pueden llamar a números de RTC en formato E. 164, es decir, + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="2542d-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="2542d-180">Sin embargo, los planes de marcado se pueden usar para permitir a los usuarios marcar números de teléfono en otros formatos, por ejemplo, las extensiones de 4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="2542d-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="2542d-181">Si desea habilitar el marcado basado en extensión a través de conferencias en red, puede configurar planes de marcado para que coincidan con el patrón de marcado de números de teléfono del número de teléfono de su organización.</span><span class="sxs-lookup"><span data-stu-id="2542d-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="2542d-182">Para configurar planes de marcado, vea [crear y administrar planes de marcado](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="2542d-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="2542d-183">Problemas conocidos en abrir vista previa</span><span class="sxs-lookup"><span data-stu-id="2542d-183">Known issues in Open Preview</span></span>

<span data-ttu-id="2542d-184">A continuación se muestra una lista de los problemas conocidos que se encuentran actualmente en la versión preliminar abierta de conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="2542d-184">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="2542d-185">Microsoft está trabajando en resolver estos problemas.</span><span class="sxs-lookup"><span data-stu-id="2542d-185">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="2542d-186">Problema</span><span class="sxs-lookup"><span data-stu-id="2542d-186">Issue</span></span> | <span data-ttu-id="2542d-187">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="2542d-187">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="2542d-188">Las llamadas de acceso telefónico con identificadores de llamadas anónimos y ocultos que se enrutan a través de conferencias en red no se pueden conectar a la reunión.</span><span class="sxs-lookup"><span data-stu-id="2542d-188">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="2542d-189">Si es posible, establezca una configuración en su PBX o SBC para enviar siempre un identificador de llamada para llamadas enrutadas a través de conferencias en red.</span><span class="sxs-lookup"><span data-stu-id="2542d-189">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="2542d-190">En algunos casos, el mensaje de bienvenida que se reproduce a los usuarios al llamar al servicio ("Bienvenido al servicio de audioconferencias...") se trunca y los usuarios no escuchan la palabra "bienvenida".</span><span class="sxs-lookup"><span data-stu-id="2542d-190">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="2542d-191">Por el momento, no hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="2542d-191">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="2542d-192">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2542d-192">Related topics</span></span>



---
title: Audioconferencias con enrutamiento directo, GCCH y DoD
author: LanaChin
ms.author: v-lanac
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
description: Administrador puede aprender a usar las conferencias de audio con enrutamiento directo en entornos GCCH y DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17b928dc62cb6e4da0a88fd868ff0e599705d89a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610259"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a025c-103">Audioconferencia con enrutamiento directo para GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="a025c-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="a025c-104">Las conferencias de audio con enrutamiento directo para GCC High y DoD permiten a los participantes unirse a reuniones de Teams en su organización GCC High o DoD con un dispositivo telefónico.</span><span class="sxs-lookup"><span data-stu-id="a025c-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="a025c-105">Es posible que los participantes de la reunión prefieran usar un dispositivo telefónico para unirse a reuniones de Teams en escenarios, como cuando la conexión a Internet es limitada o cuando los usuarios viajan y no tienen acceso a los equipos.</span><span class="sxs-lookup"><span data-stu-id="a025c-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="a025c-106">Los participantes pueden elegir unirse a un número de teléfono de acceso telefónico local para su organización o hacer que la reunión llame a su dispositivo telefónico.</span><span class="sxs-lookup"><span data-stu-id="a025c-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="a025c-107">Con las videoconferencias con enrutamiento directo para GCC High y DoD, su organización usa números propios como números de teléfono de acceso telefónico local y todos los accesos a la reunión a los dispositivos telefónicos se enrutan a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="a025c-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="a025c-108">Para habilitar el servicio, las organizaciones necesitan configurar el enrutamiento directo y configurar los números de teléfono que se pueden usar como números de teléfono de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a025c-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="a025c-109">El requisito de usar el enrutamiento directo es diferente del servicio de audioconferencia ofrecido a organizaciones que no son de GCC y de alta calidad y no de DoD en los que Microsoft proporciona los números de teléfono de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a025c-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a025c-110">Implementar audioconferencias con enrutamiento directo para GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="a025c-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="a025c-111">Paso 1: obtener conferencias de audio con enrutamiento directo para las licencias de GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="a025c-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="a025c-112">Para usar audioconferencia en GCC High o DoD, su organización y los usuarios de su organización necesitan tener una conferencia de audio con una licencia de enrutamiento directo asignada.</span><span class="sxs-lookup"><span data-stu-id="a025c-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="a025c-113">Estas son las licencias que necesita para habilitar las conferencias de audio con enrutamiento directo para GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="a025c-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="a025c-114">GCC High: una licencia de multiinquilino de audioconferencias-GCC High tenant para su organización y Conferencia de audio-GCC: licencias altas para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="a025c-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="a025c-115">DoD: una licencia de conferencia de audio-espacio empresarial DoD para su organización y las licencias de audio y las licencias DoD de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a025c-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="a025c-116">Para habilitar el servicio, se necesita una licencia de inquilino y al menos una licencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="a025c-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="a025c-117">No puede habilitar el servicio solo con la licencia de inquilino o con licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="a025c-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="a025c-118">Para obtener licencias de servicio para su inquilino y los usuarios de su organización, póngase en contacto con el equipo de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="a025c-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a025c-119">Los usuarios no pueden habilitarse para las conferencias de audio con enrutamiento directo hasta que se configuran los números de teléfono de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a025c-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="a025c-120">Le recomendamos que no asigne conferencias de audio con enrutamiento directo para las licencias de GCC High o DoD a los usuarios hasta que configure los números de teléfono de acceso telefónico local, como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a025c-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="a025c-121">Paso 2: configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a025c-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="a025c-122">Para configurar el enrutamiento directo, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a025c-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="a025c-123">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a025c-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="a025c-124">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a025c-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="a025c-125">Cuando configure el enrutamiento directo, recuerde usar los FQDN y puertos de GCC altos o específicos de DoD que se describen en estos dos artículos.</span><span class="sxs-lookup"><span data-stu-id="a025c-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="a025c-126">Paso 3: configurar números de teléfono de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a025c-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="a025c-127">Los números de teléfono de acceso telefónico local son los números de teléfono que están asociados a su puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="a025c-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="a025c-128">Los participantes usan estos números para unirse a las reuniones programadas por los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="a025c-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="a025c-129">Estos números también se incluyen en las invitaciones a reuniones de los usuarios que programan las reuniones de su organización y en la página "buscar un número local".</span><span class="sxs-lookup"><span data-stu-id="a025c-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="a025c-130">Definir números de teléfono de servicio en su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="a025c-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="a025c-131">Puede usar el cmdlet de PowerShell New-csHybridTelephoneNumber para definir los números de teléfono de servicio de su inquilino que se pueden usar para enrutar llamadas al servicio de audioconferencia a través de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="a025c-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="a025c-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a025c-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="a025c-133">Asignar los números de teléfono de servicio al puente de audioconferencia de su organización</span><span class="sxs-lookup"><span data-stu-id="a025c-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="a025c-134">Puede asignar números de teléfono de servicio al puente de audioconferencia de su organización mediante el cmdlet de PowerShell Register-csOnlineDialInConferencingServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="a025c-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="a025c-135">Puede ver el identificador de su puente de audioconferencia con get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="a025c-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="a025c-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a025c-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="a025c-137">Paso 4: asignar audioconferencias con enrutamiento directo para las licencias de GCC High o DoD a los usuarios</span><span class="sxs-lookup"><span data-stu-id="a025c-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="a025c-138">Para asignar conferencias de audio con enrutamiento directo para las licencias GCC High o DoD para el usuario, consulte [Agregar usuarios de forma individual o en bloque](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).</span><span class="sxs-lookup"><span data-stu-id="a025c-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="a025c-139">Paso 5: (opcional) ver una lista de números de conferencias de audio en Teams</span><span class="sxs-lookup"><span data-stu-id="a025c-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="a025c-140">Para ver la lista de números de audioconferencia de su organización, vaya a [ver una lista de los números de audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a025c-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="a025c-141">Paso 6: (opcional) establecer los idiomas del operador automático para los números de acceso telefónico de las conferencias de audio de la organización</span><span class="sxs-lookup"><span data-stu-id="a025c-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="a025c-142">Para cambiar los idiomas de los números de acceso telefónico de las conferencias de audio de su organización, consulte [establecer los idiomas del operador automático para audioconferencia en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a025c-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="a025c-143">Paso 7: (opcional) cambiar la configuración del puente de audioconferencia de su organización</span><span class="sxs-lookup"><span data-stu-id="a025c-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="a025c-144">Para cambiar la configuración del puente de conferencias de audio de su organización, consulte [cambiar la configuración de un puente de audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="a025c-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="a025c-145">Paso 8: (opcional) establecer los números de teléfono incluidos en las invitaciones a reuniones de los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="a025c-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="a025c-146">Para cambiar el conjunto de números de teléfono que se incluyen en las invitaciones a reuniones de los usuarios es su organización, consulte [configurar los números de teléfono incluidos en los invitados en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="a025c-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a025c-147">Capacidades de audioconferencia no compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="a025c-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="a025c-148">Las siguientes son capacidades de audioconferencia que no son compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD:</span><span class="sxs-lookup"><span data-stu-id="a025c-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="a025c-149">Notificaciones de entrada y salida que usan la grabación de nombres.</span><span class="sxs-lookup"><span data-stu-id="a025c-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="a025c-150">Para las conferencias de audio con enrutamiento directo, las notificaciones de entrada y salida se reproducen como tonos en la reunión.</span><span class="sxs-lookup"><span data-stu-id="a025c-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="a025c-151">Directivas de restricciones de llamadas salientes para audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="a025c-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="a025c-152">Los controles de nivel de usuario para restringir las llamadas salientes no son aplicables a las llamadas de llamada salientes de las reuniones dirigidas por enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="a025c-152">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="a025c-153">Deshabilite el uso de números gratuitos para el organizador específico de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="a025c-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="a025c-154">Los controles de nivel de usuario para restringir el uso de números gratuitos para unirse a las reuniones de su organización no son aplicables a las llamadas enrutadas por enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="a025c-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="a025c-155">Envío de correos electrónicos de notificación a los usuarios cuando cambia la configuración.</span><span class="sxs-lookup"><span data-stu-id="a025c-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="a025c-156">Los correos electrónicos de notificación de audioconferencia no son compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="a025c-156">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>

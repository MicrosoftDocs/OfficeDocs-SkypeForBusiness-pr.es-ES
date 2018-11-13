---
title: Configurar para eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Aprenda los pasos para configurar live para los eventos de Microsoft Teams, incluida la preparación de su red, asignación de licencias, habilitar el evento en directo de programación para los usuarios y la configuración de un proveedor de red eCDN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296383"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a><span data-ttu-id="5ea1f-103">Configurar para eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ea1f-103">Set up for live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="5ea1f-104">Cuando se configura para eventos en directo, hay varios pasos que debe seguir:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-104">When you are setting up for live events, there are several steps that you must take:</span></span>

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a><span data-ttu-id="5ea1f-105">Paso 1: Configurar la red para eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ea1f-105">Step 1: Set up your network for live events in Microsoft Teams</span></span>
<span data-ttu-id="5ea1f-106">Los eventos de live de inicio rápido requieren para [Preparar la red de su organización para que los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-106">The quick start live events require you to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>  

## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="5ea1f-107">Paso 2: obtener licencias y asignarlas</span><span class="sxs-lookup"><span data-stu-id="5ea1f-107">Step 2: Get and assign licenses</span></span>
<span data-ttu-id="5ea1f-108">Asegúrese de que tiene asignaciones de licencia correcta para [quién puede crear y programar eventos en directo?](#who-can-create-and-schedule-live-events) y [quién puede ver los eventos en directo?](#who-can-watch-live-events).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-108">Ensure you have correct license assignments for [Who can create and schedule live events?](#who-can-create-and-schedule-live-events) and [Who can watch live events?](#who-can-watch-live-events).</span></span>

## <a name="step-3-enable-live-event-scheduling-for-users"></a><span data-ttu-id="5ea1f-109">Paso 3: Habilitar el evento en directo de programación para los usuarios</span><span class="sxs-lookup"><span data-stu-id="5ea1f-109">Step 3: Enable live event scheduling for users</span></span>
<span data-ttu-id="5ea1f-110">Programación de evento en directo está habilitada de forma predeterminada para los usuarios de los equipos, pero si desea que los usuarios programar eventos externos codificador existen pasos adicionales que debe realizar.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-110">Live event scheduling is enabled by default for Teams users but if you are wanting users to schedule external encoder events there are additional steps that you must do.</span></span>

### <a name="for-quick-start-events"></a><span data-ttu-id="5ea1f-111">Para los eventos de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="5ea1f-111">For quick start events</span></span>
<span data-ttu-id="5ea1f-112">Use la opción *AllowBroadcastScheduling* en **TeamsMeetingBroadcastPolicy** en los equipos de PowerShell para controlar si el usuario puede crear eventos en directo en los equipos o no.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-112">Use the setting *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in Teams PowerShell to control whether the user can create live events in Teams or not.</span></span> <span data-ttu-id="5ea1f-113">Encontrará más información acerca de cómo administrar TeamsMeetingBroadcastPolicy [aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-113">You can learn more about managing TeamsMeetingBroadcastPolicy [here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

 <span data-ttu-id="5ea1f-114">Si no ha asignado una directiva personalizada asignada a los usuarios, los usuarios obtendrá la directiva *Global* , que tiene la grabación habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-114">If you haven't assigned a custom policy assigned to the users, the users will get the *Global* policy, which has recording enabled by default.</span></span>

<span data-ttu-id="5ea1f-115">Compruebe que el parámetro *AllowBroadcastScheduling* se establece en *True*:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-115">Verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="5ea1f-116">A continuación, asigne al usuario a la directiva *Global* , ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-116">Then assign the user to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a><span data-ttu-id="5ea1f-117">Escenarios de usuario</span><span class="sxs-lookup"><span data-stu-id="5ea1f-117">User scenarios</span></span>
<span data-ttu-id="5ea1f-118">**Desea que todos los usuarios de su compañía para poder crear eventos en directo.**</span><span class="sxs-lookup"><span data-stu-id="5ea1f-118">**You want all users in your company to be able to create live events.**</span></span>

<span data-ttu-id="5ea1f-119">Si los usuarios tienen asignados la directiva *global* , ejecute y compruebe que *AllowBroadcastScheduling* \* está establecida en *True*:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-119">If users are assigned the *Glocal* policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="5ea1f-120">Si los usuarios se les asigna una directiva que no sea la directiva *Global* , ejecute lo siguiente y comprobación *- AllowBroadcastScheduling* se establece en *True*:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-120">If the users are assigned a policy other than the *Global* policy, run the following and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

<span data-ttu-id="5ea1f-121">**Desea que el evento en directo programación se va a 100% deshabilitado en toda la organización.**</span><span class="sxs-lookup"><span data-stu-id="5ea1f-121">**You want live event scheduling to be 100% disabled across your organization.**</span></span>

<span data-ttu-id="5ea1f-122">Deshabilitar la programación de difusión, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-122">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="5ea1f-123">Asignar a todos los usuarios de la organización a la directiva *Global* , ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-123">Assign all users in your organization to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="5ea1f-124">**Desea un gran número de usuarios que puedan crear eventos en directo, pero desea evitar que un conjunto de usuarios desde su creación.**</span><span class="sxs-lookup"><span data-stu-id="5ea1f-124">**You want a large number of users to be able to create live events, but want to prevent a set of users from creating them.**</span></span>

<span data-ttu-id="5ea1f-125">Asigne la directiva *Global* mediante la **Concesión CsTeamsMeetingBroadcastPolicy** para algunos de los usuarios (que desea que se estén activados) pero primero ejecute lo siguiente y compruebe que *AllowBroadcastScheduling* está establecido en *True*:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-125">Assign the *Global* policy using the **Grant-CsTeamsMeetingBroadcastPolicy** for some of the users (that you want enabled) but first run the following and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="5ea1f-126">A continuación, asignar un usuario o a los usuarios a la directiva *Global* , ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-126">Then assign a user or users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="5ea1f-127">Crear y asignar una directiva para deshabilitar la programación mediante el cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** a los demás usuarios (que desee deshabilitado).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-127">Create and assign a policy for disabling scheduling using the  **Grant-CsTeamsMeetingBroadcastPolicy** cmdlet to the other users (you want disabled).</span></span> 

<span data-ttu-id="5ea1f-128">Crear la nueva directiva con él deshabilitado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-128">Create the new policy with it disabled, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="5ea1f-129">Deshabilitar la programación, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-129">Disable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="5ea1f-130">A continuación, asignar a usuarios a esta directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-130">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="5ea1f-131">**Desea eventos en directo que se deshabilite para un gran número de los usuarios, pero desea permitir que un conjunto de usuarios para crearlos.**</span><span class="sxs-lookup"><span data-stu-id="5ea1f-131">**You want live events to be disabled for a large number of the users, but want to allow a set of users to create them.**</span></span>

<span data-ttu-id="5ea1f-132">Deshabilitar la programación de difusión, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-132">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="5ea1f-133">A continuación, asignar a los usuarios a la directiva *Global* , ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-133">Then assign those users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="5ea1f-134">Crear y asignar una directiva para habilitar la programación, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-134">Create and assign a policy for enabling scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="5ea1f-135">Habilitar la programación, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-135">Enable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="5ea1f-136">A continuación, asignar a usuarios a esta directiva, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-136">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a><span data-ttu-id="5ea1f-137">Para los eventos de codificador externo</span><span class="sxs-lookup"><span data-stu-id="5ea1f-137">For external encoder events</span></span>
<span data-ttu-id="5ea1f-138">Debe hacer lo siguiente para habilitar el evento en directo de programación para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-138">You must do the following to enable live event scheduling for those users.</span></span>

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a><span data-ttu-id="5ea1f-139">Paso 1: Habilitar Microsoft Stream para los usuarios de su organización \*\*</span><span class="sxs-lookup"><span data-stu-id="5ea1f-139">Step 1: Enable Microsoft Stream for users in your organization\*\*</span></span>
<span data-ttu-id="5ea1f-140">Microsoft Stream está disponible como parte de suscripciones a Office 365 optan o como un servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-140">Microsoft Stream is available as part of eligible Office 365 subscriptions or as a standalone service.</span></span> <span data-ttu-id="5ea1f-141">Para obtener más información, vea [información general sobre licencias de secuencia](https://docs.microsoft.com/stream/license-overview) .</span><span class="sxs-lookup"><span data-stu-id="5ea1f-141">See [Stream licensing overview](https://docs.microsoft.com/stream/license-overview) for more details.</span></span>

> <span data-ttu-id="5ea1f-142">! [NOTA] Microsoft Stream no se incluye en los planes de negocio Essentials o Business Premium.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-142">![NOTE] Microsoft Stream is not included in Business Essentials or Business Premium plans.</span></span>  

<span data-ttu-id="5ea1f-143">Obtenga más información acerca de cómo se pueden [asignar licencias a los usuarios de Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios pueden tener acceso a Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-143">Learn more about how you can [assign licenses to users in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Microsoft Stream.</span></span> <span data-ttu-id="5ea1f-144">Asegúrese de que no se bloquea Microsoft Stream para los usuarios tal como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-144">Ensure Microsoft Stream is not blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).</span></span>

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a><span data-ttu-id="5ea1f-145">Paso 2: Asegúrese de los usuarios tienen permiso de creación de evento en directo en la secuencia de Microsoft \*\*</span><span class="sxs-lookup"><span data-stu-id="5ea1f-145">Step 2: Ensure users have live event creation permission in Microsoft Stream\*\*</span></span>
<span data-ttu-id="5ea1f-146">De forma predeterminada, los administradores pueden crear codificador externo eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-146">By default, administrators can create external encoder live events.</span></span> <span data-ttu-id="5ea1f-147">Administrador de Microsoft Stream puede [Permitir que los usuarios adicionales para la creación de evento en directo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) en secuencia.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-147">Microsoft Stream administrator can [enable additional users for live event creation](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.</span></span>  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a><span data-ttu-id="5ea1f-148">Paso 3: Asegúrese de evento en directo han dado su consentimiento los organizadores de la directiva de empresa establecida por secuencia admin \*\*</span><span class="sxs-lookup"><span data-stu-id="5ea1f-148">Step 3: Ensure live event organizers have consented to the company policy set by Stream admin\*\*</span></span>
<span data-ttu-id="5ea1f-149">Si un administrador de Microsoft Stream tiene que [Configurar una directiva de instrucciones de la compañía](https://docs.microsoft.com/stream/company-policy-and-consent) y requiere que los empleados Aceptar esta directiva antes de guardar el contenido, a continuación, los usuarios deben hacerlo antes de crear un evento en directo (con producción codificador externo) en los equipos.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-149">If a Microsoft Stream administrator has [set up a company guidelines policy](https://docs.microsoft.com/stream/company-policy-and-consent) and requires employees to accept this policy before saving content, then users must do so before creating a live event (with External Encoder production) in Teams.</span></span> <span data-ttu-id="5ea1f-150">Antes de la implantación la característica de eventos en directo en la organización, asegúrese de que los usuarios que vayan a crear estos eventos en directo han dado su consentimiento a la directiva.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-150">Before you rollout the live events feature in the organization, make sure users who will be creating these live events have consented to the policy.</span></span> 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a><span data-ttu-id="5ea1f-151">Paso 4: Configurar proveedor eCDN para eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ea1f-151">Step 4: Set up eCDN provider for live events in Microsoft Teams</span></span> 
<span data-ttu-id="5ea1f-152">Reproducción de vídeos de evento en directo usa adaptable velocidad de bits de transmisión por secuencias (ABR) pero es una secuencia de unidifusión, lo que significa que cada visor obtiene su propia secuencia de vídeo de internet.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-152">Playback of live event videos uses adaptive bitrate streaming (ABR) but it is a unicast stream, meaning every viewer is getting their own video stream from the internet.</span></span> <span data-ttu-id="5ea1f-153">Para eventos en directo o los vídeos que se envía al gran parte de su organización, podría ser una cantidad considerable de ancho de banda de internet que consume los visores.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-153">For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers.</span></span> <span data-ttu-id="5ea1f-154">Para las organizaciones que desean reducir este tráfico de internet para eventos en directo, eventos en directo soluciones se integran con de Microsoft de confianza definen de socios de entrega de vídeo que ofrecen software redes (SDNs) o redes de entrega de contenido empresarial (eCDNs).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-154">For organizations that want to reduce this internet traffic for live events, live events solutions are integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or enterprise content delivery networks (eCDNs).</span></span> <span data-ttu-id="5ea1f-155">Estos SDN eCDN plataformas permiten a las organizaciones a optimizar el ancho de banda de red sin sacrificar usuario final experiencias de visualización.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-155">These SDN / eCDN platforms enable organizations to optimize network bandwidth without sacrificing end user viewing experiences.</span></span> <span data-ttu-id="5ea1f-156">Nuestros socios pueden ayudar a permitir una distribución de vídeo más escalable y eficaz a través de la red de la empresa.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-156">Our partners can help enable a more scalable and efficient video distribution across your enterprise network.</span></span>

<span data-ttu-id="5ea1f-157">**Compra & el programa de instalación la solución fuera de Microsoft Teams** Obtenga ayuda de expertos con ajuste de escala entrega vídeo mediante el aprovechamiento de los socios de entrega de vídeo de confianza de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-157">**Purchase & setup your solution outside of Microsoft Teams** Get expert help with scaling video delivery by leveraging Microsoft’s trusted video delivery partners.</span></span> <span data-ttu-id="5ea1f-158">Para poder habilitar un proveedor de entrega de vídeo que se usará con los equipos de debe comprar y configurar la solución SDN/eCDN externa e independiente de los equipos.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-158">Before you can enable a video delivery provider to be used with Teams you must purchase and setup the SDN/eCDN solution outside and separate from Teams.</span></span>

<span data-ttu-id="5ea1f-159">Las siguientes soluciones SDN/eCDN están integradas en previamente y pueden ser el programa de instalación para usarse con Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-159">The following SDN/eCDN solutions are pre-integrated and can be setup to be used with Microsoft Stream.</span></span>

- <span data-ttu-id="5ea1f-160">**Subárbol de transmisión por secuencias** proporciona una solución sencilla y eficaz para la distribución de vídeo en directo y a petición enterprise.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-160">**Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution.</span></span> <span data-ttu-id="5ea1f-161">Subárbol es una solución basada en software que no requiere ningún hardware adicional o el ancho de banda y proporciona un modo seguro para habilitar miles de visores de vídeo simultáneos sin afectar a la red.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-161">Hive is a software-based solution that requires no additional hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without impact to your network.</span></span> <span data-ttu-id="5ea1f-162">Para clientes que desean para comprender el vídeo de impacto que tiene en su red antes de adquirir una solución de SDN/eCDN, también subárbol de transmisión por secuencias proporciona una solución de análisis basada en explorador para los clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-162">For customers looking to understand the impact video is having on their network prior to purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers.</span></span> <span data-ttu-id="5ea1f-163">[Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-163">[Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span></span>
 
- <span data-ttu-id="5ea1f-164">**Kollective** es una basada en la nube, smart interconexión distribución plataforma que aprovecha la infraestructura de red existente para entregar contenido, en muchas formas, (live transmisiones de vídeo, vídeo y a petición, las actualizaciones de software, las revisiones de seguridad, etc.) con mayor rapidez, confiable y con menos ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-164">**Kollective** is a cloud-based, smart peering distribution platform that leverages your existing network infrastructure to deliver content, in many forms, (live streaming video, on-demand video, software updates, security patches, etc.) faster, more reliably and with less bandwidth.</span></span> <span data-ttu-id="5ea1f-165">Nuestra plataforma segura es de confianza por las instituciones financieras más grandes del mundo y sin hardware adicional y, a continuación, el programa de instalación y mantenimiento son fáciles.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-165">Our secure platform is trusted by the world’s largest financial institutions and with no additional hardware, setup and maintenance are easy.</span></span> <span data-ttu-id="5ea1f-166">[Más información](http://www.kollective.com).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-166">[Learn more](http://www.kollective.com).</span></span>
 
- <span data-ttu-id="5ea1f-167">**Mejorar OmniCache** proporciona la distribución de red de próxima generación y garantiza la entrega perfecta de contenido de vídeo a través de WAN global, ayudar a los productores de evento optimizar el ancho de banda de red y admitir las difusiones de evento correcta en directo y a petición transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-167">**Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth and support successful live event broadcasts and on-demand streaming.</span></span> <span data-ttu-id="5ea1f-168">La compatibilidad para mejorar OmniCache para eventos en directo inicio rápido estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-168">The support for Ramp OmniCache for quick start live events is coming soon.</span></span>  <span data-ttu-id="5ea1f-169">[Más información](http://www.ramp.com).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-169">[Learn more](http://www.ramp.com).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="5ea1f-170">La solución elegida eCDN está sujeto a la seleccionado **términos 3ª del proveedor de servicio y política de privacidad**, donde se regula el uso de la solución del proveedor eCDN.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-170">Your chosen eCDN solution is subject to the selected **3rd party provider’s terms of service and privacy policy**, which will governs your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="5ea1f-171">El uso de la solución del proveedor eCDN no estará sujeto a los términos de licencia por volumen de Microsoft o los términos de servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-171">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="5ea1f-172">Si no acepta los **términos de 3ª del proveedor**, a continuación, no habilite la solución eCDN en los equipos.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-172">If you do not agree to the **3rd party provider’s terms**, then don't enable the eCDN solution in Teams.</span></span> 

<span data-ttu-id="5ea1f-173">**Configurar una red eCDN para "Inicio rápido" eventos en directo** Puede configurar el proveedor eCDN para eventos en directo en los equipos de uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-173">**Set up an eCDN for "Quick start" live events** You can configure eCDN provider for live events in Teams using PowerShell.</span></span> 

> [!NOTE] 
> <span data-ttu-id="5ea1f-174">Un proveedor único eCDN puede configurarse para su organización.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-174">A single eCDN provider can be configured for your organization.</span></span> 

<span data-ttu-id="5ea1f-175">***Subárbol*** Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-175">***Hive*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="5ea1f-176">En primer lugar, obtener la dirección URL licencia API y el identificador de plantilla desde su contacto subárbol, a continuación, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-176">First obtain the license ID and API template URL from your Hive contact then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="5ea1f-177">***Kollective*** Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-177">***Kollective*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="5ea1f-178">En primer lugar obtener el token de API y la dirección URL de plantilla de API de su contacto Kollective, a continuación, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ea1f-178">First obtain the API token and the API template URL from your Kollective contact, then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="5ea1f-179">**Configurar una red eCDN para eventos en directo "Codificador externo"**</span><span class="sxs-lookup"><span data-stu-id="5ea1f-179">**Set up an eCDN for "External encoder" live events**</span></span> 

<span data-ttu-id="5ea1f-180">Si va a crear eventos en directo que usar codificadores externos, necesita [configurar su proveedor eCDN con la secuencia de Microsoft](https://docs.microsoft.com/stream/network-caching) así como.</span><span class="sxs-lookup"><span data-stu-id="5ea1f-180">If you plan to create live events that use external encoders, you will need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching) as well.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="5ea1f-181">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5ea1f-181">Next steps</span></span>
<span data-ttu-id="5ea1f-182">Vaya a [configurar los equipos de eventos en directo](configure-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="5ea1f-182">Go to [Confgure Teams live events](configure-teams-live-events.md).</span></span>

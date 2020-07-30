---
title: Usar NDI en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a usar NDI en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522948"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="00ab9-103">Usar NDI en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00ab9-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="00ab9-104">La interfaz de dispositivo de red (NDI) es una solución moderna para conectar dispositivos de medios (como una cámara de estudio y un mezclador).</span><span class="sxs-lookup"><span data-stu-id="00ab9-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="00ab9-105">En lugar de usar conexiones físicas, NDI permite la conectividad en una Intranet local, incluido en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="00ab9-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="00ab9-106">NewTek NDI® se ha convertido en una solución estándar de la industria para producir contenido en vivo para transmisiones por secuencias y ha obtenido un importante conocimiento y adopción en el mundo de la difusión profesional.</span><span class="sxs-lookup"><span data-stu-id="00ab9-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="00ab9-107">Skype agregó previamente la funcionalidad de NDI-out a Skype a finales del 2018.</span><span class="sxs-lookup"><span data-stu-id="00ab9-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="00ab9-108">Microsoft Teams aprovecha esta funcionalidad para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="00ab9-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="00ab9-109">NDI está limitado a una red local y solo se debe considerar parte del flujo de trabajo de producción, no de una solución de difusión.</span><span class="sxs-lookup"><span data-stu-id="00ab9-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="00ab9-110">Activar NDI</span><span class="sxs-lookup"><span data-stu-id="00ab9-110">Turn on NDI</span></span>

<span data-ttu-id="00ab9-111">NDI requiere que se activen dos pasos para un usuario.</span><span class="sxs-lookup"><span data-stu-id="00ab9-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="00ab9-112">El administrador de inquilinos debe habilitar la característica de marca de enableStreamingCallsOverNdi.</span><span class="sxs-lookup"><span data-stu-id="00ab9-112">The tenant admin must enable the feature flag enableStreamingCallsOverNdi.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="00ab9-113">Después de completar este cambio, el usuario final debe activar NDI para su cliente específico a partir **Settings**de  >  **los permisos**de configuración.</span><span class="sxs-lookup"><span data-stu-id="00ab9-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="00ab9-114">Cuando un usuario se une a una reunión, verá un mensaje en el que se le notifica que la reunión se está transmitiendo.</span><span class="sxs-lookup"><span data-stu-id="00ab9-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="00ab9-115">Si los usuarios no desean que se incluyan en la difusión, tendrán que quitarlos de la reunión.</span><span class="sxs-lookup"><span data-stu-id="00ab9-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="00ab9-116">La imagen siguiente muestra el mensaje emergente que un usuario ve en una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="00ab9-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Una imagen del banner NDI que se muestra en una reunión de Teams.](media/NDI-disclosure.png)

<span data-ttu-id="00ab9-118">La pancarta tiene un vínculo a la [política de privacidad de Microsoft](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span><span class="sxs-lookup"><span data-stu-id="00ab9-118">The banner has a link to the [Microsoft privacy policy](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="00ab9-119">Configuraciones regionales y tipos de usuario admitidos</span><span class="sxs-lookup"><span data-stu-id="00ab9-119">Supported locales and user types</span></span>

<span data-ttu-id="00ab9-120">NDI es compatible con todas las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="00ab9-120">NDI is supported in all locales.</span></span> <span data-ttu-id="00ab9-121">Los siguientes usuarios son compatibles con una reunión de NDI:</span><span class="sxs-lookup"><span data-stu-id="00ab9-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="00ab9-122">En el inquilino: soporte completo, entregado en función de ring/tenantId/userId (controlado por la marca de características y Directiva de reuniones)</span><span class="sxs-lookup"><span data-stu-id="00ab9-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy + Feature Flag)</span></span>
- <span data-ttu-id="00ab9-123">Federado: no (incluso cuando se NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="00ab9-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="00ab9-124">Freemium: no (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="00ab9-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="00ab9-125">Anonymous: no (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="00ab9-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="00ab9-126">Invitado: no (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="00ab9-126">Guest – no  (default value)</span></span>

<span data-ttu-id="00ab9-127"><sup>1</sup> los dispositivos tienen una configuración NDI que está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00ab9-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="00ab9-128">Si un participante de la reunión usa un dispositivo con NDI desactivado, tendrá que activar NDI.</span><span class="sxs-lookup"><span data-stu-id="00ab9-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>

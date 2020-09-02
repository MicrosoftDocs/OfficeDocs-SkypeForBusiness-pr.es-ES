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
ms.openlocfilehash: 24e4312af520bf783c0382b7543190644bfc1ff0
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "47323994"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="565b0-103">Usar la tecnología de NDI® en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="565b0-103">Use NDI® technology in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

 <span data-ttu-id="565b0-104">La tecnología NDI® (interfaz de dispositivo de red) es una solución moderna para conectar dispositivos de medios (como una cámara de estudio y un mezclador).</span><span class="sxs-lookup"><span data-stu-id="565b0-104">NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="565b0-105">En lugar de usar conexiones físicas, la tecnología de® de NDI permite la conectividad en una Intranet local, incluso en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="565b0-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="565b0-106">NewTek NDI® tecnología se ha convertido en una solución estándar del sector para producir contenido en vivo para transmisiones por secuencias y ha obtenido un importante conocimiento y adopción en el mundo de la difusión profesional.</span><span class="sxs-lookup"><span data-stu-id="565b0-106">NewTek NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="565b0-107">Skype añadió previamente la funcionalidad de® de salida de NDI a Skype a finales del 2018.</span><span class="sxs-lookup"><span data-stu-id="565b0-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="565b0-108">Microsoft Teams aprovecha esta funcionalidad para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="565b0-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="565b0-109">NDI® tecnología está limitada a una red local y solo se debe considerar parte del flujo de trabajo de producción, no de una solución de difusión.</span><span class="sxs-lookup"><span data-stu-id="565b0-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="565b0-110">Activar NDI® tecnología</span><span class="sxs-lookup"><span data-stu-id="565b0-110">Turn on NDI® technology</span></span>

<span data-ttu-id="565b0-111">NDI® tecnología requiere que se activen dos pasos para un usuario.</span><span class="sxs-lookup"><span data-stu-id="565b0-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="565b0-112">El administrador de inquilinos debe habilitar la propiedad ' AllowNDIStreaming ' en CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="565b0-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="565b0-113">Después de completar este cambio, el usuario final debe activar NDI tecnología® para su cliente específico a partir **Settings**de  >  **los permisos**de configuración.</span><span class="sxs-lookup"><span data-stu-id="565b0-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="565b0-114">Cuando un usuario se une a una reunión, verá un mensaje en el que se le notifica que la reunión se está transmitiendo.</span><span class="sxs-lookup"><span data-stu-id="565b0-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="565b0-115">Si los usuarios no desean que se incluyan en la difusión, tendrán que quitarlos de la reunión.</span><span class="sxs-lookup"><span data-stu-id="565b0-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="565b0-116">La imagen siguiente muestra el mensaje emergente que un usuario ve en una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="565b0-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Una imagen del banner de tecnología de NDI® que se muestra en una reunión de Teams.](media/NDI-disclosure.png)

<span data-ttu-id="565b0-118">La pancarta tiene un vínculo a la [política de privacidad de Microsoft](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="565b0-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="565b0-119">Configuraciones regionales y tipos de usuario admitidos</span><span class="sxs-lookup"><span data-stu-id="565b0-119">Supported locales and user types</span></span>

<span data-ttu-id="565b0-120">NDI® tecnología es compatible con todas las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="565b0-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="565b0-121">Los siguientes usuarios están incluidos en un flujo tecnológico de NDI®, pero no todos los usuarios pueden acceder a la NDI tecnología de®:</span><span class="sxs-lookup"><span data-stu-id="565b0-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="565b0-122">En el inquilino: soporte completo, entregado en función de ring/tenantId/userId (controlado por la Directiva de reuniones)</span><span class="sxs-lookup"><span data-stu-id="565b0-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="565b0-123">Federado: sin acceso a secuencias (incluso cuando tiene activada la tecnología® NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="565b0-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="565b0-124">Freemium: sin acceso a la transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="565b0-124">Freemium - no stream access</span></span>
- <span data-ttu-id="565b0-125">Anónimo: sin acceso a secuencias</span><span class="sxs-lookup"><span data-stu-id="565b0-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="565b0-126">Invitado: sin acceso a secuencias</span><span class="sxs-lookup"><span data-stu-id="565b0-126">Guest – no stream access</span></span>  

<span data-ttu-id="565b0-127"><sup>1</sup> los dispositivos tienen una configuración de tecnología de NDI® que está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="565b0-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="565b0-128">Si un participante de la reunión usa un dispositivo con NDI tecnología®, tendrá que activar NDI tecnología de®.</span><span class="sxs-lookup"><span data-stu-id="565b0-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>

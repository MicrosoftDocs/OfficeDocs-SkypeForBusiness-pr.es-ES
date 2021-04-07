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
description: Obtenga información sobre cómo usar NDI en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598469"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="882e5-103">Usar la tecnología ® NDI en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="882e5-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="882e5-104">La tecnología newtek NDI® (interfaz de dispositivo de red) es una solución moderna para conectar dispositivos multimedia (como una cámara de estudio y un mezclador).</span><span class="sxs-lookup"><span data-stu-id="882e5-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="882e5-105">En lugar de usar conexiones físicas, la tecnología NDI® permite la conectividad a través de una intranet local, incluso en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="882e5-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="882e5-106">La tecnología ® NDI se ha convertido en una solución estándar del sector para producir contenido en directo para transmisiones y ha adquirido una conciencia y adopción significativas en el mundo de la difusión profesional.</span><span class="sxs-lookup"><span data-stu-id="882e5-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="882e5-107">Skype agregó anteriormente la funcionalidad de ® de salida a Skype a finales de 2018.</span><span class="sxs-lookup"><span data-stu-id="882e5-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="882e5-108">Microsoft Teams usa esta funcionalidad para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="882e5-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="882e5-109">La tecnología ® NDI está limitada a una red local y solo debe considerarse una parte del flujo de trabajo de producción, no una solución de difusión.</span><span class="sxs-lookup"><span data-stu-id="882e5-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="882e5-110">Activar la tecnología ® NDI</span><span class="sxs-lookup"><span data-stu-id="882e5-110">Turn on NDI® technology</span></span>

<span data-ttu-id="882e5-111">La tecnología ® NDI requiere dos pasos para estar activado para un usuario.</span><span class="sxs-lookup"><span data-stu-id="882e5-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="882e5-112">El administrador de inquilinos debe habilitar la propiedad "AllowNDIStreaming" en CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="882e5-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="882e5-113">Una vez que se haya rellenado este cambio, el usuario final debe activar la tecnología NDI® para su cliente específico desde **Permisos**  >  **de configuración.**</span><span class="sxs-lookup"><span data-stu-id="882e5-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="882e5-114">Cuando un usuario se une a una reunión, verá un mensaje que le notifica que la reunión se está difundiendo.</span><span class="sxs-lookup"><span data-stu-id="882e5-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="882e5-115">Si los usuarios no quieren incluirse en la difusión, necesitarán abandonar la reunión.</span><span class="sxs-lookup"><span data-stu-id="882e5-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="882e5-116">La siguiente imagen muestra el mensaje de banner que un usuario ve en una reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="882e5-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![he NDI® de tecnología que se muestra en una reunión de Teams.](media/NDI-disclosure.png)

<span data-ttu-id="882e5-118">El banner tiene un vínculo a la directiva [de privacidad de Microsoft.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="882e5-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="882e5-119">NDI® se activa solo por sesión.</span><span class="sxs-lookup"><span data-stu-id="882e5-119">NDI® is activated per session only.</span></span> <span data-ttu-id="882e5-120">En el siguiente inicio de sesión, el usuario debe activarlo antes de usar NDI®.</span><span class="sxs-lookup"><span data-stu-id="882e5-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="882e5-121">Configuraciones regionales y tipos de usuario compatibles</span><span class="sxs-lookup"><span data-stu-id="882e5-121">Supported locales and user types</span></span>

<span data-ttu-id="882e5-122">La tecnología ® NDI es compatible con todas las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="882e5-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="882e5-123">Los siguientes usuarios se incluyen en una transmisión de tecnología NDI®, pero no todos los usuarios pueden acceder a la transmisión de tecnología ® NDI:</span><span class="sxs-lookup"><span data-stu-id="882e5-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="882e5-124">In-tenant: soporte completo, entregado en función de ring/tenantId/userId (controlado por la directiva de reuniones)</span><span class="sxs-lookup"><span data-stu-id="882e5-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="882e5-125">Federado: no hay acceso de transmisión (incluso cuando tienen NDI® tecnología en)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="882e5-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="882e5-126">Premium: sin acceso de transmisión</span><span class="sxs-lookup"><span data-stu-id="882e5-126">Premium - no stream access</span></span>
- <span data-ttu-id="882e5-127">Anónimo: sin acceso de transmisión</span><span class="sxs-lookup"><span data-stu-id="882e5-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="882e5-128">Invitado: sin acceso de transmisión</span><span class="sxs-lookup"><span data-stu-id="882e5-128">Guest – no stream access</span></span>  

<span data-ttu-id="882e5-129"><sup>1</sup> Los dispositivos tienen una configuración de tecnología ® NDI que está predeterminada.</span><span class="sxs-lookup"><span data-stu-id="882e5-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="882e5-130">Si un participante de la reunión usa un dispositivo con la tecnología NDI® desactivada, tendrá que activar la tecnología ® NDI.</span><span class="sxs-lookup"><span data-stu-id="882e5-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>

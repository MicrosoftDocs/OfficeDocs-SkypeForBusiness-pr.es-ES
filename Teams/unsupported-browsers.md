---
title: Reuniones de Microsoft Teams en exploradores no compatibles
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo Teams admite audio y vídeo en exploradores no compatibles.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4aca1592a89e36e7a26a9a22b111968e4b44a302
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804530"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="ce174-103">Reuniones de Microsoft Teams en exploradores no compatibles</span><span class="sxs-lookup"><span data-stu-id="ce174-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="ce174-104">Algunos exploradores, como Internet Explorer 11, Safari y Firefox, admiten la aplicación web de Microsoft Teams, pero no admiten algunas de las características de llamadas y reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="ce174-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="ce174-105">Para evitar esta limitación, la aplicación web de Teams permite a los usuarios recibir audio a través de una conexión RTC y les permite ver el contenido presentado (uso compartido de pantalla) a una velocidad de visualización reducida.</span><span class="sxs-lookup"><span data-stu-id="ce174-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="ce174-106">Las aplicaciones y servicios de Microsoft 365 no admitirán Internet Explorer 11 a partir del 17 de agosto de 2021 (Microsoft Teams no admitirá Internet Explorer 11 antes, a partir del 30 de noviembre de 2020).</span><span class="sxs-lookup"><span data-stu-id="ce174-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="ce174-107">[Más información](https://aka.ms/AA97tsw).</span><span class="sxs-lookup"><span data-stu-id="ce174-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="ce174-108">Tenga en cuenta que Internet Explorer 11 seguirá siendo un navegador compatible.</span><span class="sxs-lookup"><span data-stu-id="ce174-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="ce174-109">Internet Explorer 11 es un componente [](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) del sistema operativo Windows y sigue la directiva del ciclo de vida del producto en el que está instalado.</span><span class="sxs-lookup"><span data-stu-id="ce174-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="ce174-110">Cuando Teams detecta un explorador no compatible, muestra automáticamente un mensaje que explica el problema y las limitaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="ce174-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="ce174-111">El mensaje proporciona instrucciones adicionales para acceder al audio de la reunión, como, por ejemplo, aconsejar al usuario que deje un número de detrás de la llamada para que Teams pueda llamar al usuario o indicar al usuario que llame al número de conferencia incluido en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="ce174-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="ce174-112">El mensaje también anima al usuario a descargar y usar el cliente de escritorio [de Teams](https://teams.microsoft.com/downloads) para disfrutar de la experiencia completa de Teams.</span><span class="sxs-lookup"><span data-stu-id="ce174-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="ce174-113">Si RTC no está disponible, el usuario no verá las instrucciones para acceder a la reunión y no podrá unirse a ella.</span><span class="sxs-lookup"><span data-stu-id="ce174-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="ce174-114">Limitaciones del explorador</span><span class="sxs-lookup"><span data-stu-id="ce174-114">Browser limitations</span></span>

<span data-ttu-id="ce174-115">Los usuarios de la aplicación web de Teams en exploradores no compatibles experimentarán las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="ce174-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="ce174-116">El audio solo está disponible a través de una conexión RTC.</span><span class="sxs-lookup"><span data-stu-id="ce174-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="ce174-117">Los usuarios no pueden usar el micrófono.</span><span class="sxs-lookup"><span data-stu-id="ce174-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="ce174-118">Los usuarios no pueden compartir su cámara ni ver vídeos de otros participantes, pero pueden ver contenido presentado mediante pantalla compartida basada en imágenes.</span><span class="sxs-lookup"><span data-stu-id="ce174-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="ce174-119">Los usuarios no pueden compartir su pantalla, aunque pueden ver una que otro participante de la reunión comparte.</span><span class="sxs-lookup"><span data-stu-id="ce174-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="ce174-120">Los usuarios no pueden tomar el control durante una sesión de pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="ce174-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="ce174-121">Los usuarios no recibirán notificaciones de llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="ce174-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="ce174-122">Si se interrumpe la llamada, la reunión no volverá a conectarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ce174-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="ce174-123">Los usuarios no pueden iniciar reuniones.</span><span class="sxs-lookup"><span data-stu-id="ce174-123">Users can't start meetings.</span></span>

<span data-ttu-id="ce174-124">Para obtener más información sobre la compatibilidad de exploradores en Teams, vea [Límites y especificaciones para Teams.](/microsoftteams/limits-specifications-teams#browsers)</span><span class="sxs-lookup"><span data-stu-id="ce174-124">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ce174-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ce174-125">Related topics</span></span>

- [<span data-ttu-id="ce174-126">Unirse a una reunión de Teams en un explorador no compatible</span><span class="sxs-lookup"><span data-stu-id="ce174-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)

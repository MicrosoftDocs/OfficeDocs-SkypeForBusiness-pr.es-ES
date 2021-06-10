---
title: Microsoft Teams reuniones en exploradores no compatibles
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
description: Obtenga información sobre Teams audio y vídeo en exploradores no compatibles.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121318"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="00587-103">Microsoft Teams reuniones en exploradores no compatibles</span><span class="sxs-lookup"><span data-stu-id="00587-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="00587-104">Algunos exploradores, como Internet Explorer 11, Safari y Firefox, admiten la aplicación web Microsoft Teams pero no admiten algunas de las características de Teams llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="00587-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="00587-105">Para evitar esta limitación, la aplicación web Teams permite a los usuarios recibir audio a través de una conexión RTC y les permite ver el contenido presentado (uso compartido de pantalla) a una velocidad de visualización reducida.</span><span class="sxs-lookup"><span data-stu-id="00587-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="00587-106">Microsoft 365 aplicaciones y servicios no admitirán Internet Explorer 11 a partir del 17 de agosto de 2021 (Microsoft Teams no admitirá Internet Explorer 11 anteriormente, a partir del 30 de noviembre de 2020).</span><span class="sxs-lookup"><span data-stu-id="00587-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="00587-107">[Más información](https://aka.ms/AA97tsw).</span><span class="sxs-lookup"><span data-stu-id="00587-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="00587-108">Tenga en cuenta que Internet Explorer 11 seguirá siendo un navegador compatible.</span><span class="sxs-lookup"><span data-stu-id="00587-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="00587-109">Internet Explorer 11 es un componente del [](/lifecycle/faq/internet-explorer-microsoft-edge) Windows operativo y sigue la directiva de ciclo de vida del producto en el que está instalado.</span><span class="sxs-lookup"><span data-stu-id="00587-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="00587-110">Cuando Teams un explorador no compatible, muestra automáticamente un mensaje que explica el problema y las limitaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="00587-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="00587-111">El mensaje proporciona instrucciones adicionales para obtener acceso al audio de la reunión, como aconsejar al usuario que deje un número de llamada para que Teams pueda llamar al usuario, o indicar al usuario que llame al número de conferencia incluido en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="00587-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="00587-112">El mensaje también anima al usuario a descargar y usar el Teams de escritorio [para](https://teams.microsoft.com/downloads) disfrutar de la experiencia Teams usuario.</span><span class="sxs-lookup"><span data-stu-id="00587-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="00587-113">Si rtc no está disponible, el usuario no verá las instrucciones para acceder a la reunión y no podrá unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="00587-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="00587-114">Limitaciones del explorador</span><span class="sxs-lookup"><span data-stu-id="00587-114">Browser limitations</span></span>

<span data-ttu-id="00587-115">Las personas que usan la Teams web en exploradores no admitidos experimentarán las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="00587-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="00587-116">El audio solo está disponible a través de una conexión RTC.</span><span class="sxs-lookup"><span data-stu-id="00587-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="00587-117">Los usuarios no pueden usar el micrófono.</span><span class="sxs-lookup"><span data-stu-id="00587-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="00587-118">Los usuarios no pueden compartir su cámara ni ver vídeos de otros participantes, pero pueden ver el contenido presentado mediante el uso compartido de pantalla basado en imágenes.</span><span class="sxs-lookup"><span data-stu-id="00587-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="00587-119">Los usuarios no pueden compartir su pantalla, aunque pueden ver una pantalla que comparte otro participante de la reunión.</span><span class="sxs-lookup"><span data-stu-id="00587-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="00587-120">Los usuarios no pueden tomar el control durante una sesión de uso compartido de pantalla.</span><span class="sxs-lookup"><span data-stu-id="00587-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="00587-121">Los usuarios no recibirán notificaciones de llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="00587-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="00587-122">Si la llamada se interrumpe, la reunión no se volverá a conectar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="00587-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="00587-123">Los usuarios no pueden iniciar reuniones.</span><span class="sxs-lookup"><span data-stu-id="00587-123">Users can't start meetings.</span></span>

<span data-ttu-id="00587-124">Para obtener más información sobre el soporte del explorador en Teams, vea [Límites y especificaciones para Teams](./limits-specifications-teams.md#browsers).</span><span class="sxs-lookup"><span data-stu-id="00587-124">For more information about browser support in Teams, see [Limits and specifications for Teams](./limits-specifications-teams.md#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="00587-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="00587-125">Related topics</span></span>

- [<span data-ttu-id="00587-126">Unirse a Teams reunión en un explorador no compatible</span><span class="sxs-lookup"><span data-stu-id="00587-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
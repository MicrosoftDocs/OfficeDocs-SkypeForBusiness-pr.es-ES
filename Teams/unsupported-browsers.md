---
title: Reuniones de Microsoft Teams en exploradores no admitidos
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 1dfd2ba704aa2428555dd126c506e1673a120b72
ms.sourcegitcommit: 46b15a11755a89526be2a0b20befad61c628cdb4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955719"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="1a3e4-103">Reuniones de Microsoft Teams en exploradores no admitidos</span><span class="sxs-lookup"><span data-stu-id="1a3e4-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="1a3e4-104">Algunos exploradores, como Internet Explorer 11, Safari y Firefox, admiten la aplicación Web de Microsoft Teams, pero no admiten algunas de las características de llamadas y reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="1a3e4-105">Para evitar esta limitación, Team Web App permite a los usuarios recibir audio a través de una conexión RTC y les permite ver el contenido presentado (compartir pantalla) a una velocidad de visualización reducida.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

<span data-ttu-id="1a3e4-106">Cuando Teams detecta un explorador no compatible, muestra automáticamente un mensaje que explica el problema y las limitaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-106">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="1a3e4-107">El mensaje proporciona más instrucciones para obtener acceso al audio de la reunión, como, por ejemplo, aconsejar al usuario que deje un número de devolución de llamada para que los equipos puedan llamar al usuario, o bien instruir al usuario para que llame al número de conferencia incluido en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-107">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="1a3e4-108">El mensaje también anima al usuario a descargar y usar el cliente de [escritorio de Teams](https://teams.microsoft.com/downloads) para la experiencia de todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-108">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="1a3e4-109">Si la RTC no está disponible, el usuario no verá las instrucciones para acceder a la reunión y no podrá unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-109">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="1a3e4-110">Limitaciones del explorador</span><span class="sxs-lookup"><span data-stu-id="1a3e4-110">Browser limitations</span></span>

<span data-ttu-id="1a3e4-111">Los usuarios que usen la aplicación Teams Web en exploradores no admitidos experimentarán las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="1a3e4-111">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="1a3e4-112">El audio solo está disponible a través de una conexión RTC.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-112">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="1a3e4-113">Los usuarios no pueden usar el micrófono.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-113">Users can't use their microphone.</span></span>
- <span data-ttu-id="1a3e4-114">Los usuarios no pueden compartir sus cámaras ni ver los vídeos de otros participantes, pero pueden ver el contenido presentado mediante la pantalla compartida basada en imágenes.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-114">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="1a3e4-115">Los usuarios no pueden compartir su pantalla, aunque pueden ver una pantalla compartida por otro participante de la reunión.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-115">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="1a3e4-116">Los usuarios no pueden tomar el control durante una sesión compartida de pantalla.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-116">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="1a3e4-117">Los usuarios no recibirán notificaciones de llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-117">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="1a3e4-118">Si la llamada se interrumpe, la reunión no se volverá a conectar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-118">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="1a3e4-119">Los usuarios no pueden iniciar reuniones.</span><span class="sxs-lookup"><span data-stu-id="1a3e4-119">Users can't start meetings.</span></span>

<span data-ttu-id="1a3e4-120">Para obtener más información sobre la compatibilidad del explorador en Teams, consulte [límites y especificaciones de Teams](/microsoftteams/limits-specifications-teams#browsers).</span><span class="sxs-lookup"><span data-stu-id="1a3e4-120">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a3e4-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1a3e4-121">Related topics</span></span>

- [<span data-ttu-id="1a3e4-122">Unirse a una reunión de Teams en un explorador no admitido</span><span class="sxs-lookup"><span data-stu-id="1a3e4-122">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)

---
title: Configurar la característica llamarme para los usuarios
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar la característica llamarme en Teams para que los usuarios puedan unirse a la parte de audio por teléfono en escenarios en los que es posible que no se pueda usar el equipo para el audio.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432150"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="3c502-103">Configurar la característica llamarme para los usuarios</span><span class="sxs-lookup"><span data-stu-id="3c502-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="3c502-104">En Microsoft Teams, \*\*\*\* la característica llamarme proporciona a los usuarios una manera de unirse a la parte de audio de una reunión por teléfono.</span><span class="sxs-lookup"><span data-stu-id="3c502-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="3c502-105">Esto es útil en escenarios en los que es posible que no sea posible usar un equipo para el audio.</span><span class="sxs-lookup"><span data-stu-id="3c502-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="3c502-106">Los usuarios obtienen la parte de audio de la reunión a través del teléfono móvil o la línea terrestre y la parte&mdash;de contenido de la reunión, cuando otro participante de la reunión&mdash;comparte su pantalla o reproduce un vídeo a través de su equipo.</span><span class="sxs-lookup"><span data-stu-id="3c502-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="3c502-107">La experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="3c502-107">The user experience</span></span>

<span data-ttu-id="3c502-108">Haga clic en **unirse** para unirse a una reunión y, a continuación, haga clic en **audio del teléfono** en la pantalla **elegir la configuración de audio y vídeo** .</span><span class="sxs-lookup"><span data-stu-id="3c502-108">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="3c502-109">Desde aquí, los usuarios pueden tener la llamada de la reunión y unirse a la reunión de forma manual.</span><span class="sxs-lookup"><span data-stu-id="3c502-109">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de pantalla de la opción audio del teléfono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="3c502-111">**Permitir que los equipos de la reunión llamen**</span><span class="sxs-lookup"><span data-stu-id="3c502-111">**Let the Teams meeting call**</span></span>

<span data-ttu-id="3c502-112">En la pantalla **usar teléfono para audio** , el usuario escribe su número de teléfono y luego hace clic en **llamarme**.</span><span class="sxs-lookup"><span data-stu-id="3c502-112">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="3c502-113">La reunión llama al usuario y lo une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="3c502-113">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de pantalla de la opción llamarme en la pantalla usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="3c502-115">**Marcación manual**</span><span class="sxs-lookup"><span data-stu-id="3c502-115">**Dial in manually**</span></span>

<span data-ttu-id="3c502-116">Otra forma de unirse es llamar directamente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="3c502-116">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="3c502-117">En la pantalla **usar teléfono para audio** , haga clic en **marcar de forma manual** para obtener una lista de números de teléfono que usar para llamar a la reunión.</span><span class="sxs-lookup"><span data-stu-id="3c502-117">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de pantalla de la opción de marcado manual](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="3c502-119">Configurar la característica llamarme</span><span class="sxs-lookup"><span data-stu-id="3c502-119">Set up the Call me feature</span></span>

<span data-ttu-id="3c502-120">Para habilitar la característica llamar a los usuarios de su organización, debe configurar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="3c502-120">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="3c502-121">La Conferencia de audio está habilitada para los usuarios de su organización que programan reuniones (organizadores de reuniones).</span><span class="sxs-lookup"><span data-stu-id="3c502-121">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="3c502-122">Para obtener más información, vea [configurar las conferencias de audio para Teams](set-up-audio-conferencing-in-teams.md) y [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3c502-122">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="3c502-123">Los usuarios pueden llamar desde reuniones.</span><span class="sxs-lookup"><span data-stu-id="3c502-123">Users can dial out from meetings.</span></span> <span data-ttu-id="3c502-124">Para obtener más información, vea [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3c502-124">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="3c502-125">Si un usuario no tiene la opción de marcado de las reuniones habilitadas, la opción **llamar me** no está disponible y el usuario no recibirá una llamada para unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="3c502-125">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="3c502-126">En su lugar, el usuario verá una lista de números de teléfono en la pantalla **de uso de teléfono para audio** que pueden usar para llamar de forma manual a la reunión de su teléfono.</span><span class="sxs-lookup"><span data-stu-id="3c502-126">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>


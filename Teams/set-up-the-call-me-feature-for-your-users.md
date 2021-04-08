---
title: Configure la característica llamarme para sus usuarios
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo configurar la característica Llamarme en Teams para que los usuarios puedan unirse a la parte de audio por teléfono al usar su equipo para el audio es posible que no sea posible.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623138"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="195bd-103">Configure la característica llamarme para sus usuarios</span><span class="sxs-lookup"><span data-stu-id="195bd-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="195bd-104">En Microsoft Teams, la característica **Llamarme** ofrece a los usuarios una forma de unirse a la parte de audio de una reunión por teléfono.</span><span class="sxs-lookup"><span data-stu-id="195bd-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="195bd-105">Esto es útil en escenarios en los que puede que no sea posible usar un equipo para audio.</span><span class="sxs-lookup"><span data-stu-id="195bd-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="195bd-106">Los usuarios obtienen la parte de audio de la reunión a través de su teléfono móvil o línea terrestre y la parte de contenido de la reunión, como cuando otro participante de la reunión comparte su pantalla o reproduce un vídeo a través de &mdash; &mdash; su equipo.</span><span class="sxs-lookup"><span data-stu-id="195bd-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="195bd-107">Durante los períodos de alto volumen de reuniones (que hemos estado experimentando con el brote del COVID-19), se recomienda que los usuarios se unan a las reuniones al hacer clic en el botón <strong>Unirse a la reunión de Teams</strong> en lugar de usar los números de conferencia RTC o <strong>Llamarme al</strong>.</span><span class="sxs-lookup"><span data-stu-id="195bd-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="195bd-108">Esto contribuye a garantizar la calidad del audio cuando el alto volumen de reuniones provoca congestión en la red RTC.</span><span class="sxs-lookup"><span data-stu-id="195bd-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="195bd-109">La experiencia de usuario</span><span class="sxs-lookup"><span data-stu-id="195bd-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="195bd-110">Unirse a una reunión usando el teléfono para el audio</span><span class="sxs-lookup"><span data-stu-id="195bd-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="195bd-111">Haga **clic en** Unirse para unirse a una reunión, a continuación, audio de **teléfono** en la pantalla Elegir las opciones de vídeo y **audio** y haga clic **en Unirse ahora.**</span><span class="sxs-lookup"><span data-stu-id="195bd-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="195bd-112">Desde aquí, los usuarios pueden hacer la llamada de reunión y unirse a ellas o llamar manualmente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="195bd-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de pantalla de la opción audio del teléfono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="195bd-114">**Permitir que la llamada de reunión de Teams**</span><span class="sxs-lookup"><span data-stu-id="195bd-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="195bd-115">En la **pantalla Usar teléfono para audio,** el usuario escribe su número de teléfono y, a continuación, hace clic en **Llamarme.**</span><span class="sxs-lookup"><span data-stu-id="195bd-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="195bd-116">La reunión llama al usuario y los une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="195bd-116">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de pantalla de la opción Llamarme en la pantalla Usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="195bd-118">**Marcar manualmente**</span><span class="sxs-lookup"><span data-stu-id="195bd-118">**Dial in manually**</span></span>

<span data-ttu-id="195bd-119">Otra forma de unirse es llamar directamente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="195bd-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="195bd-120">En la pantalla Usar teléfono  **para audio,** haga clic en Marcar manualmente para obtener una lista de números de teléfono que se usarán para llamar a la reunión.</span><span class="sxs-lookup"><span data-stu-id="195bd-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de pantalla de la opción Marcar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="195bd-122">Obtener una llamada cuando hay un problema con el audio durante una reunión</span><span class="sxs-lookup"><span data-stu-id="195bd-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="195bd-123">Si un usuario experimenta problemas de audio al usar su equipo durante una reunión, el usuario puede cambiar fácilmente al uso de su teléfono para el audio.</span><span class="sxs-lookup"><span data-stu-id="195bd-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="195bd-124">Teams detecta cuando se produce un problema de audio o dispositivo y redirige al usuario para que use su teléfono mostrando una **opción Llamarme** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="195bd-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="195bd-125">Este es un ejemplo del  mensaje y la opción Llamarme atrás que se muestra cuando Teams no detecta un micrófono.</span><span class="sxs-lookup"><span data-stu-id="195bd-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Captura de pantalla de la opción Llamarme atrás](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="195bd-127">El usuario hace clic **en Llamarme** de nuevo, que muestra la **pantalla Usar teléfono para audio.**</span><span class="sxs-lookup"><span data-stu-id="195bd-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="195bd-128">Desde aquí, pueden escribir su número de teléfono y hacer que la llamada de reunión de Teams y unirse a ella a la reunión o llamar manualmente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="195bd-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="195bd-129">Configurar la característica Llamarme</span><span class="sxs-lookup"><span data-stu-id="195bd-129">Set up the Call me feature</span></span>

<span data-ttu-id="195bd-130">Para habilitar la característica Llamarme para los usuarios de su organización, debe configurarse lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="195bd-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="195bd-131">Las audioconferencias están habilitadas para los usuarios de su organización que programan reuniones (organizadores de reuniones).</span><span class="sxs-lookup"><span data-stu-id="195bd-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="195bd-132">Para obtener más información, vea Configurar audioconferencias para [Teams](set-up-audio-conferencing-in-teams.md) y Administrar la configuración de [audioconferencia para un usuario en Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="195bd-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="195bd-133">El organizador de la reunión puede llamar desde reuniones.</span><span class="sxs-lookup"><span data-stu-id="195bd-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="195bd-134">Para obtener más información, vea [Administrar la configuración de audioconferencias para un usuario en Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="195bd-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="195bd-135">Si el organizador de la reunión no tiene habilitada la llamada desde las reuniones, la opción Audio del teléfono de la pantalla Elegir las opciones de **vídeo** y **audio** no está disponible para nadie y otros usuarios no pueden recibir una llamada para unirse a ella.</span><span class="sxs-lookup"><span data-stu-id="195bd-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="195bd-136">Para los usuarios con acceso telefónico habilitado, una vez que se han unido a la reunión, pueden unirse a otros marcando su número desde el icono **Mostrar participantes.**</span><span class="sxs-lookup"><span data-stu-id="195bd-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>

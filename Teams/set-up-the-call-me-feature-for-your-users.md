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
description: Aprenda a configurar la característica Llamarme en Teams para que los usuarios no puedan unirse a la parte de audio por teléfono cuando usan su PC para el audio.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821100"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="f96f1-103">Configure la característica llamarme para sus usuarios</span><span class="sxs-lookup"><span data-stu-id="f96f1-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="f96f1-104">En Microsoft Teams, la característica **Llamarme** ofrece a los usuarios una forma de unirse a la parte de audio de una reunión por teléfono.</span><span class="sxs-lookup"><span data-stu-id="f96f1-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="f96f1-105">Esto es útil en escenarios en los que es posible que no sea posible usar un equipo para audio.</span><span class="sxs-lookup"><span data-stu-id="f96f1-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="f96f1-106">Los usuarios obtienen la parte de audio de la reunión a través de su teléfono móvil o línea fijo y la parte de contenido de la reunión, como cuando otro participante comparte su pantalla o reproduce un vídeo a través de su &mdash; &mdash; equipo.</span><span class="sxs-lookup"><span data-stu-id="f96f1-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="f96f1-107">Durante los períodos de alto volumen de reuniones (que hemos estado experimentando con el brote del COVID-19), se recomienda que los usuarios se unan a las reuniones al hacer clic en el botón <strong>Unirse a la reunión de Teams</strong> en lugar de usar los números de conferencia RTC o <strong>Llamarme al</strong>.</span><span class="sxs-lookup"><span data-stu-id="f96f1-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="f96f1-108">Esto contribuye a garantizar la calidad del audio cuando el alto volumen de reuniones provoca congestión en la red RTC.</span><span class="sxs-lookup"><span data-stu-id="f96f1-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f96f1-109">Mientras dure el brote de COVID-19, se recomienda a los usuarios que se unan a las reuniones mediante el botón **Unirse a la reunión de Teams** en lugar de usar los números de conferencia RTC o la opción **Llamarme al**</strong>.</span><span class="sxs-lookup"><span data-stu-id="f96f1-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="f96f1-110">Esto se debe principalmente a la congestión de las infraestructuras de telefonía de países afectados por COVID-19.</span><span class="sxs-lookup"><span data-stu-id="f96f1-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="f96f1-111">Si evita las llamadas RTC, es probable que experimente mayor calidad de audio.</span><span class="sxs-lookup"><span data-stu-id="f96f1-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="f96f1-112">La experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="f96f1-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="f96f1-113">Unirse a una reunión mediante el teléfono para el audio</span><span class="sxs-lookup"><span data-stu-id="f96f1-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="f96f1-114">Haga **clic en** Unirse para unirse a una reunión y, a continuación, haga clic en Audio **del** teléfono en la pantalla Elegir la configuración de audio **y vídeo.**</span><span class="sxs-lookup"><span data-stu-id="f96f1-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="f96f1-115">Desde aquí, los usuarios pueden realizar la llamada de reunión y unirse a ellos o llamar manualmente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f96f1-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de pantalla de la opción de audio del teléfono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="f96f1-117">**Dejar que se llame a la reunión de Teams**</span><span class="sxs-lookup"><span data-stu-id="f96f1-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="f96f1-118">En la **pantalla Usar teléfono para audio,** el usuario escribe su número de teléfono y hace clic en **Llamarme.**</span><span class="sxs-lookup"><span data-stu-id="f96f1-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="f96f1-119">La reunión llama al usuario y lo une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f96f1-119">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de pantalla de la opción Llamarme en la pantalla Usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="f96f1-121">**Marcar manualmente**</span><span class="sxs-lookup"><span data-stu-id="f96f1-121">**Dial in manually**</span></span>

<span data-ttu-id="f96f1-122">Otra forma de unirse es llamar directamente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f96f1-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="f96f1-123">En la pantalla Usar teléfono  para **el audio,** haga clic en Marcar manualmente para obtener una lista de números de teléfono que se usarán para llamar a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f96f1-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de pantalla de la opción Marcar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="f96f1-125">Obtener una llamada cuando algo va mal con el audio durante una reunión</span><span class="sxs-lookup"><span data-stu-id="f96f1-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="f96f1-126">Si un usuario experimenta problemas de audio al usar su equipo durante una reunión, el usuario puede cambiar fácilmente al uso de su teléfono para el audio.</span><span class="sxs-lookup"><span data-stu-id="f96f1-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="f96f1-127">Teams detecta cuando se produce un problema con el audio o dispositivo y redirige al usuario **para** que use su teléfono mostrando una opción Devolver la llamada.</span><span class="sxs-lookup"><span data-stu-id="f96f1-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="f96f1-128">Este es un ejemplo del  mensaje y la opción Volver a llamar que se muestra cuando Teams no detecta un micrófono.</span><span class="sxs-lookup"><span data-stu-id="f96f1-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Captura de pantalla de la opción Volver a llamarme](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="f96f1-130">El usuario hace clic **en Volver a** llamar, lo que abre la pantalla Usar teléfono para el **audio.**</span><span class="sxs-lookup"><span data-stu-id="f96f1-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="f96f1-131">Desde aquí, pueden introducir su número de teléfono, hacer que se llame a la reunión de Teams y unirse a ella, o bien llamar manualmente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f96f1-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="f96f1-132">Configurar la característica Llamarme</span><span class="sxs-lookup"><span data-stu-id="f96f1-132">Set up the Call me feature</span></span>

<span data-ttu-id="f96f1-133">Para habilitar la característica Llamarme para los usuarios de su organización, es necesario configurar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f96f1-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="f96f1-134">La audioconferencia está habilitada para los usuarios de su organización que programan reuniones (organizadores de reuniones).</span><span class="sxs-lookup"><span data-stu-id="f96f1-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="f96f1-135">Para obtener más información, consulte [Configurar Audioconferencia](set-up-audio-conferencing-in-teams.md) para Teams y Administrar la configuración de [Audioconferencia para un usuario en Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f96f1-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="f96f1-136">Los usuarios pueden llamar desde las reuniones.</span><span class="sxs-lookup"><span data-stu-id="f96f1-136">Users can dial out from meetings.</span></span> <span data-ttu-id="f96f1-137">Para obtener más información, [consulte Administrar la configuración de Audioconferencia para un usuario en Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f96f1-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="f96f1-138">Si un usuario no tiene habilitada la opción Llamarme desde las reuniones, la opción **Llamarme** no está disponible y el usuario no recibirá una llamada para unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f96f1-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="f96f1-139">En su lugar, el usuario ve una lista de números de teléfono en la pantalla Usar teléfono para **audio** que puede usar para llamar manualmente a la reunión en su teléfono.</span><span class="sxs-lookup"><span data-stu-id="f96f1-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>

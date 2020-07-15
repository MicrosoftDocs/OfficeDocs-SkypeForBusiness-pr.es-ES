---
title: Configure la característica llamarme para sus usuarios
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo configurar la característica llamarme en Teams para que los usuarios puedan unirse a la parte de audio por teléfono cuando use su equipo para el audio puede no ser posible.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138020"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="4dd3c-103">Configure la característica llamarme para sus usuarios</span><span class="sxs-lookup"><span data-stu-id="4dd3c-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="4dd3c-104">En Microsoft Teams, la característica **llamarme** proporciona a los usuarios una manera de unirse a la parte de audio de una reunión por teléfono.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="4dd3c-105">Esto es útil en escenarios en los que es posible que no sea posible usar un equipo para el audio.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="4dd3c-106">Los usuarios obtienen la parte de audio de la reunión a través del teléfono móvil o la línea terrestre y la parte de contenido de la reunión &mdash; , como cuando otro participante de la reunión comparte su pantalla o reproduce un vídeo &mdash; a través de su equipo.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="4dd3c-107">Durante los períodos de gran volumen de reunión (que hemos estado experimentando con el brote COVID-19), recomendamos que los usuarios se unan a las reuniones haciendo clic en el botón unirse a la <strong>reunión de Teams</strong> en lugar de llamar usando los números de la Conferencia RTC o llamando <strong>al</strong>.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="4dd3c-108">Esto ayuda a garantizar la calidad de audio en las ocasiones en que el volumen de las reuniones altas provoca congestión en la red PSTN.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4dd3c-109">Mientras dure el brote de COVID-19, se recomienda a los usuarios que se unan a las reuniones mediante el botón **Unirse a la reunión de Teams** en lugar de usar los números de conferencia RTC o la opción **Llamarme al**</strong>.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="4dd3c-110">Esto se debe principalmente a la congestión de las infraestructuras de telefonía de países afectados por COVID-19.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="4dd3c-111">Si evita las llamadas RTC, es probable que experimente mayor calidad de audio.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="4dd3c-112">La experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="4dd3c-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="4dd3c-113">Unirse a una reunión con el teléfono para el audio</span><span class="sxs-lookup"><span data-stu-id="4dd3c-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="4dd3c-114">Haga clic en **unirse** para unirse a una reunión y, a continuación, haga clic en **audio del teléfono** en la pantalla **elegir la configuración de audio y vídeo** .</span><span class="sxs-lookup"><span data-stu-id="4dd3c-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="4dd3c-115">Desde aquí, los usuarios pueden tener la llamada de la reunión y unirse a la reunión de forma manual.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de pantalla de la opción audio del teléfono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="4dd3c-117">**Permitir que los equipos de la reunión llamen**</span><span class="sxs-lookup"><span data-stu-id="4dd3c-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="4dd3c-118">En la pantalla **usar teléfono para audio** , el usuario escribe su número de teléfono y luego hace clic en **llamarme**.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="4dd3c-119">La reunión llama al usuario y lo une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-119">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de pantalla de la opción llamarme en la pantalla usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="4dd3c-121">**Marcación manual**</span><span class="sxs-lookup"><span data-stu-id="4dd3c-121">**Dial in manually**</span></span>

<span data-ttu-id="4dd3c-122">Otra forma de unirse es llamar directamente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="4dd3c-123">En la pantalla **usar teléfono para audio** , haga clic en **marcar de forma manual** para obtener una lista de números de teléfono que usar para llamar a la reunión.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de pantalla de la opción de marcado manual](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="4dd3c-125">Recuperar una llamada cuando algo sale mal con el audio durante una reunión</span><span class="sxs-lookup"><span data-stu-id="4dd3c-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="4dd3c-126">Si un usuario experimenta problemas de audio al usar su equipo durante una reunión, el usuario puede cambiar fácilmente a usar el teléfono para el audio.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="4dd3c-127">Teams detecta cuando se produce un problema de audio o dispositivo y redirige al usuario para que use su teléfono con una opción para **volver a llamarme** .</span><span class="sxs-lookup"><span data-stu-id="4dd3c-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="4dd3c-128">Este es un ejemplo del mensaje y la opción **llamarme atrás** que se muestra cuando Teams no detecta un micrófono.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Captura de pantalla de la opción llamarme atrás](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="4dd3c-130">El usuario hace clic en **llamarme de nuevo**, que muestra la pantalla **usar teléfono para audio** .</span><span class="sxs-lookup"><span data-stu-id="4dd3c-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="4dd3c-131">Desde aquí puede escribir su número de teléfono y hacer que los equipos de la reunión se llamen y se unan a la reunión o marquen de forma manual en la reunión.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="4dd3c-132">Configurar la característica llamarme</span><span class="sxs-lookup"><span data-stu-id="4dd3c-132">Set up the Call me feature</span></span>

<span data-ttu-id="4dd3c-133">Para habilitar la característica llamar a los usuarios de su organización, debe configurar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4dd3c-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="4dd3c-134">La Conferencia de audio está habilitada para los usuarios de su organización que programan reuniones (organizadores de reuniones).</span><span class="sxs-lookup"><span data-stu-id="4dd3c-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="4dd3c-135">Para obtener más información, vea [configurar las conferencias de audio para Teams](set-up-audio-conferencing-in-teams.md) y [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4dd3c-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="4dd3c-136">Los usuarios pueden llamar desde reuniones.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-136">Users can dial out from meetings.</span></span> <span data-ttu-id="4dd3c-137">Para obtener más información, vea [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4dd3c-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="4dd3c-138">Si un usuario no tiene la opción de marcado de las reuniones habilitadas, la opción **llamar me** no está disponible y el usuario no recibirá una llamada para unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="4dd3c-139">En su lugar, el usuario verá una lista de números de teléfono en la pantalla **de uso de teléfono para audio** que pueden usar para llamar de forma manual a la reunión de su teléfono.</span><span class="sxs-lookup"><span data-stu-id="4dd3c-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>

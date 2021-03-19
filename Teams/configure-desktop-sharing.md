---
title: Configure el uso compartido del escritorio en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a configurar una directiva de reuniones que permita a los usuarios compartir sus escritorios en los chats o reuniones de Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75e540de7e40206f0b1dd15e26adc62d6f6baa7
ms.sourcegitcommit: d27b97f012d0cb3f1690d3673d50bbaa0caae16f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47652482"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="ad0e8-103">Configure el uso compartido del escritorio en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad0e8-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="ad0e8-104">Al compartir el escritorio, los usuarios pueden presentar una pantalla o aplicación durante una reunión o un chat.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="ad0e8-105">Los administradores pueden configurar la pantalla compartiendo en Microsoft Teams para que los usuarios puedan compartir una pantalla completa, una aplicación o un archivo.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="ad0e8-106">Puede permitir que los usuarios puedan dar control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="ad0e8-107">Asimismo, puede configurar si los usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="ad0e8-108">Los participantes externos en reuniones de Teams se pueden categorizar de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="ad0e8-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="ad0e8-109">Usuario anónimo</span><span class="sxs-lookup"><span data-stu-id="ad0e8-109">Anonymous user</span></span>
- <span data-ttu-id="ad0e8-110">Usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="ad0e8-110">Guest users</span></span>
- <span data-ttu-id="ad0e8-111">Usuario B2B</span><span class="sxs-lookup"><span data-stu-id="ad0e8-111">B2B user</span></span>
- <span data-ttu-id="ad0e8-112">Usuario federado</span><span class="sxs-lookup"><span data-stu-id="ad0e8-112">Federated user</span></span>

<span data-ttu-id="ad0e8-113">Para configurar el uso compartido de la pantalla, debe crear una nueva Directiva de reuniones y, a continuación, asignarla a los usuarios que quiera administrar.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="ad0e8-114">**En el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="ad0e8-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="ad0e8-115">Seleccione **Reuniones** > **Directivas de reunión**.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![Directivas de reuniones seleccionadas](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="ad0e8-117">En la página **Directivas de reunión**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![El mensaje de directivas de reunión](media/addMeeting.png)

3. <span data-ttu-id="ad0e8-119">Asigne un título único a la directiva y escriba una breve descripción.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="ad0e8-120">En **de uso compartido de contenido**, elija **un modo de uso compartido de** Pantalla de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="ad0e8-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="ad0e8-121">**Toda la pantalla**: le permite a los usuarios compartir todo el escritorio.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="ad0e8-122">**Una sola aplicación**: esto permite a los usuarios limitar el uso compartido de la pantalla a una única aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="ad0e8-123">**Deshabilitada**: desactiva el uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-123">**Disabled** – Turns off screen sharing.</span></span>

    ![Las opciones del modo de uso compartido](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="ad0e8-125">No tiene que habilitar la directiva de llamada para que los usuarios puedan usar el recurso compartido de pantalla desde el chat.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="ad0e8-126">Sin embargo, su audio se desactivará hasta lo activen ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="ad0e8-127">Además, el usuario que comparte la pantalla puede hacer clic en **Agregar audio** para habilitar el audio.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="ad0e8-128">Si la directiva de llamada está deshabilitada, los usuarios no podrán agregar audio a la pantalla compartida desde una sesión de chat.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="ad0e8-129">Activar o desactivar la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="ad0e8-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="ad0e8-130">**Permitir que un participante ceda o solicite control**: permite a los miembros del equipo ceder o dar el control de la aplicación o el escritorio del presentador.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="ad0e8-131">**Permitir a un participante externo ceder o solicitar el control**: esta es una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="ad0e8-132">Que una organización haya definido esto para un usuario no controla lo que puedan hacer los participantes externos, independientemente de lo que haya configurado el organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="ad0e8-133">Lo que controla este parámetro es si los participantes externos pueden recibir o solicitar el control de la pantalla que comparten, en función de lo que la persona que comparte haya establecido en las directivas de reuniones de su organización.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="ad0e8-134">**Permitir el uso compartido de PowerPoint**: permite a los usuarios crear reuniones que permiten cargar y compartir presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="ad0e8-135">**Permitir pizarra**: permite a los usuarios compartir una pizarra.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="ad0e8-136">**Permitir notas compartidas**: permite a los usuarios tomar notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="ad0e8-137">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="ad0e8-138">Use PowerShell para configurar el escritorio compartido</span><span class="sxs-lookup"><span data-stu-id="ad0e8-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="ad0e8-139">También puede usar [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-139">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="ad0e8-140">Ajuste los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="ad0e8-140">Set the following parameters:</span></span>

- <span data-ttu-id="ad0e8-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad0e8-141">Description</span></span>
- <span data-ttu-id="ad0e8-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="ad0e8-142">ScreenSharingMode</span></span>
- <span data-ttu-id="ad0e8-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="ad0e8-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="ad0e8-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="ad0e8-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="ad0e8-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="ad0e8-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="ad0e8-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="ad0e8-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="ad0e8-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="ad0e8-147">AllowWhiteboard</span></span>
- <span data-ttu-id="ad0e8-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="ad0e8-148">AllowSharedNotes</span></span>

<span data-ttu-id="ad0e8-149">[Obtenga más información sobre el uso del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ad0e8-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

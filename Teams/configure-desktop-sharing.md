---
title: Configure el uso compartido del escritorio en Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurar una directiva de reuniones para permitir que los usuarios compartan los escritorios en Teams de chats o reuniones
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366aaeb4f48670ae04d4b53d21196ef2d9e81fb4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825548"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="f5f92-103">Configure el uso compartido del escritorio en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5f92-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="f5f92-104">Al compartir el escritorio, los usuarios pueden presentar una pantalla o aplicación durante una reunión o un chat.</span><span class="sxs-lookup"><span data-stu-id="f5f92-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="f5f92-105">Los administradores pueden configurar la pantalla compartiendo en Microsoft Teams para que los usuarios puedan compartir una pantalla completa, una aplicación o un archivo.</span><span class="sxs-lookup"><span data-stu-id="f5f92-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="f5f92-106">Puede permitir que los usuarios puedan dar control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="f5f92-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="f5f92-107">Asimismo, puede configurar si los usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="f5f92-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="f5f92-108">Para configurar el uso compartido de la pantalla, debe crear una nueva Directiva de reuniones y, a continuación, asignarla a los usuarios que quiera administrar.</span><span class="sxs-lookup"><span data-stu-id="f5f92-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="f5f92-109">**En el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="f5f92-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="f5f92-110">Seleccione **Reuniones** > **Directivas de reunión**.</span><span class="sxs-lookup"><span data-stu-id="f5f92-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Captura de pantalla que muestra las directivas de reuniones seleccionadas](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="f5f92-112">En la página **Directivas de reunión**, seleccione **Nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="f5f92-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Captura de pantalla que muestra el mensaje directivas de reunión](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="f5f92-114">Asigne un título único a la directiva y escriba una breve descripción.</span><span class="sxs-lookup"><span data-stu-id="f5f92-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="f5f92-115">En **de uso compartido de contenido**, elija \*\*un modo de uso compartido de \*\*Pantalla de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="f5f92-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="f5f92-116">**Toda la pantalla**: le permite a los usuarios compartir todo el escritorio.</span><span class="sxs-lookup"><span data-stu-id="f5f92-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="f5f92-117">**Una sola aplicación**: esto permite a los usuarios limitar el uso compartido de la pantalla a una única aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="f5f92-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="f5f92-118">**Deshabilitada**: desactiva el uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f5f92-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Captura de pantalla que muestra las opciones del modo de uso compartido](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="f5f92-120">Activar o desactivar la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="f5f92-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="f5f92-121">**Permitir un participante que de o** solicite un control: permite a los miembros del equipo dar control de la aplicación o el escritorio del presentador.</span><span class="sxs-lookup"><span data-stu-id="f5f92-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="f5f92-122">**Permitir a un participante dar o** solicitar un control: permite a los miembros del equipo dar control de la aplicación o el escritorio del moderador.</span><span class="sxs-lookup"><span data-stu-id="f5f92-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="f5f92-123">**Permitir el uso compartido de PowerPoint**: permite a los usuarios crear reuniones que permiten cargar y compartir presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f5f92-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="f5f92-124">**Permitir pizarra**: permite a los usuarios compartir una pizarra.</span><span class="sxs-lookup"><span data-stu-id="f5f92-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="f5f92-125">**Permitir notas compartidas**: permite a los usuarios tomar notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="f5f92-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="f5f92-126">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="f5f92-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="f5f92-127">Use PowerShell para configurar el escritorio compartido</span><span class="sxs-lookup"><span data-stu-id="f5f92-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="f5f92-128">También puede usar [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="f5f92-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="f5f92-129">Ajuste los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="f5f92-129">Set the following parameters:</span></span>

- <span data-ttu-id="f5f92-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5f92-130">Description</span></span>
- <span data-ttu-id="f5f92-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="f5f92-131">ScreenSharingMode</span></span>
- <span data-ttu-id="f5f92-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="f5f92-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="f5f92-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="f5f92-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="f5f92-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="f5f92-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="f5f92-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="f5f92-135">AllowWhiteboard</span></span>
- <span data-ttu-id="f5f92-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="f5f92-136">AllowSharedNotes</span></span>

<span data-ttu-id="f5f92-137">[Obtenga más información sobre el uso del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f5f92-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>


---
title: Configurar Compartir escritorio en Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurar una directiva de reunión para permitir a los usuarios compartir sus escritorios en chats de los equipos o las reuniones
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 757f023d5f988e5a4f45c6274358aa51f3417ce0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464463"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="c0700-103">Configurar Compartir escritorio en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0700-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="c0700-104">Uso compartido de escritorio permite a los usuarios presentar una pantalla o una aplicación durante una reunión o conversación.</span><span class="sxs-lookup"><span data-stu-id="c0700-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="c0700-105">Los administradores pueden configurar el uso compartido en Microsoft Teams para permitir a los usuarios compartir una pantalla completa, una aplicación o un archivo de pantalla.</span><span class="sxs-lookup"><span data-stu-id="c0700-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="c0700-106">Puede permitir a los usuarios conceder o solicitar el control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="c0700-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="c0700-107">También puede configurar si los usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="c0700-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="c0700-108">Para configurar el uso compartido de la pantalla, crear una nueva directiva de reuniones y, a continuación, se asigna a los usuarios que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="c0700-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="c0700-109">**En el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="c0700-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c0700-110">Seleccione **las reuniones** > **las directivas de reunión**.</span><span class="sxs-lookup"><span data-stu-id="c0700-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Seleccione las directivas de reunión](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="c0700-112">En la página de **directivas de reunión** , seleccione **nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="c0700-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Seleccione nueva directiva](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="c0700-114">Asigne un título único a la directiva y escriba una descripción breve.</span><span class="sxs-lookup"><span data-stu-id="c0700-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="c0700-115">En el **uso compartido de contenido**, elija un **modo de uso compartido de pantalla** de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="c0700-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="c0700-116">**Pantalla completa** – permite a los usuarios compartir su escritorio completo.</span><span class="sxs-lookup"><span data-stu-id="c0700-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="c0700-117">**Única aplicación** – permite a los usuarios límite pantalla de uso compartido en una única aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="c0700-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="c0700-118">**Deshabilitado** : desactiva el uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="c0700-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Elija una modo de uso compartido de pantalla](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="c0700-120">Activar o desactivar la los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0700-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="c0700-121">A **Permitir que un participante dar o solicitar el control** – permite a los miembros del equipo de dar o solicitar el control del escritorio del moderador o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0700-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="c0700-122">**Permitir que un participante externo a proporcionar o solicitar el control** – permite a los invitados y usuarios (federados) externos concesión o solicitar el control del escritorio del moderador o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0700-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="c0700-123">El **uso compartido de PowerPoint permitir** - permite a los usuarios crear reuniones que permiten presentaciones de PowerPoint cargar y compartir.</span><span class="sxs-lookup"><span data-stu-id="c0700-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="c0700-124">**Permitir Pizarra** – permite a los usuarios compartir una pizarra.</span><span class="sxs-lookup"><span data-stu-id="c0700-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="c0700-125">**Permitir notas compartidas** – permite a los usuarios tomar notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="c0700-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="c0700-126">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c0700-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="c0700-127">Uso de PowerShell para configurar el escritorio compartido</span><span class="sxs-lookup"><span data-stu-id="c0700-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="c0700-128">También puede usar el cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="c0700-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="c0700-129">Establezca los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="c0700-129">Set the following parameters:</span></span>

- <span data-ttu-id="c0700-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0700-130">Description</span></span>
- <span data-ttu-id="c0700-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="c0700-131">ScreenSharingMode</span></span>
- <span data-ttu-id="c0700-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="c0700-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="c0700-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="c0700-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="c0700-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="c0700-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="c0700-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="c0700-135">AllowWhiteboard</span></span>
- <span data-ttu-id="c0700-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="c0700-136">AllowSharedNotes</span></span>

<span data-ttu-id="c0700-137">[Más información sobre cómo usar el cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c0700-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>


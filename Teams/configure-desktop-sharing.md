---
title: Configuración de uso compartido de escritorio en Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurar una directiva de reunión para permitir a los usuarios compartir sus escritorios en chats de los equipos o las reuniones
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 422d5fb3a19dad2e14e0cdf54a532b0afc6eed67
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2018
ms.locfileid: "27202516"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="23469-103">Configuración de uso compartido de escritorio en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23469-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="23469-104">Uso compartido de escritorio permite a los usuarios presentar una pantalla o una aplicación durante una reunión o conversación.</span><span class="sxs-lookup"><span data-stu-id="23469-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="23469-105">Los administradores pueden configurar el uso compartido en Microsoft Teams para permitir a los usuarios compartir una pantalla completa, una aplicación o un archivo de pantalla.</span><span class="sxs-lookup"><span data-stu-id="23469-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="23469-106">Puede permitir a los usuarios conceder o solicitar el control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="23469-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="23469-107">También puede configurar si los usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="23469-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="23469-108">Para configurar el uso compartido de la pantalla, crear una nueva directiva de reuniones y, a continuación, se asigna a los usuarios que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="23469-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="23469-109">En los equipos de Microsoft & Skype para el centro de administración de negocio:</span><span class="sxs-lookup"><span data-stu-id="23469-109">In the Microsoft Teams & Skype for Business Admin Center:</span></span>

1. <span data-ttu-id="23469-110">Seleccione **las reuniones** > **las directivas de reunión**.</span><span class="sxs-lookup"><span data-stu-id="23469-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Seleccione las directivas de reunión](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="23469-112">En la página de **directivas de reunión** , seleccione **nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="23469-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Seleccione nueva directiva](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="23469-114">Asigne un título único a la directiva y escriba una descripción breve.</span><span class="sxs-lookup"><span data-stu-id="23469-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="23469-115">En el **uso compartido de contenido**, elija un **modo de uso compartido de pantalla** de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="23469-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="23469-116">**Pantalla completa** – permite a los usuarios compartir su escritorio completo.</span><span class="sxs-lookup"><span data-stu-id="23469-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="23469-117">**Única aplicación** – permite a los usuarios límite pantalla de uso compartido en una única aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="23469-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="23469-118">**Deshabilitado** : desactiva el uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="23469-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Elija una modo de uso compartido de pantalla](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="23469-120">Activar o desactivar la los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="23469-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="23469-121">A **Permitir que un participante dar o solicitar el control** – permite a los miembros del equipo de dar o solicitar el control del escritorio del moderador o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23469-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="23469-122">**Permitir que un participante externo a proporcionar o solicitar el control** – permite a los invitados y usuarios (federados) externos concesión o solicitar el control del escritorio del moderador o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23469-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="23469-123">El **uso compartido de PowerPoint permitir** - permite a los usuarios crear reuniones que permiten presentaciones de PowerPoint cargar y compartir.</span><span class="sxs-lookup"><span data-stu-id="23469-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="23469-124">**Permitir Pizarra** – permite a los usuarios compartir una pizarra.</span><span class="sxs-lookup"><span data-stu-id="23469-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="23469-125">**Permitir notas compartidas** – permite a los usuarios tomar notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="23469-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="23469-126">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="23469-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="23469-127">Uso de PowerShell para configurar el escritorio compartido</span><span class="sxs-lookup"><span data-stu-id="23469-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="23469-128">También puede usar el cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="23469-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="23469-129">Establezca los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="23469-129">Set the following parameters:</span></span>

- <span data-ttu-id="23469-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="23469-130">Description</span></span>
- <span data-ttu-id="23469-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="23469-131">ScreenSharingMode</span></span>
- <span data-ttu-id="23469-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="23469-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="23469-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="23469-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="23469-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="23469-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="23469-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="23469-135">AllowWhiteboard</span></span>
- <span data-ttu-id="23469-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="23469-136">AllowSharedNotes</span></span>

<span data-ttu-id="23469-137">[Más información sobre cómo usar el cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="23469-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>


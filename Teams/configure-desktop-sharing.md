---
title: Configurar Compartir escritorio en Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Configurar una directiva de reunión para permitir que los usuarios compartan sus escritorios en chats o reuniones de Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "37516891"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="384b9-103">Configurar Compartir escritorio en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="384b9-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="384b9-104">El uso compartido de escritorio permite a los usuarios presentar una pantalla o una aplicación durante una reunión o un chat.</span><span class="sxs-lookup"><span data-stu-id="384b9-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="384b9-105">Los administradores pueden configurar la pantalla compartida en Microsoft Teams para permitir que los usuarios compartan una pantalla completa, una aplicación o un archivo.</span><span class="sxs-lookup"><span data-stu-id="384b9-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="384b9-106">Puede permitir a los usuarios asignar o solicitar el control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="384b9-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="384b9-107">También puede configurar si usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="384b9-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="384b9-108">Para configurar la pantalla compartida, debe crear una nueva Directiva de reuniones y, a continuación, asignarla a los usuarios que desee administrar.</span><span class="sxs-lookup"><span data-stu-id="384b9-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="384b9-109">**En el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="384b9-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="384b9-110">Seleccione \*\*\*\* > **políticas**de reuniones de reuniones.</span><span class="sxs-lookup"><span data-stu-id="384b9-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Captura de pantalla que muestra las directivas de reunión seleccionadas](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="384b9-112">En la página directivas de la **reunión** , seleccione **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="384b9-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Captura de pantalla que muestra el mensaje directivas de la reunión](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="384b9-114">Asigne un título único a la Directiva y escriba una descripción breve.</span><span class="sxs-lookup"><span data-stu-id="384b9-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="384b9-115">En **uso compartido de contenido**, seleccione un **modo de uso compartido de pantalla** de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="384b9-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="384b9-116">**Pantalla completa** : permite que los usuarios compartan todo su escritorio.</span><span class="sxs-lookup"><span data-stu-id="384b9-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="384b9-117">Una **sola aplicación** : permite que los usuarios limiten la pantalla compartida a una sola aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="384b9-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="384b9-118">**Deshabilitado** : desactiva la pantalla compartida.</span><span class="sxs-lookup"><span data-stu-id="384b9-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Captura de pantalla que muestra las opciones del modo de uso compartido](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="384b9-120">Activar o desactivar la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="384b9-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="384b9-121">**Permitir que un participante pueda ceder o solicitar el control** : permite a los miembros del equipo ceder o solicitar el control del escritorio o de la aplicación del moderador.</span><span class="sxs-lookup"><span data-stu-id="384b9-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="384b9-122">**Permitir que un participante externo pueda ceder o solicitar el control** : permite a los invitados y a los usuarios externos (federados) ceder o solicitar el control del escritorio o de la aplicación del moderador.</span><span class="sxs-lookup"><span data-stu-id="384b9-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="384b9-123">**Permitir el uso compartido de PowerPoint** : permite a los usuarios crear reuniones que permiten que las presentaciones de PowerPoint se carguen y compartan.</span><span class="sxs-lookup"><span data-stu-id="384b9-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="384b9-124">**Permitir pizarra** : permite a los usuarios compartir una pizarra.</span><span class="sxs-lookup"><span data-stu-id="384b9-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="384b9-125">**Permitir notas compartidas** : permite a los usuarios tomar notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="384b9-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="384b9-126">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="384b9-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="384b9-127">Usar PowerShell para configurar el escritorio compartido</span><span class="sxs-lookup"><span data-stu-id="384b9-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="384b9-128">También puede usar el cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="384b9-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="384b9-129">Establezca los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="384b9-129">Set the following parameters:</span></span>

- <span data-ttu-id="384b9-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="384b9-130">Description</span></span>
- <span data-ttu-id="384b9-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="384b9-131">ScreenSharingMode</span></span>
- <span data-ttu-id="384b9-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="384b9-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="384b9-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="384b9-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="384b9-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="384b9-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="384b9-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="384b9-135">AllowWhiteboard</span></span>
- <span data-ttu-id="384b9-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="384b9-136">AllowSharedNotes</span></span>

<span data-ttu-id="384b9-137">[Más información sobre cómo usar el cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="384b9-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>


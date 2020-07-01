---
title: Activar o desactivar los anuncios de entrada y salida de las reuniones de Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Administrador puede aprender a activar o desactivar los anuncios de entrada y salida en una reunión de Microsoft Teams.
ms.openlocfilehash: ae2e8936b3fe0dbac0ba0d6ad7bfad3ab2e322ef
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938559"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="b9df3-103">Activar o desactivar los anuncios de entrada y salida para las reuniones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9df3-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="b9df3-104">Si está configurando conferencias de audio en Microsoft 365 u Office 365, recibirá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="b9df3-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="b9df3-105">Un puente de conferencia puede contener uno o varios números de teléfono que los contactos usarán para llamar a una reunión de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9df3-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="b9df3-106">El puente de conferencia responderá a las llamadas de los usuarios que llamen a una reunión con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="b9df3-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="b9df3-107">El puente de conferencia responde a la persona que llama con avisos de voz de un operador automático de conferencia y, luego, según cuál sea su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que registren sus nombres y configurar la seguridad del PIN.</span><span class="sxs-lookup"><span data-stu-id="b9df3-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="b9df3-108">El PIN se ofrece al organizador de la reunión de Microsoft Teams para que pueda iniciar una reunión si no puede hacerlo con la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9df3-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="b9df3-109">Sin embargo, puede configurarlo para que no se solicite al iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="b9df3-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="b9df3-110">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="b9df3-110">Setting meeting join options</span></span>

<span data-ttu-id="b9df3-111">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b9df3-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="b9df3-112">Debe ser administrador para realizar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="b9df3-112">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="b9df3-113">Inicie sesión en el centro de administración en  <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="b9df3-113">Log in to the admin center at <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b9df3-114">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="b9df3-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

3. <span data-ttu-id="b9df3-115">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="b9df3-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

4. <span data-ttu-id="b9df3-116">En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="b9df3-116">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="b9df3-117">Esta es la opción seleccionada de forma predeterminada,</span><span class="sxs-lookup"><span data-stu-id="b9df3-117">This is selected by default.</span></span> <span data-ttu-id="b9df3-118">pero, si la desactiva, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre en la reunión o la abandone.</span><span class="sxs-lookup"><span data-stu-id="b9df3-118">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="b9df3-119">En **Tipo de anuncio de entrada o salida**, seleccione **Nombres o números de teléfono** o **Tonos**.</span><span class="sxs-lookup"><span data-stu-id="b9df3-119">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b9df3-120">De forma predeterminada, los participantes externos no pueden ver los números de teléfono de los participantes marcados.</span><span class="sxs-lookup"><span data-stu-id="b9df3-120">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="b9df3-121">Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** de **entrada/salida tipo de anuncio** (esto evita que los Teams lean los números).</span><span class="sxs-lookup"><span data-stu-id="b9df3-121">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>
    
6. <span data-ttu-id="b9df3-122">Si ha elegido **Nombres o números de teléfono**, habilite o deshabilite **Pida a los autores de llamadas que registren su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="b9df3-122">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="b9df3-123">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9df3-123">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b9df3-124">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b9df3-124">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b9df3-125">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="b9df3-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b9df3-126">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="b9df3-126">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b9df3-127">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="b9df3-127">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b9df3-128">¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b9df3-128">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b9df3-129">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9df3-129">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b9df3-130">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b9df3-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b9df3-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b9df3-131">Related topics</span></span>

[<span data-ttu-id="b9df3-132">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b9df3-132">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)

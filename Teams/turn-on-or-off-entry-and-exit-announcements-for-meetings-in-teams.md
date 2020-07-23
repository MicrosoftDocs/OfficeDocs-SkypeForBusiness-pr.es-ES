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
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372209"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="2171d-103">Activar o desactivar los anuncios de entrada y salida para las reuniones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2171d-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="2171d-104">Si está configurando conferencias de audio en Microsoft 365 u Office 365, recibirá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="2171d-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="2171d-105">Un puente de conferencia puede contener uno o varios números de teléfono que los contactos usarán para llamar a una reunión de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2171d-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="2171d-106">El puente de conferencia responderá a las llamadas de los usuarios que llamen a una reunión con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="2171d-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="2171d-107">El puente de conferencia responde a la persona que llama con avisos de voz de un operador automático de conferencia y, luego, según cuál sea su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que registren sus nombres y configurar la seguridad del PIN.</span><span class="sxs-lookup"><span data-stu-id="2171d-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="2171d-108">El PIN se ofrece al organizador de la reunión de Microsoft Teams para que pueda iniciar una reunión si no puede hacerlo con la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2171d-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="2171d-109">Sin embargo, puede configurarlo para que no se solicite al iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="2171d-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="2171d-110">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="2171d-110">Setting meeting join options</span></span>

<span data-ttu-id="2171d-111">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="2171d-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="2171d-112">Para realizar estos cambios, debe ser administrador del servicio de Teams.</span><span class="sxs-lookup"><span data-stu-id="2171d-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="2171d-113">Consulte [usar los roles de administrador de Teams para administrar los equipos](https://docs.microsoft.com/microsoftteams/using-admin-roles) para obtener información sobre cómo obtener roles y permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="2171d-113">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="2171d-114">Inicie sesión en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="2171d-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="2171d-115">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2171d-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="2171d-116">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="2171d-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="2171d-117">En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="2171d-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="2171d-118">Esta es la opción seleccionada de forma predeterminada,</span><span class="sxs-lookup"><span data-stu-id="2171d-118">This is selected by default.</span></span> <span data-ttu-id="2171d-119">pero, si la desactiva, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre en la reunión o la abandone.</span><span class="sxs-lookup"><span data-stu-id="2171d-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="2171d-120">En **Tipo de anuncio de entrada o salida**, seleccione **Nombres o números de teléfono** o **Tonos**.</span><span class="sxs-lookup"><span data-stu-id="2171d-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2171d-121">De forma predeterminada, los participantes externos no pueden ver los números de teléfono de los participantes marcados.</span><span class="sxs-lookup"><span data-stu-id="2171d-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="2171d-122">Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** de **entrada/salida tipo de anuncio** (esto evita que los Teams lean los números).</span><span class="sxs-lookup"><span data-stu-id="2171d-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="2171d-123">Si ha elegido **Nombres o números de teléfono**, habilite o deshabilite **Pida a los autores de llamadas que registren su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="2171d-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="2171d-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2171d-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2171d-125">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2171d-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="2171d-126">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="2171d-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2171d-127">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="2171d-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2171d-128">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="2171d-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="2171d-129">¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2171d-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="2171d-130">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2171d-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="2171d-131">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="2171d-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2171d-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2171d-132">Related topics</span></span>

[<span data-ttu-id="2171d-133">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="2171d-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)

---
title: Activar o desactivar los anuncios de entrada y salida para las reuniones en Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda cómo se activan o se desactivan los anuncios de entrada y salida en una reunión de Microsoft Teams. '
ms.openlocfilehash: a646718d861737435244ee43c7206402f602f63c
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012460"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="0c78b-103">Activar o desactivar los anuncios de entrada y salida para las reuniones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c78b-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="0c78b-104">Cuando vaya a configurar una audioconferencia en Office 365, recibirá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="0c78b-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="0c78b-105">Un puente de conferencia puede contener uno o varios números de teléfono que los contactos usarán para llamar a una reunión de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0c78b-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="0c78b-106">El puente de conferencia responderá a las llamadas de los usuarios que llamen a una reunión con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="0c78b-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="0c78b-107">El puente de conferencia responde a la persona que llama con avisos de voz de un operador automático de conferencia y, luego, según cuál sea su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que registren sus nombres y configurar la seguridad del PIN.</span><span class="sxs-lookup"><span data-stu-id="0c78b-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="0c78b-108">El PIN se ofrece al organizador de la reunión de Microsoft Teams para que pueda iniciar una reunión si no puede hacerlo con la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0c78b-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="0c78b-109">Sin embargo, puede configurarlo para que no se solicite al iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="0c78b-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="0c78b-110">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="0c78b-110">Setting meeting join options</span></span>

1. <span data-ttu-id="0c78b-111">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="0c78b-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0c78b-112">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="0c78b-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="0c78b-113">En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="0c78b-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="0c78b-114">Esta es la opción seleccionada de forma predeterminada,</span><span class="sxs-lookup"><span data-stu-id="0c78b-114">This is selected by default.</span></span> <span data-ttu-id="0c78b-115">pero, si la desactiva, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre en la reunión o la abandone.</span><span class="sxs-lookup"><span data-stu-id="0c78b-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="0c78b-116">En **Tipo de anuncios de entrada/salida**, seleccione **Nombres o números de teléfono** o **Tonos**.</span><span class="sxs-lookup"><span data-stu-id="0c78b-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="0c78b-117">Si ha elegido **Nombres o números de teléfono**, habilite o deshabilite **Pida a los autores de llamadas que registren su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="0c78b-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="0c78b-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c78b-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0c78b-119">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0c78b-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0c78b-p104">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="0c78b-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0c78b-123">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="0c78b-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0c78b-124">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c78b-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0c78b-125">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0c78b-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0c78b-126">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0c78b-126">Related topics</span></span>

[<span data-ttu-id="0c78b-127">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="0c78b-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)

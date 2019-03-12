---
title: Iniciar una audioconferencia por teléfono sin PIN en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos puedan unirse a una reunión desde el Centro de administración de Teams. '
ms.openlocfilehash: 5f2dbd84b71058e75b710f37994e41c9adb488ef
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542426"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="48e6a-103">Iniciar una audioconferencia por teléfono sin PIN en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48e6a-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="48e6a-104">Puede resultar frustrante para los usuarios que la llamada local a una reunión se mantenga en espera en la sala de espera de la reunión mientras se reproduce música, porque el organizador de la reunión de Microsoft Teams no haya iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="48e6a-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="48e6a-105">Si un organizador de la reunión llama a la reunión, de manera predeterminada, se le pedirá un PIN para iniciarla.</span><span class="sxs-lookup"><span data-stu-id="48e6a-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="48e6a-106">Pero puede configurarla para que cualquier usuario pueda entrar en la reunión con una llamada sin que se le pida el PIN para iniciarla.</span><span class="sxs-lookup"><span data-stu-id="48e6a-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="48e6a-107">Puede usar el centro de administración para habilitar o deshabilitar este parámetro para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="48e6a-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="48e6a-108">El organizador de la reunión no necesita el PIN si otra persona ha iniciado la reunión desde la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="48e6a-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="48e6a-109">Solo será necesario si el organizador de la reunión se une a ella a través de un teléfono.</span><span class="sxs-lookup"><span data-stu-id="48e6a-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="48e6a-110">El PIN para reuniones se envía al usuarios de audioconferencias cuando se le asigna la licencia de **Audioconferencia** o cuando se habilita para estas.</span><span class="sxs-lookup"><span data-stu-id="48e6a-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="48e6a-111">Consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) y [Correos electrónicos que se envían de forma automática a los usuarios cuando cambia la configuración de Audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="48e6a-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="48e6a-112">Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a una reunión</span><span class="sxs-lookup"><span data-stu-id="48e6a-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="48e6a-113">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="48e6a-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="48e6a-114">En el panel de navegación izquierdo, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="48e6a-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="48e6a-115">Seleccione un usuario de la lista y haga clic en **Editar** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="48e6a-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="48e6a-116">Junto a **Audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="48e6a-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="48e6a-117">En el panel **Audioconferencia**, habilite o deshabilite **Los autores de llamada sin autenticar pueden ser los primeros en unirse a una reunión**.</span><span class="sxs-lookup"><span data-stu-id="48e6a-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="48e6a-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="48e6a-118">Click **Save**.</span></span> 

<span data-ttu-id="48e6a-119">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="48e6a-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="48e6a-120">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="48e6a-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="48e6a-121">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="48e6a-121">What else should you know?</span></span>

- <span data-ttu-id="48e6a-122">Si desea restablecer el PIN, consulte [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="48e6a-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="48e6a-123">Si se ha habilitado el acceso anónimo o la posibilidad de iniciar una reunión sin PIN:</span><span class="sxs-lookup"><span data-stu-id="48e6a-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="48e6a-124">Si la reunión no ha empezado (no hay nadie todavía en la reunión): se le preguntará al autor de la llamada si es el organizador. Si indica que lo es, se le solicitará el PIN. La reunión se iniciará cuando lo especifique y el usuario se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="48e6a-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="48e6a-125">Si la reunión ha empezado (ya hay personas en la reunión): no se le preguntará al autor de la llamada si es el organizador y en ningún momento se le solicitará el PIN. La reunión ya ha empezado y el autor de la llamada se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="48e6a-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="48e6a-126">Si se ha deshabilitado el acceso anónimo o no se solicita el PIN para iniciar una reunión:</span><span class="sxs-lookup"><span data-stu-id="48e6a-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="48e6a-127">Si la reunión no ha empezado (no hay nadie todavía en la reunión): no se le preguntará al autor de la llamada si es el organizador y en ningún momento se le solicitará el PIN.</span><span class="sxs-lookup"><span data-stu-id="48e6a-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="48e6a-128">Como la configuración del organizador estará desactivada, la reunión se iniciará y los autores de llamada anónimos se unirán a ella.</span><span class="sxs-lookup"><span data-stu-id="48e6a-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="48e6a-129">Si la reunión ha empezado (ya hay personas en la reunión): no se le preguntará al autor de la llamada si es el organizador y en ningún momento se le solicitará el PIN. La reunión ya ha empezado y el autor de la llamada se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="48e6a-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="48e6a-130">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="48e6a-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="48e6a-p104">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="48e6a-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="48e6a-134">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="48e6a-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="48e6a-135">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48e6a-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="48e6a-136">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="48e6a-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="48e6a-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="48e6a-137">Related topics</span></span>

[<span data-ttu-id="48e6a-138">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="48e6a-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

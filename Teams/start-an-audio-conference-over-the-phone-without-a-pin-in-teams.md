---
title: Iniciar audioconferencia por teléfono sin un PIN en Teams
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Obtenga información sobre cómo habilitar o deshabilitar a los autores de llamadas anónimos para que no se unan a una reunión desde el Teams de administración. '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116968"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="bd369-103">Iniciar una audioconferencia por teléfono sin PIN en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd369-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="bd369-104">Puede resultar frustrante que los usuarios que llamen a una reunión se celebre en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Microsoft Teams no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="bd369-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="bd369-105">Si un organizador de la reunión llama a la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="bd369-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="bd369-106">Puede configurarlo para que cualquier persona pueda llamar a una reunión y no se le pida un PIN para iniciar la reunión.</span><span class="sxs-lookup"><span data-stu-id="bd369-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="bd369-107">Puede usar el Centro de administración para habilitar o deshabilitar esta configuración para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="bd369-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="bd369-108">No es necesario un PIN para el organizador de la reunión si alguien ha iniciado la reunión desde la aplicación Microsoft Teams reunión.</span><span class="sxs-lookup"><span data-stu-id="bd369-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="bd369-109">El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono.</span><span class="sxs-lookup"><span data-stu-id="bd369-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="bd369-110">El PIN de las reuniones se envía al usuario de audio cuando se les asigna la licencia de **conferencias** de audio y se habilitan para conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="bd369-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="bd369-111">Vea [Enviar un correo electrónico a](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) un usuario con su información de audioconferencia y Correos electrónicos que se envían automáticamente a los usuarios cuando cambia la configuración de audioconferencia. [](emails-sent-to-users-when-their-settings-change-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bd369-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="bd369-112">Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión</span><span class="sxs-lookup"><span data-stu-id="bd369-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="bd369-113">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="bd369-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bd369-114">En el panel de navegación izquierdo, haga clic en **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="bd369-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="bd369-115">Seleccione un usuario en la lista y, a continuación, haga clic **en Editar** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="bd369-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="bd369-116">Junto a **Audioconferencia,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="bd369-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="bd369-117">En el **panel Audioconferencia,** habilitar o deshabilitar las llamadas de acceso telefónico local puede ser la primera persona **de una reunión.**</span><span class="sxs-lookup"><span data-stu-id="bd369-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="bd369-118">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="bd369-118">Click **Apply**.</span></span> 

<span data-ttu-id="bd369-119">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="bd369-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="bd369-120">Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bd369-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="bd369-121">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="bd369-121">What else should you know?</span></span>

- <span data-ttu-id="bd369-122">Si desea restablecer el PIN, vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bd369-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="bd369-123">Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="bd369-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="bd369-124">Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): se le pedirá a un autor de la llamada si es el organizador; si dice que sí, se le pedirá su PIN y, después de introducir el PIN, se iniciará la reunión y el usuario se unirá a la reunión.</span><span class="sxs-lookup"><span data-stu-id="bd369-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="bd369-125">Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a un autor de la llamada si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="bd369-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="bd369-126">Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está habilitado:</span><span class="sxs-lookup"><span data-stu-id="bd369-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="bd369-127">Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="bd369-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="bd369-128">Como la configuración del organizador está desactivada, la reunión se iniciará y los autores de llamadas anónimos se unirán a la reunión.</span><span class="sxs-lookup"><span data-stu-id="bd369-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="bd369-129">Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="bd369-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bd369-130">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bd369-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bd369-131">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="bd369-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bd369-132">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="bd369-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="bd369-133">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="bd369-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd369-134">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="bd369-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="bd369-135">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="bd369-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="bd369-136">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="bd369-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bd369-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bd369-137">Related topics</span></span>

[<span data-ttu-id="bd369-138">Pruebe o compre Audioconferencia en Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="bd369-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
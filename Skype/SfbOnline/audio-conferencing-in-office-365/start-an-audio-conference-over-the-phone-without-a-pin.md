---
title: Iniciar una audioconferencia por teléfono sin un PIN en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 6eb62e2a2a295644185b3f0e6fd424749dc5bf56
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111946"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="7cc9d-103">Iniciar una audioconferencia por teléfono sin un PIN en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7cc9d-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="7cc9d-104">Para obtener información sobre cómo iniciar una audioconferencia sin un PIN en Microsoft Teams, vea Iniciar una conferencia de audio por teléfono sin [un PIN en Microsoft Teams.](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)</span><span class="sxs-lookup"><span data-stu-id="7cc9d-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="7cc9d-105">Puede ser frustrante que los usuarios que llamen a una reunión se celebre en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Skype Empresarial no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="7cc9d-106">Si un organizador de la reunión llama a la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="7cc9d-107">Puede configurarlo para que cualquier persona pueda llamar a una reunión y no se le pida un PIN para iniciar la reunión.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="7cc9d-108">Puede usar el Centro de administración de Skype Empresarial para habilitar o deshabilitar este parámetro para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="7cc9d-109">No se requiere un PIN para el organizador de la reunión si alguien ha iniciado la reunión desde la aplicación de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="7cc9d-110">El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="7cc9d-111">El PIN de las reuniones se envía al usuario de audio cuando se les asigna la licencia de **conferencias** de audio y se habilitan para conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="7cc9d-112">Vea [Enviar un correo electrónico a](send-an-email-to-a-user-with-their-dial-in-information.md) un usuario con su información de audioconferencia y Correos electrónicos que se envían automáticamente a los usuarios cuando cambia la configuración de audioconferencia. [](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="7cc9d-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="7cc9d-113">Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión</span><span class="sxs-lookup"><span data-stu-id="7cc9d-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="7cc9d-114">En el **Centro de administración de Skype Empresarial,** en el panel de navegación izquierdo, vaya a Usuarios de **audioconferencia.**  >  </span><span class="sxs-lookup"><span data-stu-id="7cc9d-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="7cc9d-115">En la lista, seleccione el usuario y, en el panel de acciones, haga clic **en Editar.**</span><span class="sxs-lookup"><span data-stu-id="7cc9d-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="7cc9d-116">En la página de propiedades del usuario, en Opciones de **reunión,** seleccione o desactive Permitir que los autores de llamadas no autenticados sean los primeros en **una reunión. Si no es así, esperarán en** la sala de espera hasta que se una un usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="7cc9d-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="7cc9d-118">**Usar Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="7cc9d-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="7cc9d-119">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7cc9d-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="7cc9d-120">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="7cc9d-120">What else should you know?</span></span>

- <span data-ttu-id="7cc9d-121">Si desea restablecer el PIN, vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="7cc9d-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="7cc9d-122">Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="7cc9d-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="7cc9d-123">Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): se le pedirá a un autor de la llamada si es el organizador; si dice que sí, se le pedirá su PIN y, después de introducir el PIN, se iniciará la reunión y el usuario se unirá a la reunión.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="7cc9d-124">Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a un autor de la llamada si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="7cc9d-125">Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está habilitado:</span><span class="sxs-lookup"><span data-stu-id="7cc9d-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="7cc9d-126">Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="7cc9d-127">Como la configuración del organizador está desactivada, la reunión se iniciará y los autores de llamadas anónimos se unirán a la reunión.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="7cc9d-128">Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7cc9d-129">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7cc9d-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7cc9d-130">Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="7cc9d-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="7cc9d-131">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7cc9d-132">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7cc9d-133">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="7cc9d-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7cc9d-134">Por qué necesita usar Microsoft 365 u Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cc9d-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7cc9d-135">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7cc9d-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="7cc9d-136">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad frente solo al uso del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="7cc9d-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="7cc9d-137">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7cc9d-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="7cc9d-138">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7cc9d-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="7cc9d-139">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7cc9d-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="7cc9d-140">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7cc9d-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="7cc9d-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="7cc9d-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7cc9d-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7cc9d-143">Related topics</span></span>

[<span data-ttu-id="7cc9d-144">Probar o comprar audioconferencias en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="7cc9d-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
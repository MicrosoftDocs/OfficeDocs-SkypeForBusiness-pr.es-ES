---
title: Iniciar una conferencia de audio a través del teléfono sin un PIN en Skype empresarial online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 146a23c35bca8e313f193dbd1407990fc8c6a788
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "35535870"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="a2e88-103">Iniciar una conferencia de audio a través del teléfono sin un PIN en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="a2e88-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="a2e88-104">Para obtener información sobre cómo iniciar una conferencia de audio sin un PIN en Microsoft Teams, consulte [iniciar una conferencia de audio a través del teléfono sin un PIN en Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a2e88-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="a2e88-105">Es posible que sea frustrante para los usuarios que llaman a una reunión en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Skype empresarial no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="a2e88-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="a2e88-106">Si un organizador de la reunión llama a la reunión, de forma predeterminada, se necesita un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="a2e88-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="a2e88-107">Puede configurarlo para que cualquier persona pueda llamar a una reunión y no se le pida un PIN para iniciar la reunión.</span><span class="sxs-lookup"><span data-stu-id="a2e88-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="a2e88-108">Puede usar el Centro de administración de Skype Empresarial para habilitar o deshabilitar este parámetro para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="a2e88-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="a2e88-109">Si alguien ha iniciado la reunión desde la aplicación Skype empresarial, no es necesario un PIN para el organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a2e88-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="a2e88-110">El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono.</span><span class="sxs-lookup"><span data-stu-id="a2e88-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="a2e88-111">El PIN para las reuniones se envía al usuario de audio cuando se le asigna \*\*\*\* la licencia de audioconferencias y está habilitado para las conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="a2e88-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a2e88-112">Consulte [Enviar un correo electrónico a un usuario con la información de la audioconferencia y los](send-an-email-to-a-user-with-their-dial-in-information.md) [correos electrónicos que se envían de forma automática a los usuarios cuando cambia la configuración de audioconferencia](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="a2e88-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="a2e88-113">Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión</span><span class="sxs-lookup"><span data-stu-id="a2e88-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="a2e88-114">En el **centro de administración de Skype empresarial**, en el navegación de la izquierda, vaya a**usuarios**de **conferencias** > de audio.</span><span class="sxs-lookup"><span data-stu-id="a2e88-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="a2e88-115">En la lista, seleccione el usuario y, en el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a2e88-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="a2e88-116">En la página de propiedades del usuario, en **Opciones de reunión**, Active o desactive permitir que **los autores de llamadas no autenticados sean las primeras personas de una reunión. En caso contrario, esperarán en la sala de espera hasta que se unan un usuario autenticado**.</span><span class="sxs-lookup"><span data-stu-id="a2e88-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="a2e88-117">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="a2e88-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="a2e88-118">**Usar Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a2e88-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="a2e88-119">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2e88-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="a2e88-120">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="a2e88-120">What else should you know?</span></span>

- <span data-ttu-id="a2e88-121">Si desea restablecer el PIN, consulte [restablecer el PIN de audioconferencia](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="a2e88-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="a2e88-122">Si el acceso anónimo, o si no necesita un PIN para iniciar una reunión, está deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="a2e88-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="a2e88-123">Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): se preguntará a una persona que llame si es el organizador. Si dice sí, se le solicitará su PIN y, después de especificar el PIN, la reunión se iniciará y el usuario se unirá a la reunión.</span><span class="sxs-lookup"><span data-stu-id="a2e88-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="a2e88-124">Si la reunión ya ha comenzado (otra persona ya está en la reunión): no se le pedirá la llamada si es el organizador y nunca se le solicitará el PIN. la reunión ya se ha iniciado y la persona que llama se une.</span><span class="sxs-lookup"><span data-stu-id="a2e88-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="a2e88-125">Si el acceso anónimo, o si no necesita un PIN para iniciar una reunión, está habilitado:</span><span class="sxs-lookup"><span data-stu-id="a2e88-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="a2e88-126">Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): no se le solicitará al autor de la llamada si es el organizador, y nunca se le pedirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="a2e88-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="a2e88-127">Puesto que la configuración del organizador está deshabilitada, la reunión se iniciará y los autores de llamadas anónimos se unirán a la reunión.</span><span class="sxs-lookup"><span data-stu-id="a2e88-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="a2e88-128">Si la reunión ya ha comenzado (otra persona ya está en la reunión): no se le solicitará una llamada si es el organizador, y nunca se le pedirá el PIN; la reunión ya se ha iniciado, y el autor de la llamada se unirá a ella.</span><span class="sxs-lookup"><span data-stu-id="a2e88-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a2e88-129">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a2e88-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a2e88-130">Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="a2e88-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="a2e88-p104">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="a2e88-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a2e88-134">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="a2e88-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a2e88-135">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2e88-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a2e88-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="a2e88-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a2e88-138">An introduction to Windows PowerShell and Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a2e88-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="a2e88-139">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a2e88-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a2e88-140">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a2e88-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a2e88-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="a2e88-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a2e88-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a2e88-143">Related topics</span></span>

[<span data-ttu-id="a2e88-144">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="a2e88-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

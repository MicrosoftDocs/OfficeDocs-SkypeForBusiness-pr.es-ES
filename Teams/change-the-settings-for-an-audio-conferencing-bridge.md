---
title: Cambiar la configuración de un puente de Audioconferencias.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Cambie la configuración del puente de audioconferencia, incluidas las notificaciones de entrada y salida, reproducir nombres o números de teléfono, tonos y pedir a los autores de llamadas que graben su nombre.
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102647"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="77d90-103">Cambiar la configuración de un puente de Audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="77d90-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="77d90-104">Al configurar las audioconferencias en Microsoft 365 o Office 365, recibirá números de teléfono para los usuarios de lo que se denomina un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="77d90-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="77d90-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="77d90-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="77d90-106">Estos números de teléfono se usan cuando las personas que llaman llaman a una reunión.</span><span class="sxs-lookup"><span data-stu-id="77d90-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="77d90-107">El número de teléfono se incluye en la parte inferior de la Skype Empresarial o Microsoft Teams reunión.</span><span class="sxs-lookup"><span data-stu-id="77d90-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="77d90-108">El puente de conferencia responde a una llamada y le pide al autor de la llamada mensajes de voz con un operador automático de reunión y, después, según la configuración, puede reproducir notificaciones, pedir a los autores de llamadas que graben su nombre y controlar la configuración del PIN.</span><span class="sxs-lookup"><span data-stu-id="77d90-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="77d90-109">Los PIN se entregan a los organizadores de la reunión para permitirles iniciar una reunión cuando no están usando una Skype Empresarial o Microsoft Teams aplicación.</span><span class="sxs-lookup"><span data-stu-id="77d90-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="77d90-110">Solo se requiere un PIN para el organizador de la reunión cuando un Skype Empresarial o Microsoft Teams de la aplicación aún no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="77d90-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="77d90-111">Si todos los usuarios están iniciando sesión en la reunión, el PIN es necesario para que el organizador de la reunión inicie la reunión.</span><span class="sxs-lookup"><span data-stu-id="77d90-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="77d90-113">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77d90-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="77d90-114">En el panel de navegación izquierdo, vaya a **Puentes de conferencia**  >  **reuniones.**</span><span class="sxs-lookup"><span data-stu-id="77d90-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="77d90-115">En la parte superior de la **página Puentes de conferencia,** haga clic en **Configuración de puente.**</span><span class="sxs-lookup"><span data-stu-id="77d90-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="77d90-116">En el **panel Configuración de puente,** seleccione:</span><span class="sxs-lookup"><span data-stu-id="77d90-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="77d90-117">**Notificaciones de entrada y salida de la reunión** Si desactiva esta opción, los usuarios que ya se han unido a la reunión no se notificarán cuando alguien entre o abandone la reunión.</span><span class="sxs-lookup"><span data-stu-id="77d90-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="77d90-118">Al activar las notificaciones **de entrada y salida de la** reunión, puede seleccionar estas opciones:</span><span class="sxs-lookup"><span data-stu-id="77d90-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="77d90-119">**Nombres o números de teléfono** Cuando los usuarios llamen a una reunión, su número de teléfono se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="77d90-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="77d90-120">**Tonos** Cuando los usuarios llamen a una reunión, se reproducirá un tono de audio cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="77d90-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="77d90-121">**Pedir a los autores de llamadas que graben su nombre antes de unirse a la reunión** Si desactiva esta opción, no se pedirá a los autores de llamadas que graben su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="77d90-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="77d90-122">Para establecer la longitud del PIN para las reuniones, seleccione el número de dígitos que desea para el PIN en la lista **longitud del PIN.**</span><span class="sxs-lookup"><span data-stu-id="77d90-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="77d90-123">Para especificar si desea enviar correo electrónico a los usuarios, habilite o deshabilite Enviar automáticamente correos electrónicos a los usuarios si cambia la configuración de las **audioconferencias.**</span><span class="sxs-lookup"><span data-stu-id="77d90-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="77d90-124">Vea [Correos electrónicos enviados](emails-sent-to-users-when-their-settings-change-in-teams.md) automáticamente a los usuarios cuando la configuración de audioconferencia cambia en Microsoft Teams o Correos electrónicos enviados a los usuarios cuando la configuración cambia [en Skype Empresarial Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="77d90-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="77d90-125">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="77d90-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="77d90-126">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="77d90-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="77d90-127">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)</span><span class="sxs-lookup"><span data-stu-id="77d90-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="77d90-128">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="77d90-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="77d90-129">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="77d90-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="77d90-130">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="77d90-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77d90-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="77d90-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="77d90-132">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="77d90-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="77d90-133">Windows PowerShell tiene muchas ventajas en la velocidad, la sencillez y la productividad sobre el uso del centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="77d90-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="77d90-134">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="77d90-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="77d90-135">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77d90-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="77d90-136">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77d90-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="77d90-137">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77d90-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="77d90-p107">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="77d90-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="77d90-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="77d90-140">Related topics</span></span>

[<span data-ttu-id="77d90-141">Configurar audioconferencias en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77d90-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="77d90-142">Configurar audioconferencias para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77d90-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
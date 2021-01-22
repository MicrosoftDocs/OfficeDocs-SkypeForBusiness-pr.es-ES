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
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918712"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="1c144-103">Cambiar la configuración de un puente de Audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="1c144-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="1c144-p101">Al configurar Audioconferencia en Microsoft 365 u Office 365, recibirá números de teléfono para los usuarios de lo que se denomina un puente de audioconferencia. Un puente de conferencia puede contener uno o varios números de teléfono. Estos números de teléfono se usan cuando las personas que llaman llaman a una reunión. El número de teléfono se incluye en la parte inferior de la invitación a la reunión de Skype Empresarial o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1c144-p101">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="1c144-p102">El puente de conferencia responde una llamada y le pide al autor de la llamada avisos de voz con un operador automático de la reunión y, a continuación, según su configuración, puede reproducir notificaciones, pedir a los autores de las llamadas que graben sus nombres y controlar la configuración del PIN. Los NÚMEROS PIN se entregan a los organizadores de la reunión para permitirles iniciar una reunión cuando no estén usando una aplicación de Skype Empresarial o de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1c144-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1c144-p103">Solo es necesario un PIN para el organizador de la reunión cuando un usuario de la aplicación skype empresarial o de Microsoft Teams todavía no ha iniciado la reunión. Si todos los usuarios marcan para un acceso a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.</span><span class="sxs-lookup"><span data-stu-id="1c144-p103">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="1c144-113">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c144-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1c144-114">En el panel de navegación izquierdo, vaya **a puentes de**  >  **conferencias de reuniones.**</span><span class="sxs-lookup"><span data-stu-id="1c144-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="1c144-115">En la parte superior de la página **Puentes de** conferencia, haga clic en **Configuración de puente.**</span><span class="sxs-lookup"><span data-stu-id="1c144-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="1c144-116">En el **panel Configuración del** puente, seleccione:</span><span class="sxs-lookup"><span data-stu-id="1c144-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="1c144-117">**Notificaciones de entrada y salida de la reunión** Si lo desactiva, los usuarios que ya se han unido a la reunión no serán notificados cuando alguien se una o abandone la reunión.</span><span class="sxs-lookup"><span data-stu-id="1c144-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="1c144-118">Al activar las notificaciones **de entrada y salida de una** reunión, puede seleccionar estas opciones:</span><span class="sxs-lookup"><span data-stu-id="1c144-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="1c144-119">**Nombres o números de teléfono** Cuando los usuarios llamen a una reunión, se reproducirá su número de teléfono cuando se unan a esta.</span><span class="sxs-lookup"><span data-stu-id="1c144-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="1c144-120">**Tonos** Cuando los usuarios llamen a una reunión, se reproducirá un tono de audio cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="1c144-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="1c144-121">**Pedir a los autores de la llamada que graben su nombre antes de unirse a la reunión** Si desactiva esta opción, no se pedirá a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="1c144-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="1c144-122">Para establecer la longitud del PIN para las reuniones, seleccione el número de dígitos que desea para el PIN en la lista de longitud **del PIN.**</span><span class="sxs-lookup"><span data-stu-id="1c144-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="1c144-123">Para especificar si desea enviar correo electrónico a sus usuarios, habilite o deshabilite el envío automático de correos electrónicos a los usuarios si cambia la configuración **de las audioconferencias.**</span><span class="sxs-lookup"><span data-stu-id="1c144-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="1c144-124">Vea los correos electrónicos enviados automáticamente a los usuarios cuando cambia la configuración de [Audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md) en Microsoft Teams o los correos electrónicos enviados a los usuarios cuando cambia su configuración en Skype Empresarial [Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1c144-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="1c144-125">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1c144-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1c144-126">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1c144-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1c144-127">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsDialinConferencingBridge.](https://go.microsoft.com/fwlink/?LinkId=617686)</span><span class="sxs-lookup"><span data-stu-id="1c144-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="1c144-128">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="1c144-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1c144-129">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="1c144-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1c144-130">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="1c144-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1c144-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="1c144-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1c144-132">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c144-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1c144-133">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="1c144-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1c144-134">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c144-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1c144-135">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1c144-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1c144-136">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1c144-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1c144-137">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1c144-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1c144-p107">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="1c144-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1c144-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1c144-140">Related topics</span></span>

[<span data-ttu-id="1c144-141">Configurar audioconferencias en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c144-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="1c144-142">Configurar Audioconferencia para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1c144-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

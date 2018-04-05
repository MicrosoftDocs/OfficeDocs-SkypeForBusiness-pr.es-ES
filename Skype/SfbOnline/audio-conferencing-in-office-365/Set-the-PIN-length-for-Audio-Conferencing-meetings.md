---
title: Establecer la longitud del perno para las reuniones de conferencia de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: d8e6073bd60612131e54e10be6498370d8dfe3bb
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a><span data-ttu-id="eb505-103">Establecer la longitud del perno para las reuniones de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="eb505-103">Set the PIN length for Audio Conferencing meetings</span></span>

<span data-ttu-id="eb505-104">Cuando se configure conferencias de audio por Skype para negocios o Teams de Microsoft, obtendrá un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="eb505-104">When you are setting up audio conferencing for Skype for Business or Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="eb505-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="eb505-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="eb505-106">Establece el número de teléfono se incluyen en las invitaciones de la reunión de Skype para aplicaciones de negocios y Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eb505-106">The phone number you set will be included on the meeting invites for Skype for Business and Microsoft Teams apps.</span></span>
  
<span data-ttu-id="eb505-107">El puente de conferencia de audio responde a una llamada para las personas que llaman a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="eb505-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="eb505-108">Responde al llamador con indicaciones de voz de un operador automático y a continuación, dependiendo de la configuración, puede reproducir las notificaciones y solicitar los llamadores para registrar su nombre.</span><span class="sxs-lookup"><span data-stu-id="eb505-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="eb505-109">**Configuración de puente de Microsoft** le permiten cambiar la configuración de notificaciones de la reunión y unirse a la experiencia de la reunión y establecer la longitud de las clavijas que son utilizados por los organizadores de la reunión.</span><span class="sxs-lookup"><span data-stu-id="eb505-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="eb505-110">Organizadores de reuniones Utilice pines para iniciar reuniones si ellos no pueden unirse a la reunión mediante el Skype para la aplicación de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eb505-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business or Microsoft Teams app.</span></span>
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="eb505-111">Configurar la longitud del PIN</span><span class="sxs-lookup"><span data-stu-id="eb505-111">Setting the PIN length</span></span>

<span data-ttu-id="eb505-112">**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**</span><span class="sxs-lookup"><span data-stu-id="eb505-112">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="eb505-113">En la exploración de la izquierda, vaya a **reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="eb505-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="eb505-114">En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="eb505-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="eb505-115">En el panel de **configuración de puente** , en **longitud PIN**, seleccione el número de dígitos que desee para el PIN.</span><span class="sxs-lookup"><span data-stu-id="eb505-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="eb505-116">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="eb505-116">Click **Apply**.</span></span>

<span data-ttu-id="eb505-117">Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="eb505-117">**Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="eb505-118">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="eb505-118">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="eb505-119">En **seguridad** > **longitud PIN**, seleccione el número de dígitos que desee para el PIN y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="eb505-119">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb505-p103">Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="eb505-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 
  
## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="eb505-124">¿Desea saber más acerca de la configuración de PIN?</span><span class="sxs-lookup"><span data-stu-id="eb505-124">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="eb505-125">Pines pueden oscilar entre 4 y 12 dígitos; el valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="eb505-125">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="eb505-126">En la creación de un PIN solo pueden usarse números.</span><span class="sxs-lookup"><span data-stu-id="eb505-126">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="eb505-127">Por lo tanto, no pueden usarse letras ni caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="eb505-127">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="eb505-128">Un PIN sólo es necesario para el organizador de la reunión cuando un Skype para usuarios de negocios o Teams de Microsoft ya no ha iniciado la conferencia.</span><span class="sxs-lookup"><span data-stu-id="eb505-128">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="eb505-129">Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.</span><span class="sxs-lookup"><span data-stu-id="eb505-129">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="eb505-p106">La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente.</span><span class="sxs-lookup"><span data-stu-id="eb505-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="eb505-132">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="eb505-132">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="eb505-133">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="eb505-133">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="eb505-134">Para establecer el número de dígitos del PIN en 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="eb505-134">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="eb505-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="eb505-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eb505-138">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="eb505-138">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="eb505-139">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb505-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="eb505-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="eb505-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="eb505-142">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="eb505-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="eb505-143">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="eb505-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="eb505-144">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="eb505-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="eb505-145">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="eb505-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="eb505-p109">[Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="eb505-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb505-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb505-148">See also</span></span>

[<span data-ttu-id="eb505-149">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="eb505-149">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

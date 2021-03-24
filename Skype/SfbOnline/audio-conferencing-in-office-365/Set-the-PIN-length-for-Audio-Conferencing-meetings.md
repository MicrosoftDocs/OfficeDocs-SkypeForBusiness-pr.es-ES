---
title: Establecer la longitud del PIN para las reuniones de audioconferencia en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: a2acaad15712621c33b275e914263f6781178d9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100796"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="bb8c4-103">Establecer la longitud del PIN para las reuniones de audioconferencia en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb8c4-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="bb8c4-104">Para obtener información sobre cómo establecer la longitud del PIN en Microsoft Teams, vea Establecer la longitud del PIN para las reuniones [de audioconferencia en Microsoft Teams.](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)</span><span class="sxs-lookup"><span data-stu-id="bb8c4-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="bb8c4-105">Cuando esté configurando las audioconferencias para Skype Empresarial, recibirá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="bb8c4-106">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="bb8c4-107">El número de teléfono que establezca se incluirá en las invitaciones a la reunión para la aplicación de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="bb8c4-108">El puente de audio conferencia responde a una llamada de personas que están llamando a una reunión usando un teléfono.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="bb8c4-109">Responde al autor de la llamada con mensajes de voz de un operador automático y, después, según la configuración, puede reproducir notificaciones y pedir a los autores de llamadas que graben su nombre.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="bb8c4-110">**La configuración del** puente de Microsoft le permite cambiar la configuración de las notificaciones de reunión y la experiencia de unirse a la reunión, y establecer la longitud de los PIN que usan los organizadores de la reunión.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="bb8c4-111">Los organizadores de la reunión usan NÚMEROS PIN para iniciar reuniones si no pueden unirse a la reunión con la aplicación de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="bb8c4-112">Configurar la longitud del PIN</span><span class="sxs-lookup"><span data-stu-id="bb8c4-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="bb8c4-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="bb8c4-114">En **Longitud del** PIN  >  **de** seguridad, seleccione el número de dígitos que desee para el PIN y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb8c4-p103">Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="bb8c4-119">¿Desea obtener más información sobre la configuración de PIN?</span><span class="sxs-lookup"><span data-stu-id="bb8c4-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="bb8c4-120">Los PIN pueden ser de 4 a 12 dígitos; el valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="bb8c4-121">En la creación de un PIN solo pueden usarse números.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="bb8c4-122">Por lo tanto, no pueden usarse letras ni caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="bb8c4-123">Solo se requiere un PIN para el organizador de la reunión cuando un usuario de Skype Empresarial aún no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="bb8c4-124">Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="bb8c4-p106">La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bb8c4-127">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bb8c4-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bb8c4-128">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span><span class="sxs-lookup"><span data-stu-id="bb8c4-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="bb8c4-129">Para establecer el número de dígitos del PIN en 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="bb8c4-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="bb8c4-130">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bb8c4-131">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="bb8c4-132">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bb8c4-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bb8c4-133">Por qué necesita usar Microsoft 365 u Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb8c4-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="bb8c4-134">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="bb8c4-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="bb8c4-135">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad frente solo al uso del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="bb8c4-136">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb8c4-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="bb8c4-137">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb8c4-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="bb8c4-138">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb8c4-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="bb8c4-139">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb8c4-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="bb8c4-140">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bb8c4-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="bb8c4-p109">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="bb8c4-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb8c4-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb8c4-143">See also</span></span>

[<span data-ttu-id="bb8c4-144">Probar o comprar audioconferencias en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="bb8c4-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
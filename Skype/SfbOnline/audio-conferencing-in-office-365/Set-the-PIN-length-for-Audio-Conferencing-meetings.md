---
title: Establecer la longitud PIN para las reuniones de conferencia de Audio en Skype para profesionales en línea
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: c5add9cff2855fd969b76d96647f05e6e6dab290
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883599"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="77b61-103">Establecer la longitud PIN para las reuniones de conferencia de Audio en Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="77b61-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="77b61-104">Para obtener información acerca de cómo establecer la longitud PIN en Microsoft Teams, vea [establecer la longitud PIN para las reuniones de conferencia de Audio en los equipos de Microsoft](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="77b61-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="77b61-105">Cuando se configure Servicios de audioconferencia por Skype para la empresa, obtendrá un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="77b61-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="77b61-106">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="77b61-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="77b61-107">Establece el número de teléfono se incluirá en la reunión de invitaciones para la Skype para la aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="77b61-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="77b61-108">El puente de conferencia de audio responde a una llamada para las personas que llaman a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="77b61-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="77b61-109">Atiende el autor de la llamada con mensajes de voz de un operador automático y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones y pida a los autores de llamadas para registrar su nombre.</span><span class="sxs-lookup"><span data-stu-id="77b61-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="77b61-110">**Configuración de puente de Microsoft** le permiten cambiar la configuración de las notificaciones de la reunión y experiencia al unirse a la reunión y establecer la longitud de los ejes que se usan por los organizadores de reuniones.</span><span class="sxs-lookup"><span data-stu-id="77b61-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="77b61-111">Los organizadores de reuniones Utilice PIN para iniciar reuniones si no puede unirse a la reunión utilizando el Skype para la aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="77b61-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="77b61-112">Configurar la longitud del PIN</span><span class="sxs-lookup"><span data-stu-id="77b61-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="77b61-113">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsof**.</span><span class="sxs-lookup"><span data-stu-id="77b61-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="77b61-114">En **seguridad** > **longitud PIN**, seleccione el número de dígitos que desee para el PIN y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="77b61-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="77b61-p103">Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="77b61-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="77b61-119">¿Desea saber más acerca de la configuración de NIP?</span><span class="sxs-lookup"><span data-stu-id="77b61-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="77b61-120">PIN pueden contener de 4 a 12 dígitos; el valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="77b61-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="77b61-121">En la creación de un PIN solo pueden usarse números.</span><span class="sxs-lookup"><span data-stu-id="77b61-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="77b61-122">Por lo tanto, no pueden usarse letras ni caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="77b61-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="77b61-123">Un PIN sólo es necesaria para el organizador de la reunión cuando un Skype para usuarios de empresa ya no ha comenzado la reunión.</span><span class="sxs-lookup"><span data-stu-id="77b61-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="77b61-124">Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.</span><span class="sxs-lookup"><span data-stu-id="77b61-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="77b61-p106">La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente.</span><span class="sxs-lookup"><span data-stu-id="77b61-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="77b61-127">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="77b61-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="77b61-128">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="77b61-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="77b61-129">Para establecer el número de dígitos del PIN en 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="77b61-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="77b61-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="77b61-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77b61-133">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="77b61-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="77b61-134">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77b61-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="77b61-p108">Windows PowerShell tiene muchas ventajas en velocidad, simplificidad y productividad respecto a utilizar únicamente el centro de administración de Office 365 como, por ejemplo, al realizar cambios de configuración para muchos usuarios en una única ubicación. Obtenga más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="77b61-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="77b61-137">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77b61-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="77b61-138">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77b61-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="77b61-139">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77b61-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="77b61-140">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77b61-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="77b61-p109">[Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="77b61-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77b61-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="77b61-143">See also</span></span>

[<span data-ttu-id="77b61-144">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="77b61-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

---
title: Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: Obtenga información sobre los parámetros para la duración y los requisitos de un PIN y vea cómo establecer la duración de las reuniones en Microsoft Teams.
ms.openlocfilehash: 50c6ffe31e673dc7573ebb27f0eeb2ca78a30918
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571276"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="38351-103">Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38351-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="38351-104">Cuando vaya a configurar una audioconferencia para Microsoft Teams, recibirá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="38351-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="38351-105">Un puente de conferencia puede contener uno o varios números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="38351-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="38351-106">El que defina se incluirá en las invitaciones a la reunión para la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38351-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="38351-107">El puente de audioconferencia responderá a las llamadas de las personas que llamen a una reunión con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="38351-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="38351-108">Responde a la persona que llama con avisos de voz de un operador automático y, luego, según cuál sea su configuración, puede reproducir notificaciones y solicitar a los autores de las llamadas que registren sus nombres.</span><span class="sxs-lookup"><span data-stu-id="38351-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="38351-109">En **Configuración de puente de Microsoft**, puede cambiar la configuración de las notificaciones de reunión y de la experiencia de unirse a esta, así como establecer la longitud de los PIN que usan los organizadores de la reunión.</span><span class="sxs-lookup"><span data-stu-id="38351-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="38351-110">Los organizadores de la reunión usan números PIN para iniciar reuniones si no pueden unirse a la reunión con la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38351-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="38351-111">Configurar la longitud del PIN</span><span class="sxs-lookup"><span data-stu-id="38351-111">Setting the PIN length</span></span>

<span data-ttu-id="38351-112">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="38351-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="38351-113">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="38351-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="38351-114">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="38351-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="38351-115">En el panel **configuración de puente** , en longitud del **PIN**, seleccione el número de dígitos que desee para el PIN.</span><span class="sxs-lookup"><span data-stu-id="38351-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="38351-116">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="38351-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="38351-p103">Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="38351-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="38351-121">¿Desea saber más sobre la configuración de PIN?</span><span class="sxs-lookup"><span data-stu-id="38351-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="38351-122">Los pin pueden estar entre 4 y 12 dígitos; el valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="38351-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="38351-123">En la creación de un PIN solo pueden usarse números.</span><span class="sxs-lookup"><span data-stu-id="38351-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="38351-124">Por lo tanto, no pueden usarse letras ni caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="38351-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="38351-125">Un PIN solo es necesario para el organizador de la reunión cuando un usuario de Microsoft Teams ya no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="38351-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="38351-126">Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.</span><span class="sxs-lookup"><span data-stu-id="38351-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="38351-p106">La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente.</span><span class="sxs-lookup"><span data-stu-id="38351-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="38351-129">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="38351-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="38351-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="38351-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="38351-133">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="38351-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="38351-134">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38351-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="38351-135">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="38351-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="38351-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="38351-136">Related topics</span></span>

[<span data-ttu-id="38351-137">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="38351-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

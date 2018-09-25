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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Conozca cuáles son los parámetros de longitud y los requisitos de un PIN, y vea cómo se configura la duración de las reuniones en Microsoft Teams.
ms.openlocfilehash: db7c62920dc7440cc8356dd3f5275dd551cdfd78
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014920"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="e0557-103">Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0557-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="e0557-104">Al establecer una conferencia de audio para Microsoft Teams, obtendrá un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="e0557-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="e0557-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e0557-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="e0557-106">Establece el número de teléfono se incluirá en la reunión de invitaciones para la aplicación Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0557-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="e0557-107">El puente de conferencia de audio responde a una llamada para las personas que llaman a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="e0557-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e0557-108">Atiende el autor de la llamada con mensajes de voz de un operador automático y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones y pida a los autores de llamadas para registrar su nombre.</span><span class="sxs-lookup"><span data-stu-id="e0557-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="e0557-109">**Configuración de puente de Microsoft** le permiten cambiar la configuración de las notificaciones de la reunión y experiencia al unirse a la reunión y establecer la longitud de los ejes que se usan por los organizadores de reuniones.</span><span class="sxs-lookup"><span data-stu-id="e0557-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="e0557-110">Los organizadores de reuniones Utilice PIN para iniciar reuniones si no puede unirse a la reunión mediante la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0557-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="e0557-111">Configurar la longitud del PIN</span><span class="sxs-lookup"><span data-stu-id="e0557-111">Setting the PIN length</span></span>

1. <span data-ttu-id="e0557-112">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="e0557-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="e0557-113">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="e0557-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="e0557-114">En el panel **Configuración de puente**, en **Longitud del PIN**, seleccione el número de dígitos que quiere que tenga el PIN.</span><span class="sxs-lookup"><span data-stu-id="e0557-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="e0557-115">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0557-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e0557-p103">Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="e0557-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="e0557-120">¿Quiere saber más sobre la configuración del PIN?</span><span class="sxs-lookup"><span data-stu-id="e0557-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="e0557-121">PIN pueden contener de 4 a 12 dígitos; el valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="e0557-121">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="e0557-122">En la creación de un PIN solo pueden usarse números.</span><span class="sxs-lookup"><span data-stu-id="e0557-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="e0557-123">Por lo tanto, no pueden usarse letras ni caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="e0557-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="e0557-124">Un PIN sólo es necesario para el organizador de la reunión cuando un usuario de Microsoft Teams ya no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="e0557-124">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="e0557-125">Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.</span><span class="sxs-lookup"><span data-stu-id="e0557-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="e0557-p106">La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente.</span><span class="sxs-lookup"><span data-stu-id="e0557-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e0557-128">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e0557-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e0557-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="e0557-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e0557-132">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="e0557-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e0557-133">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0557-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e0557-134">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e0557-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="e0557-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e0557-135">Related topics</span></span>

[<span data-ttu-id="e0557-136">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="e0557-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

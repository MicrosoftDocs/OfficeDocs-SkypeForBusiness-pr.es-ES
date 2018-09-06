---
title: Activar o desactivar la entrada y salir de anuncios para reuniones en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo activar la entrada y salir de anuncios activado o desactivado en una reunión de Microsoft Teams. '
ms.openlocfilehash: b1409c34adce4bdb32013c184e273072858d3322
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23781178"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="fae27-103">Activar o desactivar la entrada y salir de anuncios para reuniones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fae27-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="fae27-104">Cuando establece una audioconferencia en Office 365, obtendrá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="fae27-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="fae27-105">Un puente de conferencia puede contener uno o más números de teléfono que los usuarios utilizarán para llamar a en una reunión de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fae27-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="fae27-106">El puente de conferencia responde a una llamada de un usuario que se llama a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="fae27-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="fae27-107">El puente de conferencia responde el autor de la llamada con mensajes de voz de un operador automático de conferencia y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los autores de llamadas para registrar su nombre y configurar la seguridad de NIP.</span><span class="sxs-lookup"><span data-stu-id="fae27-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="fae27-108">Se concede un PIN al organizador de una reunión de Microsoft Teams, y les permite iniciar una reunión si no pueden iniciar la reunión mediante la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fae27-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="fae27-109">Sin embargo, lo puede establecer para que no sea necesario un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="fae27-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="fae27-110">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="fae27-110">Setting meeting join options</span></span>

1. <span data-ttu-id="fae27-111">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="fae27-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fae27-112">En la parte superior de la página de **Puentes de conferencia** , haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="fae27-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="fae27-113">En el panel **configuración de puente** , habilitar o deshabilitar la **entrada de la reunión y salir de las notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="fae27-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="fae27-114">Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fae27-114">This is selected by default.</span></span> <span data-ttu-id="fae27-115">Si se desactiva, los usuarios que ya se han unido a la reunión no recibirá una notificación cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="fae27-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="fae27-116">En **Tipo de anuncio de entrada o salida**, seleccione **Nombres o números de teléfono** o **Tonos**.</span><span class="sxs-lookup"><span data-stu-id="fae27-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="fae27-117">Si opta por **nombres o números de teléfono**, habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="fae27-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="fae27-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fae27-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fae27-119">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="fae27-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="fae27-p104">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="fae27-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fae27-123">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="fae27-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="fae27-124">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fae27-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="fae27-125">Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fae27-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fae27-126">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fae27-126">Related topics</span></span>

[<span data-ttu-id="fae27-127">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="fae27-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)

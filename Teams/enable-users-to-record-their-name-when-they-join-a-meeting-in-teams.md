---
title: Permitir a los usuarios grabar su nombre para una reunión
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Vea cómo puede habilitar o deshabilitar a los usuarios para que registren su nombre cuando se unan a una reunión en Microsoft Teams
ms.openlocfilehash: d7cab4fca4ad3e7732704da9837522d51314061d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691586"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="4ba24-103">Habilitar que los usuarios registren su nombre cuando se unan a una reunión en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ba24-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="4ba24-p101">Al configurar las conferencias de audio en Microsoft 365 u Office 365, recibirá números de teléfono y lo que se denomina un puente de audioconferencia. Un puente de conferencia puede contener uno o más números de teléfono que pueden ser un número de teléfono dedicado o compartido.</span><span class="sxs-lookup"><span data-stu-id="4ba24-p101">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="4ba24-p102">El puente de conferencia responde a la llamada de un usuario que llama a una reunión con un teléfono. Ese puente responde al autor de la llamada con avisos de voz de un operador automático y, luego, de acuerdo con su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que graben sus nombres y configura la seguridad del PIN para los organizadores de reuniones. Los PIN se proporcionan al organizador de la reunión y con ellos se puede empezar una reunión, pero puede configurarlo de modo que no se necesite un PIN para comenzar una reunión.</span><span class="sxs-lookup"><span data-stu-id="4ba24-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="4ba24-110">Establecer si los autores de las llamadas tienen que grabar sus nombres</span><span class="sxs-lookup"><span data-stu-id="4ba24-110">Set whether callers should record their name</span></span>

<span data-ttu-id="4ba24-111">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4ba24-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ba24-112">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="4ba24-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4ba24-113">En la parte superior de la página **puentes de conferencia** , haga clic en **configuración del puente**.</span><span class="sxs-lookup"><span data-stu-id="4ba24-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4ba24-114">Habilitar o deshabilitar las **notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="4ba24-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="4ba24-115">Si habilita las notificaciones, elija **nombres o números de teléfono** en **introducir/salir de tipo de anuncio**y luego Active las **personas que llaman para grabar su nombre antes de unirse a una reunión.**</span><span class="sxs-lookup"><span data-stu-id="4ba24-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="4ba24-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4ba24-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4ba24-117">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4ba24-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4ba24-118">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="4ba24-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4ba24-119">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="4ba24-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4ba24-120">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="4ba24-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4ba24-121">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba24-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4ba24-122">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ba24-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4ba24-123">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4ba24-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4ba24-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4ba24-124">Related topics</span></span>

[<span data-ttu-id="4ba24-125">Probar o comprar audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4ba24-125">Try or purchase Audio Conferencing</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

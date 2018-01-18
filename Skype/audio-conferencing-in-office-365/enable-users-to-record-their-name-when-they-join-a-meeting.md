---
title: "Permitir a los usuarios registrar su nombre cuando se unen a una reunión"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Obtenga información sobre cómo habilitar o deshabilitar si los usuarios pueden registrar sus nombres cuando se unen a una reunión "
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="1c79e-103">Permitir a los usuarios registrar su nombre cuando se unen a una reunión</span><span class="sxs-lookup"><span data-stu-id="1c79e-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="1c79e-104">Cuando configura la audioconferencia en Office 365, recibirá los números de teléfono y lo que se denomina un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="1c79e-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="1c79e-105">Un puente de conferencia puede contener uno o más números de teléfono que pueden ser un número de teléfono dedicado o compartido.</span><span class="sxs-lookup"><span data-stu-id="1c79e-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="1c79e-106">El puente de conferencia responde a una llamada de un usuario que está marcando a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="1c79e-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="1c79e-107">El puente de conferencia responde al llamador con indicaciones de voz de un operador automático y, a continuación, dependiendo de su configuración, puede reproducir las notificaciones, pida a los llamadores para registrar su nombre y configurar la seguridad de NIP para los organizadores de la reunión.</span><span class="sxs-lookup"><span data-stu-id="1c79e-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="1c79e-108">Pines se otorgan a los organizadores de la reunión para que puedan iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="1c79e-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="1c79e-109">Sin embargo, puede configurar, por lo que no requiere un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="1c79e-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="1c79e-110">Establecer si los llamadores deben registrar su nombre</span><span class="sxs-lookup"><span data-stu-id="1c79e-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="1c79e-111">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="1c79e-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1c79e-112">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="1c79e-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1c79e-113">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1c79e-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1c79e-114">En **experimentar join Meeting**, vea la casilla de verificación **Habilitar la entrada de la reunión y salir de notificaciones para activarse**.</span><span class="sxs-lookup"><span data-stu-id="1c79e-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="1c79e-115">**Seleccionado** Se pedirá a los llamadores para registrar su nombre antes de entrar en la reunión.</span><span class="sxs-lookup"><span data-stu-id="1c79e-115">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="1c79e-116">Esto está seleccionada por defecto.</span><span class="sxs-lookup"><span data-stu-id="1c79e-116">This is selected by default.</span></span>
    
  - <span data-ttu-id="1c79e-117">**Desactivada** Los llamadores no pedirá que registre su nombre antes de entrar en la reunión.</span><span class="sxs-lookup"><span data-stu-id="1c79e-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="1c79e-118">**Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="1c79e-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1c79e-119">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1c79e-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1c79e-120">Para ahorrar tiempo o automatizar esta tarea, puede utilizar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="1c79e-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="1c79e-121">Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="1c79e-121">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="1c79e-122">Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="1c79e-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1c79e-123">Para empezar a utilizar Windows PowerShell, consulte estos temas:</span><span class="sxs-lookup"><span data-stu-id="1c79e-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="1c79e-124">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="1c79e-124">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="1c79e-125">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="1c79e-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1c79e-126">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="1c79e-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1c79e-127">Obtenga información acerca de estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="1c79e-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1c79e-128">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1c79e-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1c79e-129">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1c79e-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1c79e-130">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1c79e-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1c79e-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="1c79e-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1c79e-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1c79e-133">Related topics</span></span>

[<span data-ttu-id="1c79e-134">Configurar Audioconferencia para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c79e-134">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)


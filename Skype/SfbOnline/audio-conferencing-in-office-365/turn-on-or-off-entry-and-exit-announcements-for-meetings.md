---
title: Activar o desactivar la entrada y salida de anuncios para reuniones en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Obtenga información sobre cómo activar o desactivar la entrada y salida de anuncios en una reunión de Skype for Business Online usando el centro de administración de Skype for Business. '
ms.openlocfilehash: f097563ca8dce47277a44573f2af66ed7f1539dd
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237576"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="6abed-103">Activar o desactivar la entrada y salida de anuncios para reuniones en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6abed-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="6abed-104">Para obtener información acerca de anuncios de entrada y salida en Microsoft Teams, vea [Activar o desactivar los anuncios de entrada y salida para las reuniones en Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="6abed-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="6abed-105">Al configurar conferencias de audio en Microsoft 365 o Office 365, recibirá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="6abed-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="6abed-106">Un puente de conferencia puede contener uno o más números de teléfono que los usuarios utilizarán para llamar a una reunión de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6abed-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="6abed-107">El puente de conferencia responderá a las llamadas de los usuarios que llamen a una reunión con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="6abed-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="6abed-108">El puente de conferencia responde a la persona que llama con avisos de voz de un operador automático de conferencia y, luego, según cuál sea su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que registren sus nombres y configurar la seguridad del PIN.</span><span class="sxs-lookup"><span data-stu-id="6abed-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="6abed-109">Se da un PIN a un organizador de Skype for Business, y este les permite iniciar una reunión si no pueden iniciar la reunión utilizando la aplicación de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6abed-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="6abed-110">Sin embargo, lo puede establecer para que no sea necesario un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="6abed-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="6abed-111">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="6abed-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="6abed-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="6abed-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="6abed-113">En **Experiencia de unirse a la** reunión, seleccione o desactive Habilitar las notificaciones de entrada y salida de la reunión para que se **activen.**</span><span class="sxs-lookup"><span data-stu-id="6abed-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="6abed-114">Esta es la opción seleccionada de forma predeterminada,</span><span class="sxs-lookup"><span data-stu-id="6abed-114">This is selected by default.</span></span> <span data-ttu-id="6abed-115">pero, si la desactiva, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre en la reunión o la abandone.</span><span class="sxs-lookup"><span data-stu-id="6abed-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="6abed-116">En **Tipo de anuncio de entrada o salida**, seleccione **Nombres o números de teléfono** o **Tonos**.</span><span class="sxs-lookup"><span data-stu-id="6abed-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="6abed-117">Active o desactive **Pedir a los autores de llamadas que registren su nombre antes de unirse a la reunión.**</span><span class="sxs-lookup"><span data-stu-id="6abed-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="6abed-118">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6abed-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6abed-119">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6abed-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6abed-120">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6abed-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="6abed-121">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6abed-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6abed-122">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="6abed-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="6abed-123">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="6abed-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6abed-124">¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6abed-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="6abed-125">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6abed-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="6abed-126">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="6abed-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="6abed-127">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6abed-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="6abed-128">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6abed-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6abed-129">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6abed-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6abed-130">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6abed-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="6abed-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="6abed-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6abed-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6abed-133">Related topics</span></span>

[<span data-ttu-id="6abed-134">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="6abed-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)

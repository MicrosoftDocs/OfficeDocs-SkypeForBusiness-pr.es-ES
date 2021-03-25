---
title: Permitir que los usuarios graben su nombre cuando se unan a una reunión en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Obtenga información sobre cómo habilitar o deshabilitar si los usuarios pueden grabar sus nombres cuando se unan a una reunión en Skype Empresarial Online.
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114246"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="0e394-103">Permitir que los usuarios graben su nombre cuando se unan a una reunión en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0e394-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="0e394-104">Si desea permitir a los usuarios registren sus nombres en Teams, consulte [Habilitar a los usuarios para registrar su nombre cuando se unen a una reunión en Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span><span class="sxs-lookup"><span data-stu-id="0e394-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="0e394-105">Al configurar audioconferencias en Microsoft 365 u Office 365, recibirá números de teléfono y lo que se denomina un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="0e394-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="0e394-106">Un puente de conferencia puede contener uno o más números de teléfono que pueden ser un número de teléfono dedicado o compartido.</span><span class="sxs-lookup"><span data-stu-id="0e394-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="0e394-p102">El puente de conferencia responde a la llamada de un usuario que llama a una reunión con un teléfono. Ese puente responde al autor de la llamada con avisos de voz de un operador automático y, luego, de acuerdo con su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que graben sus nombres y configura la seguridad del PIN para los organizadores de reuniones. Los PIN se proporcionan al organizador de la reunión y con ellos se puede empezar una reunión, pero puede configurarlo de modo que no se necesite un PIN para comenzar una reunión.</span><span class="sxs-lookup"><span data-stu-id="0e394-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="0e394-111">Establecer si los autores de las llamadas tienen que grabar sus nombres</span><span class="sxs-lookup"><span data-stu-id="0e394-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="0e394-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="0e394-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="0e394-113">En **Experiencia de unirse a la reunión**, vea que esté activa la casilla de verificación **Habilitar las notificaciones de entrada y salida de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="0e394-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="0e394-p103">**Activado**: se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión. Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e394-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
   - <span data-ttu-id="0e394-116">**Desactivado**: no se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="0e394-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="0e394-117">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e394-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0e394-118">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0e394-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="0e394-119">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span><span class="sxs-lookup"><span data-stu-id="0e394-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="0e394-120">Windows PowerShell se trata de administrar usuarios y lo que los usuarios pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="0e394-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="0e394-121">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="0e394-121">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0e394-122">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="0e394-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0e394-123">Por qué necesita usar Microsoft 365 u Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e394-123">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="0e394-124">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0e394-124">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="0e394-125">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del Centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="0e394-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0e394-126">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e394-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="0e394-127">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0e394-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0e394-128">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0e394-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0e394-129">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0e394-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="0e394-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="0e394-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0e394-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0e394-132">Related topics</span></span>

[<span data-ttu-id="0e394-133">Probar o comprar audioconferencias en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="0e394-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
---
title: Permitir a los usuarios grabar su nombre al unirse a una reunión
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: 940d4eefb6a997b03bb25fc558faf15ce9edb507
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703498"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="acb23-103">Permitir a los usuarios grabar su nombre al unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="acb23-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="acb23-p101">[] Al configurar las conferencias de acceso telefónico local en Skype Empresarial Online, recibirá números de teléfono y lo que se denomina un puente de audioconferencia o de conferencia de acceso telefónico local. Un puente de conferencia puede contener uno o más números de teléfono que pueden ser un número de teléfono dedicado o compartido.</span><span class="sxs-lookup"><span data-stu-id="acb23-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="acb23-p102">El puente de conferencia responde a la llamada de un usuario que llama a una reunión con un teléfono. Ese puente responde al autor de la llamada con avisos de voz de un operador automático y, luego, de acuerdo con su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que graben sus nombres y configura la seguridad del PIN para los organizadores de reuniones. Los PIN se proporcionan al organizador de la reunión y con ellos se puede empezar una reunión, pero puede configurarlo de modo que no se necesite un PIN para comenzar una reunión.</span><span class="sxs-lookup"><span data-stu-id="acb23-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="acb23-110">Establecer si los autores de las llamadas tienen que grabar sus nombres</span><span class="sxs-lookup"><span data-stu-id="acb23-110">Set whether callers should record their name</span></span>

<span data-ttu-id="acb23-111">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="acb23-111">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="acb23-112">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="acb23-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="acb23-113">En la parte superior de la página de **Puentes de conferencia** , haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="acb23-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="acb23-114">Habilitar o deshabilitar **Habilitar la entrada de la reunión y salir de notificaciones para activarse**.</span><span class="sxs-lookup"><span data-stu-id="acb23-114">Enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span>

4. <span data-ttu-id="acb23-115">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="acb23-115">Click **Apply**.</span></span>


<span data-ttu-id="acb23-116">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="acb23-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business Admin Center**</span></span>
    
1. <span data-ttu-id="acb23-117">En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencia de acceso telefónico local** > **Configuración del puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="acb23-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="acb23-118">En la **experiencia de unirse a la reunión**, vea la casilla de verificación **Habilitar la entrada de la reunión y salir de notificaciones para activarse**.</span><span class="sxs-lookup"><span data-stu-id="acb23-118">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="acb23-p103">**Activado**: se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión. Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="acb23-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
  - <span data-ttu-id="acb23-121">**Desactivado**: no se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="acb23-121">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="acb23-122">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="acb23-122">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="acb23-123">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="acb23-123">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="acb23-124">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="acb23-124">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="acb23-p104">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="acb23-p104">Windows PowerShell is all about managing users and what users are allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="acb23-128">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="acb23-128">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="acb23-129">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="acb23-129">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="acb23-p105">Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="acb23-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="acb23-132">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="acb23-132">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="acb23-133">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="acb23-133">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="acb23-134">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="acb23-134">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="acb23-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="acb23-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="acb23-137">See also</span><span class="sxs-lookup"><span data-stu-id="acb23-137">Related topics</span></span>

[<span data-ttu-id="acb23-138">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="acb23-138">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

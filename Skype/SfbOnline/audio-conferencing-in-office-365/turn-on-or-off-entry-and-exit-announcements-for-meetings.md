---
title: Activar o desactivar los anuncios de entrada y salida para las reuniones
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
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: 18b22e5491b67b6f4ec3f089803bcfb5e486eb14
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703458"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="8059e-103">Activar o desactivar los anuncios de entrada y salida para las reuniones</span><span class="sxs-lookup"><span data-stu-id="8059e-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="8059e-104">Cuando establece una conferencia con Audio en Office 365, obtendrá un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="8059e-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="8059e-105">Un puente de conferencia puede contener uno o más números de teléfono que los usuarios utilizarán para llamar a en un Skype para reuniones de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8059e-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="8059e-106">El puente de conferencia responde a una llamada de un usuario que se llama a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="8059e-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="8059e-107">El puente de conferencia responde el autor de la llamada con mensajes de voz de un operador automático de conferencia y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los autores de llamadas para registrar su nombre y configurar la seguridad de NIP.</span><span class="sxs-lookup"><span data-stu-id="8059e-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="8059e-108">Un PIN se asignó a un Skype para profesionales o Microsoft Teams organizador de la reunión, y les permite iniciar una reunión si no pueden iniciar la reunión utilizando un Skype para aplicación empresarial o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8059e-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="8059e-109">Sin embargo, se puede establecer para que no es necesario un NIP para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="8059e-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="8059e-110">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="8059e-110">Setting meeting join options</span></span>

<span data-ttu-id="8059e-111">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="8059e-111">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="8059e-112">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="8059e-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="8059e-113">En la parte superior de la página de **Puentes de conferencia** , haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="8059e-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="8059e-114">En el panel **configuración de puente** , habilitar o deshabilitar **Habilitar la entrada de la reunión y salir de notificaciones para activarse**.</span><span class="sxs-lookup"><span data-stu-id="8059e-114">In the **Bridge settings** pane, enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="8059e-115">Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8059e-115">This is selected by default.</span></span> <span data-ttu-id="8059e-116">Si se desactiva, los usuarios que ya se han unido a la reunión no recibirá una notificación cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="8059e-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="8059e-117">En **tipo de anuncio de entrada o salida**, seleccione **los nombres o números de teléfono** o **tonos**.</span><span class="sxs-lookup"><span data-stu-id="8059e-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="8059e-118">Habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="8059e-118">Enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="8059e-119">Después de realizar los cambios, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8059e-119">After you make your changes, click **Apply**.</span></span>

<span data-ttu-id="8059e-120">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="8059e-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="8059e-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="8059e-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="8059e-122">En la **experiencia de unirse a la reunión**, active o desactive **Habilitar la entrada de la reunión y salir de notificaciones para activarse**.</span><span class="sxs-lookup"><span data-stu-id="8059e-122">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="8059e-123">Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8059e-123">This is selected by default.</span></span> <span data-ttu-id="8059e-124">Si se desactiva, los usuarios que ya se han unido a la reunión no recibirá una notificación cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="8059e-124">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="8059e-125">En **tipo de anuncio de entrada o salida**, seleccione **los nombres o números de teléfono** o **tonos**.</span><span class="sxs-lookup"><span data-stu-id="8059e-125">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="8059e-126">Active o desactive **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="8059e-126">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="8059e-127">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8059e-127">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8059e-128">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8059e-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8059e-129">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).</span><span class="sxs-lookup"><span data-stu-id="8059e-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="8059e-p105">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="8059e-p105">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8059e-133">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="8059e-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8059e-134">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8059e-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="8059e-135">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre solo usa el centro de administración de Office 365, como cuando desea realizar cambios en la configuración de muchos usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8059e-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="8059e-136">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8059e-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="8059e-137">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8059e-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8059e-138">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8059e-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8059e-139">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8059e-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="8059e-p107">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="8059e-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8059e-142">See also</span><span class="sxs-lookup"><span data-stu-id="8059e-142">Related topics</span></span>

[<span data-ttu-id="8059e-143">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="8059e-143">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)

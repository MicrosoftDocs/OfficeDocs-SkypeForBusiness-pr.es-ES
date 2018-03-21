---
title: Activar o desactivar los anuncios de entrada y salida para las reuniones
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: ca353400d78a37a4b7cc362df6ed44a7f25fd869
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="0df57-103">Activar o desactivar los anuncios de entrada y salida para las reuniones</span><span class="sxs-lookup"><span data-stu-id="0df57-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="0df57-104">Cuando configura la audioconferencia en Office 365, obtendrá un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="0df57-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="0df57-105">Un puente de conferencia puede contener uno o más números de teléfono que utilizarán las personas que llaman a un Skype para reuniones de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0df57-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="0df57-106">El puente de conferencia responde a una llamada de un usuario que está marcando a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="0df57-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="0df57-107">El puente de conferencia responde al llamador con indicaciones de voz de un operador automático de conferencia y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los llamadores para registrar su nombre y configurar la seguridad de NIP.</span><span class="sxs-lookup"><span data-stu-id="0df57-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="0df57-108">Un PIN se asigna a un Skype para el organizador de la reunión de negocios o Teams de Microsoft, y les permite iniciar una reunión si no pueden comenzar la reunión mediante un Skype para la aplicación de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0df57-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="0df57-109">Sin embargo, se puede establecer para que no sea necesario un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="0df57-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="0df57-110">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="0df57-110">Setting meeting join options</span></span>

1. <span data-ttu-id="0df57-111">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="0df57-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0df57-112">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="0df57-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0df57-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="0df57-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="0df57-114">En **experimentar la combinación de la reunión**, active o desactive **Permitir la entrada de la reunión y salir notificaciones al activarse**.</span><span class="sxs-lookup"><span data-stu-id="0df57-114">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="0df57-115">Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0df57-115">This is selected by default.</span></span> <span data-ttu-id="0df57-116">Si lo desactiva, los usuarios que ya han participado en la reunión no le notificará cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="0df57-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="0df57-117">En **tipo de anuncio de entrada/salida**, seleccione **los nombres o números de teléfono** o **tonos**.</span><span class="sxs-lookup"><span data-stu-id="0df57-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
6. <span data-ttu-id="0df57-118">Active o desactive **los llamadores Ask para registrar su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="0df57-118">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="0df57-119">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0df57-119">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0df57-120">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0df57-120">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="0df57-121">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).</span><span class="sxs-lookup"><span data-stu-id="0df57-121">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="0df57-p104">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="0df57-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0df57-125">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="0df57-125">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0df57-126">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0df57-126">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="0df57-127">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="0df57-127">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="0df57-128">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0df57-128">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="0df57-129">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0df57-129">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0df57-130">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0df57-130">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0df57-131">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0df57-131">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="0df57-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="0df57-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0df57-134">See also</span><span class="sxs-lookup"><span data-stu-id="0df57-134">Related topics</span></span>

[<span data-ttu-id="0df57-135">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="0df57-135">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)


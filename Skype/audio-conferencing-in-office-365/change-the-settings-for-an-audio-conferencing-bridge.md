---
title: "Cambiar la configuración de un puente de conferencia de Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: 'Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that''s used to prompt callers and gather names and pins for meeting organizers when they''re not using Skype for Business clients. '
ms.openlocfilehash: f37af15b4ab66eb5765cccbdba63b3bb6bb14597
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="d1863-103">Cambiar la configuración de un puente de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="d1863-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="d1863-104">Cuando configura la audioconferencia en Office 365, recibirá los números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="d1863-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="d1863-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="d1863-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="d1863-106">Estos números de teléfono se utilizan cuando los llamadores llama a una reunión.</span><span class="sxs-lookup"><span data-stu-id="d1863-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="d1863-107">El número de teléfono se incluye en la parte inferior de la Skype para invitar a la reunión de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1863-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="d1863-108">El puente de conferencia contesta una llamada y solicita al llamador con indicaciones de voz utilizando un auto reunión operador y a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pregunte a los llamadores para registrar su nombre y controlar la configuración de pines.</span><span class="sxs-lookup"><span data-stu-id="d1863-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="d1863-109">Pines se otorgan a los organizadores de reuniones para permitirles iniciar una reunión cuando están no esté utilizando un Skype para la aplicación de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1863-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="d1863-110">Cambiar la configuración de un puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="d1863-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="d1863-111">**Configurar la experiencia de reunión cuando los llamadores unirse a una reunión**</span><span class="sxs-lookup"><span data-stu-id="d1863-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="d1863-112">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="d1863-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d1863-113">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d1863-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d1863-114">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d1863-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="d1863-115">En la página **configuración de puente de Microsoft** , en la **experiencia de unión de la reunión**, seleccione:</span><span class="sxs-lookup"><span data-stu-id="d1863-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="d1863-116">**Habilitar la entrada de la reunión y salir de notificaciones para activarse** Esto está seleccionada por defecto.</span><span class="sxs-lookup"><span data-stu-id="d1863-116">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="d1863-117">Si desactiva la casilla de verificación, los usuarios que ya han participado en la reunión no se le notificará cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="d1863-117">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="d1863-118">Cuando selecciona **Habilitar la entrada de la reunión y salir notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de entrada o salida de anuncio** :</span><span class="sxs-lookup"><span data-stu-id="d1863-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="d1863-119">**Los nombres o números de teléfono** Cuando los usuarios de acceso telefónico a una reunión, su número de teléfono se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="d1863-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="d1863-120">**Tonos** Cuando los usuarios de acceso telefónico a una reunión, un tono de sonido se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="d1863-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1863-121">**Tono** está ahora disponible como tipo de anuncio para todos los clientes como una característica de vista previa.</span><span class="sxs-lookup"><span data-stu-id="d1863-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="d1863-122">**Llamadores ASK para registrar su nombre antes de unirse a la reunión** Esto está seleccionada por defecto.</span><span class="sxs-lookup"><span data-stu-id="d1863-122">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="d1863-123">Si desactiva la casilla de verificación, los llamadores no pedirá que registre su nombre antes de que se unen a una reunión.</span><span class="sxs-lookup"><span data-stu-id="d1863-123">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="d1863-124">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d1863-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="d1863-125">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d1863-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="d1863-126">Configurar la longitud del PIN de las reuniones</span><span class="sxs-lookup"><span data-stu-id="d1863-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d1863-127">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d1863-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d1863-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="d1863-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="d1863-129">En la página de **configuración de puente de Microsoft** en **seguridad**, especifique el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d1863-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d1863-130">The PIN must be between 4 and 12 digits.</span><span class="sxs-lookup"><span data-stu-id="d1863-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="d1863-131">**Seleccione si desea enviar correo electrónico a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="d1863-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="d1863-132">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="d1863-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d1863-133">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d1863-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d1863-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="d1863-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="d1863-135">En la página **configuración de puente de Microsoft** , seleccione o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d1863-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="d1863-136">Para obtener más información, consulte [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="d1863-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d1863-137">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d1863-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d1863-138">Para ahorrar tiempo o automatizar este proceso, puede utilizar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="d1863-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="d1863-p105">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="d1863-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d1863-142">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="d1863-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d1863-143">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1863-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="d1863-p106">Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1863-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d1863-146">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d1863-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d1863-147">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d1863-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d1863-148">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d1863-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="d1863-p107">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="d1863-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d1863-151">See also</span><span class="sxs-lookup"><span data-stu-id="d1863-151">Related topics</span></span>

[<span data-ttu-id="d1863-152">Conferencias de acceso telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="d1863-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)


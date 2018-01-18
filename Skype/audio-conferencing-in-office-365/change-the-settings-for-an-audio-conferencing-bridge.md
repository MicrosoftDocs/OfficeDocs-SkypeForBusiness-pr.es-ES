---
title: "Cambiar la configuración de un puente de conferencia de Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "Obtenga los pasos que necesarios para cambiar la configuración de un puente de acceso telefónico de la conferencia de Microsoft que se utiliza para solicitar a los llamadores y recopilar nombres y clavijas para los organizadores de la reunión cuando no utilizan Skype para clientes empresariales. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="3b3be-103">Cambiar la configuración de un puente de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="3b3be-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="3b3be-104">Cuando configura la audioconferencia en Office 365, recibirá los números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="3b3be-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="3b3be-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="3b3be-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="3b3be-106">Estos números de teléfono se utilizan cuando los llamadores llama a una reunión.</span><span class="sxs-lookup"><span data-stu-id="3b3be-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="3b3be-107">El número de teléfono se incluye en la parte inferior de la Skype para invitar a la reunión de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b3be-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="3b3be-108">El puente de conferencia contesta una llamada y solicita al llamador con indicaciones de voz utilizando un auto reunión operador y a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pregunte a los llamadores para registrar su nombre y controlar la configuración de pines.</span><span class="sxs-lookup"><span data-stu-id="3b3be-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="3b3be-109">Pines se otorgan a los organizadores de reuniones para permitirles iniciar una reunión cuando están no esté utilizando un Skype para la aplicación de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b3be-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="3b3be-110">Cambiar la configuración de un puente de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="3b3be-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="3b3be-111">**Configurar la experiencia de reunión cuando los llamadores unirse a una reunión**</span><span class="sxs-lookup"><span data-stu-id="3b3be-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="3b3be-112">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="3b3be-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3b3be-113">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="3b3be-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3b3be-114">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3b3be-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="3b3be-115">En la página **configuración de puente de Microsoft** , en la **experiencia de unión de la reunión**, seleccione:</span><span class="sxs-lookup"><span data-stu-id="3b3be-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="3b3be-116">**Habilitar la entrada de la reunión y salir de notificaciones para activarse** Esto está seleccionada por defecto.</span><span class="sxs-lookup"><span data-stu-id="3b3be-116">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="3b3be-117">Si desactiva la casilla de verificación, los usuarios que ya han participado en la reunión no se le notificará cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="3b3be-117">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="3b3be-118">Cuando selecciona **Habilitar la entrada de la reunión y salir notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de entrada o salida de anuncio** :</span><span class="sxs-lookup"><span data-stu-id="3b3be-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="3b3be-119">**Los nombres o números de teléfono** Cuando los usuarios de acceso telefónico a una reunión, su número de teléfono se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="3b3be-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="3b3be-120">**Tonos** Cuando los usuarios de acceso telefónico a una reunión, un tono de sonido se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="3b3be-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b3be-121">Con **tono** como el tipo de anuncio está disponible actualmente para todos los clientes como una característica de vista previa.</span><span class="sxs-lookup"><span data-stu-id="3b3be-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="3b3be-122">**Llamadores ASK para registrar su nombre antes de unirse a la reunión** Esto está seleccionada por defecto.</span><span class="sxs-lookup"><span data-stu-id="3b3be-122">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="3b3be-123">Si desactiva la casilla de verificación, los llamadores no pedirá que registre su nombre antes de que se unen a una reunión.</span><span class="sxs-lookup"><span data-stu-id="3b3be-123">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="3b3be-124">**Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="3b3be-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="3b3be-125">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3b3be-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="3b3be-126">Configurar la longitud del PIN de las reuniones</span><span class="sxs-lookup"><span data-stu-id="3b3be-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3b3be-127">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="3b3be-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3b3be-128">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3b3be-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="3b3be-129">En la página de **configuración de puente de Microsoft** en **seguridad**, especifique el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3b3be-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3b3be-130">El NIP debe tener entre 4 y 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="3b3be-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="3b3be-131">**Seleccione si desea enviar correo electrónico a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="3b3be-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="3b3be-132">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="3b3be-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3b3be-133">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="3b3be-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3b3be-134">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3b3be-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="3b3be-135">En la página **configuración de puente de Microsoft** , seleccione o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3b3be-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="3b3be-136">Para obtener más información, consulte [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="3b3be-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3b3be-137">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3b3be-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3b3be-138">Para ahorrar tiempo o automatizar este proceso, puede utilizar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="3b3be-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="3b3be-139">Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no realizar.</span><span class="sxs-lookup"><span data-stu-id="3b3be-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3b3be-140">Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="3b3be-140">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="3b3be-141">Para empezar a utilizar Windows PowerShell, consulte estos temas:</span><span class="sxs-lookup"><span data-stu-id="3b3be-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="3b3be-142">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="3b3be-142">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="3b3be-143">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="3b3be-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3b3be-144">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3b3be-144">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3b3be-145">Obtenga información acerca de estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="3b3be-145">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3b3be-146">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3b3be-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3b3be-147">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3b3be-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3b3be-148">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3b3be-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3b3be-p107">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="3b3be-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3b3be-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3b3be-151">Related topics</span></span>

[<span data-ttu-id="3b3be-152">Configurar Audioconferencia para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b3be-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)


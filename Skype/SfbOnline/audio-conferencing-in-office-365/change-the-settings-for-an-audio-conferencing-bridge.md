---
title: Cambiar la configuración de un puente de conferencia de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Obtenga los pasos que necesarios para cambiar la configuración de un puente de conferencia que se utiliza para solicitar a los llamadores y recopilar nombres y clavijas para los organizadores de la reunión cuando no utilizan Skype para aplicaciones empresariales o Teams de Microsoft. '
ms.openlocfilehash: d5af21ab1df8b2b4b5b7e6d296a585812a5888c1
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="23ed0-103">Cambiar la configuración de un puente de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="23ed0-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="23ed0-104">Cuando configura la audioconferencia en Office 365, recibirá los números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="23ed0-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="23ed0-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="23ed0-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="23ed0-106">Estos números de teléfono se utilizan cuando los llamadores llama a una reunión.</span><span class="sxs-lookup"><span data-stu-id="23ed0-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="23ed0-107">El número de teléfono se incluye en la parte inferior de la Skype para invitar a la reunión de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23ed0-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="23ed0-108">El puente de conferencia contesta una llamada y solicita al llamador con indicaciones de voz utilizando un auto reunión operador y a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pregunte a los llamadores para registrar su nombre y controlar la configuración de pines.</span><span class="sxs-lookup"><span data-stu-id="23ed0-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="23ed0-109">Pines se otorgan a los organizadores de reuniones para permitirles iniciar una reunión cuando están no esté utilizando un Skype para la aplicación de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23ed0-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="23ed0-110">Un PIN sólo es necesario para el organizador de la reunión cuando un Skype para usuario de la aplicación empresarial o Teams de Microsoft ya no ha iniciado la conferencia.</span><span class="sxs-lookup"><span data-stu-id="23ed0-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="23ed0-111">Si todo el mundo está marcando a la reunión, el PIN es necesario para el organizador de la reunión iniciar la reunión.</span><span class="sxs-lookup"><span data-stu-id="23ed0-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

## <a name="teams-logo-30x30pngimagesteams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![logotipo-equipos-30x30.png](../images/teams-logo-30x30.png) <span data-ttu-id="23ed0-113">Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios</span><span class="sxs-lookup"><span data-stu-id="23ed0-113">Using the Microsoft Teams and Skype for Business Admin Center</span></span>
   > [!NOTE]
   > [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

1. <span data-ttu-id="23ed0-114">En la exploración de la izquierda, vaya a **reuniones** > **puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="23ed0-115">En la parte superior de la página **puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="23ed0-116">En el panel **configuración de puente** , seleccione:</span><span class="sxs-lookup"><span data-stu-id="23ed0-116">In the **Bridge settings** pane, select:</span></span> 
  - <span data-ttu-id="23ed0-117">**Entrada de reunión y salir de las notificaciones** Si desactiva esta opción, los usuarios que ya han participado en la reunión no se le notificará cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="23ed0-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="23ed0-118">Al activar **las notificaciones de entrada y salida de la reunión**, puede seleccionar estas opciones:</span><span class="sxs-lookup"><span data-stu-id="23ed0-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
  - <span data-ttu-id="23ed0-119">**Los nombres o números de teléfono** Cuando los usuarios de acceso telefónico a una reunión, su número de teléfono se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="23ed0-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="23ed0-120">**Tonos** Cuando los usuarios de acceso telefónico a una reunión, un tono de sonido se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="23ed0-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
  - <span data-ttu-id="23ed0-121">**Llamadores ASK para registrar su nombre antes de unirse a la reunión** Si desactiva esta opción, los llamadores no pedirá que registre su nombre antes de que se unen a una reunión.</span><span class="sxs-lookup"><span data-stu-id="23ed0-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="23ed0-122">Para establecer la longitud del perno para las reuniones, seleccione el número de dígitos que desee para el PIN en la lista de **longitud PIN** .</span><span class="sxs-lookup"><span data-stu-id="23ed0-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="23ed0-123">Para especificar si desea enviar correo electrónico a los usuarios, activar o desactivar **automáticamente enviar correos electrónicos a los usuarios si cambia su configuración de conferencia de audio**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="23ed0-124">Para obtener más información, consulte [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="23ed0-124">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
 
6. <span data-ttu-id="23ed0-125">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-125">Click **Apply**.</span></span> 

## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-skype-for-business-admin-center"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="23ed0-127">Usar Skype para el centro de administración de negocios</span><span class="sxs-lookup"><span data-stu-id="23ed0-127">Using Skype for Business admin center</span></span>

 <span data-ttu-id="23ed0-128">**Configurar la experiencia de reunión cuando los llamadores unirse a una reunión**</span><span class="sxs-lookup"><span data-stu-id="23ed0-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="23ed0-129">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="23ed0-130">En la página **configuración de puente de Microsoft** , en la **experiencia de unión de la reunión**, seleccione:</span><span class="sxs-lookup"><span data-stu-id="23ed0-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="23ed0-131">**Habilitar la entrada de la reunión y salir de notificaciones para activarse** Esto está seleccionada por defecto.</span><span class="sxs-lookup"><span data-stu-id="23ed0-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="23ed0-132">Si desactiva la casilla de verificación, los usuarios que ya han participado en la reunión no se le notificará cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="23ed0-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="23ed0-133">Cuando selecciona **Habilitar la entrada de la reunión y salir notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de entrada o salida de anuncio** :</span><span class="sxs-lookup"><span data-stu-id="23ed0-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="23ed0-134">**Los nombres o números de teléfono** Cuando los usuarios de acceso telefónico a una reunión, su número de teléfono se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="23ed0-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="23ed0-135">**Tonos** Cuando los usuarios de acceso telefónico a una reunión, un tono de sonido se reproducirá cuando se unan a ella.</span><span class="sxs-lookup"><span data-stu-id="23ed0-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
  - <span data-ttu-id="23ed0-136">**Llamadores ASK para registrar su nombre antes de unirse a la reunión** Esto está seleccionada por defecto.</span><span class="sxs-lookup"><span data-stu-id="23ed0-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="23ed0-137">Si desactiva la casilla de verificación, los llamadores no pedirá que registre su nombre antes de que se unen a una reunión.</span><span class="sxs-lookup"><span data-stu-id="23ed0-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="23ed0-138">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="23ed0-139">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="23ed0-140">Configurar la longitud del PIN de las reuniones</span><span class="sxs-lookup"><span data-stu-id="23ed0-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="23ed0-141">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="23ed0-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="23ed0-143">En la página de **configuración de puente de Microsoft** en **seguridad**, especifique el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="23ed0-144">The PIN must be between 4 and 12 digits.</span><span class="sxs-lookup"><span data-stu-id="23ed0-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="23ed0-145">**Seleccione si desea enviar correo electrónico a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="23ed0-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="23ed0-146">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="23ed0-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="23ed0-147">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="23ed0-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="23ed0-149">En la página **configuración de puente de Microsoft** , seleccione o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su información de acceso telefónico**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="23ed0-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="23ed0-150">Para obtener más información, consulte [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="23ed0-150">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="23ed0-151">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="23ed0-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="23ed0-152">Para ahorrar tiempo o automatizar este proceso, puede utilizar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="23ed0-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="23ed0-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="23ed0-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="23ed0-156">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="23ed0-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="23ed0-157">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23ed0-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="23ed0-p108">Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="23ed0-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="23ed0-160">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="23ed0-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="23ed0-161">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="23ed0-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="23ed0-162">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="23ed0-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="23ed0-p109">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="23ed0-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="23ed0-165">See also</span><span class="sxs-lookup"><span data-stu-id="23ed0-165">Related topics</span></span>

[<span data-ttu-id="23ed0-166">Configurar Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="23ed0-166">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)

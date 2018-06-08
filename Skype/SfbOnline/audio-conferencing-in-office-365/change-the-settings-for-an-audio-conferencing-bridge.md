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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga los pasos que necesarios para cambiar la configuración de un puente de conferencia que se usa para solicitar los autores de llamadas y recopilar los nombres y los PIN para los organizadores de reuniones cuando no utilizan Skype para las aplicaciones empresariales o Teams de Microsoft. '
ms.openlocfilehash: d01ef5f96483ae26ccfaf429e87221b1a5c61d11
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703682"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="614c4-103">Cambiar la configuración de un puente de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="614c4-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="614c4-104">Cuando establece una conferencia con Audio en Office 365, recibirá los números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="614c4-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="614c4-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="614c4-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="614c4-106">Estos números de teléfono se utilizan cuando los autores de llamadas llama a una reunión.</span><span class="sxs-lookup"><span data-stu-id="614c4-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="614c4-107">El número de teléfono se incluye en la parte inferior de la Skype para la invitación a la reunión de negocio o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="614c4-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="614c4-108">El puente de conferencia responde a una llamada y solicita el autor de la llamada con mensajes de voz con un automático de reunión attendant y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los autores de llamadas para registrar su nombre y controlar la configuración de PIN.</span><span class="sxs-lookup"><span data-stu-id="614c4-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="614c4-109">PIN se conceden a los organizadores de reuniones para permitirles para iniciar una reunión cuando están no esté utilizando un Skype para aplicación empresarial o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="614c4-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="614c4-110">Un PIN sólo es necesaria para el organizador de la reunión cuando un Skype para usuario de aplicación empresarial o Teams de Microsoft ya no ha comenzado la reunión.</span><span class="sxs-lookup"><span data-stu-id="614c4-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="614c4-111">Si todos los usuarios se llaman a la reunión, el PIN se requiere para el organizador de la reunión iniciar la reunión.</span><span class="sxs-lookup"><span data-stu-id="614c4-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngimagesteams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) <span data-ttu-id="614c4-113">Uso del equipos de Microsoft y Skype para centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="614c4-113">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="614c4-114">En el panel de navegación izquierdo, vaya a **las reuniones** > **puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="614c4-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="614c4-115">En la parte superior de la página de **puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="614c4-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="614c4-116">En el panel **configuración de puente** , seleccione:</span><span class="sxs-lookup"><span data-stu-id="614c4-116">In the **Bridge settings** pane, select:</span></span> 
  - <span data-ttu-id="614c4-117">**Entrada de la reunión y salir de las notificaciones** Si desactiva esta opción, no se le notificará a los usuarios que ya se han unido a la reunión cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="614c4-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="614c4-118">Al activar **las notificaciones de entrada y salida de la reunión**, puede seleccionar estas opciones:</span><span class="sxs-lookup"><span data-stu-id="614c4-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
  - <span data-ttu-id="614c4-119">**Los nombres o números de teléfono** Cuando los usuarios conectan a una reunión, su número de teléfono se reproducirá cuando se unan a él.</span><span class="sxs-lookup"><span data-stu-id="614c4-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="614c4-120">**Tonos** Cuando los usuarios conectan a una reunión, un tono de audio se reproducirá cuando se unan a él.</span><span class="sxs-lookup"><span data-stu-id="614c4-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
  - <span data-ttu-id="614c4-121">**Autores de llamadas ASK para registrar su nombre antes de unirse a la reunión** Si desactiva esta opción, los autores de llamadas no se le pida para registrar su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="614c4-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="614c4-122">Para establecer la longitud PIN para las reuniones, seleccione el número de dígitos que desee para el PIN en la lista de **longitud PIN** .</span><span class="sxs-lookup"><span data-stu-id="614c4-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="614c4-123">Para especificar si desea enviar correo electrónico a los usuarios, habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.</span><span class="sxs-lookup"><span data-stu-id="614c4-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="614c4-124">Para obtener más información, vea [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="614c4-124">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
 
6. <span data-ttu-id="614c4-125">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="614c4-125">Click **Apply**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png)  <span data-ttu-id="614c4-127">Usar el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="614c4-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="614c4-128">**Configurar la experiencia de reunión cuando los autores de llamadas, unirse a una reunión**</span><span class="sxs-lookup"><span data-stu-id="614c4-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="614c4-129">En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo vaya a la **conferencia de Audio** > **configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="614c4-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="614c4-130">En la página de **configuración de puente de Microsoft** , en la **experiencia de unirse a la reunión**, seleccione:</span><span class="sxs-lookup"><span data-stu-id="614c4-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="614c4-131">**Habilitar la entrada de la reunión y salir de las notificaciones para ser activado** Está seleccionada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="614c4-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="614c4-132">Si desactiva la casilla de verificación, no se le notificará a los usuarios que ya se han unido a la reunión cuando alguien entra o sale de la reunión.</span><span class="sxs-lookup"><span data-stu-id="614c4-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
  - <span data-ttu-id="614c4-133">Cuando se selecciona **Habilitar la entrada de la reunión y salir de las notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de anuncio de entrada o salida** :</span><span class="sxs-lookup"><span data-stu-id="614c4-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="614c4-134">**Los nombres o números de teléfono** Cuando los usuarios conectan a una reunión, su número de teléfono se reproducirá cuando se unan a él.</span><span class="sxs-lookup"><span data-stu-id="614c4-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="614c4-135">**Tonos** Cuando los usuarios conectan a una reunión, un tono de audio se reproducirá cuando se unan a él.</span><span class="sxs-lookup"><span data-stu-id="614c4-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="614c4-136">**Autores de llamadas ASK para registrar su nombre antes de unirse a la reunión** Está seleccionada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="614c4-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="614c4-137">Si desactiva la casilla de verificación, los autores de llamadas no se le pida para registrar su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="614c4-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="614c4-138">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="614c4-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="614c4-139">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="614c4-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="614c4-140">Configurar la longitud del PIN de las reuniones</span><span class="sxs-lookup"><span data-stu-id="614c4-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="614c4-141">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="614c4-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="614c4-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="614c4-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="614c4-143">En la página **configuración de puente de Microsoft** , en **seguridad**, escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="614c4-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="614c4-144">The PIN must be between 4 and 12 digits.</span><span class="sxs-lookup"><span data-stu-id="614c4-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="614c4-145">**Seleccione si desea enviar correo electrónico a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="614c4-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="614c4-146">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="614c4-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="614c4-147">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="614c4-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="614c4-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="614c4-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="614c4-149">En la página **configuración de puente de Microsoft** , seleccione o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si se cambia su información de marcado**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="614c4-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="614c4-150">Para obtener más información, vea [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="614c4-150">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="614c4-151">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="614c4-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="614c4-152">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="614c4-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="614c4-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="614c4-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="614c4-156">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="614c4-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="614c4-157">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="614c4-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="614c4-p108">Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="614c4-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="614c4-160">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="614c4-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="614c4-161">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="614c4-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="614c4-162">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="614c4-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="614c4-p109">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="614c4-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="614c4-165">See also</span><span class="sxs-lookup"><span data-stu-id="614c4-165">Related topics</span></span>

[<span data-ttu-id="614c4-166">Configurar Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="614c4-166">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)

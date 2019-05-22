---
title: Cambiar la configuración de un puente de Audioconferencias.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Siga los pasos que necesita para cambiar la configuración de un puente de conferencia que se usa para avisar a las personas que llaman y recopilar nombres y PIN de los organizadores de reuniones cuando no usan las aplicaciones de Skype empresarial o Microsoft Teams. '
ms.openlocfilehash: eaccf6b09499c819451aabd4c1785b326f98ac6d
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344872"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="aba2b-103">Cambiar la configuración de un puente de Audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="aba2b-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="aba2b-104">Al configurar las conferencias de audio en Office 365, recibirá números de teléfono para los usuarios de lo que se denomina un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="aba2b-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="aba2b-105">Un puente de conferencia puede contener uno o más números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="aba2b-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="aba2b-106">Estos números de teléfono se usan cuando las personas que llaman llaman a una reunión.</span><span class="sxs-lookup"><span data-stu-id="aba2b-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="aba2b-107">El número de teléfono se incluye en la parte inferior de la invitación a una reunión de Skype empresarial o de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aba2b-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="aba2b-108">El puente de conferencia responde a una llamada y le pide a la persona que llama con un operador automático de la reunión y, a continuación, en función de la configuración, puede reproducir notificaciones, pedir a los participantes que graben su nombre y controlar la configuración del PIN.</span><span class="sxs-lookup"><span data-stu-id="aba2b-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="aba2b-109">Los PIN se otorgan a los organizadores de reuniones para que puedan iniciar una reunión cuando no estén usando una aplicación de Skype empresarial o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aba2b-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="aba2b-110">Un PIN solo es necesario para el organizador de la reunión cuando un usuario de la aplicación de Skype empresarial o de Microsoft Teams ya no ha iniciado la reunión.</span><span class="sxs-lookup"><span data-stu-id="aba2b-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="aba2b-111">Si todos los usuarios llaman a la reunión, el PIN es necesario para que el organizador de la reunión la inicie.</span><span class="sxs-lookup"><span data-stu-id="aba2b-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="aba2b-113">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aba2b-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="aba2b-114">En el navegación de la izquierda, vaya a**puentes de conferencia**de **reuniones** > .</span><span class="sxs-lookup"><span data-stu-id="aba2b-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="aba2b-115">En la parte superior de la página **puentes de conferencia** , haga clic en **configuración del puente**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="aba2b-116">En el panel **configuración de puente** , seleccione:</span><span class="sxs-lookup"><span data-stu-id="aba2b-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="aba2b-117">**Notificaciones de entrada y salida de reunión** Si desactiva esta opción, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre o salga de la reunión.</span><span class="sxs-lookup"><span data-stu-id="aba2b-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="aba2b-118">Al activar las notificaciones de **entrada y salida**de la reunión, puede seleccionar estas opciones:</span><span class="sxs-lookup"><span data-stu-id="aba2b-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="aba2b-119">**Nombres o números de teléfono** Cuando los usuarios llaman a una reunión, su número de teléfono se reproducirá cuando se una a una.</span><span class="sxs-lookup"><span data-stu-id="aba2b-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="aba2b-120">**Tonos** Cuando los usuarios llaman a una reunión, se reproduce un tono de audio al unirse a la misma.</span><span class="sxs-lookup"><span data-stu-id="aba2b-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="aba2b-121">**Pedir a las personas que llamen para que graben su nombre antes de unirse a la reunión** Si desactiva esta opción, no se pedirá a las personas que llamen su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="aba2b-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="aba2b-122">Para establecer la longitud del PIN para las reuniones, seleccione el número de dígitos que desea para el PIN en la lista **longitud del PIN** .</span><span class="sxs-lookup"><span data-stu-id="aba2b-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="aba2b-123">Para especificar si se debe enviar correo electrónico a los usuarios, habilitar o deshabilitar el **envío automático de correos electrónicos a los usuarios si cambia la configuración**de las conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="aba2b-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="aba2b-124">Ver [los correos electrónicos enviados de forma automática a los usuarios cuando cambia la configuración de la audioconferencia en Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o [correos electrónicos enviados a los usuarios cuando cambia su configuración en Skype empresarial online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="aba2b-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="aba2b-125">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="aba2b-125">Click **Save**.</span></span> 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![SFB-logo-30x30. png](media/sfb-logo-30x30.png)  <span data-ttu-id="aba2b-127">Using the Skype for Business admin center</span><span class="sxs-lookup"><span data-stu-id="aba2b-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="aba2b-128">**Configurar la experiencia de reunión cuando las personas que llaman se unen a una reunión**</span><span class="sxs-lookup"><span data-stu-id="aba2b-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="aba2b-129">En el **centro de administración de Skype empresarial**, en el navegación de la \*\*\*\* > izquierda, vaya a**configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="aba2b-130">En la página **configuración del puente de Microsoft** , en experiencia de unirse a la **reunión**, seleccione:</span><span class="sxs-lookup"><span data-stu-id="aba2b-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="aba2b-131">**Habilitar las notificaciones de entrada y salida de reunión para que se activen** Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aba2b-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="aba2b-132">Si desactiva la casilla, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre o salga de la reunión.</span><span class="sxs-lookup"><span data-stu-id="aba2b-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="aba2b-133">Si selecciona **permitir que las notificaciones de entrada y salida de la reunión estén activadas**, puede seleccionar estas opciones en la lista de **tipo de anuncio de entrada/salida** :</span><span class="sxs-lookup"><span data-stu-id="aba2b-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="aba2b-134">**Nombres o números de teléfono** Cuando los usuarios llaman a una reunión, su número de teléfono se reproducirá cuando se una a una.</span><span class="sxs-lookup"><span data-stu-id="aba2b-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="aba2b-135">**Tonos** Cuando los usuarios llaman a una reunión, se reproduce un tono de audio al unirse a la misma.</span><span class="sxs-lookup"><span data-stu-id="aba2b-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="aba2b-136">**Pedir a las personas que llamen para que graben su nombre antes de unirse a la reunión** Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aba2b-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="aba2b-137">Si desactiva la casilla, no se pedirá a las personas que llamen su nombre antes de unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="aba2b-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="aba2b-138">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="aba2b-139">Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="aba2b-140">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="aba2b-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="aba2b-141">Vaya al **Centro** > de administración de Microsoft 365**Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="aba2b-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="aba2b-143">En la **página Configuración del puente de Microsoft** , en **seguridad**, escriba la cantidad de dígitos que desee para el PIN en la lista **longitud del PIN** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="aba2b-144">The PIN must be between 4 and 12 digits.</span><span class="sxs-lookup"><span data-stu-id="aba2b-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="aba2b-145">**Seleccione si desea enviar correo electrónico a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="aba2b-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="aba2b-146">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="aba2b-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="aba2b-147">Vaya al **Centro** > de administración de Microsoft 365**Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="aba2b-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="aba2b-149">En la página **configuración del puente de Microsoft** , Active o desactive **enviar automáticamente correos electrónicos a los usuarios si cambia la información de acceso telefónico**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aba2b-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="aba2b-150">Ver [los correos electrónicos enviados de forma automática a los usuarios cuando cambia la configuración de la audioconferencia en Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o [correos electrónicos enviados a los usuarios cuando cambia su configuración en Skype empresarial online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="aba2b-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="aba2b-151">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="aba2b-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="aba2b-152">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .</span><span class="sxs-lookup"><span data-stu-id="aba2b-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="aba2b-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="aba2b-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="aba2b-156">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="aba2b-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="aba2b-157">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aba2b-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="aba2b-158">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="aba2b-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="aba2b-159">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="aba2b-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="aba2b-160">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aba2b-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="aba2b-161">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aba2b-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="aba2b-162">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aba2b-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="aba2b-p109">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="aba2b-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="aba2b-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aba2b-165">Related topics</span></span>

[<span data-ttu-id="aba2b-166">Configurar audioconferencias en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aba2b-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="aba2b-167">Configurar audioconferencias para Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="aba2b-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

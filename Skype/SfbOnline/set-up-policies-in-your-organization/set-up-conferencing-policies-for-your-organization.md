---
title: "Configurar directivas de conferencias para la organización"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos."
ms.openlocfilehash: 7e2540bc043476ca2a768c701b93c2ce8d6a4431
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="f3a66-103">Configurar directivas de conferencias para la organización</span><span class="sxs-lookup"><span data-stu-id="f3a66-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="f3a66-104">[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.</span><span class="sxs-lookup"><span data-stu-id="f3a66-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="f3a66-p101">Es importante para mantener el control sobre la configuración de conferencia y conferencias. En algunos casos, puede haber problemas de seguridad: de forma predeterminada, cualquier persona, incluidos los usuarios no autenticados, puede participar en las reuniones y guardar cualquiera de las diapositivas o documentos que se distribuyen durante las reuniones. Además, puede haber problemas legales ocasionales. Por ejemplo, de forma predeterminada, los participantes de la reunión pueden hacer anotaciones en contenido compartido; Sin embargo, estas anotaciones no se guardan cuando se archiva la reunión. Si su organización es necesaria para mantener un registro de todas las comunicaciones electrónicas, desea deshabilitar las anotaciones.</span><span class="sxs-lookup"><span data-stu-id="f3a66-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="f3a66-p102">En Skype para los negocios en línea, conferencias se administran mediante directivas de conferencia. Directivas de conferencia determinan las características y capacidades que pueden utilizarse en una conferencia, incluyendo todo, desde el hecho de la conferencia puede incluir IP audio y vídeo para el número máximo de personas que pueden asistir a una reunión. Las directivas de la conferencia pueden configurarse en el ámbito global o en el ámbito de cada usuario. Esto proporciona a los administradores con una enorme flexibilidad en cuanto a decidir qué funciones estarán disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3a66-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="f3a66-114">Configuración de la directiva puede configurarse en el momento en que se crea una directiva, o puede utilizar el cmdlet **Set-CsConferencingPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="f3a66-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="f3a66-115">Establecer las directivas de conferencia</span><span class="sxs-lookup"><span data-stu-id="f3a66-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="f3a66-116">Para todas las configuraciones de directiva de conferencia en Skype para los negocios en línea, debe utilizar Windows PowerShell y **no se puede utilizar** el **Skype para el centro de administración de negocios**.</span><span class="sxs-lookup"><span data-stu-id="f3a66-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="f3a66-117">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3a66-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="f3a66-118">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="f3a66-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="f3a66-119">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f3a66-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f3a66-120">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f3a66-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="f3a66-p103">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="f3a66-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="f3a66-p104">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="f3a66-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="f3a66-127">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="f3a66-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="f3a66-128">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3a66-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="f3a66-129">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f3a66-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f3a66-130">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="f3a66-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3a66-131">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="f3a66-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="f3a66-132">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f3a66-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="f3a66-133">Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones</span><span class="sxs-lookup"><span data-stu-id="f3a66-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="f3a66-134">Para crear una nueva directiva para estas configuraciones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f3a66-134">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```
  <span data-ttu-id="f3a66-135">Obtenga más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3a66-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f3a66-136">Para conceder a la nueva directiva creada para todos los usuarios de la organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f3a66-136">To grant the new policy you created to all users in your organization, run:</span></span>
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```
  <span data-ttu-id="f3a66-137">Obtenga más información acerca del cmdlet [Grant CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3a66-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="f3a66-138">Si ya ha creado una directiva, puede utilizar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios a la directiva existente y, a continuación, use el cmdlet de[Concesión CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3a66-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="f3a66-139">Bloquear la grabación de conferencias y evitar a los participantes de la reunión anónima</span><span class="sxs-lookup"><span data-stu-id="f3a66-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="f3a66-140">Para crear una nueva directiva para estas configuraciones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f3a66-140">To create a new policy for these settings, run:</span></span> 
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```
<span data-ttu-id="f3a66-141">Obtenga más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3a66-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f3a66-142">Para conceder a la nueva directiva que ha creado al Mármol Amos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f3a66-142">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```
<span data-ttu-id="f3a66-143">Obtenga más información acerca del cmdlet [Grant CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3a66-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f3a66-144">Si ya ha creado una directiva, puede utilizar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios a la directiva existente y, a continuación, use el cmdlet de [Concesión CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3a66-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="f3a66-145">Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="f3a66-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="f3a66-146">Para crear una nueva directiva para estas configuraciones, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f3a66-146">To create a new policy for these settings, run:</span></span>  
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```
<span data-ttu-id="f3a66-147">Obtenga más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3a66-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f3a66-148">Para conceder a la nueva directiva creada para todos los usuarios de la organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f3a66-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

<span data-ttu-id="f3a66-149">Obtenga más información acerca del cmdlet [Grant CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3a66-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f3a66-150">Si ya ha creado una directiva, puede utilizar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios a la directiva existente y, a continuación, use el cmdlet de[Concesión CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3a66-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f3a66-151">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f3a66-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="f3a66-p105">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="f3a66-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f3a66-155">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f3a66-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f3a66-156">Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 </span><span class="sxs-lookup"><span data-stu-id="f3a66-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f3a66-p106">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f3a66-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f3a66-159">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3a66-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f3a66-160">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f3a66-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f3a66-161">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f3a66-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="f3a66-162">See also</span><span class="sxs-lookup"><span data-stu-id="f3a66-162">Related topics</span></span>
[<span data-ttu-id="f3a66-163">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="f3a66-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="f3a66-164">Transferencias de archivos punto a punto de bloque</span><span class="sxs-lookup"><span data-stu-id="f3a66-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="f3a66-165">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="f3a66-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

## <a name="feedback"></a><span data-ttu-id="f3a66-166">¿Comentarios?</span><span class="sxs-lookup"><span data-stu-id="f3a66-166">Feedback?</span></span>
<span data-ttu-id="f3a66-167">Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="f3a66-167">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
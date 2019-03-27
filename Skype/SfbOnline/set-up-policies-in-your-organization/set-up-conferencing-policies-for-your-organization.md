---
title: Establecer directivas de conferencia en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.'
ms.openlocfilehash: 46e22191875709f13936db395563eb9f7326300f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884538"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="40906-103">Establecer directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="40906-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="40906-104">[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.</span><span class="sxs-lookup"><span data-stu-id="40906-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="40906-p101">Es importante para mantener el control sobre las conferencias y la configuración de la conferencia. En algunos casos, puede haber problemas de seguridad: de forma predeterminada, cualquier usuario, incluidos los usuarios no autenticados, puede participar en reuniones y guardar cualquiera de las diapositivas o documentos que se distribuyen durante las reuniones. Además, puede haber problemas legales ocasionales. Por ejemplo, de forma predeterminada, los participantes de la reunión se permiten realizar anotaciones en contenido compartido; Sin embargo, estas anotaciones no se guardan cuando se archiva la reunión. Si su organización se requiere para mantener un registro de todas las comunicaciones electrónicas, es posible que desee deshabilitar las anotaciones.</span><span class="sxs-lookup"><span data-stu-id="40906-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="40906-p102">En Skype para profesionales en línea, las conferencias se administran mediante el uso de las directivas de conferencia. Las directivas de conferencia determinan las características y capacidades que se pueden usar en una conferencia, incluido todo el contenido de si la conferencia puede incluir IP audio y vídeo para el número máximo de personas que pueden asistir a una reunión. Las directivas de conferencia se pueden configurar en el ámbito global o en el ámbito por usuario. Esto proporciona a los administradores con una enorme flexibilidad en cuanto a decidir qué capacidades estarán disponibles para que los usuarios.</span><span class="sxs-lookup"><span data-stu-id="40906-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="40906-114">Configuración de la directiva se puede configurar en el momento en que se crea una directiva, o puede usar el cmdlet **Set-CsConferencingPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="40906-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="40906-115">Establecer las directivas de conferencia</span><span class="sxs-lookup"><span data-stu-id="40906-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="40906-116">Para todos los de la configuración de directiva de conferencia en Skype para profesionales en línea, debe usar Windows PowerShell y **no se puede usar** el **Skype para el centro de administración de negocio**.</span><span class="sxs-lookup"><span data-stu-id="40906-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="40906-117">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40906-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="40906-118">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="40906-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="40906-119">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="40906-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="40906-120">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="40906-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="40906-p103">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="40906-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="40906-p104">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="40906-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="40906-127">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="40906-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="40906-128">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="40906-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="40906-129">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="40906-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="40906-130">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="40906-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40906-131">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="40906-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="40906-132">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Configurar el equipo de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="40906-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="40906-133">Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones</span><span class="sxs-lookup"><span data-stu-id="40906-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="40906-134">Para crear una nueva directiva para estas opciones de configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="40906-134">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  > ```
  > <span data-ttu-id="40906-135">Obtenga más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="40906-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="40906-136">Para conceder a la nueva directiva que se ha creado para todos los usuarios de la organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="40906-136">To grant the new policy you created to all users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  > ```
  > <span data-ttu-id="40906-137">Obtenga más información acerca del cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="40906-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="40906-138">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="40906-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="40906-139">Bloquear la grabación de las conferencias y evitar que los participantes de la reunión anónimo</span><span class="sxs-lookup"><span data-stu-id="40906-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="40906-140">Para crear una nueva directiva para estas opciones de configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="40906-140">To create a new policy for these settings, run:</span></span> 
  > 
  > ```
  > New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  > ```
  > <span data-ttu-id="40906-141">Obtenga más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="40906-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="40906-142">Para conceder a la nueva directiva que creó para Amos mármol, ejecute:</span><span class="sxs-lookup"><span data-stu-id="40906-142">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```
  >  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  > ```
  > <span data-ttu-id="40906-143">Obtenga más información acerca del cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="40906-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="40906-144">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="40906-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="40906-145">Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="40906-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="40906-146">Para crear una nueva directiva para estas opciones de configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="40906-146">To create a new policy for these settings, run:</span></span>  
  > 
  > ```
  > New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  > ```
  > <span data-ttu-id="40906-147">Obtenga más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="40906-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="40906-148">Para conceder a la nueva directiva que se ha creado para todos los usuarios de la organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="40906-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
>   ```

<span data-ttu-id="40906-149">Obtenga más información acerca del cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="40906-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="40906-150">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="40906-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="40906-151">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="40906-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="40906-152">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="40906-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="40906-153">Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="40906-153">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="40906-154">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="40906-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="40906-155">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="40906-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="40906-156">Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 </span><span class="sxs-lookup"><span data-stu-id="40906-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="40906-p106">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="40906-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="40906-159">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40906-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="40906-160">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="40906-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="40906-161">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="40906-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="40906-162">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="40906-162">Related topics</span></span>
[<span data-ttu-id="40906-163">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="40906-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="40906-164">Transferencias de archivos punto a punto de bloque</span><span class="sxs-lookup"><span data-stu-id="40906-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="40906-165">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="40906-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 

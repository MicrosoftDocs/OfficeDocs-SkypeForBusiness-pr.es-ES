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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.'
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814759"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="d4331-103">Establecer directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="d4331-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="d4331-104">[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.</span><span class="sxs-lookup"><span data-stu-id="d4331-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="d4331-p101">Es importante que mantenga el control sobre las conferencias y la configuración de conferencias. En algunos casos, puede haber problemas de seguridad: de forma predeterminada, todos los usuarios, incluidos los usuarios no autenticados, pueden participar en las reuniones y guardar cualquiera de las diapositivas o los folletos distribuidos durante esas reuniones. Además, puede haber problemas legales ocasionales. Por ejemplo, de forma predeterminada, los participantes de la reunión pueden hacer anotaciones en el contenido compartido; sin embargo, estas anotaciones no se guardan al archivar la reunión. Si su organización necesita mantener un registro de todas las comunicaciones electrónicas, es posible que desee deshabilitar las anotaciones.</span><span class="sxs-lookup"><span data-stu-id="d4331-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="d4331-p102">En Skype Empresarial Online, las conferencias se administran mediante directivas de conferencia. Las directivas de conferencia determinan las características y capacidades que se pueden usar en una conferencia, incluido todo, desde si la conferencia puede incluir audio y vídeo IP hasta el número máximo de personas que pueden asistir a una reunión. Las directivas de conferencia se pueden configurar en el ámbito global o en el ámbito por usuario. Esto ofrece a los administradores una enorme flexibilidad a la hora de decidir qué capacidades estarán disponibles para qué usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4331-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="d4331-114">La configuración de la directiva se puede configurar al mismo tiempo que se crea la directiva o puede usar el cmdlet **Set-CsConferencingPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="d4331-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="d4331-115">Establecer las directivas de conferencia</span><span class="sxs-lookup"><span data-stu-id="d4331-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="d4331-116">Para todas las configuraciones de directivas de conferencia en Skype Empresarial Online, debe usar Windows PowerShell y no puede usar el **Centro** de administración de **Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="d4331-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="d4331-117">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4331-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="d4331-118">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="d4331-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="d4331-119">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d4331-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="d4331-120">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d4331-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="d4331-p103">Si no tiene la versión 3.0 o posterior, deberá descargar e instalar las actualizaciones para Windows PowerShell. Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="d4331-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="d4331-124">También necesitará instalar el módulo de Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="d4331-124">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="d4331-125">Si necesita más información, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.</span><span class="sxs-lookup"><span data-stu-id="d4331-125">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="d4331-126">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d4331-126">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="d4331-127">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d4331-127">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="d4331-128">En la **Windows PowerShell** de correo electrónico, conéctese a Su Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="d4331-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
     > [!NOTE]
     > <span data-ttu-id="d4331-129">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="d4331-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
     >
     > <span data-ttu-id="d4331-130">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d4331-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="d4331-131">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d4331-131">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="d4331-132">Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones</span><span class="sxs-lookup"><span data-stu-id="d4331-132">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="d4331-133">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4331-133">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="d4331-134">Más información sobre el [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4331-134">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d4331-135">Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4331-135">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="d4331-136">Más información sobre el [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4331-136">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="d4331-137">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4331-137">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="d4331-138">Bloquear la grabación de conferencias y evitar que los participantes anónimos de la reunión</span><span class="sxs-lookup"><span data-stu-id="d4331-138">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="d4331-139">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4331-139">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="d4331-140">Más información sobre el [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4331-140">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d4331-141">Para conceder la nueva directiva a Amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4331-141">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="d4331-142">Más información sobre el [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4331-142">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d4331-143">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4331-143">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="d4331-144">Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="d4331-144">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="d4331-145">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4331-145">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="d4331-146">Más información sobre el [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4331-146">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d4331-147">Para conceder la nueva directiva que ha creado a todos los usuarios de la organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4331-147">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="d4331-148">Más información sobre el [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4331-148">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d4331-149">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4331-149">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d4331-150">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d4331-150">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d4331-151">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="d4331-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d4331-152">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="d4331-152">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d4331-153">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="d4331-153">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d4331-154">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d4331-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d4331-155">Seis motivos por los que podría desear usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="d4331-155">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d4331-156">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="d4331-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d4331-157">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d4331-157">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d4331-158">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4331-158">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d4331-159">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d4331-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d4331-160">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d4331-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="d4331-161">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d4331-161">Related topics</span></span>
[<span data-ttu-id="d4331-162">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="d4331-162">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="d4331-163">Bloquear las transferencias de archivos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="d4331-163">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="d4331-164">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="d4331-164">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 

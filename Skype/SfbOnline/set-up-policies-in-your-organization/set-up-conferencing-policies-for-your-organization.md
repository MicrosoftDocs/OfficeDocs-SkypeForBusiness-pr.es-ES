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
description: '[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.'
ms.openlocfilehash: f4c8831408ed5c17073456306c0f48add73161ff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100526"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="9ac38-103">Establecer directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="9ac38-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="9ac38-104">[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.</span><span class="sxs-lookup"><span data-stu-id="9ac38-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="9ac38-105">Es importante que mantenga el control sobre las conferencias y su configuración.</span><span class="sxs-lookup"><span data-stu-id="9ac38-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="9ac38-106">En algunos casos puede ser necesario cierto grado de seguridad, pues, de forma predeterminada, todos los usuarios, incluidos los no autenticados, pueden participar en las reuniones, y guardar las diapositivas y documentos informativos que se distribuyan en ellas.</span><span class="sxs-lookup"><span data-stu-id="9ac38-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="9ac38-107">Además, es posible que deban tenerse en cuenta aspectos legales.</span><span class="sxs-lookup"><span data-stu-id="9ac38-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="9ac38-108">Por ejemplo, de forma predeterminada, los participantes de la reunión pueden realizar anotaciones en contenido compartido; sin embargo, estas anotaciones no se guardan cuando se archiva la reunión.</span><span class="sxs-lookup"><span data-stu-id="9ac38-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="9ac38-109">Si su organización debe conservar un registro de toda la comunicación electrónica, es posible que prefiera desactivar las anotaciones.</span><span class="sxs-lookup"><span data-stu-id="9ac38-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="9ac38-110">En Skype Empresarial Online, las conferencias se administran mediante directivas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9ac38-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="9ac38-111">Las directivas de conferencia determinan las funcionalidades y características que se pueden usar en una conferencia y cubren todos los aspectos, desde si la conferencia puede incluir o no audio y vídeo IP, hasta el número máximo de personas que pueden asistir a una reunión.</span><span class="sxs-lookup"><span data-stu-id="9ac38-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="9ac38-112">Las directivas de conferencia se pueden configurar para que tengan aplicación global o por usuario.</span><span class="sxs-lookup"><span data-stu-id="9ac38-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="9ac38-113">Esto ofrece a los administradores una enorme flexibilidad a la hora de decidir qué características podrán usar qué usuarios.</span><span class="sxs-lookup"><span data-stu-id="9ac38-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="9ac38-114">La configuración de directiva se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **Set-CsConferencingPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="9ac38-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="9ac38-115">Establecer las directivas de conferencia</span><span class="sxs-lookup"><span data-stu-id="9ac38-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="9ac38-116">Para todas las configuraciones de directiva de conferencia en Skype Empresarial  Online, debe usar Windows PowerShell y no puede usar el Centro de administración **de Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="9ac38-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="9ac38-117">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ac38-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="9ac38-118">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="9ac38-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="9ac38-119">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="9ac38-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="9ac38-120">Instale el [módulo de PowerShell de Teams.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="9ac38-120">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="9ac38-121">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="9ac38-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="9ac38-122">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) en una sola ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9ac38-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="9ac38-123">Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones</span><span class="sxs-lookup"><span data-stu-id="9ac38-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="9ac38-124">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ac38-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="9ac38-125">Vea más sobre el cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="9ac38-125">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="9ac38-126">Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ac38-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="9ac38-127">Vea más sobre el cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="9ac38-127">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="9ac38-128">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9ac38-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="9ac38-129">Bloquear la grabación de conferencias y evitar participantes anónimos de la reunión</span><span class="sxs-lookup"><span data-stu-id="9ac38-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="9ac38-130">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ac38-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="9ac38-131">Vea más sobre el cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="9ac38-131">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="9ac38-132">Para conceder la nueva directiva que creó a Amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ac38-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="9ac38-133">Vea más sobre el cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="9ac38-133">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="9ac38-134">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9ac38-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="9ac38-135">Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="9ac38-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="9ac38-136">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ac38-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="9ac38-137">Vea más sobre el cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="9ac38-137">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="9ac38-138">Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ac38-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="9ac38-139">Vea más sobre el cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="9ac38-139">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="9ac38-140">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9ac38-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9ac38-141">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9ac38-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9ac38-142">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="9ac38-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9ac38-143">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="9ac38-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9ac38-144">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="9ac38-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9ac38-145">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9ac38-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9ac38-146">Seis razones por las que es posible que desee usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="9ac38-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="9ac38-147">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="9ac38-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9ac38-148">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="9ac38-148">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="9ac38-149">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9ac38-149">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="9ac38-150">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9ac38-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9ac38-151">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9ac38-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="9ac38-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9ac38-152">Related topics</span></span>
[<span data-ttu-id="9ac38-153">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="9ac38-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="9ac38-154">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="9ac38-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="9ac38-155">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="9ac38-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  

---
title: Establecer directivas móviles en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Puede configurar la forma en que los usuarios se conectan a Skype empresarial online con la aplicación de Skype empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Las directivas de movilidad también se pueden usar para requerir conexiones Wi-Fi al realizar o recibir llamadas.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814749"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="2325b-104">Establecer directivas móviles en su organización</span><span class="sxs-lookup"><span data-stu-id="2325b-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="2325b-p102">Puede configurar la forma en que los usuarios se conectan a Skype empresarial online con la aplicación de Skype empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Las directivas de movilidad también se pueden usar para requerir conexiones Wi-Fi al realizar o recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="2325b-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="2325b-107">La configuración de la Directiva móvil se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **set-CsMobilityPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="2325b-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="2325b-108">Establecer las directivas móviles</span><span class="sxs-lookup"><span data-stu-id="2325b-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="2325b-109">Para todas las configuraciones de directiva móvil de Skype empresarial online, debe usar Windows PowerShell y **no puede usar** el centro de **Administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="2325b-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="2325b-110">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2325b-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="2325b-111">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="2325b-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="2325b-112">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2325b-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="2325b-113">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2325b-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="2325b-p103">Si no tiene la versión 3,0 o superior, debe descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="2325b-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="2325b-117">También tendrá que instalar el módulo de Windows PowerShell para Teams, que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="2325b-117">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="2325b-118">Si necesita más información, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="2325b-118">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="2325b-119">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2325b-119">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="2325b-120">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2325b-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="2325b-121">En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="2325b-121">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
       > [!NOTE]
       > <span data-ttu-id="2325b-122">En este momento, el conector de Skype empresarial online forma parte del módulo de PowerShell más reciente de Teams.</span><span class="sxs-lookup"><span data-stu-id="2325b-122">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
       >
       > <span data-ttu-id="2325b-123">Si está usando la [versión pública de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="2325b-123">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="2325b-124">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2325b-124">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="2325b-125">Requerir que un usuario disponga de conexión WiFi para usar el vídeo</span><span class="sxs-lookup"><span data-stu-id="2325b-125">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="2325b-126">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2325b-126">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="2325b-127">Para obtener más información, consulte el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2325b-127">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2325b-128">Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2325b-128">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="2325b-129">Para obtener más información, consulta el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2325b-129">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="2325b-130">Si ya ha creado una directiva, puede usar el cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2325b-130">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="2325b-131">Impedir que un usuario use la aplicación Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="2325b-131">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="2325b-132">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2325b-132">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="2325b-133">Para obtener más información, consulte el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2325b-133">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2325b-134">Para conceder a la nueva directiva que ha creado a amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2325b-134">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="2325b-135">Para obtener más información, consulta el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2325b-135">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="2325b-136">Si ya ha creado una directiva, puede usar el cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2325b-136">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="2325b-137">Impedir que un usuario haga llamadas de voz sobre IP con un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="2325b-137">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="2325b-138">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2325b-138">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="2325b-139">Para obtener más información, consulte el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2325b-139">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2325b-140">Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2325b-140">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="2325b-141">Para obtener más información, consulta el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2325b-141">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="2325b-142">Si ya ha creado una directiva, puede usar el cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2325b-142">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2325b-143">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2325b-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="2325b-144">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="2325b-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2325b-145">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="2325b-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="2325b-146">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="2325b-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2325b-147">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2325b-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="2325b-148">Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="2325b-148">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="2325b-149">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="2325b-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="2325b-150">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="2325b-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="2325b-151">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2325b-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="2325b-152">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2325b-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2325b-153">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2325b-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="2325b-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2325b-154">Related topics</span></span>
[<span data-ttu-id="2325b-155">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="2325b-155">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="2325b-156">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="2325b-156">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="2325b-157">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="2325b-157">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="2325b-158">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="2325b-158">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

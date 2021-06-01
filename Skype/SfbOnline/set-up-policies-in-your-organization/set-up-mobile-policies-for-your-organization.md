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
description: Puede configurar cómo se conectan los usuarios a Skype Empresarial Online con la aplicación Skype Empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Las directivas de movilidad también se pueden usar para requerir conexiones WiFi para hacer o recibir llamadas.
ms.openlocfilehash: e29a02bddcb9ace29ebd059f8cbc42c5a85c3f12
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240072"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="5a961-104">Establecer directivas móviles en su organización</span><span class="sxs-lookup"><span data-stu-id="5a961-104">Set up mobile policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="5a961-105">Puede configurar cómo se conectan los usuarios a Skype Empresarial Online con la aplicación Skype Empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="5a961-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="5a961-106">Las directivas de movilidad también se pueden usar para requerir conexiones WiFi para hacer o recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="5a961-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="5a961-107">La configuración de directiva móvil se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **Set-CsMobilityPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="5a961-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="5a961-108">Establecer las directivas móviles</span><span class="sxs-lookup"><span data-stu-id="5a961-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="5a961-109">Para todas las configuraciones de directiva móvil en Skype Empresarial Online, debe  usar Windows PowerShell y no puede usar el centro de administración Skype Empresarial **móvil.**</span><span class="sxs-lookup"><span data-stu-id="5a961-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="5a961-110">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a961-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="5a961-111">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="5a961-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="5a961-112">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="5a961-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="5a961-113">Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="5a961-113">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="5a961-114">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="5a961-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="5a961-115">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectar todos los servicios de Microsoft 365 o Office 365 en una única ventana de [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5a961-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="5a961-116">Requerir que un usuario disponga de conexión WiFi para usar el vídeo</span><span class="sxs-lookup"><span data-stu-id="5a961-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="5a961-117">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5a961-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="5a961-118">Vea más sobre el cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="5a961-118">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="5a961-119">Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5a961-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="5a961-120">Vea más sobre el [cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="5a961-120">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="5a961-121">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5a961-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="5a961-122">Impedir que un usuario use la aplicación Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5a961-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="5a961-123">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5a961-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="5a961-124">Vea más sobre el cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="5a961-124">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="5a961-125">Para conceder la nueva directiva que creó a Amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5a961-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="5a961-126">Vea más sobre el [cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="5a961-126">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="5a961-127">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5a961-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="5a961-128">Impedir que un usuario haga llamadas de voz sobre IP con un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="5a961-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="5a961-129">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5a961-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="5a961-130">Vea más sobre el cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="5a961-130">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="5a961-131">Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5a961-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="5a961-132">Vea más sobre el [cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="5a961-132">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
<span data-ttu-id="5a961-133">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5a961-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5a961-134">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5a961-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5a961-135">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="5a961-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5a961-136">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="5a961-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5a961-137">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5a961-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5a961-138">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5a961-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5a961-139">Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="5a961-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="5a961-140">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="5a961-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5a961-141">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5a961-141">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="5a961-142">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5a961-142">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="5a961-143">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5a961-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5a961-144">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5a961-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="5a961-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5a961-145">Related topics</span></span>
[<span data-ttu-id="5a961-146">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="5a961-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="5a961-147">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="5a961-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="5a961-148">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="5a961-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="5a961-149">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="5a961-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  

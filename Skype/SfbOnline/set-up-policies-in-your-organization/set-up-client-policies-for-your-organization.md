---
title: Establecer directivas de cliente en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814359"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="bfc5f-103">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="bfc5f-103">Set up client policies for your organization</span></span>

<span data-ttu-id="bfc5f-104">[] Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="bfc5f-105">La configuración de la Directiva de cliente se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **set-ClientPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="bfc5f-106">Establecer las directivas de cliente</span><span class="sxs-lookup"><span data-stu-id="bfc5f-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="bfc5f-107">Para todas las configuraciones de directiva de cliente de Skype empresarial online, debe usar Windows PowerShell y no puede **usar** el **centro de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="bfc5f-108">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfc5f-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="bfc5f-109">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="bfc5f-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="bfc5f-110">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="bfc5f-111">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="bfc5f-p101">Si no tiene la versión 3,0 o superior, debe descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="bfc5f-115">También tendrá que instalar el módulo de Windows PowerShell para Teams, que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-115">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="bfc5f-116">Si necesita más información, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="bfc5f-116">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="bfc5f-117">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bfc5f-117">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="bfc5f-118">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="bfc5f-119">En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-119">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bfc5f-120">En este momento, el conector de Skype empresarial online forma parte del módulo de PowerShell más reciente de Teams.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-120">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="bfc5f-121">Si está usando la [versión pública de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-121">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
<span data-ttu-id="bfc5f-122">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bfc5f-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="bfc5f-123">Deshabilitar emoticonos y notificaciones de presencia y evitar el guardado de mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="bfc5f-123">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="bfc5f-124">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-124">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="bfc5f-125">Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bfc5f-125">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bfc5f-126">Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-126">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="bfc5f-127">Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bfc5f-127">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="bfc5f-128">Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-128">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="bfc5f-129">Permitir que se pueda hacer clic en las URL y los hiperenlaces en MI</span><span class="sxs-lookup"><span data-stu-id="bfc5f-129">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="bfc5f-130">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-130">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="bfc5f-131">Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bfc5f-131">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bfc5f-132">Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-132">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="bfc5f-133">Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bfc5f-133">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="bfc5f-134">Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-134">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="bfc5f-135">Impedir que se muestren los contactos recientes</span><span class="sxs-lookup"><span data-stu-id="bfc5f-135">Prevent showing recent contacts</span></span>

- <span data-ttu-id="bfc5f-136">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-136">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="bfc5f-137">Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bfc5f-137">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bfc5f-138">Para conceder a la nueva directiva que ha creado a amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-138">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="bfc5f-139">Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bfc5f-139">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="bfc5f-140">Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-140">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bfc5f-141">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bfc5f-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bfc5f-142">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bfc5f-143">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bfc5f-144">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bfc5f-145">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bfc5f-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bfc5f-146">Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="bfc5f-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bfc5f-147">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bfc5f-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bfc5f-148">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="bfc5f-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bfc5f-149">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfc5f-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bfc5f-150">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bfc5f-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bfc5f-151">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bfc5f-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bfc5f-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bfc5f-152">Related topics</span></span>
[<span data-ttu-id="bfc5f-153">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="bfc5f-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="bfc5f-154">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="bfc5f-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="bfc5f-155">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="bfc5f-155">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

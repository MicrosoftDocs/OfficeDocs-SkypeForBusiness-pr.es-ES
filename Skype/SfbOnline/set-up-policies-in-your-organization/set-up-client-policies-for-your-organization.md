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
ms.openlocfilehash: 43b51b800b3107410c64bd2605b5a6a7622fe65a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776295"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="5330a-103">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="5330a-103">Set up client policies for your organization</span></span>

<span data-ttu-id="5330a-104">[] Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.</span><span class="sxs-lookup"><span data-stu-id="5330a-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="5330a-105">La configuración de la Directiva de cliente se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **set-ClientPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="5330a-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="5330a-106">Establecer las directivas de cliente</span><span class="sxs-lookup"><span data-stu-id="5330a-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="5330a-107">Para todas las configuraciones de directiva de cliente de Skype empresarial online, debe usar Windows PowerShell y no puede **usar** el **centro de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="5330a-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="5330a-108">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5330a-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="5330a-109">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="5330a-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="5330a-110">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5330a-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="5330a-111">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5330a-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="5330a-p101">Si no tiene la versión 3,0 o superior, debe descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="5330a-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="5330a-p102">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="5330a-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="5330a-118">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="5330a-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="5330a-119">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5330a-119">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="5330a-120">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5330a-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="5330a-121">En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="5330a-121">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="5330a-122">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="5330a-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```powershell
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```
<span data-ttu-id="5330a-123">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5330a-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="5330a-124">Deshabilitar emoticonos y notificaciones de presencia y evitar el guardado de mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="5330a-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="5330a-125">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5330a-125">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="5330a-126">Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5330a-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="5330a-127">Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5330a-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="5330a-128">Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5330a-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="5330a-129">Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5330a-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="5330a-130">Permitir que se pueda hacer clic en las URL y los hiperenlaces en MI</span><span class="sxs-lookup"><span data-stu-id="5330a-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="5330a-131">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5330a-131">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="5330a-132">Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5330a-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="5330a-133">Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5330a-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="5330a-134">Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5330a-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="5330a-135">Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5330a-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="5330a-136">Impedir que se muestren los contactos recientes</span><span class="sxs-lookup"><span data-stu-id="5330a-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="5330a-137">Para crear una nueva Directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5330a-137">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="5330a-138">Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5330a-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="5330a-139">Para conceder a la nueva directiva que ha creado a amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5330a-139">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="5330a-140">Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5330a-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="5330a-141">Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5330a-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5330a-142">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5330a-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5330a-143">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="5330a-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5330a-144">Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="5330a-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5330a-145">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5330a-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5330a-146">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5330a-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5330a-147">Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="5330a-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5330a-148">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="5330a-148">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5330a-149">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5330a-149">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5330a-150">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5330a-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5330a-151">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5330a-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5330a-152">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5330a-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="5330a-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5330a-153">Related topics</span></span>
[<span data-ttu-id="5330a-154">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="5330a-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="5330a-155">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="5330a-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="5330a-156">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="5330a-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

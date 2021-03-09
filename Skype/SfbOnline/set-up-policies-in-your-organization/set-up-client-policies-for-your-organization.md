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
description: '[] Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.'
ms.openlocfilehash: 65a346f0f16892d5995b723431fc796e3faa1a3b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569232"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="83185-103">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="83185-103">Set up client policies for your organization</span></span>

<span data-ttu-id="83185-104">[] Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.</span><span class="sxs-lookup"><span data-stu-id="83185-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="83185-105">La configuración de directiva de cliente se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **Set-CsClientPolicy** para modificar la configuración de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="83185-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="83185-106">Establecer las directivas de cliente</span><span class="sxs-lookup"><span data-stu-id="83185-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="83185-107">Para toda la configuración de directiva de cliente en Skype Empresarial  Online, debe usar Windows PowerShell y no puede usar el Centro de administración **de Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="83185-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="83185-108">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83185-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="83185-109">Skype Empresarial Online Connector forma parte actualmente del último módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="83185-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="83185-110">Si usa la última versión pública de PowerShell de Teams, no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="83185-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="83185-111">Instale el [módulo de PowerShell de Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="83185-111">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="83185-112">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="83185-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="83185-113">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una sola ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="83185-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="83185-114">Deshabilitar emoticonos y notificaciones de presencia y evitar el guardado de MENSAJES</span><span class="sxs-lookup"><span data-stu-id="83185-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="83185-115">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="83185-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="83185-116">Más información sobre el cmdlet [New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="83185-116">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="83185-117">Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="83185-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="83185-118">Vea más sobre el cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="83185-118">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="83185-119">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="83185-119">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="83185-120">Permitir que se pueda hacer clic en las URL y los hiperenlaces en MI</span><span class="sxs-lookup"><span data-stu-id="83185-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="83185-121">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="83185-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="83185-122">Más información sobre el cmdlet [New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="83185-122">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="83185-123">Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="83185-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="83185-124">Vea más sobre el cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="83185-124">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="83185-125">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="83185-125">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="83185-126">Impedir que se muestren los contactos recientes</span><span class="sxs-lookup"><span data-stu-id="83185-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="83185-127">Para crear una nueva directiva para esta configuración, ejecute:</span><span class="sxs-lookup"><span data-stu-id="83185-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="83185-128">Más información sobre el cmdlet [New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="83185-128">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="83185-129">Para conceder la nueva directiva que creó a Amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="83185-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="83185-130">Vea más sobre el cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="83185-130">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="83185-131">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="83185-131">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="83185-132">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="83185-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="83185-133">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="83185-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="83185-134">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="83185-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="83185-135">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="83185-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="83185-136">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="83185-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="83185-137">Seis razones por las que es posible que desee usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="83185-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="83185-138">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="83185-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="83185-139">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="83185-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="83185-140">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83185-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="83185-141">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="83185-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="83185-142">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="83185-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="83185-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="83185-143">Related topics</span></span>
[<span data-ttu-id="83185-144">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="83185-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="83185-145">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="83185-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="83185-146">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="83185-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

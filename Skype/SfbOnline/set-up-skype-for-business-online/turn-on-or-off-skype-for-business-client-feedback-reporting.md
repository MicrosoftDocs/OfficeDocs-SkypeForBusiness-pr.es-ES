---
title: Activar o desactivar los informes de comentarios de clientes de Skype Empresarial
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: Puede permitir que los usuarios de Skype empresarial usen la herramienta de comentarios de la aplicación integrada de Skype empresarial para permitir a los usuarios informar de problemas y enviar comentarios directamente a Microsoft sobre su experiencia.
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814189"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="4eb9f-103">Activar o desactivar los informes de comentarios de clientes de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4eb9f-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="4eb9f-104">Puede permitir que los usuarios de Skype empresarial online usen la herramienta de comentarios de la aplicación integrada de Skype empresarial para permitir a los usuarios informar de problemas y proporcionar comentarios directamente a Microsoft sobre su experiencia.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="4eb9f-106">Con esta herramienta, un usuario puede copiar los registros de la aplicación en su dispositivo para ayudar a Microsoft a investigar y solucionar problemas que puedan surgir.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="4eb9f-108">También puede utilizar la configuración  _EnableOnlineFeedbackScreenshot_ para que los usuarios puedan incluir una captura de pantalla de su dispositivo como parte de los comentarios.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="4eb9f-110">Los registros recopilados por la herramienta de comentarios de la aplicación se almacenarán hasta un máximo de 90 días en los Estados Unidos mientras se está investigando el problema.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="4eb9f-111">Por ello, no habilite esta herramienta de comentarios si esto infringe la Directiva de protección de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="4eb9f-112">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eb9f-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="4eb9f-113">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="4eb9f-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="4eb9f-114">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4eb9f-115">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="4eb9f-116">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="4eb9f-117">Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="4eb9f-118">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="4eb9f-119">También tendrá que instalar el módulo de Windows PowerShell para Teams, que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
<span data-ttu-id="4eb9f-120">Si necesita más información, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="4eb9f-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="4eb9f-121">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4eb9f-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="4eb9f-122">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4eb9f-123">En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="4eb9f-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="4eb9f-124">En este momento, el conector de Skype empresarial online forma parte del módulo de PowerShell más reciente de Teams.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="4eb9f-125">Si está usando la [versión pública de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
 
   ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="4eb9f-126">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4eb9f-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="4eb9f-127">Activar los informes de comentarios del cliente sobre la aplicación para todos los usuarios en la organización</span><span class="sxs-lookup"><span data-stu-id="4eb9f-127">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="4eb9f-128">Para habilitar los informes de comentarios para los usuarios de su organización y permitirles enviar capturas de pantalla de dispositivos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="4eb9f-128">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4eb9f-129">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4eb9f-129">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="4eb9f-130">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4eb9f-131">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4eb9f-132">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="4eb9f-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4eb9f-133">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4eb9f-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4eb9f-134">Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="4eb9f-134">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4eb9f-135">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="4eb9f-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4eb9f-136">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="4eb9f-136">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4eb9f-137">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eb9f-137">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4eb9f-138">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4eb9f-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4eb9f-139">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4eb9f-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="4eb9f-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4eb9f-140">Related topics</span></span>
[<span data-ttu-id="4eb9f-141">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4eb9f-141">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4eb9f-142">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="4eb9f-142">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

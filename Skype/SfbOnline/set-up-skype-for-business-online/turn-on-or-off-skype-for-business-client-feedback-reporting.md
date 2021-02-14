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
description: Puede permitir que sus usuarios de Skype Empresarial usen la herramienta de comentarios de la aplicación integrada de Skype Empresarial para permitir que los usuarios informen de problemas y proporcionen comentarios directamente a Microsoft sobre su experiencia.
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814189"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="1311a-103">Activar o desactivar los informes de comentarios de clientes de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1311a-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="1311a-104">Puede permitir que sus usuarios de Skype Empresarial Online usen la herramienta de comentarios de la aplicación integrada de Skype Empresarial para permitir que los usuarios informen de problemas y proporcionen comentarios directamente a Microsoft sobre su experiencia.</span><span class="sxs-lookup"><span data-stu-id="1311a-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="1311a-106">Con esta herramienta, un usuario puede copiar los registros de la aplicación en su dispositivo para ayudar a Microsoft a investigar y solucionar los problemas que puedan tener.</span><span class="sxs-lookup"><span data-stu-id="1311a-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="1311a-108">También puede utilizar la configuración  _EnableOnlineFeedbackScreenshot_ para que los usuarios puedan incluir una captura de pantalla de su dispositivo como parte de los comentarios.</span><span class="sxs-lookup"><span data-stu-id="1311a-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="1311a-110">Los registros recopilados por la herramienta de comentarios de la aplicación se almacenarán durante un máximo de 90 días en Estados Unidos mientras se investiga el problema.</span><span class="sxs-lookup"><span data-stu-id="1311a-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="1311a-111">Por este problema, no habilite esta herramienta de comentarios si esto infringe la directiva de protección de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="1311a-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="1311a-112">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1311a-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="1311a-113">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="1311a-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="1311a-114">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1311a-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1311a-115">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1311a-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="1311a-116">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1311a-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="1311a-117">Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="1311a-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="1311a-118">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="1311a-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="1311a-119">También necesitará instalar el módulo de Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="1311a-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
<span data-ttu-id="1311a-120">Si necesita más información, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.</span><span class="sxs-lookup"><span data-stu-id="1311a-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="1311a-121">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1311a-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="1311a-122">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1311a-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1311a-123">En la **Windows PowerShell** de correo electrónico, conéctese a Su Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="1311a-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="1311a-124">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="1311a-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="1311a-125">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="1311a-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
 
   ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="1311a-126">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para[Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1311a-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="1311a-127">Activar los informes de comentarios del cliente sobre la aplicación para todos los usuarios en la organización</span><span class="sxs-lookup"><span data-stu-id="1311a-127">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="1311a-128">Para habilitar los informes de comentarios para los usuarios de su organización y permitirles enviar capturas de pantalla del dispositivo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1311a-128">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1311a-129">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1311a-129">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="1311a-130">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="1311a-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1311a-131">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="1311a-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1311a-132">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="1311a-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1311a-133">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1311a-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1311a-134">Seis motivos por los que podría desear usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="1311a-134">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1311a-135">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="1311a-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1311a-136">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="1311a-136">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1311a-137">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1311a-137">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1311a-138">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1311a-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1311a-139">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1311a-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="1311a-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1311a-140">Related topics</span></span>
[<span data-ttu-id="1311a-141">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1311a-141">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1311a-142">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="1311a-142">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

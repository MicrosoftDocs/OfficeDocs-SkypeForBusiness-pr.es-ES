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
description: Puede permitir que sus Skype Empresarial usuarios puedan usar la herramienta integrada de comentarios de la aplicación Skype Empresarial para permitir que los usuarios informen de problemas y proporcionen comentarios directamente a Microsoft sobre su experiencia.
ms.openlocfilehash: 151ba9ee82c95f088f5c7fc87de3a06ce609ab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239103"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="5d50e-103">Activar o desactivar los informes de comentarios de clientes de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5d50e-103">Turn on or off Skype for Business client feedback reporting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="5d50e-104">Puede permitir que los usuarios de Skype Empresarial Online usen la herramienta integrada de comentarios de la aplicación Skype Empresarial para permitir que los usuarios informen de problemas y proporcionen comentarios directamente a Microsoft sobre su experiencia.</span><span class="sxs-lookup"><span data-stu-id="5d50e-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Icono Proporcionar comentarios](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="5d50e-106">Con esta herramienta, un usuario puede copiar los registros de la aplicación en su dispositivo para ayudar a Microsoft a investigar y solucionar mejor los problemas que puedan tener.</span><span class="sxs-lookup"><span data-stu-id="5d50e-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Informar de un problema con Configuración icono](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="5d50e-108">También puede utilizar la configuración  _EnableOnlineFeedbackScreenshot_ para que los usuarios puedan incluir una captura de pantalla de su dispositivo como parte de los comentarios.</span><span class="sxs-lookup"><span data-stu-id="5d50e-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="5d50e-110">Los registros recopilados por la herramienta de comentarios de la aplicación se almacenarán durante un máximo de 90 días en Estados Unidos mientras se investiga el problema.</span><span class="sxs-lookup"><span data-stu-id="5d50e-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="5d50e-111">Debido a esto, no habilite esta herramienta de comentarios si esto infringe la directiva de protección de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="5d50e-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="5d50e-112">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d50e-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="5d50e-113">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="5d50e-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="5d50e-114">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d50e-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="5d50e-115">Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="5d50e-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="5d50e-116">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="5d50e-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="5d50e-117">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectar todos los servicios de Microsoft 365 o Office 365 en una única ventana de [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5d50e-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="5d50e-118">Activar los informes de comentarios del cliente sobre la aplicación para todos los usuarios en la organización</span><span class="sxs-lookup"><span data-stu-id="5d50e-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="5d50e-119">Para habilitar los informes de comentarios de los usuarios de su organización y permitirles enviar capturas de pantalla del dispositivo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5d50e-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5d50e-120">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5d50e-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="5d50e-121">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="5d50e-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5d50e-122">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="5d50e-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5d50e-123">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5d50e-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5d50e-124">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d50e-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5d50e-125">Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="5d50e-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="5d50e-126">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="5d50e-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5d50e-127">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5d50e-127">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="5d50e-128">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5d50e-128">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="5d50e-129">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d50e-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5d50e-130">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d50e-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="5d50e-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5d50e-131">Related topics</span></span>
[<span data-ttu-id="5d50e-132">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d50e-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5d50e-133">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="5d50e-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  

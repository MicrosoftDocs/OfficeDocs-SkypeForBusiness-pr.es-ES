---
title: Activar o desactivar la precarga de contenido con Outlook en las reuniones
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239113"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="6b5e0-103">Activar o desactivar la precarga de contenido con Outlook en las reuniones</span><span class="sxs-lookup"><span data-stu-id="6b5e0-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="6b5e0-104">Los usuarios pueden precargar contenido, archivos o datos adjuntos que se adjuntan Outlook una invitación Outlook una reunión de Skype Empresarial Online, pero puede activarla o desactivarla.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="6b5e0-105">Está activada de forma predeterminada para todas las organizaciones que usan Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="6b5e0-106">Vea información sobre cómo [Precargar datos adjuntos para una reunión de Skype Empresarial.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="6b5e0-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b5e0-107">Actualmente, no hay cmdlets disponibles en Skype Empresarial Online para configurar o ver valores en línea para _MaxContentStorageMB_ y _MaxUploadFileMB._</span><span class="sxs-lookup"><span data-stu-id="6b5e0-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="6b5e0-108">Solo están disponibles para implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="6b5e0-109">Es importante saber que el contenido no se cargará en una reunión si el contenido adjunto supera el _MaxUploadFileSizeMB_ o si se alcanza el límite _MaxContentStorageMB._</span><span class="sxs-lookup"><span data-stu-id="6b5e0-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="6b5e0-110">Para empezar</span><span class="sxs-lookup"><span data-stu-id="6b5e0-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="6b5e0-111">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b5e0-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="6b5e0-112">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="6b5e0-113">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="6b5e0-114">Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="6b5e0-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="6b5e0-115">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="6b5e0-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="6b5e0-116">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectar todos los servicios de Microsoft 365 o Office 365 en una única ventana de [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6b5e0-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="6b5e0-117">Activación o desactivación</span><span class="sxs-lookup"><span data-stu-id="6b5e0-117">Turning it on or off</span></span>

<span data-ttu-id="6b5e0-118">La posibilidad de precargar contenido adjunto Outlook una invitación de reunión de Outlook a reuniones de Skype Empresarial Online está activada de forma predeterminada, pero es posible que tenga que impedir que los usuarios de su organización precarguen contenido en sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6b5e0-119">Esta configuración solo puede estar activada o desactivada para toda la organización; no puede activarlo o desactivarlo para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="6b5e0-120">**Para desactivarla, abra Windows PowerShell y haga lo siguiente:**</span><span class="sxs-lookup"><span data-stu-id="6b5e0-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="6b5e0-121">**Si desea volver a activarla, abra Windows PowerShell y haga lo siguiente:**</span><span class="sxs-lookup"><span data-stu-id="6b5e0-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6b5e0-122">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6b5e0-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6b5e0-123">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6b5e0-124">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6b5e0-125">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="6b5e0-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6b5e0-126">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6b5e0-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6b5e0-127">Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="6b5e0-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="6b5e0-128">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6b5e0-129">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6b5e0-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="6b5e0-130">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6b5e0-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="6b5e0-131">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6b5e0-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6b5e0-132">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6b5e0-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="6b5e0-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6b5e0-133">Related topics</span></span>
[<span data-ttu-id="6b5e0-134">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6b5e0-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6b5e0-135">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="6b5e0-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
